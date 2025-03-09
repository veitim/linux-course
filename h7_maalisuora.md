# h7 Maalisuora

Raportti kirjoitettu 9.3.2025, klo 15.50 - Välisenä aikana

Raportissa on käytetty Tero Karvisen Linux Palvelimet -kurssin materiaaleja, jotka löytyvät seuraavalta sivulta: https://terokarvinen.com/linux-palvelimet/.

Tehtävät on tehty seuraavalla laittestolla,

Isäntäkone:

* Malli: Msi GE75 Raider 10sf
* OS: Windows 10 Home 64-bit
* RAM: 16 GB
* CPU: Intel(R) Core(TM) i7-10750H CPU @ 2.60GHz (12 CPUs), ~2.6GHz
* GPU: NVIDIA GeForce RTX 2070
* BIOS: E17E9IMS, 10A

Virtuaalikone:
* OS: Debian/GNU Linux 12 (bookworm) x84_64
* RAM: 4 GB
* CPU: 2 processor
* GPU: 128 MB

### a) Kirjoita ja aja "Hei maailma" kolmella kielellä
Tämä osio aloitettu klo. 16:00

Aloitin lukemalla Tero Karvisen tehtävänannon vinkkiosiosta löytyvää linkkiä: https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/. Linkistä löyty kaikki tarpeellinen tehtävän suorittamista varten.

Päätin tehdä ajaa heimaailman pythonilla, bashilla ja c++. Asensin pythonin ja c++ komennolla "$ sudo apt-get install python3 g++" Bashia ei tarvinnut erikseen asentaa.
Tein heimaailma tiedostot microlla.

![a](images/h7_a_tiedostot.png)

Pythoninilla heimaailman tulostus onnistui kirjoittamalla tekstitiedostoon print("Hei maailma!"), ja tämä sitten ajettiin komennolla "$ python3 heimaailma.py" (heimaailma.py, koska tämä on tiedoston nimi). 

![a](images/h7_a_python.png)

Kuvassa olen käyttänyt "cat" komentoa tekstitiedoston tulostukseen.

Bashilla heimaailma tiedoston päätteksi tuli ".sh", ja tekstitiedostoon lisäsin rivin 'echo "hei maailma!"'. Luin tiedoston komennolla "$ bash heimaailma.sh"

![a](images/h7_a_bash.png)

C++ poikkesi enemmän aikaisemmista siten, että täytyi lisätä enemmän tekstiä ja tiedosto piti muuttaa komennoksi. Komennolla "$ g++ heimaailma.cc -o heimaailmacc" teki tekstitiedostosta komennon, jonka pystyi suorittamaan komennolla "./heimaailmacc"

![a](images/h7_a_c++k.png)

![a](images/h7_a_c++.png)

Eli c++ vaati kirjaston "iostream", mikä haetaan "include" ja "std::cout" tarvitaan, jotta tekstiä voidaan tulostaa.

Valmis klo. 16.30

### c) Laita Linuxiin uusi, itse tekemäsi komento niin, että kaikki käyttäjät voivat ajaa sitä.

Aloitin tämän osion klo. 17.30 

Tehtävän a, aikana tein uuden komennon nimeltä "heimaailmacc", joten käytin tätä komentoa tähän tehtvään.

testasin komentoa "./heimaailmacc"

![c](images/h7_c_heimaailma.png)

Toimi kuten piti. Seuraavaksi säädin komennon oikeuksia "chmod ugo+x heimaailmacc" komennolla, eli annoin kaikille käyttäjille execute oikeudet. chmod = komento jolla oikeuksia säädetään, u = user, g = group, o = others, + lisää, x = execute ja heimaailmacc = tiedosto/kansio mille oikeuksia määritetään.

![c](images/h7_c_ugo.png)

Tarkisin, että oikeudet näyttävät hyvältä "$ ls -l" komennolla. Tällä komennoilla voi tarkastella aktiivisen hakemiston sisällön oikeuksia.

![c](images/h7_c_ls-l.png)

heimaailmacc:n oikeudet näyttävät hyvältä, eli x näkyy kaikissa ryhmissä. Kaikki voi siis komentoa suorittaa. Seuraavaksi kopioin komennon paikkaan, josta kaikki sitä voi myös käyttää. Komento oli "$ sudo cp heimaailmacc /usr/local/bin/"

![c](images/h7_c_siirto.png)

Testasin, että komento toimii oman hakemiston ulkopuolelta. Menin root juureen asti ja kokeilin.

![c](images/h7_c_root.png)

Toimii tarkistin vielä hakemiston minne siirsin komennon.

![c](images/h7_c_komennot.png)

Olinkin jo aiemmin tunnilla tehnyt toimivan komennon. Näyttää hakemistosta löytyvän kanssa kurssin alussa asentamani wikit ohjelma.

Valmis klo. 18.15

### d) Ratkaise vanha arvioitava laboratorioharjoitus soveltuvin osin.



### e) Asenna itsellesi tyhjä virtuaalikone arvioitavaa labraa varten.
