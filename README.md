# n8n İzmir Workshop — 16 Mayıs 2026

İzmir'de düzenlenen ilk resmi n8n topluluk etkinliğinin workshop materyalleri.

**Tarih:** 16 Mayıs 2026 Cumartesi, 13:00–17:00
**Yer:** IzQ Flex Etkinlik Salonu, Alsancak / İzmir
**Düzenleyen:** Onur Polat ([n8n Türkiye Ambassador](https://www.linkedin.com/in/onurpolat05))
**Sponsor:** [n8n GmbH](https://n8n.io)
**Kontenjan:** 60 kişi (kayıtlar dolu)

---

## Workshop Konsepti

**Kendi Telegram Bot'unu Kur — Canlı İzmir Verisiyle**

Hiç kod yazmadan, Telegram'da çalışan, İzmir'in canlı hava ve baraj verilerini sorgulayabilen, AI ile özetler üretebilen kendi bot'unuzu kuracaksınız. Workshop sonunda cebinizde gerçekten çalışan bir bot ile çıkacaksınız.

### Komutlar

| Komut | Ne Yapar | Veri Kaynağı |
|-------|----------|--------------|
| `Echo` | Yazdığınız mesajı geri gönderir | — (test için) |
| `/hava` | İzmir'in anlık hava durumu | [Open-Meteo](https://open-meteo.com/) |
| `/özet` | Hava verisini doğal dille özetler | Google Gemini veya OpenRouter |
| `/baraj` | İzmir baraj doluluk oranları | [İzmir Açık Veri (CKAN)](https://acikveri.bizizmir.com/) |

---

## Akış (Genel)

1. 🎯 Açılış + n8n tanıtım + canlı demo
2. 🛠 **Hands-on Bölüm 1** — BotFather + n8n Cloud + Echo bot
3. ☕ Coffee break + atıştırmalıklar
4. 🛠 **Hands-on Bölüm 2** — /hava + /özet (AI) + /baraj
5. 🎤 Konuşmacı: Burak Can Polat
6. 🎤 Konuşmacı: Kadir Zeyrek
7. 🌟 Open-mic — n8n kullananlar kendi akışlarını paylaşır
8. 🎁 Kapanış + sticker + networking

---

## Workshop Öncesi Hazırlık

Workshop'a gelmeden önce şunları yapın:

### 1. n8n Cloud hesabı

[n8n.io](https://n8n.io) adresinden ücretsiz trial hesabı açın (14 gün, kart sormaz).

### 2. LLM API Key (ikisinden biri yeter, ikisi olsa daha iyi)

**Birinci seçenek (en kolay):** [Google AI Studio](https://aistudio.google.com/app/apikey)
- "Get API key" → tek tıkla alınır
- Kart sormaz, ücretsiz

**İkinci seçenek:** [OpenRouter](https://openrouter.ai/keys)
- Kayıt → Keys sekmesinden "Create Key"
- `:free` etiketli modeller (Llama 3.3, Mistral) ücretsizdir

### 3. Telegram

- Telefonunuzda Telegram yüklü ve hesabınız aktif olsun
- BotFather'dan bot oluşturma kısmını workshop'ta birlikte yapacağız

### Yanınızda getirin

- 💻 Laptop (hands-on için, telefonla yapılamaz)
- 🔌 Şarj aleti + adaptör
- 🖱 Mouse (varsa, daha rahat olur)

### Önemli: API Key Güvenliği

Aldığınız API key'leri güvenli bir yere kaydedin (Notlar uygulaması, password manager). **Bu key'leri kimseyle paylaşmayın, GitHub gibi yerlere yüklemeyin.** Workshop'ta n8n içinde gerekli yerlere birlikte yerleştireceğiz.

---

## Repo Yapısı

```
n8n-izmir-workshop-2026/
├── README.md                  # Bu dosya
├── workflows/
│   └── izmir-bot.json         # ANA WORKFLOW — tek JSON, 4 komut
│       (echo + /hava + /özet (Gemini AI) + /baraj)
├── speakers/                  # Konuşmacıların akışları
│   ├── burak-can-polat/
│   └── kadir-zeyrek/
└── cheat-sheet.pdf            # 1 sayfa A4 hızlı referans
```

### Workflow Import (URL ile)

n8n canvas'ta sağ üst `...` menüsü → **Import from URL**:

```
https://raw.githubusercontent.com/onurpolat05/n8n-izmir-workshop-2026/main/workflows/izmir-bot.json
```

Import sonrası yapılacaklar:
1. Telegram credential oluştur: Credentials → New → Telegram API → Bot Token gir
2. Her Telegram node'unda bu credential'ı seç
3. Gemini HTTP Request node'unda `YOUR_GEMINI_API_KEY` → kendi key'in
4. Workflow'u kaydet → Active toggle ON → test et

---

## Konuşmacılar

| Ad | Konu |
|----|------|
| Onur Polat | n8n basics + hands-on Telegram bot |
| Burak Can Polat | Kendi akışı — `speakers/burak-can-polat/` |
| Kadir Zeyrek | Kendi akışı — `speakers/kadir-zeyrek/` |

---

## Workshop Sonrası

- 📝 **Feedback formu:** (workshop sırasında QR ile paylaşılacak)
- 💬 **n8n Topluluk:** [community.n8n.io](https://community.n8n.io)
- 📺 **n8n Resmi Beginner Course:** [YouTube playlist](https://www.youtube.com/playlist?list=PLlET0GsrLUL59YbxstZE71WszP3pVnZfI)
- 📚 **n8n Docs:** [docs.n8n.io](https://docs.n8n.io)

---

## Yardım & İletişim

- LinkedIn: [Onur Polat](https://www.linkedin.com/in/onurpolat05)
- E-posta: onurpolat711@gmail.com
- Workshop'la ilgili sorular için bu repo'da Issue açabilirsiniz

---

## Lisans

MIT — özgürce kullanın, fork edin, paylaşın. Üstüne bir şey kurarsanız bildirmeyi unutmayın 🙂

---

*Bu repo workshop sonrasında da güncellenecek. Tekrar gel, yeni bir şey eklenmiş olabilir.*
