# 🧾 Nutrifit 통합 문서 저장소

이 저장소는 **Nutrifit** 플랫폼의 프론트엔드, 백엔드, 관리자(운영) 시스템의 통합 문서 저장소입니다.  
각 프로젝트의 구조와 역할, 설정 방법, 실행 순서를 포함하여 전체적인 흐름을 이해할 수 있도록 정리되어 있습니다.

---

## 📌 프로젝트 구성

| 모듈        | 설명                                          | 레포지토리 링크 |
|-------------|-----------------------------------------------|------------------|
| 🛍️ Frontend | 고객이 사용하는 쇼핑몰 (Next.js + TypeScript) | [nutrifit-front](https://github.com/devyourown/nutrifit-front) |
| 🧠 Backend   | Spring Boot 기반 API 서버 (JAVA + JPA + PostgreSQL) | [nutrifit-mall](https://github.com/devyourown/nutrifit-mall) |
| 🧾 Admin     | 운영자 상품 및 주문 관리 페이지 (Next.js + TypeScript) | [nutrifit-admin](https://github.com/devtourown/nutrifit-admin) |

## ⚙️ 개발 환경 개요

- 프론엔드: Next.js (v13+), TailwindCSS, TypeScript
- 백엔드: Spring Boot 3.x, JPA (Hibernate 6), PostgreSQL
- 인증: Google, Naver, Kakao OAuth2, JWT
- 캐시/세션: Redis
- 배포: Vercel (Frontend/Admin), AWS EC2 & S3 (Backend)

---

## 🔗 연동 흐름

1. **사용자**는 `nutrifit-front`를 통해 상품을 탐색하고 주문을 진행합니다.
2. 프론트는 백엔드의 REST API (`nutrifit-mall`)와 통신하여 상품 데이터, 장바구니, 주문 등을 처리합니다.
3. 이 때, redis를 이용해 프론트엔드의 장바구니를 캐시화합니다.
4. 백엔드는 각종 API(결제, 로그인 등)을 처리합니다.
5. 관리자는 `nutrifit-admin`을 통해 상품을 등록하고 주문을 관리합니다.

---

## 🚀 실행 순서
PostgreSQL 데이터베이스 실행

nutrifit_back DB 생성

접속 정보는 application.properties 또는 application.yml에 설정

Redis 실행

세션 관리 및 캐시 처리를 위한 Redis 인스턴스 실행

백엔드 서버 실행 (nutrifit-back)

PostgreSQL 및 Redis 연결 필요

bash
./gradlew bootRun

프론트엔드 / 관리자 사이트 실행 (nutrifit-front, nutrifit-managing)

bash
npm install
npm run dev

환경 변수 설정

각 레포지토리의 .env.example 파일을 참고하여 .env.local 생성 및 설정



---

## 📁 문서 목록

- [Frontend README](https://github.com/devyourown/nutrifit-front/blob/main/README.md)
- [Backend README](https://github.com/devyourown/nutrifit-back/blob/main/README.md)
- [Managing README](https://github.com/devyourown/nutrifit-managing/blob/main/README.md)

---

## 🙋 문의

모든 기획 및 개발, 배포는 devyourown이 진행하였습니다. 

문제나 개선 사항은 이 저장소의 Issues 탭을 통해 남겨주세요.

---

## 📄 라이선스

본 프로젝트는 [MIT License](./LICENSE)를 따릅니다.
