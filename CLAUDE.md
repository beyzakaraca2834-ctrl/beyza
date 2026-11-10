# CLAUDE.md

Bu klasör (`~/claude`) Claude ile yürütülen projelerin ana çalışma alanıdır. Her alt klasör ayrı bir projedir.

## Genel kurallar

- Kullanıcıyla **Türkçe** konuş; commit mesajları ve kod içi yorumlar da Türkçe olsun.
- Bir projede çalışmadan önce o projenin kendi klasörüne geç ve varsa oradaki `CLAUDE.md` / `.claude/` ayarlarını oku.
- Kullanıcı açıkça istemedikçe bu klasörde yeni proje klasörü oluşturma veya mevcutları silme/taşıma.
- Gizli bilgileri (şifre, token, `.db` dosyaları, `settings.local.json`) asla commit'leme.

## Projeler

### `chatleşme/` — gerçek zamanlı sohbet uygulaması (asıl proje)

- GitHub: `beyzakaraca2834-ctrl/chatlesme` (dal: `main`)
- Uygulama `sohbet/` alt klasöründe:
  - `server.js` — Express + Socket.IO sunucusu; veritabanı için Node'un yerleşik `node:sqlite` modülü (`DatabaseSync`), şifreler `crypto.scrypt` ile.
  - `public/index.html` — tek sayfalık istemci.
  - `sohbet.db` — SQLite veritabanı (git'e girmez).
- Özellikler: kayıt/giriş, odalar, yazıyor göstergesi, kullanıcı arama, özel mesajlaşma (`dm:*` olayları), profil fotoğrafları.
- Gereksinim: Node.js **>= 22.5.0**.
- Çalıştırma (port 3000):
  ```bash
  cd chatleşme/sohbet && npm install && npm start
  ```
  Claude içinden önizleme için `.claude/launch.json` içindeki `sohbet` yapılandırması kullanılır.
- **Otomatik push:** `.claude/settings.json` içindeki Stop hook'u (`.claude/auto-push.sh`) her turun sonunda `main` dalındaki tüm değişiklikleri commit'leyip `origin main`'e gönderir. Bu yüzden yarım kalmış/bozuk değişiklikleri tur sonunda bırakma.

### `chatlesme/` — boş depo

- Sadece `.git` içeren, dosyası olmayan eski/yinelenen klon. Asıl çalışma `chatleşme/` klasöründedir; kullanıcı istemedikçe buraya dokunma.
