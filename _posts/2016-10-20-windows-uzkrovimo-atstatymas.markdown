---
layout: post
title:  "Windows sistemos užkrovimo atstatymas"
date:   2016-10-20 20:49:29 +0300
categories: jekyll update
---
Jeigu sugedo windows operacinės sistemos užkrovimas arba norite pašalinti šalia esančią Linux operacinę sistemą, jums prireiks windows kompaktinio disko. Paleidžiame iš disko tvarkyti windows sistemą, tada spaudžiame `komandinė eilutė` ir suvedame:

{% highlight ruby %}
bootrec /fixboot

bootrec /fixmbr
{% endhighlight %}


