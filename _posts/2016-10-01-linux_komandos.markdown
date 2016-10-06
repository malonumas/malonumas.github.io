---
layout: post
title:  "Linux komandos"
date:   2016-10-01 14:32:55 +0300
categories: linux
---

<b>Sistema</b> 

<b>uname -a</b> => Parodo linux sistemos informacija
<br><b>uname -r</b> => Parodo kelnerio išleidimo informacija
<br><b>uptime</b> => Parodo kiek laiko sistema dirba
<br><b>hostname</b> => Parodo sistemos hosta
<br><b>hostname -i</b> => Parodo hosto IP adresą
<br><b>last reboot</b> => Parodo sistemos perkrovimo istoriją
<br><b>date</b> => Parodo datą ir laiką
<br><b>cal</b> => Parodo šio mėnesio kalendorių
<br><b>w</b> =>Parodo kas yra prisijungęs
<br><b>whoami</b> => Parodo kas esate ir kaip prisijungęs
<br><b>finger user</b> =>Parodo informaciją apie vartotoją

<b>Techninė įranga</b>

<b>dmesg</b> =>Aptikti techninės įrangos ir įkrovos pranešimus
<br><b>cat /proc/cpuinfo</b> =>CPU modelis
<br><b>cat /proc/meminfo</b> => Techninės įrangos atmintis
<br><b>cat /proc/interrupts</b> => CPU ir I/O įrenginio pertraukų kiekio sąrašas
<br><b>lshw</b> =>Parodo informaciją apie sistemos aparatūros konfigūraciją
<br><b>lsblk</b> =>Parodo lustinio prietaiso informaciją Linuxe
<br><b>free -m</b> =>Naudojama ir laisva atmintis (-m dėl MB)
<br><b>lspci -tv</b> =>Parodo PCI įrenginius
<br><b>lsusb -tv</b> =>Parodo USB įrenginius
<br><b>dmidecode</b> =>Parodo aparatūros informaciją iš BIOS
<br><b>hdparm -i /dev/sda</b> =>Parodo informaciją apie disko sda
<br><b>hdparm -tT /dev/sda</b> =>Testuoja sda disko skaitymo spartą
<br><b>badblocks -s /dev/sda</b>< =>Disko sda neįskaitomų blokų testas<b>

<b>Vartotojai</b>

<b>id</b> =>Aktyvus vartotojo vardas, prisijungimo vardas ir grupė
<br><b>last</b> =>Parodo paskutinį prisijungimą prie sistemos
<br><b>who</b> =>Parodo kas yra prisijungęs prie sistemos
<br><b>groupadd admin</b> =>Prideda grupę „admin“
<br><b>userdel sam</b> =>ištrina vartotoją sam
<br><b>adduser sam</b> =>prideda vartotoją „sam“
<br><b>usermod</b> =>Keičia vartotojo informaciją

<b>Failų komandos</b>

<b>ls –al =>Parodo visą informaciją apie failus / katalogus</b>
<br><b>pwd</b> =>Parodo einamojo katalogo kelią
<br><b>mkdir</b> katalogo-pavadinimas =>Sukuria katalogą
<br><b>rm failo-pavadinimas</b> =>ištrina failą
<br><b>rm -r katalogo-pavadinimas</b> =>Ištrina katalogą rekursyviai
<br><b>rm -f failo-pavadinimas</b> =>Ryžtingai pašalina failą
<br><b>rm -rf katalogo-pavadinimas</b> =>Ryžtingai ir rekursyviai pašalina katalogą 
<br><b>cp failas1 failas2</b> =>Kopijuoja failas1 į failas2
<br><b>cp -r dir1 dir2</b> => Kopijuoja dir1 į dir2, sukuria dir2 jeigu nėra
<br><b>mv file1 file2</b> =>Pervadina šaltinį / perkelia šaltinį į katalogą
<br><b>ln –s /path/to/failo-pavadinimas nuorodos-pavadinimas</b> =>Sukuria simbolinę nuorodą į failą
<br><b>touch file</b> =>Sukuria arba atnaujina failą
<br><b>cat > file</b> =>Standartinis įvedimas į failą
<br><b>more file</b> =>Failo išvesties turinys
<br><b>head file</b> =>Failo išvesties pirmos 10 eilučių
<br><b>tail file</b> =>Failo išvesties paskutinės 10 eilučių
<br><b>tail -f file</b> =>Failo išvesties turinys kuris auga nuo prasidedančių 10 eilučių
<br><b>gpg -c file</b> =>Užšifruoti failą
<br><b>gpg file.gpg</b> =>Iššifruoti failą
<br><b>wc</b> =>spausdinti baitų, žodžių ir eilučių skaičių į failą
<br><b>xargs</b> =>Vykdyti komandas iš standartinės įvesties

<b>Procesai</b>

<b>ps</b> =>Parodo aktyvius procesus
<br><b>ps aux | grep ‘telnet’</b> =>Randa visą proceso ID, susijusią su telnet procesu
<br><b>pmap</b> =>Proceso atminties žemėlapis
<br><b>top</b> =>Parodo visus veikiančius procesus
<br><b>killpid</b> =>Nužudo procesą su minėta pid id
<br><b>killall proc</b> =>Nužudo visus procesus, pavadintus proc
<br><b>pkill proceso-vardas</b> =>Siųsti kill signalą į procesą jo vardu
<br><b>bg</b> =>Sąrašas sustabdytų arba fono darbų
<br><b>fg</b> =>Parodo naujausią darbą
<br><b>fg n</b> =>Parodo darbą n

<b>Failų teisės</b>

<b>chmod octal failo-vardas</b> =>Pakeisti failo teises į aštuntaines
<br><b>chmod 777 /data/test.c</b> =>Nustatyti rwx teises savininkui,grupei,kitiems
<br><b>chmod 755 /data/test.c</b> =>Nustatyti rwx teises savininkui,rw grupei ir kitiems
<br><b>chown savininkas-vartotojas failas</b> =>Failo savininko keitimas
<br><b>chown savininkas-vartotojas:savininkas-grupe failo-vardas </b>=>Pakeisti failo savininką ir grupę
<br><b>chown savininkas-vartotojas:savininkas-grupe katalogas</b> =>Pakeisti katalogo savininką ir grupę

<b>Tinklas</b>

<b>ifconfig –a</b> =>Parodo visus tinklo prievadus ir IP adresą
<br><b>ifconfig eth0</b> =>Parodo konkretų Ethernet portą
<br><b>ethtool eth0</b> =>Linux įrankis parodyti Ethernet statusą
<br><b>ping host</b> =>Siųsti užklausą sujingimo testavimui
<br><b>whois domain</b> =>Gauti informaciją apie domeną
<br><b>dig domain</b> =>Gauti domeno DNS informaciją
<br><b>dig -x host</b> =>Grįžtamasis hostas
<br><b>host google.com</b> =>Ieškoti DNS IP adreso pagal pavadinimą
<br><b>hostname –i</b> =>Vietinio IP adreso apžvalga
<br><b>wget failas</b> =>Parsisiųsti failą
<br><b>netstat -tupl</b> =>Sąrašai aktyvių ryšių į / iš sistemos

<b>Suspaudimas / Archyvavimas</b>

<b>tar cf home.tar home</b> =>Sukurti failo home tar archyvą
<br><b>tar xf file.tar</b> =>Išarchyvuoti failus iš file.tar
<br><b>tar czf file.tar.gz failas</b> =>Sukurti tar archyvą su gzip suspaudimu
<br><b>gzip failas</b> =>Suspausti failą ir pervadinti jį failas.gz

<b>Įdiegimo paketai</b>

<b>rpm -i pkgname.rpm</b> =>Rpm  paketo įdiegimas
<br><b>rpm -e pkgname</b> =>pašalinti paketą

<b>Įdiegti iš šaltinio</b>

./configure 
<br>make 
<br>make install

<b>Paieška</b>

<b>grep pattern failai</b> =>Ieškoti failų
<br><b>grep -r pattern dir</b> =>Ieškoti rekursyviai byloje
<br><b>locate file</b> =>Rasti visus bylos egzempliorius
<br><b>find /home/tom -name ‘index*’</b> =>Rasti failų pavadinimus, kurie prasideda„index“
<br><b>find /home -size +10000k</b> =>Rasti failus didesnius nei 10000K / home

<b>Prisijungimas (ssh ir telnet)</b>

<b>ssh user@host</b> =>Prisijungti prie hosto kaip vartotojas
<br><b>ssh -p port user@host</b> =>Prisijungti prie hosto, naudojant specifinį prievadą
<br><b>telnet host</b> =>Prisijungti prie sistemos naudojant telnet prievadą
