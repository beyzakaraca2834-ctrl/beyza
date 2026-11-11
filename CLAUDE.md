# CLAUDE.md

Bu klasör (`~/claude`) **Claude derslerimin çalışma alanı**. Burada Claude Code'u, git'i ve GitHub'ı öğreniyorum; alt klasörler ders sırasında yaptığım alıştırma projeleri.

## Benimle nasıl çalışmalısın

- **Türkçe** konuş. Commit mesajları ve kod içi yorumlar da Türkçe olsun.
- Ben öğreniyorum: her adımı **sade ve adım adım** anlat. Yeni bir kavram (commit, push, branch, hook…) geçtiğinde bir iki cümleyle ne olduğunu açıkla.
- Bir komut çalıştırdığında **ne işe yaradığını** da söyle; sadece sonucu verme.
- Bir şeyi kendim yaparak öğrenebileceksem (ör. GitHub'da depo açmak), bana yolu göster ve benim yapmamı bekle.
- Emin olmadığın ya da geri alınması zor bir işlemden (silme, `git push --force`, depo ayarlarını değiştirme) önce bana sor.
- Gizli bilgileri (şifre, token, `.db` dosyaları, `settings.local.json`) asla commit'leme.

## Git ve GitHub

- Bu klasör kendi başına bir git deposu (dal: `main`), GitHub'daki `beyzakaraca2834-ctrl/beyza` deposuna bağlı (`origin`). Ders notları ve bu dosya burada takip edilir.
- Kendi git deposu olan alıştırma projeleri `.gitignore` ile bu depodan hariç tutulur; onlar ayrı yedeklenir.
- GitHub kullanıcı adım: `beyzakaraca2834-ctrl`. Bilgisayarda `gh` (GitHub komut satırı aracı) kurulu değil; GitHub'daki işlemleri web sitesinden yapıyorum.

## Alıştırma projeleri

### `chatleşme/` — gerçek zamanlı sohbet uygulaması

- Kendi deposu var: GitHub'da `beyzakaraca2834-ctrl/chatlesme` (dal: `main`).
- Uygulama `sohbet/` klasöründe: Express + Socket.IO sunucusu (`server.js`), Node'un yerleşik `node:sqlite` veritabanı, istemci `public/index.html`.
- Çalıştırmak için (Node.js 22.5 veya üstü, port 3000):
  ```bash
  cd chatleşme/sohbet && npm install && npm start
  ```
- Dikkat: `.claude/auto-push.sh` hook'u her turun sonunda değişiklikleri otomatik commit'leyip GitHub'a gönderir; turu yarım kalmış değişikliklerle bitirme.

### `chatlesme/` — boş klon

- Yalnızca `.git` içeren eski bir kopya. Ben istemedikçe dokunma.
