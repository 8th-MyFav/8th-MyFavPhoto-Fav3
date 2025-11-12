
# 🎴 MyFavPhoto - 최애의 포토

> **나만의 최애 포토카드를 만들고, 교환하고, 거래하는 K-POP 팬들을 위한 포토카드 플랫폼**
## 🛠 Tech Stack

| Frontend | Backend | Infra & Tools |
|:----------|:----------|:----------|
| ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs) <br> ![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=flat&logo=tailwindcss) <br> ![React Query](https://img.shields.io/badge/React%20Query-FF4154?style=flat&logo=reactquery) | ![Express.js](https://img.shields.io/badge/Express.js-000000?style=flat&logo=express) <br> ![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat&logo=nodedotjs) <br> ![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat&logo=prisma) <br> ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql) | ![AWS S3](https://img.shields.io/badge/AWS%20S3-569A31?style=flat&logo=amazonaws) <br> ![Render](https://img.shields.io/badge/Render-000000?style=flat&logo=render) <br> ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel) |


<br/>

## 📖 프로젝트 소개

**MyFavPhoto**는 K-POP 팬들이 자신만의 포토카드를 만들고,  
안전하게 거래하거나 교환할 수 있는 팬 커뮤니티 기반의 마켓플레이스 서비스입니다.  
<br/>
포인트 기반의 거래 시스템으로 사기 위험 없이 즐겁게 거래하고,  
랜덤 포인트 박스 등 팬심을 자극하는 재미 요소도 함께 제공합니다 💜  

> 팬심을 기술로 잇다 — 당신의 ‘최애’를 위한, 팬 중심 거래 플랫폼

<br/>

---

## 🖥️ 프론트엔드 (Frontend)

> **📁 Repository:** [`8th-MyFavPhoto-FE`](https://github.com/your-org/8th-MyFavPhoto-FE)

### ✨ 주요 기능
- 🛒 **포토카드 마켓** – 원하는 포토카드를 검색, 판매 또는 교환 제안 가능  
- 💰 **포인트 거래 시스템** – 포인트로 안전하게 거래  
- 🔔 **실시간 알림** – 거래 요청·수락·완료 알림 실시간 확인  
- 🎁 **랜덤 박스** – 1시간마다 포인트 랜덤 획득  
- 📱 **반응형 UI** – 모바일부터 데스크탑까지 완벽 대응  

### 🧩 기술 스택
| 구분 | 사용 기술 |
| :-- | :-- |
| **Framework** | Next.js (App Router), React |
| **UI** | Tailwind CSS |
| **State / Data** | TanStack Query, React Context API |
| **Font** | Geist, Noto Sans KR (`next/font`) |
| **Deploy** | Vercel |

### 🚀 실행 방법
```bash
git clone https://github.com/your-org/8th-MyFavPhoto-FE.git
cd 8th-MyFavPhoto-FE
npm install
```

환경 변수 설정:

```env
NEXT_PUBLIC_API_URL=https://your-backend-api-url.com
```

로컬 실행:

```bash
npm run dev
# http://localhost:3000
```

### 📁 주요 디렉토리 구조

```plaintext
src/
├── app/               # Next.js App Router
│   ├── (auth)/        # 인증 필요 페이지
│   ├── (no-auth)/     # 비로그인 페이지
│   └── layout.jsx
├── components/        # UI 컴포넌트 (atoms, molecules, organisms)
├── constants/         # 상수 및 경로 관리
├── contexts/          # Auth, Query 전역 상태
├── hooks/             # 커스텀 훅
└── styles/            # Tailwind 설정 및 글로벌 스타일
```

---

## ⚙️ 백엔드 (Backend)

> **📁 Repository:** [`8th-MyFavPhoto-BE`](https://github.com/your-org/8th-MyFavPhoto-BE)

### ✨ 주요 기능

* 👤 **사용자 인증** – JWT 기반 회원가입 및 로그인
* 🖼️ **포토카드 관리** – 사용자 포토카드 생성 및 관리
* 🛒 **마켓플레이스** – 다른 사용자와 포토카드 거래
* 🔔 **실시간 알림** – 거래 및 주요 이벤트 알림 제공
* 💓 **헬스 체크** – `/` 및 `/health` 엔드포인트로 서버·DB 상태 확인

### 🧩 기술 스택

| 구분                       | 사용 기술                                             |
| :----------------------- | :------------------------------------------------ |
| **Runtime**              | Node.js                                           |
| **Framework**            | Express.js                                        |
| **ORM**                  | Prisma                                            |
| **Database**             | PostgreSQL                                        |
| **Middleware**           | `cors`, `morgan`, `cookie-parser`, `express.json` |
| **Linting / Formatting** | ESLint, Prettier                                  |

### 🚀 실행 방법

```bash
git clone https://github.com/your-org/8th-MyFavPhoto-BE.git
cd 8th-MyFavPhoto-BE
npm install
```

환경 변수 설정:

```env
# .env
DATABASE_URL="postgresql://user:password@localhost:5432/mydatabase?schema=public"
PORT=3000
JWT_SECRET=your-super-secret-key
```

Prisma 마이그레이션:

```bash
npx prisma migrate dev
npx prisma generate
```

서버 실행:

```bash
npm start
# http://localhost:3000
```

### 📁 주요 API 엔드포인트

| Method | Endpoint              | 설명          |
| :----- | :-------------------- | :---------- |
| GET    | `/`                   | 서버 상태 확인    |
| GET    | `/health`             | DB 연결 상태 확인 |
| POST   | `/auth/signup`        | 회원가입        |
| POST   | `/auth/login`         | 로그인         |
| GET    | `/users/me`           | 내 프로필 조회    |
| POST   | `/cards`              | 포토카드 생성     |
| GET    | `/cards`              | 포토카드 목록 조회  |
| GET    | `/market`             | 마켓플레이스 조회   |
| POST   | `/market/buy/:cardId` | 특정 카드 구매    |
| GET    | `/notifications`      | 알림 목록 조회    |

> ※ 상세 경로 및 로직은 `/routes/*.js` 내부에서 관리됩니다.

---

## 🧑‍💻 팀 구성

| 이름 | 역할 | GitHub | 상세 |
| :-- | :-- | :-- | :-- |
| **홍명주** | Backend Lead | [@mjhong](https://github.com/mjhong) | [상세 보기](./team/mjhong.md) |
| **조원정** | Backend & DevOps | [@wonjeongjo](https://github.com/wonjeongjo) | [상세 보기](./team/wonjeongjo.md) |
| **조성민** | Frontend Lead | [@seongmincho](https://github.com/seongmincho) | [상세 보기](./team/seongmincho.md) |
| **김성준** | Frontend | [@sungjunkim](https://github.com/sungjunkim) | [상세 보기](./team/sungjunkim.md) |
| **나주현** | Frontend | [@ariana](https://github.com/ariana) | [상세 보기](./team/ariana.md) |

---

## 💬 프로젝트 한줄평

> “팬심이 만드는 경제, 그 시작은 나의 최애 포토카드에서.”
> — MyFavPhoto 팀

