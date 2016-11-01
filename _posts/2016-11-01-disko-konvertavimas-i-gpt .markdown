---
layout: post
title:  "Disko konvertavimas į GPT"
date:   2016-11-01 17:29:29 +0300
categories: windows
---
Atidarome `Command Prompt` (Win+R, įrašome cmd, spaudžiame Enter)
<br>Vedame komandas paeiliui, po kiekvienos spausdami Enter:


diskpart
<br>list disk
<br>select disk #(šioje vietoje vietoj grotelių įrašome savo disko numerį, kurį matysite po  list disk komandos. Dėmesio, būkite atidūs ir pasirinkite tinkamą diską!)
<br>clean
<br>convert gpt
<br>create partition primary
<br>select partition 1
<br>format quick fs=fat32
<br>assign
<br>exit


Tą patį darome norėdami konvertuoti atgal, tik vietoj gpt įrašome mbr.


