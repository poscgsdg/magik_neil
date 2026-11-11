# Magic Nails — сайт студії манікюру

Одна сторінка для студії Magic Nails (Вінниця, просп. Коцюбинського 38).

- `index.html` — сайт (адаптивний, під телефон і компʼютер)
- `content/*.json` — **весь вміст, що змінюється**, по файлу на розділ адмінки: `prices`, `gallery`, `masters`, `reviews`, `contacts`, `hero`, `about`, `services`
- `images/` — лого й фото
- `admin/` — адмінка (Decap CMS) для редагування вмісту без коду; підлаштована під телефон

## Посилання
- Telegram: https://t.me/magic_nails_vin
- Instagram: https://www.instagram.com/magic_nails_vin/
- TikTok: https://www.tiktok.com/@magic.nails.vi

## Адмінка

Сторінка `/admin`. Після входу там окремі розділи: Ціни, Фото робіт, Майстри, Відгуки, Контакти і графік, Головний екран, Про нас, Послуги.
Кнопка «Опублікувати» зберігає зміни прямо в цей репозиторій, і сайт оновлюється сам за хвилину-дві.

### Перевірити на своєму компʼютері (без налаштувань входу)
```
git clone https://github.com/poscgsdg/magik_neil
cd magik_neil
npx decap-server          # у першому терміналі
npx serve .               # у другому терміналі
```
Відкрий адресу, яку покаже `serve` (напр. http://localhost:3000), і додай `/admin`.
Зміни записуються у файли локально — потім їх треба закомітити й запушити.

### Вхід для власниці (через GitHub)
Вхід у Decap через GitHub потребує OAuth. Найпростіше — тримати сайт на Netlify (безкоштовно):
1. netlify.com → увійти через GitHub → **Add new site → Import an existing project** → вибрати `magik_neil` → Deploy (команду збірки залишити порожньою).
2. GitHub → Settings → Developer settings → **OAuth Apps → New OAuth App**:
   - Homepage URL: адреса сайту на Netlify
   - Authorization callback URL: `https://api.netlify.com/auth/done`
3. Netlify → налаштування сайту → **Access & security → OAuth → Install provider → GitHub** → вставити Client ID і Client Secret з кроку 2.
4. У `admin/config.yml` поміняти `site_url` і `display_url` на адресу Netlify.
5. Власниці потрібен безкоштовний акаунт GitHub, і її треба додати в репозиторій: Settings → Collaborators.

## Що ще замінити
- Картки майстрів — фото й імена (зараз заглушки) — тепер це можна зробити в адмінці
