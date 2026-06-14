# 11. Sınıf Müfredat Takibi

AYT seviyesi sorularla 11. sınıf Matematik, Fizik, Kimya ve Biyoloji müfredatı takip uygulaması.

## Özellikler
- 4 ders, ~170 konu, soru havuzu konuya göre 4-10 arası (her seferinde 3 rastgele soru)
- 3/3 doğru yapmazsan tik gelmiyor
- İlerleme tarayıcıda kalıcı (localStorage)
- API key gerektirmiyor — tüm sorular local
- 📅 15 Günlük Program: günlere göre konu planı, çalışma notu (kaynak/test/D-Y-B) ve genel özet
- ⏱ Ders bazlı kronometre + manuel süre ekleme, genel özette toplam çalışma süresi

## Deploy (Vercel)

```bash
# 1. Bu klasörü GitHub'a push et
git init
git add .
git commit -m "ilk commit"
git remote add origin https://github.com/KULLANICI/mufredat-takip.git
git push -u origin main

# 2. vercel.com → New Project → GitHub repo seç → Deploy
```

Vercel otomatik algılar, build adımı yok. 30 saniyede canlı.

## Yeni Soru Eklemek

`questions.js` dosyasını aç, şu formata uygun ekle:

```js
QUESTIONS["ders::Unite::Konu Adı"] = [
  {
    "soru": "Soru metni?",
    "siklar": {"A": "...", "B": "...", "C": "...", "D": "..."},
    "dogru": "A",
    "aciklama": "Kısa açıklama."
  },
  // ... en az 3, tercihen 4 soru
];
```

Yeni eklenen konularda 4 soru havuzu yeterlidir (her testte 3'ü rastgele gelir).

## Proje Yapısı
```
mufredat-takip/
├── index.html      ← Uygulama
├── questions.js    ← Soru veritabanı (440 soru)
├── vercel.json     ← Vercel routing
└── README.md
```
