# h2 - Komentaja Pingviini

### x) Tiivistelmä

### a) Micro editorin asennus

Aloitin työskentelyn noin kello 18.20. Ensimmäiseksi avasin terminaalin ja päivitin ohjelmat komennolla "$ sudo apt-get update
". Seuraavaksi kokeilin asentaa microa komennolla "$ sudo apt install micro". Ilokseni huomasin, että micro ei asentunut sillä olin tämän jo aiemmin asentanut, eikä muita häiriö viestejä ilmaantunut, vaan komentotulkki ilmaisi, että ohjelma on jo asennettu uusimpaan versioon.

![a](images/micro.png)

Valmis kello 18.30

### b) 3 uutta komentorivi ohjelmaa

Googlasin: "komentorivi ohjelma". Valitsin seuraavan linkin, "https://www.linux.fi/wiki/Comm". Tässä linkissä esitellään komentoriviohjelma comm

### c) Tärkeät kansiot

Aloitin tämän osion kello 20.20

Tärkeät kansiot löytyivät seuraavasta osoitteesta: "https://terokarvinen.com/2020/command-line-basics-revisited/"

#### "/" 
Root polku löytyi seuraavasti:
![c](images/root.png)

#### "/home/" 
Löytyi seuraavasti:
![c](images/home.png)

#### "/home/timov/" 
"home/" hakemistosta siirryttiin "timov/ hakemistoon komennolla "cd timov/". 

#### "/etc/" 
löytyi siten, että palasin "root" hakemistoon käyttämällä "cd .." komentoa kahdesti. Ja täältä "ls" komennolla pystyi näkemään, että täällä sijaitsee "etc/" hakemisto. Tähän navigoin komennolla "cd etc/"
![root](images/root.png)

#### "/media/" 
Hakemistoon menin seuraavasti. Aloitin siten, että tarkistin löytyykö "etc/" hakemistosta media kansiota kirjoittamalla komentotulkkiin "ls m" ja painamalla "tab" painiketta kahdesti.
![search](images/searching.png)

Ei löytynyt, joten palasin "root/" hakemistoon "cd .." komentoa käyttäen ja kirjoitin komentotulkkiin "ls m" ja painoin "tab" painiketta kahdesti. Täältä löytyi "media/" hakemisto, johon navigoin "cd media/" komentoa käyttäen.
![media](images/media.png)

#### "var/log/"
Hakemiston löysin palaamalla "root" hakemistoon. Tänne, kun kirjoitti "cd v" ja tupla tab, niin "var/" hakemisto jo tarjoutukin. Tämän jälkeen piti vain lisätä "log/" ja enter.
![varlog](images/var_log2.png)

### d) Grep-komento
Aloin tekemään tätä klo. 21.30

Teron Karvisen (https://terokarvinen.com/linux-palvelimet/) materiaalin pohjalta navigoin seuraavalle sivustolle "https://man7.org/linux/man-pages/man1/grep.1.html" Ja rupesin testailemaan grep-komentoa.
Tein grep-komentoa varten itseäni helpottavan tiedoston microlla documents/h2/ hakemistoon nimeltä "testaaja"
![testaaja](images/testaaja.png)

Alkuun en tahtonut tajuta miksen saa mitään komennosta irti. Joten avasin youtuben ja täältä seuraavasta videosta sain vähän työkaluja grepin käyttöön "https://www.youtube.com/watch?v=Tc_jntovCM0"

Hoksasinkin, etten ollut käyttänyt greppiä oikein. Eli olin yrittänyt hakea esim. -c (countilla) en mitään tiedostosta testaaja. komennolla "grep -c testaaja"

Hetken hämmästeltyäni tajusin sitten hakea jotain tiedostosta.
Käytin seuraavia komentoja:
grep mansikka testaaja
grep -c mansikka testaaja
grep ma testaaja
![grep](images/grep.png)

### f)

