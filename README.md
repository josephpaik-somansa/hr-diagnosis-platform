# 🏢 Somansa HR Diagnosis & Analytics Platform

## 📖 프로젝트 개요
본 프로젝트는 대한민국 최고의 보안 기업 **'소만사(Somansa)'**의 임직원 조직문화 및 직무역량을 진단하고 심층 분석하기 위한 엔터프라이즈 통합 플랫폼입니다. 오픈소스 설문 엔진인 LimeSurvey를 코어로 사용하되, 완벽한 사내 시스템 연동(SSO)과 데이터 시각화 대시보드를 구축하여 HR의 전략적 의사결정을 지원합니다.

## 🏛 시스템 아키텍처 및 모듈 구성
시스템은 크게 4가지 독립된 마이크로서비스(MSA) 영역으로 나뉩니다.

1. **Survey Engine (LimeSurvey Core)**: PHP/MariaDB 기반, 맞춤형 Twig 테마 적용.
2. **Integration Middleware (Core API)**: NestJS 기반, 사내 포털 JWT SSO 인증 및 토큰 발급.
3. **Analytics Dashboard (Front-end)**: React/ECharts 기반, HR 관리자용 결과 분석 및 시각화.
4. **Data Warehouse (Core DB)**: PostgreSQL 기반, 역량 진단 결과 T-점수 스코어링 및 적재.

## 🛠 기술 스택 (Tech Stack)
*   **Infrastructure**: Docker, Docker-compose, Nginx (Reverse Proxy)
*   **Front-end (Dashboard)**: React.js, TypeScript, TailwindCSS, ECharts
*   **Back-end (API & SSO)**: Node.js (NestJS), TypeORM, Axios
*   **Survey Core**: LimeSurvey v6.x, Twig Template Engine
*   **Database**: MariaDB 10.5 (Survey Raw), PostgreSQL 15 (Core Analytics)
*   **Security**: 사내 WAF, MariaDB TDE (File Key Management), pgcrypto (Field-level Encryption)

## 🚀 빠른 시작 (Getting Started)

### 1. 환경 변수 설정
루트 디렉토리의 `.env.example` 파일을 복사하여 `.env` 파일을 생성하고 사내 보안 규정에 맞게 키를 세팅합니다.
```bash
cp .env.example .env
# vi .env (DB 패스워드, JWT Secret, Lime API 정보 등 수정)
