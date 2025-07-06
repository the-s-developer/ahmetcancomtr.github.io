---
layout: post
title: Don’t Just Write Code with LLMs—Let Them Manage the Code Generation Process
categories: [AI, LLM, RAG, Tool, Architecture, Agentic AI,  Python, NLP , AI Tools, Backend, Prompt Engineering]
image: /images/blog-1.jpeg
---

# LLM ile Kod Yazmayın, Kod Oluşturmayı Yönetmesini Sağlayın

Yapay zekâ destekli kodlama dünyasında en çok duyduğumuz cümlelerden biri şu:
**“LLM (Large Language Model) ile kod yazmak harika!”**
Evet, GitHub Copilot, ChatGPT ve benzeri araçlar sayesinde çok hızlı kod üretebiliyoruz. Fakat gerçekten en verimli yaklaşım bu mu?

Bu yazıda, LLM’leri doğrudan kod yazmak için kullanmak yerine, kod oluşturma sürecini yönetmek için nasıl konumlandırabileceğimizi tartışacağız. Yani; kodun nasıl üretileceği, test edileceği, analiz edileceği ve PR’ın (Pull Request) nasıl açılacağı gibi süreçlerin koordinasyonunu LLM’e bırakmak.

## Kod Üretmekten Fazlası: Süreci LLM’e Yönettirmek

Çoğu geliştirici, LLM’den bir fonksiyon veya sınıf isteyip çıkan kodu alıp doğrudan kullanıyor. Ancak yazılım geliştirme süreci yalnızca kod üretmekten ibaret değil. Aşağıdaki adımlar çoğu zaman daha da kritik:

* Kodun doğru ve güvenli olması
* Testlerinin yazılması ve çalıştırılması
* Statik analizden geçmesi (lint, type check, vs.)
* Takımda tartışılması ve kodun gözden geçirilmesi (PR)

Burada LLM’i sadece kod üreten bir “otomatik yazıcı” gibi değil, yazılım üretim sürecini yöneten bir *orkestra şefi* gibi düşünmek mümkün.

## Pratikte Nasıl Çalışır? Bir Senaryo

Diyelim ki yeni bir API endpoint’i eklemek istiyorsunuz. Klasik yöntemle ChatGPT’ye “Bir Node.js endpoint’i yazar mısın?” diye soruyorsunuz ve cevapta direkt kodu kopyalıyorsunuz.

Ama modern LLM entegrasyonlarında süreç şöyle ilerleyebilir:

1. **Komut Veriliyor:**
   “/yeni-endpoint oluştur” gibi bir komut LLM’e iletiliyor.

2. **Kod Üretimi:**
   LLM, istenen endpoint’in kodunu oluşturuyor. Ama hemen burada durmuyor!

3. **Test Üretimi ve Çalıştırma:**
   Kodun testlerini de otomatik olarak oluşturuyor, local test runner veya CI/CD pipeline üzerinden test ediyor.

4. **Analiz ve Lint:**
   Kodun statik analizden (ör. ESLint, SonarQube) geçip geçmediğini kontrol ediyor. Sorun varsa revize ediyor.

5. **Pull Request Oluşturma:**
   Kod hazır ve testlerden geçtiyse, doğrudan bir PR açıyor. İsterseniz açıklama ve değişiklik özetini de kendisi yazıyor.

Her adımda LLM bir tool çağrısı (API ya da lokal script) kullanıyor. Yani LLM’in rolü, bütün süreci *koordine etmek* ve her adımı otomatikleştirmek. Kodun herhangi bir aşamasında problem çıkarsa, LLM o adımı tekrar edebiliyor veya kullanıcıya bilgilendirme yapıyor.

## Neden Bu Yaklaşım Daha Mantıklı?

* **Güvenlik:** Sadece kodun değil, test ve analiz adımlarının da otomasyonu hataları ve açıkları azaltır.
* **Verimlilik:** İnsan-makine iş bölümü netleşir; LLM süreci yönetir, geliştirici yüksek seviyede karar verir.
* **Standardizasyon:** Her adım LLM üzerinden geçtiği için kodun kalitesi ve stilinde tutarlılık artar.
* **Takım İşbirliği:** Otomatik PR ve açıklama süreçleri, takım içi iletişimi kolaylaştırır.

## Sonuç: LLM’i Geliştiricinin Asistanı Olarak Yeniden Konumlandırmak

Kod yazdırmak kolay, ama sürdürülebilir yazılım geliştirmek zordur. LLM’i kodun tek başına üreticisi olarak değil, kodun *oluşturulma sürecini yöneten* bir asistan olarak görmek, uzun vadede daha güvenli, kaliteli ve işbirliğine açık projeler ortaya çıkarır.

**Kodun kendisini yazdırmak yerine, kodu nasıl üreteceğini LLM’e bırakın.**
