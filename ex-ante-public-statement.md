# Algoritmi ennakoi tiukkaa kamppailua vaalien ykköspaikasta

Tutkijat ovat keränneet aineistoa ehdokkaiden Facebook ja Twitter seuraajamääristä jo kolmien eduskuntavaalien ajan. Aineiston pohjalta tehty ennuste ennakoi tiukkaa kamppailua ykköspaikasta Kokoomuksen, Perussuomalaisten ja Sosiaalidemokraattien välillä.

Tietojärjestelmätieteen oppiaineessa väitöskirjaa tekevä Tapio Vepsäläinen tutkii sosiaalisessa mediassa kerättyjen seuraajamäärien yhteyttä vaalimenestykseen. Tutkimusta varten on kerätty aineisto vuosien 2015, 2019, ja nyt viimeisimpänä, 2023 eduskuntavaalien ehdokkaista. Tämän vuoden eduskuntavaalien alla Facebookista löytyi 1146 ehdokkaan julkisilta kampanjasivuilta n. 2 miljoonaa tykkäystä, ja Twitteristä 1146 ehdokkaan sivuilta n. 5 miljoonaa seuraajaa. Lisäksi ennusteessa hyödynnettiin muuta julkisesti saatavilla olevaa aineistoa, kuten ehdokkaiden historiallisia äänimääriä eri vaaleissa, ehdokkaiden taustatietoja, sekä poliittisia meriittejä. Aineiston perusteella on laadittu ehdokaskohtainen ennuste.

## Ennustetulokset

Ennusteen perusteella Kokoomus, SDP ja Perussuomalaiset muodostavat kolmen kärjen. Eniten ääniä keräisi Kokoomus 19,2% kannatuksella. Kokoomukselle irtoaa 41 paikkaa, Perussuomalaisille 40, ja SDP:lle 39. Neljännelle sijalle päätyy keskusta, joka menettää edellisiin vaaleihin nähden 4 paikkaa. Myös vihreät menettävät 2 paikkaa. Vasemmistoliitto saa yhden paikan lisää, kuten myös Liike Nyt ja RKP. Ainoastaan KD:n paikkamäärä pysyy samana.

| Puolue | Paikat | Kannatus prosentti |
|--------|--------|-------------------|
| KOK | 41 | 19,20 % |
| PS | 40 | 17,19 % |
| SDP | 39 | 17,22 % |
| KESK | 27 | 11,60 % |
| VIHR | 18 | 10,71 % |
| VAS | 17 | 8,51 % |
| RKP | 10 | 4,89 % |
| KD | 5 | 3,58 % |
| LIIK | 2 | 2,62 % |
| FÅ (Ahvenanmaan vaalipiiri) | 1 | 0,37 % |
| Muut | 0 | 4,11 % |

Tulokset ovat melko lähellä Ylen viimeisimpiä kannatusmittauksia ja mahtuvat annettuun virhemarginaaliin. Ennusteen perusteella ei ole siis odotettavissa suurempia yllätyksiä.

## Merkittävä ero aikaisempiin ennusteisiin

Aikaisemmat ennusteet (linkki 2015, linkki 2019) ovat pohjautuneet pelkästään Facebookissa kerättyihin seuraajamääriin. Uusin malli hyödyntää Twitteristä kerättyjen tietoja, sekä lisäksi muita taustatietoja. Ennusteessa korkean painoarvon on saanut etenkin aikaisempi vaalimenestys. Ehkä voisi sanoa, että malli ennustaa ehdokaslistojen laatua. Kuinka kokeneita ja menestyneitä ehdokkaita puolueilla on listoilla? Asetelma ei ota kovin tarkasti kantaa nykyiseen mielipide-ilmapiiriin, vaan antaa isomman painoarvon historialliselle menestykselle.

Ehdokkaiden sosiaalisen median käyttö on muuttunut selvästi aikaisempiin vaaleihin verrattuna. Perussuomalaiset ovat olleet aikaisemmissa ennusteisa selkeästi ali-edustettuina, mutta asettuisivat nyt 2. sijalle. Tämä näkyy myös pelkästään sosiaaliseen mediaan pohjautuvassa arviossa. Kokoomus on yhä vahvin sosiaalisessa mediassa tykkäys- ja seuraajamäärien perusteella, mutta Perussuomalaiset ja SDP ovat kiilanneet vihreiden ohi.

## Miten ennuste on laadittu?

Malli pohjautuu verkossa julkisesti saatavilla olevaan aineistoon. Ennustavia muuttujia ovat ehdokkaiden seuraajamäärät Facebookissa ja Twitterissä, ehdokkaiden ja puolueiden aikaisempi vaalimenestys, muut ehdokkaiden julkisesti saatavilla olevat taustatiedot, sekä heidän arvioitu poliittinen kokemus. Malli on toteutettu avoimeen lähdekoodiin pohjautuvalla XGBoost (eXtreme Gradient Boosting) koneoppimis algoritmilla ([https://github.com/dmlc/xgboost](https://github.com/dmlc/xgboost)). Hyperparametrien optimointiin on käytetty Optunaa ([https://github.com/optuna/optuna](https://github.com/optuna/optuna)), joka on myös avoimen lähdekoodin ohjelmisto.

Malli ennustaa kunkin ehdokkaan tietoihin perustuen ehdokas kohtaisen äänimäärän. Lopuksi ehdokkaiden vertausluvut ja läpimeno on laskettu D'Hondtin menetelmän mukaisesti.

Nykyisen mallin kehittämisen mahdollisti aikaisemmissa vaaleissa kerätty aineisto. Koneoppimismalli on opetettu eduskuntavaaleista 2015 ja 2019 kerätyllä uniikilla aineistolla. Hyödynnetty algoritmi ei ole uusi, mutta sen hyödyntäminen vaalien kontekstissa on ollut aikaisemmin haastavaa riittävän datan puuttuessa.

## Aineiston keräys

Aineistoa on kerätty vuosien varrella eri menetelmillä. Sosiaalisen median palvelut muuttuvat jatkuvasti. Facebook sulki rajapintansa tutkijoilta 2018, ja Twitter rajoitti merkittävästi tiedon saatavuutta helmikuussa 2023 ([https://techcrunch.com/2023/02/01/twitter-to-end-free-access-to-its-api/](https://techcrunch.com/2023/02/01/twitter-to-end-free-access-to-its-api/)). Facebook ja Twitter sivut ovat kuitenkin julkisesti saatavilla, joten aineistoa voi yhä kerätä. Vuoden 2023 aineiston keräys eroaa sikäli aikaisemmista vaaleista, että tällä kertaa suurin osa tiedoista on haettu hakukoneiden kautta.

## Vastaavien ennusteiden tulevaisuus

Facebookin suosio näyttää hieman hiipuneen ehdokkaiden keskuudessa. Puhetta käyttäjien siirtymisestä muille alustoille on ollut pitkään. Twitterin omistajapohjan muutokset ovat myös omalta osaltaan johtaneet spekulaatioon alustan tulevaisuudesta. Erilaiset sosiaalisen median palvelut tulevat varmasti olemaan jatkossa ajankohtaisia, mutta on vaikea sanoa mitkä kanavat tulevat olemaan tärkeimpiä. Tulevaisuudessa olisi kenties viisainta etsiä se kanava, jossa ehdokkaalla on eniten seuraajia, oli se sitten Facebook, Twitter tai Instagram, ja hyödyntää sitä mittarina.

Uudet innovaatiot tekoälyn saralla saattavat helpottaa aineiston keräämistä tulevaisuudessa. Tällä hetkellä aineiston keräämiseen liittyy vielä jonkin verran haasteita, etenkin tietojen oikeellisuuden tarkistuksessa. Tulevaisuudessa esimerkiksi internettiin kytketyt GPT-3 tyyppiset LLM mallit voisivat helpottaa materiaalien keräämistä. Tästä esimerkkinä Bingin haku botti, jonka ainakin teoriassa pitäisi olla tehokas työkalu seuraajamäärien keräämiseen. LLM mallit voisivat myös helpottaa muun mediasisällön keräämistä. Aiheella on hieman aikaista spekuloida, mutta odotan innolla miten käy.
