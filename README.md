# 🚀 내 맥북에 Strapi + SMTP + CDN 설치하기

이 Repository는 ["코딩없이 백엔드 API 서버 구축하기 (Strapi + Heroku)"](https://tera.co.kr/course/%EC%BD%94%EB%94%A9%EC%97%86%EC%9D%B4-%EB%B0%B1%EC%97%94%EB%93%9C-api-%EC%84%9C%EB%B2%84-%EA%B5%AC%EC%B6%95%ED%95%98%EA%B8%B0/) 과정 중 내 맥북에 로컬 개발환경 구축을 위한 소스입니다.

Heroku에 배포하여 사용하려면 추가로 몇가지 작업이 더 필요하며 위 강의의 "운영 환경 구성(Heroku에 배포)
" 섹션을 참고하세요.

# 소스 사용방법

## 대충 빠르게 시작하는 법
- .env.example 파일을 복사하여 .env 로 저장합니다.
- yarn 을 실행하여 노드 모듈을 설치합니다.
- yarn develop 를 실행하면 끝
---
## 제대로 시작하기
프론트엔드 인증 개발시 이메일 인증 및 비밀번호 찾기 기능 구현을 위해서는 SendGrid에 가입해서 .env 파일에 설정값을 넣어야 하고 Heroku에 배포해보기를 원하는 분들은 이미지 파일 저장을 위한 무료 CDN인 Cloudinary에 가입해서 정보를 .env파일에 넣으면 됩니다.
### 무료 SMTP 서비스인 [SendGrid](https://sendgrid.com)에 가입
위 사이트에 가입하여 API-KEY를 발급받아 .env파일을 구성하세요. 가입에 대한 자세한 내용은 강의를 참고하세요.
이미 계정이 있는 분은 .env.example 파일을 수정하여 .env로 저장하여 사용하면됩니다.
```
# .env.example 파일 수정할 부분 
SENDGRID_API_KEY={Your SendGrid API_KEY}
SENDGRID_FROM_EMAIL={Your SendGrid Sender Email}
SENDGRID_REPLYTO_EMAIL={Your SendGrid Sender Email}
SENDGRID_TEST_EMAIL={Your any Email}
```

### 무료 이미지 저장 서비스인 [Cloudinary](https://cloudinary.com)에 가입
위 사이트에 가입하여 API-KEY를 발급받아 .env파일을 구성하세요. 가입에 대한 자세한 내용은 강의를 참고하세요.
이미 계정이 있는 분은 .env.example 파일을 수정하여 .env로 저장하여 사용하면됩니다.

```
# .env.example 파일 수정할 부분 
CLOUDINARY_NAME={Your CLOUDINARY_NAME}
CLOUDINARY_KEY={Your CLOUDINARY_KEY}
CLOUDINARY_SECRET={Your CLOUDINARY_SECRET}
```

### .env 파일 생성

아래 Random String 항목을 정말 랜덤으로 대충 입력하고
```
APP_KEYS={Random Your String}
API_TOKEN_SALT={Random Your String}
ADMIN_JWT_SECRET={Random Your String}
JWT_SECRET={Random Your String}
```
위에서 수정한 내용까지 모두 반영한 다음 .env 파일로 생성해 보세요.
