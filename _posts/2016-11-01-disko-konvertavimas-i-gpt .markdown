---
layout: post
title:  "Disko konvertavimas į GPT"
date:   2016-11-01 17:29:29 +0300
categories: windows
---
Atidarome `Command Prompt` (Win+R, įrašome cmd, spaudžiame Enter)

<br>Vedame komandas paeiliui, po kiekvienos spausdami Enter:

{% highlight ruby %}
diskpart
list disk
select disk # (šioje vietoje vietoj grotelių įrašome savo disko numerį, kurį <br>matysite po  list disk komandos. Dėmesio, būkite atidūs ir pasirinkite tinkamą diską!)
clean
convert gpt
create partition primary
select partition 1
format quick fs=fat32
assign
exit
{% endhighlight %}

Tą patį darome norėdami konvertuoti atgal, tik vietoj gpt įrašome mbr


