---
layout: post
title: 'Lambda Geçişi'
subtitle: 'Belirsiz Sonlu otomatalarda lambda geçişini yok etmek'
date: 2017-09-30
categories: Otomata
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags: otomata teorisi, lambda geçişini kaldırmak, boş geçişin kaldırılması, belirsiz otomatalarda boş geçiş 
---
# Lambda Geçişi

Bazı NFA'larda alfabenin dışında λ ve ε karakterleri de görülebilir.Bu karakterlerin anlamı boş geçiş demektir. Yani bir karakter olmadan da okun karşısındaki duruma geçebilir. Bu karakterler belirsizlik belirtir ve bunları kaldırmamız gerekmektedir.

![2-1](https://user-images.githubusercontent.com/19302254/31046561-4022a362-a603-11e7-811b-338587e4fb96.jpg)
Bu örnekte, her durumda, alfabenin tüm karakterleri tanımlı olmasına rağmen NFA'dır. Çünkü λ karakteri vardır.  λ karakteri belirsizlik belirtir. λ varsa yok edilmelidir.

## λ'dan Kurtulmak
λ'yı yok etmek için aşağıdaki 3 şartı uygulamamız gerekiyor. 
- λ geçişinin gittiği durumun bütün geçişleri, λ'nın geldiği duruma taşınır.
- Eğer λ final state e gidiyorsa, λ nın geldiği durum final state olur. 
- Eğer λ start stateden geliyorsa, λ'nın gittiği durum start state olur. 
Bu 3 şartı yerine getirirsek artık λ'yı silebiliriz demektir.

*Örnek:*
λ'dan kurtulunuz.
![2-2](https://user-images.githubusercontent.com/19302254/31046560-3f7cedaa-a603-11e7-851c-8be007af6136.jpg)

C'den A'ya olan geçişi B'den A'ya taşıdık.
![2-3](https://user-images.githubusercontent.com/19302254/31046570-685d025a-a603-11e7-8a74-05f71285b865.jpg)

C'den D'ya olan geçişi B'den D'ya taşıdık.
![2-4](https://user-images.githubusercontent.com/19302254/31046558-3f496a0c-a603-11e7-8220-98d1c2e7bd4f.jpg)
Gittiği durum final state mi ? (Hayır)
Geldiği durum start state mi ? (Hayır)

3 şartı da sağladığımıza göre λ'dan kurtulduk. 
