# h3_hello_web_server
Tehty 2.2.2025
Tämä harjoitus on osana Tero Karvisen kurssitoteutusta Linux Palvelimet 2025 alkukevät.
Enimmäkseen tehtävää tehdessä on käytetty Tero Karvisen kurssimateriaaleja, jotka löytyvät seuraavalta sivustolta: https://terokarvinen.com/linux-palvelimet/.

Lähdeluettelo päivitetty 9.3.2025

### x) tiivistys

Name-based Virtual Host Support (The Apache Software Foundation)
* Nimipohjainen virtuaalinen isännöinti mahdollistaa yhdelle IP-osoitteelle monta isäntää. IP-pohjaisessa, jokaisella isännällä oma IP.
* Nimipohjaista on yleensä helpompi käyttää ja ei tosiaan tarvitse useita eri IP-osoitteita.
* Pyyntö tapahtuu nimipohjaisessa siten, että palvelin vertailee ServerNamea sekä ServerAliasta ja valitsee näiden perusteella oikean isännän, vaikka IP-osoite onkin sama.

Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address (Tero Karvinen 2018)
* Komento: "$ sudo apt-get -y install apache2" asentaa apachen.
* Komento: "$ sudo systemctl restart apache2" uudelleen käynnistää apachen.
* Komento: "$ sudo a2ensite <sivu>" Tekee aktivoi sivuston (näkyy "/sites-enabled" hakemistossa).
* Komento: "$ sudoedit /etc/hosts" Tätä kautta voidaan simuloida nimipalvelua.


### a) Apachen asennus
Aloitin tämän klo. 17.30

Apachen asennus lähtee komennosta "$ sudo apt-get install apache2" Itse en tätä nyt tällä kertaa tehnyt, kun olin apachen jo asentanut aiemmin. Seuraava kuva tästä todisteena.

![apac](images/apache.png)

Testasin kuitenkin, toimivuutta tekemällä pyynnön omalla ip osoitteella. Eli kirjoitin konsoliin komennon "$ ip addr", josta sai oman ip osoitteen. Sitten lisäsin oman ip osoitteen komentoon "$ firefox 127.0.0.1"
![iphaku](images/h3_iphaku.png)

Tämä avasi localhostin ja sinne määritetyn sivuston, joten apache kyllä toimii.

![ip](images/h3_ip.png)


### b) Lokit
Aloitin tämän osion klo. 17.35

Lokitiedostoa "access.log" tutkin seuraavalla komennolla "sudo tail /var/log/apache2/access.log". "tail" komento tulostaa oletuksena tiedoston 10 viimeistä riviä.

![localhost](images/lokit1.png)

Rivien tulkintata:

  Seuraavaksi tulkitsen kuvasta toisiksi ylintä riviä.

  * "127.0.0.1" - on IP osoite, mistä pyyntö on lähetetty.
  
  * "-" - on nimitunniste, koska tätä ei ole asetettu, niin on se "-".
  
  * "[28/Jan/2025:19:36:44 +0200]" - Kertoo pyynnön päivämäärän ja ajan.
  
  * "GET" - On pyynnön tyyppi. Tässä tapauksessa yritetään hakea jotain mitä, voidaan näyttää.

  * "HTTP1/1" - On protokolla
  
  * "200" - Pyynnön status, eli tässä tapuksessa pyyntö on onnistunut ja haluttu objekti näytetään.

  * "3380" - on palaavan objektin koko.

  * "Mozilla/5.0" - Tässä esiintyy selain, jolla pyyntö ollaan tehty.
  
  * "(X11; Linux x86_64; rv:128.0)" - Käyttöjärjestelmä, jolla pyyntö ollaan tehty.
  
  * "Gecko/20100101" - Alusta, johon selain perustuu, millä pyyntö ollaan tehty.
  
  * "Firefox/128.0" - Selaimen versio, jolla pyyntö ollaan tehty.

  Kuvassa näkyy myös kaksi status "404". Tämä tarkoittaa sitä, että asiaa mitä pyydettiin ei löydy. Kuvan tapauksessa, yritetään hakea jotain iconi kuvaa localhost osoitteesta. Ei löydy, kun ei tämmöistä sivustolle olle asetettukkaan.
  
### c) Etusivu uusiksi

Aloitin tämän osion 18.45

Ensiksi navigoin apachen "sites-available" hakemistoon komennolla "$ cd /etc/apache2/sites-available".

![nav](images/nav_apa.png)

Tämän jälkeen tein microlla "sites-available" hakemistoon tiedoston nimeltä "hattu.example.com.conf" komennolla "micro hattu.example.com.conf".

![teehattu](images/tee_hattu_conf.png)

Tiedostoon lisäsin seuraavat rivit ja tallensin tiedoston "ctrl+s" näppäinyhdistelmällä ja poistuin tiedostosta "ctrl+q" näppäinyhdistelmällä.

![conf](images/hattu_conf.png)

Tarkisin "ls" komennolla, että hakemistoon oli tullut "hattu.example.com.conf" niminen tiedosto.
![tarkistus](images/tarkistus.png)

Tämän jälkeen kävin tekemässä microlla tiedoston "hattu.example.com" hakemistoon "/home/timov/public_html/". Tiedostoon lisäsin tekstin "THIS IS HATTU" ("mkdir public_html" komennolla olin aiemmin tehnyt "public_html" hakemiston)

![hattu.com](images/hattu.com.png)

![hattu](images/thisishattu.png)

Seuraavaksi tarkistin, että minkä sivuston apache käy lukemassa komennolla "$ ls /etc/apache2/sites-enabled".

![enable_tarkistus](images/h3_enable_tarkistus.png)

Näkyi, että tunnilla tehtty sivu on aktiivinen. Piti verestää muistia, että miten sivustot aktivoitiin/deaktivoitiin. Löysin vinkkiä seuraavalta sivustolta "https://www.linode.com/community/questions/311/how-do-i-enabledisable-a-website-hosted-with-apache". Komennot ovat seuraavat "$ a2ensite <sivu>" (aktivoi) ja "$ a2dissite <sivu>" (deaktivoi). Testataan sivuston deaktivointia komennolla "$ a2dissite supersivu.com.conf"

![endis](images/endis.png)

Kuten näkyy, ei toiminut, koska oli unohtunut "sudo" edestä. Korjasin komennon ja potkaisin apachen uusiksi käyntiin komennolla "$ sudo systemctl restart apache2". Sitten tarkistin, että onko supersivu.com aktiivinen komennolla "$ ls sites-enabled" (huom. olin hakemistossa "/etc/apache2/"). Mitään ei näkynyt, enään joten sivusto oli deaktivoitu onnistuneesti. Tämän jälkeen komennolla "$ sudo a2ensite hattu.example.com.conf" aktivoiin sivun. Sitten taas demonin potkaisu komennolla "$ sudo systemctl restart apache2" ja komennolla "$ ls sites-enabled/" tarkistus, että sivusto on aktivoitunut.

Sitten testasin miltä näyttää päivittää localhost selaimesta painamalla "shift + reload current page (Selaimessa hakupalkin vasemmalla puolella oleva ympyränmuotoinen nuolisymboli)"

![forbidden](images/h3_forbidden.png)

Ei toiminut, joten eikun selvittämään. Aloitin lokitiedostoja tutkimalla komennolla "$ sudo tail /var/log/apache2/access.log" Lokeista selvisi, apache ei suorita hakuja, koska lokit eivät päivittyneet, vaikka sivustoa yritti päivittää "shift + reload current page". 

Forbidden, joka tapauksessa viittaa siihen, että apache toimii. Tarkistin ensimmäiseksi configure tiedoston komennolla "$ micro /etc/apache2/sites-available/hattu.example.com.conf". Oikealta näytti. Sitten siirryin katsomaan itse sivusto rakennetta "/pubclic_html/" hakemistoon ja täälläpä se virhe olikin.

![selvitysta](images/h3_selvitys.png)

Eli olin vahingossa tehntyt "hattu.example.com" sivuston tiedostoksi "public_html" hakemistoon. Muutin "hattu.example.com" tiedoston "index.html" nimiseksi seuraavalla komennolla "$ mv hattu.example.com index.html". Tämän jälkeen tein hakemiston nimeltä "hattu.example.com" komennolla "$ mkdir hattu.example.com". Sitten siirsin "index.html" tiedoston hakemistoon "hattu.example.com" komennolla "$ mv index.html hattu.example.com/" Ja päivitin localhostin selaimesta.

![sivuhattu](images/h3_sivuhattu.png)

Vika selvitetty. 

Seuraavaksi kävin päivittämässä "index.html" sivun. Koska "public_html/" hakemisto oli aktiivisena pystyi komennolla "$ micro hattu.example.com/index.html" muokkauksen tekemään.

![index](images/h3_lisays.png)

Seuraavaksi piti selvitellä, että miten saan sivuston latautumaan "hattu.example.com" hakusanalla. Tero Karvisen, "https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/" Löytyikin ohjeet tähän. Eli komennolla "$ sudoedit /etc/hosts" pääsi lokaaliin nimipalveluun. Tänne lisättiin omalla ip osoitteella "hattu.example.com"

![host](images/h3_host.png)

Listassa näkyi "terminaattori" kokeilin toimiiko

![terminaattori](images/terminaattori.png)

Toimihan se. Sitten vielä kokeilin seuraavalla haulla "hattu.example.com".

![valmis](images/h3.valmis.png)

Tämäkin toimi.

### e) HTML5 sivu - validointi

Aloitin tämän osion klo. 22.30

Aloitin muokkaamalla "/home/timov/public_html/hattu.example.com" hakemistosta löytyvää tiedostoa "index.html" komennolla "micro index.html" Pohja löytyi Tero Karvisen materiaaleista "https://terokarvinen.com/2012/short-html5-page/"

![validointia](images/h3.validointia.png)

Sitten menin sivustolle "https://validator.w3.org/#validate_by_upload" valitsin "validate by file upload" sillä sivusto ei ole verkossa. Sitten etsin juuri muokkaamani "index.html" tiedoston ja painoin "Check" painiketta.

![validointia](images/h3_validointia2.png)

Tuloksena tuli pieniä herjauksia kielen ja ylimääräisen "/" merkin takia. Tein muutokset "index.html" tiedostoon. Eli lisäsin "lang=en" ja poistin ylimääräisen "/".

![validointia](images/h3_validointia3.png)

Tein validointi testin uudestaan.

![validointia](images/h3-validointia4.png)

Ei herjausta validointi onnistui.

![validointia](images/h3.hattuvalidi.png)

Yllä oleva kuva on "hattu.example.com" validoinnin jälkeen.

### f) esimerkki "curl -I" ja "curl" komennosta

Aloin tekemään tätä noin klo. 23.00

Testasin terminaalissa mitä tapahtuu, kun kirjoittaa sinne "$ curl" Seuraavaksi kokeilin komentoa "$ curl --help"

![curl](images/h3_curl1.png)

Tämän jälkeen kokeilin komentoja "$ curl localhost", "$ curl -I localhost" ja "$ curl -I hattu.example.com"

![curl](images/h3_curl.png)

Näyttäisi siltä, että "$ curl" komento näyttää html sivun ja "$ curl -I" näyttää tietoja sivustolta. Mm. serverin tyypin, statuksen, päivämäärän ja ajan milloin komento on suoritettu, milloin sivua on viimeksi muokattu, sivun pituuden ja sisällön tyypin. 

### Lähteet

Karvinen, Tero 2025: Linux Palvelimet 2025 alkukevät: (https://terokarvinen.com/linux-palvelimet/)

Linux.fi: (https://www.linux.fi/wiki/Portaali:Komentorivi)

The Apache Software Foundation 2025: Log Files: (https://httpd.apache.org/docs/2.4/logs.html)

The Apache Software Foundation 2025: Name-based Virtual Host Support: (https://httpd.apache.org/docs/2.4/vhosts/name-based.html)

Mozilla Foundation: Firefox user agent string reference: (https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent/Firefox)

Karvinen, Tero 2018: Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address: (https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/)
