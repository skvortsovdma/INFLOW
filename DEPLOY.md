# inFlow — выпуск сайта (inflow.website)

Статический сайт (один `index.html` + `/media` + SEO-файлы). Ничего собирать не нужно.

## Деплой на Vercel (рекомендую)
1. Залить папку `agency-site/` в git-репозиторий (или `vercel` CLI из этой папки).
2. В Vercel: New Project → импортировать репо → **Framework Preset: Other** → Root = папка сайта → Deploy.
3. `vercel.json` уже задаёт immutable-кэш на медиа + security-заголовки. Brotli Vercel включает сам.
4. Домен: Settings → Domains → добавить **inflow.website** (у регистратора прописать A/CNAME по инструкции Vercel).

Альтернатива — Netlify/Cloudflare Pages: просто drag-and-drop папки, включить Brotli, кэш на `/media/*` = 1 год immutable.

## Обязательно перед прод-пуском
- [ ] WhatsApp-номер **+380635503585** — проверен (стоит в nav, финале, мобильном FAB; текст меняется EN/RU). Заменить, если номер другой.
- [ ] Демо-ссылка в блоке «why» ведёт на `sightline-liard.vercel.app` (лейбл yourhome.com). Заменить на боевое демо, когда будет.
- [ ] Почта `hello@inflow.website` — завести ящик/алиас.
- [ ] Подписи 4 проектов в card-stack (NORDX = бывш. Leaders&Founders — подтвердить).
- [ ] `model-viewer` тянется с CDN unpkg — работает; для полного офлайна можно положить локально (~300 КБ).

## Сразу после деплоя (SEO)
- [ ] Google Search Console: подтвердить `inflow.website`, сабмитнуть `sitemap.xml`.
- [ ] Rich Results Test — проверить JSON-LD.
- [ ] PageSpeed Insights (mobile) — ожидаемо 90+.
- [ ] Проверить OG-превью (opengraph.xyz) — картинка `og.png`.
- Полный SEO-план: `../_core/SEO-SUPERPROMPT.md`.

## Структура
```
agency-site/
  index.html          ← весь сайт (inline CSS+JS)
  favicon.svg  og.png  apple-touch-icon.png  icon-512.png
  robots.txt  sitemap.xml  site.webmanifest  vercel.json
  media/web/   web1–4.mp4 + .webp   (горизонтальные сайты-showreel)
  media/ai/    ai1–6.mp4 + .webp    (вертикальные ИИ-ролики)
  media/renders/ r1–6.webp          (рендеры / путь покупателя)
  media/models/  tower.glb          (3D-башня)
```

## Секции
hero (lamp) → why (PDF vs ссылка) → how (путь покупателя) → work (сайты) → films (ИИ-видео) → threed (3D) → renders (рендеры) → demo (цена + CTA).
