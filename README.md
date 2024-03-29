# PubArt
소설, 만화, 웹툰 및 애니메이션 글로벌 플랫폼

## 개발 기간 및 인원
> 기간 : 2024. 03. 20. ~ 진행 중

| 유형 | 팀원
| ------ | ------
| Frontend | [장천룡](https://github.com/MTtankkeo)
| Backend | [이다영](https://github.com/verdantjuly)


## Tech Spec
| 분류 | 기술
| ------ | ------
| Frontend | React
| Backend | GO, MySQL, Redis


## 초기 세팅
PubArt 프로젝트를 빌드하고 관리하기 위해서는 종속된 주요 라이브러리들을 숙지해야 합니다.

> 사용자에게 응답되는 정적 리소스는 항상 최대한 경량화될 수 있도록 주의해야만 합니다.
> 이는 웹에서 클라이언트의 하드웨어 성능보다 네트워크 성능이 중요하다는 것을 반증합니다.

> 또한 정적 리소스에 대한 비동기 요청은 최대 1번만 수행되어야 합니다. (서비스 워커 제외)

| 유형 | 설명 | 패키지 관리
| ------ | ------ | ------
| Client | Preact, Webpack | NPM
| Server | 대부분의 경우, 내장 기능만을 사용 | GO.mod `Native`

### NPM를 통한 빌드
원활한 개발 환경이 조성되려면 `npm run release`를 반복적으로 입력하지 않고 클라이언트 측의 변경사항이 발생한다면 이를 자동으로 감지하여 빌드될 수 있도록 합니다.
아래 명령어를 터미널에 입력하여 앞서 설명되었던 기능을 사용합니다.

```
npm run dev
```

### 모든 NPM 빌드 옵션
아래 테이블은 현재 선언된 모든 빌드 옵션들을 나타냅니다.

| 유형 | 설명
| ------ | ------
| release | 높은 사용자 경험을 위해 최적화와 압축 과정을 거친 이후 빌드됩니다.
| debug | 최대한 빠르게 빌드되어야 하므로 최적화와 압축 과정이 생략되고 빌드됩니다.
| dev | 개발 전용 서버를 사용하며 디버그 모드와 마찬가지로 최적화와 압축 과정이 생략되고 메모리 상에서 빌드됩니다. 변경 사항이 발생하면 일부가 재빌드되면서 이를 웹사이트가 수신하여 자동으로 새로고침됩니다.

## ERD
아래 이미지는 데이터베이스 전체의 구조와 관계를 시각적으로 나타냅니다.   
자세한 내용은 [drawSQL](https://drawsql.app/teams/verdantjuly/diagrams/pubart)를 참고하세요.

> 최근 Access Log 의 ip와 다른 ip에서 비밀번호 불일치 등 의심스러운 접근이 발생하는 경우 TokenBlacklist에 기재하고 해당 토큰의 사용을 막습니다.
  
> 회차 별 혹은 작품 별로 쿠폰을 발급하고 포인트를 이용하여 구입할 수 있게 하였습니다.
   
![ERD](https://github.com/pubart-official/pubart/assets/131671804/41a522a8-1dfc-40ef-aeb0-e60d3bfc46fc)
