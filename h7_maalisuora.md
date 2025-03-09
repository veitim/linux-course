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

Aloitin lukemalla Tero Karvisen tehtävänannon vinkkiosiosta löytyvää linkkiä: https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/.

Päätin tehdä ajaa heimaailman pythonilla, bashilla ja c++. Asensin pythonin ja c++ komennolla "$ sudo apt-get install python3 g++" Bashia ei tarvinnut erikseen asentaa.
Tein heimaailma tiedostot microlla.

![a](images/h7_a_tiedostot.png)

Pythoninilla heimaailman tulostus onnistui kirjoittamalla tekstitiedostoon print("Hei maailma!"), ja tämä sitten ajettiin komennolla "$ python3 heimaailma.py" (heimaailma.py, koska tämä on tiedoston nimi). 

![a](images/h7_a_python.png)

Kuvassa olen käyttänyt "cat" komentoa tiedoston tarkasteluun.

Bashilla heimaailma tiedoston päätteksi tuli ".sh", ja tekstitiedostoon lisäsin rivin 'echo "hei maailma!"'. Luin tiedoston komennolla "$ bash heimaailma.sh"

![a](images/h7_a_bash.png)

C++ poikkesi enemmän aikaisemmista siten, että täytyi lisätä enemmän tekstiä ja tiedosto piti muuttaa komennoksi.

![a](images/h7_a_c++.png)

Eli c++ vaati kirjaston "iostream", mikä haetaan "include" ja "std::cout" tarvitaan, jotta tekstiä voidaan tulostaa. Komento "$ g++ heimaailma.cc -o heimaailmacc" teki tekstitiedostosta komennon, jonka pystyi suorittamaan komennolla "./heimaailmacc"

### c) Laita Linuxiin uusi, itse tekemäsi komento niin, että kaikki käyttäjät voivat ajaa sitä.

### d) Ratkaise vanha arvioitava laboratorioharjoitus soveltuvin osin.

### e) Asenna itsellesi tyhjä virtuaalikone arvioitavaa labraa varten.
