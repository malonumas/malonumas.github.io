---
layout: post
title:  "Git komandos"
date:   2016-10-06 12:04:55 +0300
categories: linux
---

`git init` => sukuria naują Git saugyklą
<br>`git status` => tikrina turinį darbinėje byloje ir konstravimo režime
<br>`git add FailoVardas` => prideda failą iš darbinės bylos į konstravimo režimą
<br>`git diff FailoVardas` => parodo skirtumus darbinės bylos ir konstravimo režimo 
<br>`git commit -m komentaras` => išsaugo pakeitimus į saugyklą su komentaru iš konstravimo režimo
<br>`git log` => parodo sąrašą visų išsaugojimų
<br>`git checkout HEAD FailoVardas` => patikrina HEAD failą
<br>`git reset HEAD FailoVardas` =>   pakeičia neetapinius failo pakeitimus į konstravimo režimą
<br>`git reset SHA` => pakeičia į ankstesnius išsaugojimus
<br>`git branch` => parodo visas atšsakas
<br>`git branch atšakos_vardas` => sukuria atšaka
<br>`git checkout atšakos_vardas` => perjungia iš vienos atšakos į kitą
<br>`git merge atšakos_vardas` => naudoja nukopijuoti pakeitimus iš vienos atšakos į kitą
<br>`git branch -d atšakos_vardas` => ištrina atšaką
<br>`git clone` =>sukuria lokalią kopiją iš nutolusios vietos
<br>`git remote -v` => Nutolusių vietų git projektų sąrašas
<br>`git fetch` => atneša darbą iš nutolusios vietos į lokalią vietą
<br>`git merge origin/master` => nukopijuoja pakeitimus origin/master į tavo lokalios vietos master
<br>`git push origin <atšakos_vardas>` => įdeda atšaką į nutolusią vietą
<br>`git remote add origin https://github.com/your-user-name/your-user-name.github.io.git` => prideda nuotolinį serverį
<br>`git remote rm origin` => pašalina nuotolinį serverį


