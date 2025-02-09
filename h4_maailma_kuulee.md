# Maailma Kuulee
Tehty 9.2.2025

Tässä työssä o

#### Rauta


### x) Tiivistelmä

### a) Virtuaalipalvelin
Aloitin tämän osion klo. 15.00

Vuokrasin virtuaaliapalvelimen seuraavalta sivustolta: "https://upcloud.com/"
Kun sain omat tiedot lisättyä sivustolle, niin aloitin kohdasta "servers" ja täältä painoin painiketta "Deploy server"

![deploy](images/h4_navigointia.png)

Laitoin seuraavat asetukset:

Lokaatio

![deploy](images/h4_lokaatio.png)

Palvelimen speksit

![deploy](images/h4_plan.png)

Käyttöjärjestelmä

![deploy](images/h4_os.png)

Kirjautumiskeino

![deploy](images/h4_loginmethod.png)

Palvelimelle kirjautumista varten generoin avainparin terminaalissa seuraavalla komennolla "$ ssh keygen".  

![deploy](images/avain.png)

Julkisen avaimen lisäsin "Login Methodiin" microa hyödyntäen. Ensiksi navigoin hakemistoon, jossa avain sijaitsee ja komennolla "$ micro id_rsa.pub" avasin tiedoston ja näppäinyhdistelmällä "ctrl+a" valitsin kaiken tekstitiedostosta ja yhdistelmällä "ctrl+c" kopioin tämän. Sitten lisäsin kyseisen rimpsun kirjautumis vaihtoehtoihin.

![deploy](images/h4_avaimenhaku.png)

![deploy](images/h4_julkisenavaimenlisays.png)

Palvelimen nimeäminen

![deploy](images/h4_conf.png)

Yhteenveto

![deploy](images/h4_summary.png)

Sitten käynnistin palvelimen "Deploy" painikkeesta ja sehän onnistui.

![deploy](images/h4_palvelinpaalla.png)

### b) alkutoimet

Aloitin tämän osion klo. 16.15

Lueskelin tarkemmin Tero Karvisen materiaalit aiheesta sivustolta, "https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/" sekä kävin läpi tehtävänannossa olevat vinkit ja lähdin etenemään.

Aloitin kirjautumalla palvelimelle komennolla "$ ssh root@185.26.51.157" IP osoite löytyi juuri perustamani palvelinpalvelun "servers/server list" välilehdeltä.

Seuraavaksi lähdin laittamaan palomuuria päälle. Aloitin sillä, että yritin jättää reiät palomuuriin komennolla "sudo ufw allow 22/tcp", ei onnistunut sillä en ollut asentanut palomuuria tai muitakaan paketteja. Joten aloitin sittenkin näillä toiminteilla. Eli aloitin komennolla "sudo apt-get install" ja jatkoin "sudo apt-get install ufw".

![alku](images/h4_.png)

Sitten kokeilin laittaa uudestaan reikiä palomuuriin ennen tämän käynnistämistä.

![alku](images/h4_.png)

Neuroottisesti avasin vielä 80 portin komennolla "sudo ufw allow 80/tcp" Ja sitten laitoin palomuurin päälle "sudo ufw enable". Seuraavaksi boottasin palvelimen komennolla "sudo systemctl reboot".
Kirjauduin takaisin palvelimelle komennolla "$ ssh root@185.26.51.157" ja ajoin vielä seuraavat komennot varmuudeksi "sudo apt-get update" ja "sudo apt-get dist-upgrade", jotta varmasti kaikki on päivitetty.

![alku](images/h4_.png)

### c) weppipalvelin omalle virtuaalipalvelimelle

### d) 
