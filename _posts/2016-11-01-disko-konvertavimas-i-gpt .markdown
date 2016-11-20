---
layout: post
title:  "Disko konvertavimas į GPT"
date:   2016-11-01 17:29:29 +0300
categories: windows
---
GPT (GUID Partition Table) tai atnaujinta kieto disko arba SSD disko particijų lentelė kuri pakeičia senają MBR (Master Boot Record) naudojama dar nuo 1983-iųjų.

<br>UEFI/GPT pranašumai lyginant su MBR:

<br>GPT diskai panaikina 2,2TB diskų talpos limitą, kurį turėjo MBR.
<br>MBR yra apribota iki keturių particijų lentelių.
<br>GPT pasirūpina geresniu duomenų struktūros integralumu, duomenų atsatymas juose lengvesnis.
<br>UEFI boot’as yra labiau saugus, t.y. gerokai sunkiau pažeidžiamas kenkėjiškų programų.
<br>UEFI boot’as ir sugrįžimas iš miego režimo yra gerokai greitesnis, nei tos pačios sistemos, naudojančios MBR.
<br>UEFI yra didžiausių IT korporacijų, tokių, kaip AMD, Apple, Dell, HP, IBM, Insyde Software, Intel, Lenovo, Microsoft vystomas ateities standartas. UEFI – tai kompiuterių ateitis ir ateityje bus naudojama visuose kompiuteriuose, bei daug daugiau, nei tik jų krovimo metu.

<br>Windows operacinėje sistemoje atidarome `Command Prompt` (Win+R, įrašome cmd, spaudžiame Enter). 
Vedame komandas paeiliui, po kiekvienos spausdami Enter:


<b>diskpart</b>
<br><b>list disk
<br>select disk</b> #(šioje vietoje vietoj grotelių įrašome savo disko numerį, kurį matysite po  list disk komandos. Dėmesio, būkite atidūs ir pasirinkite tinkamą diską!)
<br><b>clean
<br>convert gpt
<br>create partition primary
<br>select partition 1
<br>format quick fs=fat32
<br>assign
<br>exit</b>


Tą patį darome norėdami konvertuoti atgal, tik vietoj gpt įrašome mbr.


