# REAPER BANK — Control Your Digital Wealth

Siyah-beyaz, premium bir dijital banka ve kripto cüzdan **DEMO arayüzüdür**. Tek dosya (`index.html`), build gerektirmez.

> ⚠️ Gerçek banka, blokzincir, kart veya OAuth bağlantısı yoktur. Bakiyeler, işlemler ve grafik geçmişi simülasyondur. Yatırım tavsiyesi değildir. REAPER BANK lisanslı bir finans kuruluşu değildir.

## 1. Amaç
Fintech arayüzü ve etkileşim prototipi.

## 2. Özellikler
Dashboard, gizlenebilir bakiye, zaman aralıklı portföy grafiği, donut dağılım, Buy/Sell/Swap/Send/Receive/Add Funds (bakiye kontrollü), piyasa listesi (arama, sıralama, favori, detay), işlem filtreleri ve **CSV dışa aktarma**, analitik (K/Z, haftalık/aylık hacim), demo kartlar (gizle/dondur), bildirimler, ayarlar, **canlı fiyat modu**, responsive tasarım.

## 3. Teknoloji
Saf HTML, CSS, JavaScript ve SVG. Harici kütüphane yok.

## 4. Gereksinimler
Modern bir tarayıcı. (Canlı mod için internet.)

## 5. Yerelde çalıştırma
`index.html` dosyasını çift tıklayıp açın. İsterseniz: `npx serve .`

## 6. GitHub'a yükleme
1. github.com'da yeni bir depo oluşturun (ör. `reaper-bank`).
2. `index.html`, `netlify.toml`, `favicon.svg`, `reaper-logo.svg`, `README.md`, `.gitignore`, `.env.example` dosyalarını depo köküne yükleyin.
3. **GitHub Pages:** Settings → Pages → Branch: `main`, klasör `/ (root)` → Save. Adres: `https://KULLANICI.github.io/reaper-bank/`

## 7. Netlify'a dağıtım
- **Sürükle-bırak:** app.netlify.com/drop — dosyaları içeren **klasörü** bırakın.
- **GitHub bağlantısı:** Add new site → Import from Git → depoyu seçin. Build command **boş**, Publish directory **`.`** (`netlify.toml` bunu ayarlar).

## 8. Gerçek OAuth kurulumu (Supabase Auth)
Giriş; e-posta/şifre, Google ve GitHub ile **Supabase Auth** üzerinden gerçek kimlik doğrulama yapar. Uygulama şifre saklamaz.
1. supabase.com'da proje oluşturun. Project Settings → API'den **Project URL** ve **anon public key** değerlerini alın. (`service_role` anahtarını ASLA kullanmayın.)
2. `config.js` dosyasına bu iki değeri yazın.
3. **Google:** Google Cloud Console → APIs & Services → Credentials → OAuth client ID (Web). Authorized redirect URI: `https://PROJE_ID.supabase.co/auth/v1/callback`. Client ID/Secret'ı Supabase → Authentication → Providers → Google'a girin.
4. **GitHub:** GitHub → Settings → Developer settings → OAuth Apps → New. Callback URL aynı Supabase adresi. Client ID/Secret'ı Supabase → Providers → GitHub'a girin.
5. Supabase → Authentication → URL Configuration: **Site URL** = yayın adresiniz (Netlify/GitHub Pages), **Redirect URLs**'e aynı adresi ekleyin.
6. Bu frontend için başka ortam değişkeni gerekmez.

## 9. Canlı API
Markets sayfasında "Canlı fiyatı aç" → CoinGecko herkese açık API'sinden fiyat ve 24s değişim çekilir (anahtar yok, istek sınırı olabilir). Başarısız olursa hata gösterilir ve demo moda dönülür. Mini grafikler ve geçmiş serileri her zaman simülasyondur.

## 10. Demo sınırları
Giriş gerçektir ancak yalnızca kimlik doğrulamadır; bakiyeler, işlemler ve cüzdan verileri simülasyondur. Adresler ve QR örnektir, kart gerçek değildir. Gerçek ürün için lisanslı sağlayıcılar, güvenli backend, yetkilendirme, denetim kayıtları ve KYC/AML uyumu gerekir.
