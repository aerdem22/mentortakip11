# 11. Sınıf Müfredat Takibi

AYT seviyesi sorularla 11. sınıf Matematik, Fizik, Kimya ve Biyoloji müfredatı takip uygulaması.

## Özellikler
- 4 ders, ~140 konu, 440+ soru (10/konu havuzu, her seferinde 2 rastgele)
- 2/2 doğru yapmazsan tik gelmiyor
- İlerleme tarayıcıda kalıcı (localStorage)
- API key gerektirmiyor — tüm sorular local

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
  // ... en az 2 soru
];
```

## Proje Yapısı
```
mufredat-takip/
├── index.html      ← Uygulama
├── questions.js    ← Soru veritabanı (440 soru)
├── vercel.json     ← Vercel routing
└── README.md
```
