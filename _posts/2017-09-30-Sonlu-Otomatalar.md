---
layout: post
title: 'Sonlu Otomatalar'
date: 2017-09-30
author: Alperen Bozkurt
cover: 'https://user-images.githubusercontent.com/19302254/31045809-740ec336-a5f4-11e7-8b91-ab4ebf2eb42d.jpg'
tags: Otomata Teorisi, Sonlu Otomatalar, Belirli sonlu otomatalar, Belirsiz sonlu otomatalar,  
---

# Biçimsel Diller ve Otomata Teorisi
Biçimsel diller
---
Dilde bulunan bütün öğeler ve dilin ulaşabileceği sınırlar belirli kurallar dahilinde tanımlanıyorsa bu dillere **formal** ( **muntazam**, **biçimsel** ) dil denir. Programlama dilleri birer biçimsel dildir. 

## Sonlu otomatalar


### Belirli Sonlu Otomatalar (Deterministic Finite Automata - DFA)


![1](https://user-images.githubusercontent.com/19302254/31045809-740ec336-a5f4-11e7-8b91-ab4ebf2eb42d.jpg)

|  |  |  |  |  | 
|-----|-----|-----|----|
| **Q** |**Durum Kümesi**|{q1, q2, q3}|  |
| **Σ** | **Alfabe** | { v0,1 } | Okların üzerilerindekilere alfabe denir. |
| **q0** | **Başlangıç Durumu** | { q1 } | En az bir tane başlangıç durumu olmalıdır.|
| **F** | **Bitiş Durumu** | { q3 }| En az bir tane bitiş durumu olmalıdır. |
| **δ** | **Geçişler** | δ(q1,0) = q1 | q1'e 0 geldiğinde q1'e gitmiş |
|||δ(q1,1) = q2||
|||δ(q2,0) = q1||
|||δ(q2,1) = q3||
|||δ(q3,0) = q3||
|||δ(q3,1) = q3||

Yukarıdaki moore diyagramı Belirli sonlu otomatadır(Deterministic Finite Automata - DFA ). DFA nın 5 temel gerekliliği vardır. Bunlar : Durum Kümesi, Alfabe, Başlangıç Durumu, Bitiş Durumu ve Geçişlerdir.

Bir DFA'nın alfabesi ile oluşturulabilecek kümelere kelime denir. Eğer bir kelime start state den final state'e kadar gidebiliyorsa bu kelimeye **"DFA'nın tanıdığı bir kelimedir"** denilir. 
*Örnek*:  110, 111, 111111, 110111110

Bir otomatanın belirli olması için şu şartları sağlaması gerekir:
- Start state olmalı.
- Final state olmalı.
- Her durumda, Alfabenin tamamıyla geçiş olmalı. (Alfabe 1,0 dan oluşuyorsa her durumda 1 ve 0 geçişleri olmalıdır. )
- Bir durumda aynı karakterle birden fazla geçiş olmamalıdır.

Eğer bir otomata bu şartları sağlamıyorsa bu otomataya **Belirsiz Sonlu Otomata** (Non-Deterministic Finite Automata  - NFA ) denir. 

### Belirsiz Sonlu Automatalar (Non-Deterministic Automata - DFA)

Bir problemi NFA'da çözmek DFA'da çözmekten daha  kolaydır. Bu yüzden problemleri önce NFA'da çözüp DFA'ya geçiririz.


![2](https://user-images.githubusercontent.com/19302254/31045808-72f62214-a5f4-11e7-83cf-ab43c68c51b1.jpg)

Bu örnekte Tüm durumlarda alfabenin tüm harfleri geçiş yapmadığı için NFA'dır. (q1 durumunda 1 gelirse belirsizlik oluşur.) 

*Örnek : *
![3](https://user-images.githubusercontent.com/19302254/31045807-72134c1e-a5f4-11e7-9c0f-9e2e5b217e2b.jpg)

**abbbaaaa** => Bir kelimesidir. Çünkü start state den başladığında final state'de bitiyor.
**cacccabb** => Bir kelimesi değildir. Çünkü Start State den başladığımızda E durumunda bitiyor. E durumu bir Final State değildir.

*Örnek :* 
![4](https://user-images.githubusercontent.com/19302254/31045811-76d8b07c-a5f4-11e7-97bf-22cb5a99164a.jpg)

Her durumda alfabenin tamamı tanımlı bu yüzden bu otomata bir DFA'dır.



