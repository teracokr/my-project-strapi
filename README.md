# ๐ ๋ด ๋งฅ๋ถ์ Strapi + SMTP + CDN ์ค์นํ๊ธฐ

์ด Repository๋ ["์ฝ๋ฉ์์ด ๋ฐฑ์๋ API ์๋ฒ ๊ตฌ์ถํ๊ธฐ (Strapi + Heroku)"](https://tera.co.kr/course/%EC%BD%94%EB%94%A9%EC%97%86%EC%9D%B4-%EB%B0%B1%EC%97%94%EB%93%9C-api-%EC%84%9C%EB%B2%84-%EA%B5%AC%EC%B6%95%ED%95%98%EA%B8%B0/) ๊ณผ์  ์ค ๋ด ๋งฅ๋ถ์ ๋ก์ปฌ ๊ฐ๋ฐํ๊ฒฝ ๊ตฌ์ถ์ ์ํ ์์ค์๋๋ค.

Heroku์ ๋ฐฐํฌํ์ฌ ์ฌ์ฉํ๋ ค๋ฉด ์ถ๊ฐ๋ก ๋ช๊ฐ์ง ์์์ด ๋ ํ์ํ๋ฉฐ ์ ๊ฐ์์ "์ด์ ํ๊ฒฝ ๊ตฌ์ฑ(Heroku์ ๋ฐฐํฌ)
" ์น์์ ์ฐธ๊ณ ํ์ธ์.

# ์์ค ์ฌ์ฉ๋ฐฉ๋ฒ

## ๋์ถฉ ๋น ๋ฅด๊ฒ ์์ํ๋ ๋ฒ
- .env.example ํ์ผ์ ๋ณต์ฌํ์ฌ .env ๋ก ์ ์ฅํฉ๋๋ค.
- yarn ์ ์คํํ์ฌ ๋ธ๋ ๋ชจ๋์ ์ค์นํฉ๋๋ค.
- yarn develop ๋ฅผ ์คํํ๋ฉด ๋
---
## ์ ๋๋ก ์์ํ๊ธฐ
ํ๋ก ํธ์๋ ์ธ์ฆ ๊ฐ๋ฐ์ ์ด๋ฉ์ผ ์ธ์ฆ ๋ฐ ๋น๋ฐ๋ฒํธ ์ฐพ๊ธฐ ๊ธฐ๋ฅ ๊ตฌํ์ ์ํด์๋ SendGrid์ ๊ฐ์ํด์ .env ํ์ผ์ ์ค์ ๊ฐ์ ๋ฃ์ด์ผ ํ๊ณ  Heroku์ ๋ฐฐํฌํด๋ณด๊ธฐ๋ฅผ ์ํ๋ ๋ถ๋ค์ ์ด๋ฏธ์ง ํ์ผ ์ ์ฅ์ ์ํ ๋ฌด๋ฃ CDN์ธ Cloudinary์ ๊ฐ์ํด์ ์ ๋ณด๋ฅผ .envํ์ผ์ ๋ฃ์ผ๋ฉด ๋ฉ๋๋ค.
### ๋ฌด๋ฃ SMTP ์๋น์ค์ธ [SendGrid](https://sendgrid.com)์ ๊ฐ์
์ ์ฌ์ดํธ์ ๊ฐ์ํ์ฌ API-KEY๋ฅผ ๋ฐ๊ธ๋ฐ์ .envํ์ผ์ ๊ตฌ์ฑํ์ธ์. ๊ฐ์์ ๋ํ ์์ธํ ๋ด์ฉ์ ๊ฐ์๋ฅผ ์ฐธ๊ณ ํ์ธ์.
์ด๋ฏธ ๊ณ์ ์ด ์๋ ๋ถ์ .env.example ํ์ผ์ ์์ ํ์ฌ .env๋ก ์ ์ฅํ์ฌ ์ฌ์ฉํ๋ฉด๋ฉ๋๋ค.
```
# .env.example ํ์ผ ์์ ํ  ๋ถ๋ถ 
SENDGRID_API_KEY={Your SendGrid API_KEY}
SENDGRID_FROM_EMAIL={Your SendGrid Sender Email}
SENDGRID_REPLYTO_EMAIL={Your SendGrid Sender Email}
SENDGRID_TEST_EMAIL={Your any Email}
```

### ๋ฌด๋ฃ ์ด๋ฏธ์ง ์ ์ฅ ์๋น์ค์ธ [Cloudinary](https://cloudinary.com)์ ๊ฐ์
์ ์ฌ์ดํธ์ ๊ฐ์ํ์ฌ API-KEY๋ฅผ ๋ฐ๊ธ๋ฐ์ .envํ์ผ์ ๊ตฌ์ฑํ์ธ์. ๊ฐ์์ ๋ํ ์์ธํ ๋ด์ฉ์ ๊ฐ์๋ฅผ ์ฐธ๊ณ ํ์ธ์.
์ด๋ฏธ ๊ณ์ ์ด ์๋ ๋ถ์ .env.example ํ์ผ์ ์์ ํ์ฌ .env๋ก ์ ์ฅํ์ฌ ์ฌ์ฉํ๋ฉด๋ฉ๋๋ค.

```
# .env.example ํ์ผ ์์ ํ  ๋ถ๋ถ 
CLOUDINARY_NAME={Your CLOUDINARY_NAME}
CLOUDINARY_KEY={Your CLOUDINARY_KEY}
CLOUDINARY_SECRET={Your CLOUDINARY_SECRET}
```

### .env ํ์ผ ์์ฑ

์๋ Random String ํญ๋ชฉ์ ์ ๋ง ๋๋ค์ผ๋ก ๋์ถฉ ์๋ ฅํ๊ณ 
```
APP_KEYS={Random Your String}
API_TOKEN_SALT={Random Your String}
ADMIN_JWT_SECRET={Random Your String}
JWT_SECRET={Random Your String}
```
์์์ ์์ ํ ๋ด์ฉ๊น์ง ๋ชจ๋ ๋ฐ์ํ ๋ค์ .env ํ์ผ๋ก ์์ฑํด ๋ณด์ธ์.
