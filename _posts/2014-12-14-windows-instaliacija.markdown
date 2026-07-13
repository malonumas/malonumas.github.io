---
layout: post
title:  "Instaliuojame Windows UEFI režimu"
categories: windows
---

Nusipirkus naują kompiuterį yra tikimybė, kad vietoj senųjų Legacy BIOS, jūsų motininė plokštė palaikys naująją sąsają [UEFI](https://en.wikipedia.org/wiki/UEFI) (Unified Extensible Firmware Interface), kuri suteikia šiokių tokių privalumų ir vietoj standartinio mėlyno nustatymų lango jums suteikia grafinę aplinką, kuria galite naudotis su kompiuterio pele, o ne vien klaviatūra, kaip kad su BIOS’ais. Ir žinoma, visi mokame įsirašyti Windows iš kompaktinio disko ar USB atmintuko, tačiau tai darant paprastai, Windows’ai po default’u įsirašinėja be UEFI palaikymo, naudojant MBR failų lentelę, o ne GPT, kas ir neleidžia išnaudoti visų šios naujosios, BIOS sąsają pakeičiančios technologijos privalumų. Šiandien, būtent ir pasakosiu, kaip Windowsus priversti dirbti efektyviausiai kompiuteryje, kuris turi UEFI (visada norisi sakyti UEFI biosus, nes taip aiškiau, nors ir nėra teisinga).


## Info dalis:

Prieš pradedant, norėčiau patarti, kad jei jau esate pasirengęs tvarkyti savo kietąjį diską, jį formatuoti ar dalinti į particijas, tai akivaizdu, kad duomenis iš jo esate jau išsikopijavę ir esate užtikrintas, kad nieko svarbaus neužmiršote ir neprarasite. Tokią akimirką, prieš pradededant darbus, pirmiausia pasitikrinkite dėl savo HDD ar SSD disko firmware atnaujinimo gamintojo svetainėje. Pvz aš šiuo metu turiu savo kompiuteryje Crucial M4 SSD ir atnaujinimai jam pasirodo maždaug, kas kelis mėnesius iš kurių paskutinis buvo dar gruodį. Atsinaujinti pravartu, nes gamintojai pataiso skyles, klaidingą veikimą tam tikromis sąlygomis ar net padidina disko efektyvumą ir jis tampa mažumėle spartesnis ar stabiliau veikiantis. Kartais tokių update’ų pagalba pataisomos kritinės klaidos, dėl kurių jūsų diskas gali sugesti. Tiek Windows 7, tiek ir naujieji Windows 8 leidžia instaliaciją atlikti naudojant senąjo MBR (Master Boot Record) formato, tiek ir patobulinto GPT (GUID Partition Table) formato diskus. Po default’u būna naudojama dar nuo 1983-iųjų populiari MBR, tačiau su naujosiomis UEFI pagrindinėmis plokštėmis, nuo šio galima išbandyti ir GPT, nes šiosios palaiko abu šiuos formatus.

## UEFI/GPT pranašumai lyginant su MBR:

- GPT diskai panaikina 2,2TB diskų talpos limitą, kurį turėjo MBR.
- MBR yra apribota iki keturių particijų lentelių
- GPT pasirūpina geresniu duomenų struktūros integralumu, duomenų atsatymas juose lengvesnis
- UEFI boot’as yra labiau saugus, t.y. gerokai sunkiau pažeidžiamas kenkėjiškų programų
- UEFI boot’as ir sugrįžimas iš miego režimo yra gerokai greitesnis, nei tos pačios sistemos, naudojančios MBR
- UEFI yra didžiausių IT korporacijų, tokių, kaip AMD, Apple, Dell, HP, IBM, Insyde Software, Intel, Lenovo, Microsoft vystomas ateities standartas. UEFI – tai kompiuterių ateitis ir ateityje bus naudojama visuose kompiuteriuose, bei daug daugiau, nei tik jų krovimo metu.


## Reikalavimai:

- UEFI (GPT) bootinis diskas gali būti konfiguruojamas tik iš tuščio, nepaskirstyto (unallocated) disko, tai yra diskas negali turėti particijų. Tad atliekant veiksmus, bus privaloma ištrinti visas particijas.
- Jūsų pagrindinė plokštė turi palaikyti UEFI technologiją. Jei nežinote ar palaiko – paskaitykite gamintojo instrukcijas arba perkrovę kompiuterį įeikite į Configuration spausdami F2 (ar kitą reikalaujamą mygtuką) ir patikrinkite kas rašoma antraštėje.

- GPT bootinius diskus(sistemos paleidimo) palaiko tik 64-bit operacinės sistemos versija.
- GPT boot’as galimas tik Vista SP1 ir vėlesnėse operacinėse sistemose. Senosios Windows versijos nors ir leidžia prijungti prie sistemos GPT formato diskus, tačiau neleidžia bootinti(paleisti sistemos) iš jų.

## Instrukcijos:

1\. Pirmiausia turite pasiruošti Windows instaliacinę laikmeną. Jei naudosite kompaktinį diską – jokių specialių pasiruošimų atlikinėti nereikia, galite keliauti prie sekančio punkto.

Tad flashiukui atliekame tokius punktus:

1.1. Atsidarome **Command Prompt** (Win+R, įrašome cmd, spaudžiame Enter)
1.2. Vedame komandas paeiliui, po kiekvienos spausdami Enter:

> **diskpart**\
> **list disk**\
> **select disk**  # (šioje vietoje vietoj grotelių įrašome savo usb flashiuko numerį, kurį patysite po **list disk** komandos. Dėmesio, būkite atidūs ir pasirinkite tinkamą diską!)\
> **clean**\
> **convert gpt**\
> **create partition primary**\
> **select partition 1**\
> **format quick fs=fat32**\
> **assign**\
> **exit**

1.3. Atlikę šias komandas naudojame 7zip ar WinRar ir išarchyvuojame Windows’ų isofailiuko turinį į USB flashiuką\
2\. Išjungiame kompiuterį palikę USB flashiuką pajungtą.\
3\. Įjungimo metu įeinate į UEFI nustatymus (F2, delete ar kitas nurodomas mygtukas)\
4\. Susirandame Boot nustatymus ir sekcijoje **Boot Option #1** pasirenkame krovimą iš UEFI device’o (pirmiausia rodomas prefix’as **UEFI**: „jūsų flashiuko arba kompaktinio disko pavadinimas“)\
5\. Išsaugome nustatymus ir perkrauname kompiuterį. Jei viską atlikote teisingai, kompiuteris ims krauti Windows instaliaciją.\
6\. Windows Setup lange (parodytas paveikslėlyje) spaudžiame Shift + F10, kad atidaryti command prompt ir vėl vedame komandas:

> **diskpart**\
> **list disk**\
> **select disk** (vietoj grotelių įrašome disko, kuriame norėsite instaliuoti Windowsus numerį)\
> **clean**\
> **convert gpt**\
> **exit**

7\. Uždarykite Command Prompt langą ir spaudžiame mygtuką „Next“.\
8\. Spauskite „Install now“.\
9\. Įveskite product key ir spauskite „Next“.\
10\. Pažymite varnelę „Accept terms“ ir spauskite „Next“.\
11\. Pasirinkite „Custom: Install Windows only (advanced)“\.
12\. Pasirinkite particiją ir spauskite „Drive options (advanced)“\
13\. Spauskite mygtuką „New“ ir „Apply“. Susikurs keturios particijos:
- Recovery – 300MB
- ESP – 100MB
- MSR – 128MB
- Data

14\. Pasirinkite apatinę (Data) ir spauskite „OK“, „Next“.\
15\. Pabaigus instaliaciją vėl užsikrauname į UEFI ir keliaujame į Boot nustatymus\
16\. Boot Option #1 šį kartą pasirenkame „**Windows Boot Manager**„.

Viską atlikus Windowsai sėkmingai užsikraus ir veiks jau UEFI režimu. Patikrinti tai galite dviem būdais:

-Atsidarę Disk Management turite matyti anksčiau sukurtas particijas, kas reikš kad naudojate GPT failų lentelę. Įsitikinti tuom galite meniu juostoje pasirinkę: View -> Top -> Disk List. Prie Disk 0 turėtumėte matyti Partition Style GPT.\
-Atsidarę Run (Win+R) įvedate komandą MSINFO32. Eilutėje BIOS Mode rasite užrašą UEFI.

Turėdami Windowsus, veikiančius UEFI režimu, galite įsijungti Fast Boot opciją:

-Keliaujame į tuos pačius UEFI Boot nustatymus, kuriuose jau lankėmės prieš tai ir susirandame Fast Boot opciją.\
-Pasirenkame Enable.\
-Išsaugome ir perkrauname kompiuterį.

Šios opcijos pasirinkimas įjungia kitokią tvarkymosi su POST tvarką, kas leidžia sutrumpinti krovos laiką.

Kai kurios plokštės leidžia pasirinkti dvi Fast Boot reikšmes: Fast ir Ultra Fast. Deja Ultra Fast pasirinkimui reikalinga, kad vaizdo plokštė palaikytų GOP technologiją ir nors plokštės, kurios tai palaikytų yra išleistos, tačiau kyla problemų dėl suderinamumo su senesnėmis motininėmis plokštėmis, tad vaizdo plokščių gamintojai kolkas nesutvarkė plokščių ROM’ų ir šios technologijos palaikymas kol kas išjungtas, tad pasirinkus Ultra Fast kompiuteris jums paprasčiausiai neužsikraus.

Pasirinkus Fast Boot gali būti, kad krovos metu nebematysite pagrindinės plokštės gamintojo lango, iš kurio patekdavote į UEFI nustatymus. Patekti į juos galėsite tik iš Windows’ų Advanced Startup.
