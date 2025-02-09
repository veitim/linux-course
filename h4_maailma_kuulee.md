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

### c) weppipalvelin omalle virtuaalipalvelimelle

### d) 
