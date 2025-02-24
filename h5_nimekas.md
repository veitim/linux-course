## h5_nimekäs
Tämä raportti on tehty 24.2.2025

Tämän tehtävän aloituksessa oli lievästi ongelmia, sillä palvelimeni oli kadonnut upcloudista (krediitit olivat loppuneet, niin oletan tästä syystä tämän kadonneen) , joten jouduin tekemaan h4-tehtävän uudestaan. Ja vielä ilokseni namecheap palvelu, mitä halusin tätä tehtävää tehdessä käyttää oli huollettavana, mikä esti domainin vuokraamisen.

Tehtää tehtäessä olen käyttänyt enimmäkseen Tero Karvisen tekemiä oppimateriaaleja, mitkä löytyvät sivustolta: "https://terokarvinen.com/linux-palvelimet/".

### a ja b) Nimi
Aloitin tämän osion 24.2.2025 klo. 19.00. namecheap sivuston huolto ohitse.

Elikkä käytin domain-nimeä varten namecheap sivustoa "https://www.namecheap.com/".

![h5a](images/h5_a_namecheap.png)

Tänne kävin laittamassa ohjaukset palvelimelleni käyttäen tämän ip-osoitetta. Sitten testasin, että voiko sivustolleni navigoida käyttäen domain-nimea "timoveijalainen.com"

![h5a](images/h5_a_selain.png)

Nimipalvelu pelaa.

### c) Sivusto
Aloitin tästä osiosta, koska namecheap sivustolla oli huolto käynnissä. Aloitin tekemisen 24.2.2025 klo. 15.00

Tein alasivut "blog.html" ja "projects.html" munsivu.com hakemistoon, "index.html" oli jo aiemmin tehtynä. Html-pohjana on käytetty Tero Karvisen materiaaleista löytyvä HTML-5 sivupohja "https://terokarvinen.com/2012/short-html5-page/". Koska pystyin sivut tekemään ja näihin muokkauksia tekemään ilman sudoa, niin ymmärtääkseni nyt ei ole pääkäyttäjän oikeuksia käytetty.

Eli kopioin "index.html" ja tein tästä "projects.html". Samalla tapaa tein "blog.html" sivun. Tämän jälkeen kävin microlla muokkaamassa sivujen tekstejä ja lisäisin linkitykset.

![h5c](images/h5_c_htmlsivut.png)

![h5c](images/h5_c_micro.png)

![h5c](images/h5_c_linkit.png)

### d) Alidomain
Aloitin tämän osion klo. 20.00

Kävin lisäämässä namecheappiin kaksi uutta "host" nimikettä advanced DNS osioon.

![h5d](images/h5_d_namecheap.png)

Eli "tunari" ja "timo" pitäisi nyt toimia jotenkin.

![h5d](images/h5_d_tunari.png)

tunari.timoveijalainen.com ainakin ohjaa sivustoni etusivulle. (niin myös timo.timoveijalainen.com)
En varmaan nyt ole ymmärtänyt alidomainia oikein.

### e) tutkintaa "dig" ja "host" komennoilla.
Aloitin tämän osion klo. 20.20

Ensiksi menin www.linux.fi sivustolle ja hain tietoa dig ja host komennoista. Tämän jälkeen lähdin testailemaan komennolla "$ dig timoveijalainen.com" 

![h5e](images/h5_e_dig.png)

Eli komentoa ei ole, joten jotain täytyy asentaa. Hakukoneeseen haku "how to install dig on linux" Tällä haulla tuli seuraava komento "sudo apt-get install dnsutils" Ainakin pienin tutkimsen jälkeen näyttää ihan aidolta.

Asennus toimi ja komento "$ dig timoveijalainen.com" näyttää seuraavalta

![h5e](images/h5_e_dig2.png)

Komento "$ host timoveijalainen.com" näyttää seuraavalta

![h5e](images/h5_e_host.png)

Ja sitten tutkailin samoilla komennoilla namecheap sivustoa.

![h5e](images/h5_e_namecheap.png)

Seuraavaksi tutkailin Tero Karvisen sivustoa "terokarvinen.com"

![h5e](images/h5_e_terokarvinen.png)

Viimeiseksi tutkin sivustoa "youtube.com"

![h5e](images/h5_e_youtube.png)
