---
layout: post
title: LLM’e Her Şeyi Sormayın Business Logic'i Dışarıda Tutun
categories: [AI, LLM, Business Logic, Tool, Architecture, AI Tools, Backend, Prompt Engineering, Governance, System Design]
excerpt: İş kurallarını LLM’e gömmek kontrolü ve denetlenebilirliği zorlaştırır. LLM, sadece yönlendirici olarak kullanılmalı; iş kuralları ise dış sistemlerde, test edilebilir ve sürdürülebilir şekilde yönetilmeli. Bu yazıda, en iyi pratikleri ele alıyoruz.
image: /images/blog-6.png
---

Büyük dil modelleri (LLM) artık uygulama dünyasında güçlü bir yardımcı. Ancak her güçlü araç gibi, onu yanlış yerde kullanmak ciddi riskler doğurabiliyor. Son dönemin en kritik tartışma başlıklarından biri: **İş kurallarını (business logic) LLM’in içine gömmek mantıklı mı?**

#### Neden LLM’e Her Şeyi Sormamak Gerek?

LLM’lerin doğası gereği, verdiği cevaplar tahmine, eğitime ve bazen de “yaratıcılığa” dayanıyor. Oysa iş kuralları, sistemin temel taşı ve hatasız çalışması gereken noktalar.
Örneğin:

* Siparişin iade edilip edilemeyeceği,
* Kullanıcıya uygulanan indirim oranları,
* Onay ve doğrulama süreçleri gibi konular LLM’in değil, dış sistemlerin işi olmalı.

Eğer bu kurallar LLM’in içine gömülürse:

* **Kontrol kaybedilir:** Kurallar zamanla değişse bile, LLM’in davranışı tahmin edilemez kalır.
* **Denetlenebilirlik azalır:** Sonuçlar test edilemez ve geriye dönük incelenemez.
* **Uyumluluk sorunları çıkar:** Regülasyon ve şirket politikalarına uygunluğu zor takip edilir.

---

### Doğru Yaklaşım: LLM’i Yönlendirici Olarak Kullanmak

En verimli ve güvenli çözüm, LLM’i sadece “akıllı yönlendirici” gibi kullanmak. Yani iş kuralına dair kararları almak yerine, bu kararı dış bir sistem ya da tool’a devretmek.
Örneğin:
Bir siparişin iade edilebilir olup olmadığını LLM’e sormak yerine, LLM’in `check_ruleset(order)` gibi bir tool’u tetiklemesi gerekir. LLM, burada sadece doğru bilgiyi doğru yere yönlendiren bir köprü olur.

#### Avantajları:

* **İş kuralları merkezi olarak, kod veya servislerde yönetilir.**
* **LLM güncellense bile kural motorları aynı kalır.**
* **Test, denetim ve uyumluluk süreçleri kolaylaşır.**

---

### Özet

LLM’lerin sınırlarını iyi belirlemek, sistemin güvenilirliğini ve sürdürülebilirliğini artırır.
**LLM’e her şeyi sormayın. Özellikle iş kurallarınızı LLM’in içine gömmek yerine dışarıda, kontrol edebileceğiniz sistemlerde tutun!**

