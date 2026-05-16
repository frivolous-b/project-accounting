# Експерт. — Счетоводна кантора (Landing Page)

Production-ready single-file landing page за лицензирана счетоводна кантора в Пловдив. Без build, без dependencies, готова за drag-and-drop в Netlify.

## 🚀 Quick deploy

1. Drag `index.html` в [Netlify Drop](https://app.netlify.com/drop)
2. Готово — сайтът е online на временен `*.netlify.app` домейн
3. (По желание) Netlify → Domain settings → свържи собствен домейн

## ✏️ Клиентска редакция (без код)

Собственикът на кантората може да редактира текст, цветове и снимки през браузъра:

1. Отвори `https://<домейн>/?edit=1`
2. Първи login: парола `qwe@123` (получена от разработчика)
3. Системата изисква да зададе лична парола (мин. 8 знака)
4. **Кликни** върху текст → редактирай директно
5. **Десен клик** върху линк → смени URL (Calendly, Facebook, Google Maps, и т.н.)
6. **Кликни** върху снимка → качи нова
7. **„🎨 Цветове"** → 8 променливи на палитрата
8. **„💾 Изтегли сайта"** → нов `index.html` файл
9. Замени файла в Netlify (drag-and-drop отново)

**Master парола за recovery:** известна само на разработчика.

## 🔐 Security (Edit Mode)

- SHA-256 password hashing (Web Crypto API)
- Паролата се пази в `localStorage` (per-browser, не в HTML)
- Rate limit: 3 неуспешни опита → 5 мин блокиране
- Time-based access: пон–пет, 08:00–22:00 (Europe/Sofia)
- Auto-logout: 30 мин неактивност
- Audit log: до 50 събития, видим от бутона „📋 Log"
- Device fingerprint warning при ново устройство

## 📋 Преди публикация — заменете placeholder-ите

| Какво | Къде | Брой |
|---|---|---|
| Calendly URL | `data-edit-href="booking-link"` (или right-click) | 1 |
| Formspree ID | търси `YOUR_FORMSPREE_ID` | 1 |
| Google Reviews URLs | `g.page/r/EXAMPLE_*` | 4 |
| Facebook URL | footer + pre-footer band | 2 |
| Google Maps URL | footer social column + contact | 2 |
| Домейн в JSON-LD | `https://www.example.bg` | ~5 |
| Geo координати | `42.1354, 24.7453` → точни на офиса | 1 |
| Master парола | в JS, само ако ще се променя за този клиент | 1 |

## 🛠 Stack

- Single HTML файл, vanilla CSS + vanilla JS
- Fonts: Fraunces + Inter (Google Fonts, preconnect)
- No build, no node_modules, no dependencies
- ~163 KB общо (gzipped: ~30 KB)
- Mobile-first responsive
- WCAG-friendly: 56 SVG-та с aria-hidden, skip-link, focus-visible outlines

## 📦 SEO / Structured Data

Вградени 3 JSON-LD блока:
- `AccountingService` (организация + локация)
- `LocalBusiness` (с geo координати, opening hours, aggregate rating)
- `FAQPage` (6 въпроса)

Плюс Open Graph + Twitter Card meta tags.

## 📁 Файлове в репото

| Файл | Какво е |
|---|---|
| `index.html` | landing page (v3.2) |
| `robots.txt` | crawler instructions |
| `README.md` | този файл |
| `V3.2-TESTING-NOTES.md` | test plan за edit mode + всички features |
| `.gitignore` | стандартни патърни |

## 🔄 Restore при проблем

В Netlify: Deploys → предишен deploy → „Publish deploy" → instant rollback.
Локални backups: `AccountingLandingPage_v3.html` / `v3.1.html` / `v3.2.html` в `~/Downloads`.

## 🤝 Поддръжка

**webnova.bg** — разработка и техническа поддръжка.
