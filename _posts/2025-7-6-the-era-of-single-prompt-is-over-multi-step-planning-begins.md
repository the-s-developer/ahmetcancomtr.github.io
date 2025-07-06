---
layout: post
title: Tek Promptla Çözme Dönemi Bitti, Multi-Step Planlama Başladı
categories: [AI, LLM, Tool, Planning, Automation, Architecture, AI Tools, Prompt Engineering, Workflow, Agentic AI]
excerpt: Yapay zeka uygulamalarında “tek promptla çözüm” devri kapandı. Artık karmaşık görevler için multi-step planlama, tool chaining ve execution verification mimarileri öne çıkıyor. Bu yazıda, LLM tabanlı sistemlerde planlama ve yürütme modellerini keşfediyoruz.
image: /images/multi-step-planlama.jpeg
---


Yapay zeka tabanlı bilgiye erişim ve arama sistemleri son yıllarda hızla gelişti. Özellikle RAG (Retrieval-Augmented Generation) mimarisinde, vektör tabanlı arama (Vector DB) neredeyse bir “standart çözüm” gibi konumlanmış durumda. Fakat gerçek dünyadaki bilgi ilişkileri düşünüldüğünde, sadece vektör arama ile istenen tutarlılık ve anlamlılık her zaman sağlanamayabiliyor.
İşte bu noktada, bilgiyi “graph” gibi düşünmek ve hibrit arama yaklaşımlarını devreye almak gerekiyor.

---

### Vector DB’ler ve Sınırları

Vector DB’ler, metinleri veya nesneleri “anlamsal” uzayda temsil eder ve benzerliklerine göre arama yapar. Kullanıcı, bir sorgu girdiğinde sistem en yakın vektörleri (yani en alakalı dokümanları) bulur.
Ancak bu yöntem:

* Bilgiler arasındaki **ilişkileri** göz ardı eder.
* Karmaşık bağlantı ve bağlam gerektiren sorgularda yetersiz kalır.
* Sorgunun çok adımlı veya zincirleme ilişkilere dayalı olduğu durumlarda yanlış ya da eksik sonuçlar üretebilir.

---

### Bilgiyi ‘Graph’ Gibi Düşünmek

Gerçek dünyadaki bilgi, genellikle birbiriyle **bağlantılı** ve **ilişkisel** yapıdadır. Örneğin:
Bir şirketin çalışanları, projeleri ve müşterileri arasındaki ilişkiler; bir akademik yayının yazarları, atıfları ve konuları…

Graph veritabanları, bu ilişkileri **düğümler** (entities) ve **kenarlar** (relations) olarak modelleyerek; bilgiyi daha doğal ve tutarlı şekilde sunar.
Sorgular ise “Kim, kiminle, ne şekilde bağlı?” gibi daha derin ve anlamlı sorulara cevap verebilir.

---

### Hybrid Retrieval: En İyisi Hem Vektör, Hem Graph, Hem de SQL

Sadece vektör ya da sadece graph tabanlı arama, çoğu zaman tek başına yeterli olmaz. En güçlü mimarilerde, bu yaklaşımlar **hibrit** biçimde birleştiriliyor:

* **Vector Retrieval:** Anlamsal benzerlik tabanlı hızlı ön filtreleme.
* **Graph Traversal:** Sonuçların ilişkisel bağlamda anlamlandırılması ve derinleştirilmesi.
* **SQL Search:** Yapısal ve kesin kriterler gerektiren sorguların desteklenmesi.

Bu hibrit yapı, örneğin şu şekilde işler:

1. Kullanıcıdan gelen doğal dil sorgusu, önce vektör arama ile ilgili düğüm veya dokümanlara indirgenir.
2. Ardından graph traversal ile, ilgili düğümün bağlantıları ve ilişkileri analiz edilir.
3. Gerekirse, detaylı ve kesin sonuçlar için SQL sorguları çalıştırılır.

---

### Pratik Avantajlar ve Sonuç

* **Daha Tutarlı Sonuçlar:** Bilgiler arası ilişkiler göz önünde bulundurulduğu için, yanıtlar daha anlamlı ve bağlama uygun olur.
* **Ölçeklenebilirlik:** Büyük veri kümelerinde hızlı ön filtreleme ile performans korunur.
* **Zengin Sorgu Yeteneği:** Kullanıcı karmaşık, çok katmanlı sorular sorduğunda dahi tatmin edici sonuçlar sunulabilir.

---

Vector DB’ler RAG için önemli bir araçtır, ancak tek başına her derde deva değildir. Bilgiyi bir graph gibi modellemek ve hibrit retrieval yaklaşımlarını kullanmak, bilgiye erişimde yeni bir standart ve daha sürdürülebilir bir yol sunar.

