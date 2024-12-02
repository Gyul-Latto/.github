# 🐻‍❄️ PickHome
**빅데이터와 AI를 활용한 "아파트 추천 서비스"**

<br>

## 📌 프로젝트 배경 및 목표
아파트를 찾는 과정은 많은 시간이 소요되며, 현재 제공되는 부동산 정보는 방대하지만 사용자 맞춤형 추천 서비스는 부족한 상황입니다.  
이 프로젝트는 다음과 같은 목표를 가지고 있습니다:
- 사용자의 선호도를 반영한 맞춤형 아파트 추천 제공.
- 실시간 데이터 업데이트를 통해 사용자 의사결정 지원.
- 사용자 행동 데이터 기반으로 정확한 추천 시스템 구현.

<br>

## ✨ 주요 기능
1. **개인화 추천**: 
   - 사용자의 선호도와 좋아요 데이터를 기반으로 추천.
   - Collaborative Filtering과 Content-Based Filtering 적용.
2. **실시간 정보 제공**:
   - 아파트 매물 업데이트, 실거래가 변화, 최신 트렌드 반영.
   - Redis를 활용한 빠른 데이터 처리.
3. **직관적인 사용자 인터페이스**:
   - 지역과 아파트 검색으로 편리한 검색 기능.
4. **시장 트렌드 분석**:
   - 특정 가격대, 지역의 매물 동향 제공.

<br>

## 🛠 기술적 세부 사항
### AI Model
- **협업 필터링 (Collaborative Filtering)**: 
  - 비슷한 취향을 가진 사용자 데이터를 기반으로 추천.
- **콘텐츠 기반 필터링 (Content-Based Filtering)**: 
  - 사용자가 선호하는 속성을 가진 매물을 추천.
- **알고리즘**: 코사인 유사도, 유클리드 거리.
<img src="https://i.postimg.cc/0j7Hdtdy/image.png" alt="PickHome AI모델" width="600">

### Database & storage
- **MySQL**: 사용자 데이터 및 매물 정보 저장.
- **Redis**: 실시간 데이터 처리 및 캐싱.

### Backend
- **Spring Framework**: 핵심 비즈니스 로직 구현.
- **Spring Security**: 인증 및 권한 관리.
- **청크 단위 데이터 처리**: 대규모 데이터를 효율적으로 로드하고 학습.
- **FastAPI**: AI 모델 서빙에 활용.

### Frontend
- **Vue.js**: 사용자 인터페이스 개발.
- **Pinia**: Vue.js 애플리케이션의 상태 관리.
- **Axios**: 백엔드 API와의 통신 처리.
- **Chart.js**: 트렌드 시각화 및 데이터 대시보드 구현.

<br>

## 📐 시스템 아키텍처
<img src="https://i.postimg.cc/xCfCS78W/image.png" alt="PickHome 시스템 아키텍처" width="600">

<br>

## ⚙️ ERD
<img src="https://i.postimg.cc/c4yJxrvR/Pick-Home-ERD.png" alt="PickHome 시스템 아키텍처" width="600">

<br>

## 📅 개발 일정
| 단계              | 주요 작업                            | 일정               |
|---------------------|------------------------------------|---------------------|
| 기획 및 준비 단계  | 기능 설계, 데이터 수집              | 11월 13일 ~11월 18일          |
| 데이터 세팅        | RDS 및 더미 데이터 구축             | 11월 18일 ~ 11월 19일 |
| 핵심 개발          | AI 모델, Redis 통합                 | 11월 20일 ~ 11월 21일 |
| 기능 완성          | 주요 기능 구현 완료                | 11월 22일 ~ 11월 26일 |

<br>

## 🚧 문제 및 해결 방안
### 문제 1: **대규모 데이터 처리**
- **문제**: 640만 건의 데이터로 인해 학습 속도 저하.
- **해결**: Python generator와 Spark Streaming을 활용하여 데이터를 청크 단위로 처리.

### 문제 2: **Spring Security 예외 처리**
- **문제**: 필터 체인 단계에서 발생하는 예외가 `@ControllerAdvice`로 처리되지 않음.
- **해결**: `AuthenticationEntryPoint`와 `AccessDeniedHandler`를 사용해 필터 단계 예외 처리 구현.

<br>

## 📸 화면 예시
1. 메인 화면
2. 지도 검색 화면
3. 추천 결과 & 실시간 아파트 화면
![PickHome](https://i.postimg.cc/sXjN9PHY/Pick-Home-05.gif)


<br>

## 👥 팀원 소개

| Role       | Name      | GitHub                             |
|------------|-----------|------------------------------------|
| FE, BE, Spring Security   | 문인규    | [@ingyu-moon](https://github.com/InGyu-Moon) |
| FE, BE, AI    | 왕한솔    | [@solsoleee](https://github.com/solsoleee) |
