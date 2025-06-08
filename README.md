
# 📚 Türkçe Kitap Yorum Analizi ve Değerlendirme Sistemi

Bu proje, **Kitapyurdu** üzerindeki kitap yorumlarını otomatik olarak toplayıp, yorumlar üzerinde **duygu analizi**, **özetleme** ve **pozitif/negatif anahtar kelime çıkarımı** gerçekleştiren bütünleşik bir sistemdir. Sistem, NLP (Doğal Dil İşleme) teknikleri kullanılarak kitaplara dair nitelikli bir değerlendirme yapılmasını sağlar.

---

## 🚀 Özellikler

- 🔎 **Kitap Arama & Yorum Toplama:** Kitapyurdu arayüzü üzerinden kitap araması yapılır, ilgili kitap sayfasına ulaşılarak en fazla 100 kullanıcı yorumu çekilir.
- 🧠 **Duygu Analizi:** Hugging Face’te barındırılan `savasy/bert-base-turkish-sentiment-cased` modeli ile yorumların duygu dağılımları (Pozitif / Negatif / Nötr) belirlenir.
- 📊 **Görselleştirme:** Yorumların duygu dağılımı pasta grafiği ile görsel olarak sunulur.
- 🧵 **Batch Analiz:** Duygu analizleri yorumlar toplu olarak işlenerek daha verimli hale getirilmiştir.
- 💡 **Olumlu & Olumsuz Yön Tespiti:** En sık tekrar eden anlamlı kelimeler çıkarılarak kitabın güçlü ve zayıf yönleri belirlenir.
- 🧠 **Otomatik Özel İsim Filtreleme:** Analize girmemesi gereken özel isimler otomatik olarak tespit edilir.
- 💾 **Veri Kaydı:** Toplanan yorumlar, kullanıcı tarafından girilen kitap adına göre `.json` formatında kaydedilir ve indirilebilir.

---

## 🛠 Kullanılan Teknolojiler

| Kategori           | Teknoloji                      |
|--------------------|--------------------------------|
| Veri Toplama       | `requests`, `BeautifulSoup4`   |
| Duygu Analizi      | `transformers`, `Hugging Face` |
| Görselleştirme     | `matplotlib`, `seaborn`        |
| NLP İşlemleri      | `NLTK`, `re`, `pandas`         |
| Platform           | Google Colab                   |

---

## 📂 Proje Akışı

### 1. Kitap Seçimi ve Yorumların Çekilmesi
- Kullanıcıdan kitap adı alınır.
- Kitapyurdu üzerinde kitap aranır.
- Kitap sayfasındaki en fazla 100 yorum çekilir.
- `yorumlar.json` formatında kaydedilir.

### 2. Duygu Analizi (Batch Destekli)
- JSON dosyasındaki her yorum Türkçe BERT tabanlı modele gönderilir.
- Her yorum için pozitif/negatif/nötr etiketi ve güven skorları hesaplanır.
- Pasta grafiği ile duygu dağılımı görselleştirilir.

### 3. Gelişmiş Yorum Analizi
- Pozitif ve negatif yorumlar ayrı ayrı incelenir.
- Kitap adı, yazar adı ve kullanıcı tanımlı karakter isimleri filtrelenir.
- Her sınıf için en sık geçen anlamlı kelimeler analiz edilir.
- Pozitif ve negatif anahtar kelimeler karşılaştırılır.

---

## 📈 Örnek Çıktılar

- Yorum sayısı: `83`
- Pozitif yorum oranı: `%76.3`
- En sık geçen pozitif kelimeler: `sürükleyici, akıcı, etkileyici, gerçekçi`
- En sık geçen negatif kelimeler: `uzun, sıkıcı, ağır, tekrarlı`

---

## 🧪 Model Detayları

| Özellik        | Açıklama                                                                 |
|----------------|--------------------------------------------------------------------------|
| Model Adı      | `savasy/bert-base-turkish-sentiment-cased`                              |
| Eğitim Verisi  | Türkçe yorumlar içeren çok sınıflı duygu analizi veri setleri            |
| Pipeline Türü  | `sentiment-analysis` (transformers)                                      |
| Desteklenen Etiketler | `Pozitif`, `Negatif`, `Nötr`                                      |

---


## 📥 Kurulum & Çalıştırma

Google Colab üzerinde çalıştırmak için:

1. [Colab Notebook'u Açın](https://colab.research.google.com/drive/1gIWDsgcktMg-R2xIJ144FzyphtpSz6uU?usp=sharing)
2. Tüm hücreleri sırasıyla çalıştırın.
3. Kitap adını girerek sistemi başlatın.

---



- [öneri için bana ulaşın!]
