# Review-Analysis

## URL 업데이트 예정

## 프로젝트 아키텍처 & 주요 특징

### 전체 아키텍처
- **모던 웹 풀스택**: React(Frontend) + FastAPI(Backend) + ElasticSearch(로그/이력)
- **폴더 구조 분리**: front_study(프론트), back_woo(백엔드), 데이터/모델/유틸리티 명확 분리
- **API 기반 통신**: RESTful API로 프론트-백엔드 완전 분리

### 분석 페이지 & 3D 시각화
- **Three.js 기반 3D 시각화**: 비행체(F-16) 궤적, AI 로그, 객체 상태 등 렌더링
- **동적 데이터 매칭**: AI 로그와 객체 이력 데이터를 프레임별로 매칭하여 테이블+3D로 동시 가시화
- **Three.js 활용**: 실제 지형/좌표 기반 시각화, 다양한 뷰 모드 지원

### 백엔드 API 성능
- **초고속 응답**: FastAPI 기반, 주요 분석 API 평균 응답시간 0.1~0.3초 (ElasticSearch 활용)
- **대용량 로그 처리**: 수만 건의 객체/AI 로그도 빠르게 조회 및 분석
- **비동기 처리**: API 호출 시 병렬/비동기 처리로 실시간 분석 지원
- Python 3.x
- FastAPI (메인 웹 프레임워크)
- ElasticSearch (로그/이력 데이터 저장 및 검색)
- 기타: PyJWT, pydantic, requests 등
- 구조: `back_woo/app/` (analyzer, auth, simulator), `back_woo/util/` (유틸리티)

## Backend 주요 API
- `/analyzer/get_ai_log` : AI 로그 데이터 조회 (JSON)
- `/analyzer/get_alive_histories` : 객체 생존 이력 조회
- `/analyzer/get_dead_histories` : 객체 사망 이력 조회
- `/analyzer/get_mission_result` : 미션 결과 조회
- `/analyzer/object_history` : 객체별 상태 이력 조회
- `/auth/login` : 사용자 로그인
- `/auth/logout` : 사용자 로그아웃
- 기타 커스텀 분석/시뮬레이션 API

## Frontend 기술 스택
- React (TypeScript)
- Vite (빌드/개발 환경)
- Three.js (3D 시각화)
- Recoil (상태 관리)
- Styled-components (스타일)
- 기타: Axios, ESLint, CesiumJS 등
- 구조: `front_study/src/` (components, containers, hooks, recoil, utils 등)

---

개발 결과물 동영상

- 룰기반 회피기동

https://youtu.be/3VKJ_54wKLw

- 강화학습 기반 회피기동

https://youtu.be/GqRcHVKAKSE

- 시뮬레이션 강화학습 모델 수치 시각화

https://youtu.be/w7pPpq7nIug

