---
layout: post
title: Tek Promptla Çözme Dönemi Bitti, Multi-Step Planlama Başladı
categories: [AI, LLM, Tool, Planning, Automation, Architecture, AI Tools, Prompt Engineering, Workflow, Agentic AI]
excerpt: Yapay zeka uygulamalarında “tek promptla çözüm” devri kapandı. Artık karmaşık görevler için multi-step planlama, tool chaining ve execution verification mimarileri öne çıkıyor. Bu yazıda, LLM tabanlı sistemlerde planlama ve yürütme modellerini keşfediyoruz.
image: /images/blog-5.png
---

Büyük dil modelleri (LLM) ilk dönemlerinde çoğunlukla "tek prompt, tek çözüm" mantığıyla çalışıyordu. Kullanıcı bir istek veya soru giriyor, LLM de bunu elindeki bilgiyle çözmeye çalışıyordu. Ancak gerçek dünya problemleri ve yazılım görevleri genellikle tek adımda çözülmeyecek kadar karmaşık. Artık yeni nesil LLM uygulamaları, **planlama ve çok adımlı execution (çok adımlı yürütme)** kavramlarını merkeze alıyor.

---

### Neden Tek Prompt Yeterli Değil?

Tek adımda çözüm aramak, çoğunlukla yüzeysel veya eksik sonuçlara yol açıyor. Özellikle:

* **Birden fazla API’ye erişim**
* **Bağımlı adımların zincirleme yürütülmesi**
* **Doğrulama ve hata yönetimi**
* **Karmaşık karar verme süreçleri**

gibi durumlarda, çok adımlı ve akıllı bir planlama/uygulama akışı gerekiyor.

---

### Multi-Step Planlama Modeli Nasıl Çalışır?

#### 1. **Planner (Planlayıcı)**

LLM’e gelen görevin en iyi şekilde tamamlanması için bir dizi adım (plan) oluşturulur.
Örnek: “Bir haber kaynağından veri çek, temizle, özetle ve e-posta ile gönder” gibi.

#### 2. **Tool Call Chain (Araç Çağrı Zinciri)**

Oluşturulan plan, ilgili araçlara (API, kod, veri kaynağı, fonksiyon) uygun sırayla gönderilir. Her adım, bir öncekinin çıktısını kullanarak ilerler.

#### 3. **Execution Verifier (Yürütme Doğrulayıcı)**

Her adım tamamlandıkça, çıktıların doğruluğu ve bütünlüğü kontrol edilir. Gerekirse plan revize edilir veya hata yönetimi yapılır.

---

### Avantajları Neler?

* **Daha güvenilir ve sürdürülebilir sonuçlar**
* **Hata yönetimi ve doğrulama kolaylığı**
* **Karmaşık iş akışlarını otomatik olarak optimize etme**
* **Her adımda gözlemlenebilirlik ve geriye dönük inceleme imkanı**

---


Yapay zekâ ve otomasyon dünyasında “tek promptla çözüm” devri kapanıyor. Yerine, planlamadan yürütmeye, her adımın kontrollü ve doğrulanabilir şekilde işlendiği çok adımlı mimariler geliyor. Multi-step planlama ve execution modelleriyle, LLM tabanlı sistemlerde hem kalite hem de güvenilirlik yeni bir seviyeye taşınıyor.

