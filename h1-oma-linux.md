# Linuxin asennus virtuaalikoneelle

Asensin virtuaalikoneen ja linuxin seuraavaa lähdettä käyttäen: Karvinen, Tero: 2025-01-14 oppitunnit Linux-palvelimet -kurssi. https://terokarvinen.com/2021/install-debian-on-virtualbox/

Käytin virtuaalikoneens asennukseen Oraclen VirtualBox manageria, jolla asensin virtuaalikoneen kannettavalle tietokoneelleni (Msi GE75 Raider 10sf), minkä käyttöjärjestelmänä toimii Windows 10 Home 64-bit.

Virtuaalikoneen asensin seuraavilla spekseillä n. klo 17.
![Add file: Upload](virtuaalikone_tiedot.png)

Seuraavaksi lisäsin virtuaalikoneeseen virtuaalilsen cd-levyn, jonka latasin seuraavalta sivustolta: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/. Linkki löytyy aiemmin mainitusta lähteestä.

![Add file: Upload](iso_tiedosto.png)

Virtuaalikone toimii, joten seuraavaksi rupesin asentamaan debiania klo. 18. Askel askeleelta noudatin ohjeita.

![Add file: Upload](debian_asennus.png)

Asennus näytti onnistuvan
![Add file: Upload](login.png)

Seuraavaksi kirjauduin järjestelmään ja varmistin toimivuuden käynnistämällä verkkoselaimen.
Tämän jälkeen avasin terminaalin, jossa suoritin seuraavat komennot: $ sudo apt-get update, $ sudo apt-get -y dist-upgrade, $ sudo apt-get -y install ufw, $ sudo ufw enable. Komennoilla päivitettiin järjestelmä ja asennettiin/otettiin palomuuri käyttöön. Seuraavaksi käynnistin virtuaalikoneen uudestaan. Jonka jälkeen asensin Guest Additionin ohjeita seuraamalla. Kaikki onnistui ja toimii niinkuin pitääkin.
