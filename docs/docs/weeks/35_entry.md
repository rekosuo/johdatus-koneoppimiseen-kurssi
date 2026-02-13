# 35-36: Koneoppiminen

## Mitä ovat tekoäly ja koneoppiminen?

Tekoäly voidaan määritellä teknologiaksi, jonka avulla tietokoneet voivat tehdä asioita jotka tyypillisesti vaativat ihmisen älykkyyttä. Tekoälyllä tietokone voi oppia, ratkaista ongelmia, ymmärtää asioita, ja toimia itsenäisesti ihmisälyn kykyjä jäljittelevällä tavalla. Tekoälyn alta löytyy useimmiten koneoppiminen. Koneoppiminen tarkoittaa tekoälymallin luomista koneoppimisalgoritmin avulla niin, että algoritmi oppii tekemään ennusteita tai päätöksia datan perusteella. [^sourander][^ibm]

## Tekoälyn alkuvuodet ja talvet

Ajatus älykkäistä koneista on vanha, mutta vasta 1900-luvulla niistä tuli todellisuutta. Vuonna 1912 Leonardo Torres Quevedo rakensi ensimmäisen shakkia pelaavan koneen. Kone pystyi voittamaan kuninkaalla ja tornilla vastustajan, jolla oli vain kuningas. [^shakkikone][^ibm2]

1950-luvulla tapahtui todellista edistystä tietokoneiden ja tekoälyn kehityksessä. 1955 keksittiin termit "artificial intelligence" ja "machine learning". Vuosikymmenen merkittäviin saavutuksiin kuuluvat perseptronit (primitiivinen neuroverkko), matemaattisia ongelmia ratkovat tietokoneohjelmat kuten Logic Theorist ja General Problem Solver, sekä omaa suorituskykyään parantava tietokoneohjelma.[^ibm2]

Kehityksen jatkuessa syntyi suurta innostusta liittyen tekoälyyn, mutta sen todellinen suorituskyky ei vastannut lupauksia ja odotuksia. Tämä johti pettymyksiin, ja 1970-lvulla tekoälytutkimuksen rahoitusta leikattiin suuresti. Innostuksen lopettamisesta ollaan syytetty teoksia kuten kirjaa *Perceptrons: An Introduction to Computational Geometry* ja Brittiläistä vuoden 1973 Lighthill-raporttia. Näissä paljastui sen aikaisen tekoälytutkimuksen heikkouksia. 1980-luvulla tapahtui toinen pettymyksen aalto, kun Yhdysvalloissa ja Japanissa tekoälytutkimus ei tuottanut valtavasta rahoituksesta huolimatta tuloksia. Näistä pettymyksistä huolimatta kehitys jatkui, ja tietokoneita ja tekoälyä kehitettiin edelleen. [^ibm2][^aiwinter] 

## Koneoppimisen tyypit

On kolme koneoppimisen tyyppiä: ohjattu oppiminen, ohjaamaton oppiminen, ja vahvistusoppiminen. Nämä tyypit sopivat eri käyttötarkoituksiin.

### Ohjattu oppiminen (supervised learning)

Ohjatussa oppimisessa koulutusdata sisältää oikean vastauksen. Malli oppii tunnistamaan korrelaatioita syötetteen (input) ja oikeiden vastausten (output) välillä. Kun malli on oppinut tunnistamaan nämä korrelaatiot, malli pystyy ennustamaan oikean vastauksen datasta, joka ei ollut sen koulutusdatassa. Malli oppii tunnistamaan riippuvuussuhteet piirteitten ja annotaatioiden välillä.[^sourander][^ibmsuper]

Ohjattu oppiminen sopii hyvin luokittelu- ja regressio-ongelmiin. Luokittelussa dataa luokitellaan eri kategorioihin. Regressiossa etsitään riippuvuussuhteita riippumattomien ja riippuvien muuttujien välillä.[^sourander][^ibmsuper]

Minulla on ohjatusta oppimisesta kokemusta, sillä olen hienosäätänyt/jatkokouluttanut Stable Diffusion -malleja. Olen opettanut malleille käsitteitä ja tyylejä. Tässä datan annotointi oli avainasemassa, ja se oli kaikkein työläin vaihe. 

### Ohjaamaton oppiminen (unsupervised learning)

Ohjaamattomassa oppimisessa käytetään annotoimatonta dataa. Algoritmi oppii tunnstamaan datasta rakenteita (pattern) ilman, että sille kerrotaan mitä datassa on. Ohjaamatonta oppimista käytetään klusterointiin, assosiointiin ja ulottuvuuksien vähentämiseen.[^sourander][^ibmunsuper]

#### Klusterointi [^ibmunsuper]

Datapisteet jaetaan klustereihin. Klusterointia on useampaa eri tyyppiä:

* Eksklusiivisessa klusteroinnissa yksi datapiste voi kuulua vain yhteen klusteriin.
    * Esim. k-means clustering.
* Päällekkäisessä klusteroinnissa (overlapping clustering) yksi datapiste voi kuulua useampaan klusteriin ja jäsenyys voi olla eri tasolla.
    * Esim. fuzzy k-means clustering.
* Probabilistisessa klusteroinnissa datapisteet klusteroidaan sen mukaan, kuinka todennäköisesti datapisteet kuuluvat tiettyyn todennäköisyysjakaumaan.
    * Esim. Gaussian Mixture Model.
* Hierarkinen klusterointi
    * Agglomerative clustering. Bottom-up, pienemmistä klustereista yhdistetään suurempia klustereita kunnes vain yksi on jäljellä.
    * Divisive clustering. Top-down, yksi iso klusteri jaetaan pienempiin klustereihin datapisteiden erojen perusteella. Harvoin käytetty.

#### Assosiointi [^ibmunsuper]

Assosiaatiosääntöjä käytetään muuttujien välisien suhteiden löytämiseen. Yksi näiden suurista käyttökohteista on kuluttajien ostoskäyttäytymisen ymmärtäminen.

Eniten käytetty algoritmi on Apriori-algoritmi. Algoritmi tunnistaa usein yhdessä kulkevien asioiden rymiä. Nettikaupan tai musiikkipalvelun kontekstissa algoritmi ennustaa, kuinka todennäköisesti käyttäjä kuluttaa tuotteen, jos hän kuluttaa jonkun toisen tuotteen.

#### Ulottuvuuksien vähentäminen 

Datan ulottuvuuksien eli inputtien määrää vähennetään. Tätä tehtään, jos jostain syystä ulottuvuuksia on liian paljon. Suurempi määrä dataa on yleensä parempi mallin tarkkuuden kannalta, mutta Liiallinen ulottuvuuksien määrä voi olla myös haitaksi mallin suorituskyvylle. [^ibmunsuper]

Ulottuvuuksien vähentämiseen on eri menetelmiä, kuten:[^ibmunsuper]

* Principal component analysis
* Singular value decomposition
* Autoencoders

Haluan vähän tutkia autoenkoodereita, sillä Stable Diffusion käyttää autoenkooderin variaatiota nimeltään Variational Autoencoder (VAE). Autoenkoodereiden ideana on, että ne pakkaavat ja enkoodaavat dataa niin, että datalla on vähemmän ulottuvuuksia. Autoenkooderi sitten dekoodaa pakatun datan ja yrittää mahdollisimman tarkasti luoda uudelleen alkuperäisen datan. Autoenkooderit soveltuvat poikkeamien huomaamiseen ja kohinan poistamiseen. Poikkeama voi olla vaikka kyberhyökkäyksen aiheuttama epätavallinen toiminta tietokonejärjestelmässä. Kohina voi esimerkiksi olla kohinaa valokuvassa. [^autoenc][^spavae]

VAE:t sopivat datan generoimiseen, koska ne oppivat probabilistisen mallin datasta. Tämä mahdollistaa sen, että VAE:n ei välttämättä tarvi luoda juuri koulutusdataa vastaavaa dataa, vaan jotain joka on sitä lähellä. Tämän ansiosta VAE:t ovat normaaleja autoenkoodereita robustimpia. [^vaebadr]

### Vahvistusoppiminen

Vahvistusoppimisen perusperiaate on, että mallin kehitystä ohjataan palkkoiden ja rangaistusten avulla. Toivotusta toiminnasta annetaan palkkio, ja epätoivotusta toiminnasta rangaistus. Tavoitteena on luoda malli, joka osaa toimia ja tehdä päätöksiä tietyssä ympäristössä ilman ihmisten ohjausta. [^ibmreinforce]

Vahvistusoppimisalgoritmin tulee sekä etsiä uusia toiminnan reittejä (exploration) että hyväksikäyttää jo oppimaansa (exploitation). Näiden kahden suhdetta voi säätää. Alkuvaiheessa mallin on hyvä keskittyä enemmän tutkimaan mahdollisuuksiaan/ympäristöään selvittääkseen, minkälainen toiminta tuottaa eniten palkintoja. Kun mallin koulutusta jatketaan, kannattaa keskittyä enemmän jo opitun käyttämiseen. [^yosh1]

## Mallin kouluttamisen työnkulku [^sourander]

0. Mihin tarkoitukseen mallia tarvitaan? On epätodennäköistä, että ilman päämäärää saadaan mitään hyödyllistä aikaan.

1. Datan kerääminen. Datan pitää olla koulutettavan mallin kannalta olennaista. Kun dataa kerää, sillä tulee olla tarkoitus. Voi kysyä kysymyksen: "Mitä asiaa tai prosessia data kuvaa?" Datan kerääminen, säilyttäminen ja käsittely maksaa aina tavalla tai toisella, joten on järkevää etukäteen suunnitella datalle käyttökohteita.[^juliusdata]

2. Datan esikäsittely. Data täytyy laittaa muotoon, joka palvelee koneoppimisehtävää. Data voidaan vaikka normalisoida tai enkoodata piirteiksi. Datasta on myös suotavaa poistaa virheet. Datan käsittely on asiantuntijatyötä, joka vaatii ymmärrystä datasta ja sen käyttötarkoituksesta.

3. Mallin valinta. Valinta riippuu ongelmasta sekä saatavilla olevasta datasta. Vaikka mallin valinnalla on vaikutus lopputulokseen, datan vaikutus on paljon suurempi.

4. Mallin koulutus. Mekaaninen laskentatehoa vaativa vaihe. Koulutuksen vaatimaan aikaan ja sen tuottamaan lopputulokseen vaikuttavat valitut hyperparametrit. Oman Stable Diffusion kokemukseni perusteella hyperparametrien valinta ei ole tarkkaa rakettitiedettä, sillä oikeaan maaliin voi päästä monilla eri vaihtoehdoilla.

5. Mallin evaluointi. Mallin suorituskyky testataan testidatalla.

6. Hyperparametrien viritys. Hyperparametrien valinta voi vaikuttaa siihen, kuinka hyvin malli yleistyy dataan. Hyperparametreja viritettäessä niiden arvoja muutetaan, ja mallia testataan muutetuilla arvoilla.

7. Mallin käyttöönotto. Kun malli on ollut käytössä pitkän aikaa, se voi vanhentua. Tämä johtuu siitä, että malli on koulutettu vanhalla datalla mutta maailma on muuttunut. Tämän voi korjata keräämällä uutta dataa ja päivittämällä mallia.

## Lähteet

[^sourander]: Jani Sourander. Kurssimateriaali.

[^ibm]: Cole Stryker, Eda Kavlakoglu. What is artificial intelligence (AI)? https://www.ibm.com/think/topics/artificial-intelligence

[^ibm2]: Tim Mucci. The history of AI. https://www.ibm.com/think/topics/history-of-artificial-intelligence

[^aiwinter]: Mike Richards. From boom to bust: the AI winter. https://www.open.edu/openlearn/digital-computing/from-boom-bust-the-ai-winter

[^shakkikone]: Al Williams. The Chess Computer From 1912. https://hackaday.com/2023/07/03/the-chess-computer-from-1912/

[^ibmsuper]: Ivan Belcic, Cole Stryker. What is supervised learning? https://www.ibm.com/think/topics/supervised-learning

[^ibmunsuper]: IBM. What is unsupervised learning? https://www.ibm.com/think/topics/unsupervised-learning

[^autoenc]: Will Badr. Auto-Encoder: What Is It? And What Is It Used For? (Part 1). https://towardsdatascience.com/auto-encoder-what-is-it-and-what-is-it-used-for-part-1-3e5c6f017726/

[^vaebadr]: Will Badr. Uncovering Anomalies with Variational Autoencoders (VAE): A Deep Dive into the World of… https://towardsdatascience.com/uncovering-anomalies-with-variational-autoencoders-vae-a-deep-dive-into-the-world-of-1b2bce47e2e9/

[^spavae]: José Fuentes, Ines Ortega-Fernández, Nora M. Villanueva, Marta Sestelo. Cybersecurity threat detection based on a UEBA framework using Deep Autoencoders. https://arxiv.org/html/2505.11542v1

[^yosh1]: Yosh.  AI Learns to Drive From Scratch in Trackmania. https://www.youtube.com/watch?v=SX08NT55YhA

[^ibmreinforce]: Jacob Murel, Eda Kavlakoglu. What is reinforcement learning? https://www.ibm.com/think/topics/reinforcement-learning

[^juliusdata]: Julius Černiauskas. What Is The Purpose Of Data? https://www.forbes.com/councils/forbestechcouncil/2022/03/30/what-is-the-purpose-of-data/