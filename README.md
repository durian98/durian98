<h1 align="center">Jaehyeon Park · 박재현</h1>

<p align="center">
  Java와 Spring으로 서비스의 기능을 만들고, 데이터와 실시간 통신, 배포를 연결합니다.
</p>

<p align="center">
  <a href="https://github.com/durian98">
    <img src="https://img.shields.io/badge/GitHub-durian98-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub durian98" />
  </a>
</p>

## About Me

- 여행 추천 서비스 **GABOLLE(가볼래)**와 로봇 기반 화재·설비 모니터링 시스템 **BBIYONG(삐용)**을 팀 프로젝트로 개발했습니다.
- 인증과 세션 관리, 이벤트 저장과 실시간 알림, CI/CD를 경험했습니다.
- Python과 Java로 알고리즘을 공부하고, 구현 과정에서 배운 개념과 설계 판단을 기록합니다.

## Projects

### [GABOLLE · 가볼래](https://github.com/durian98/GABBOLE)

부산을 방문하는 여행자가 자신의 취향과 조건에 맞는 여행을 계획하고, 여행 중에도 일정을 확인하고 기록을 남길 수 있는 서비스입니다. 관심사와 식단, 이동 수단, 여행 날짜와 방문하고 싶은 장소를 입력하면 장소 후보를 고르고 여행 일정으로 구성합니다.

일정 생성 중에는 진행 상태를 확인하고, 완성된 일정은 지도에서 살펴보며 방문 순서를 조정할 수 있습니다. 동행자를 초대해 일정을 공유하고, 장소 탐색과 여행 기록·피드로 여행 전후의 경험을 이어갑니다. 일정 추천은 조건 필터링과 점수 계산을 사용하는 규칙 기반 흐름이며, 메뉴판·음식 설명 등에는 별도의 AI 기능을 활용합니다.

**담당: 백엔드 개발, 기능 통합 및 QA**

- **인증·계정:** 이메일·소셜 로그인, 사용자와 로그인 수단의 연결, 세션 관리와 토큰 갱신을 구현했습니다. 웹은 HttpOnly 쿠키, 앱은 토큰 응답으로 인증 정보를 전달하도록 구성했습니다.
- **추천·일정:** 초기 규칙 기반 추천 결과를 생성하고 저장하는 흐름을 연결했습니다. 추천 결과가 실제 일정 항목으로 저장되고 조회되도록 백엔드 구성 요소를 연결했습니다.
- **서비스 API:** 여행 기록, 동행자 초대와 역할, 장소 탐색 API를 통합하고 화면에서 사용하는 요청·응답 형식을 맞췄습니다.
- **이용 조건·화면 연동:** 음식 취향과 필수 식단 조건을 구분해 후보 판정을 보완하고, 설정 흐름과 공용 시트·사진 UI 개선에 참여했습니다.

`Java` `Spring Boot` `Spring Security` `PostgreSQL` `Flyway` `Docker`

[저장소](https://github.com/durian98/GABBOLE) · [백엔드 코드](https://github.com/durian98/GABBOLE/tree/main/backend)

### [BBIYONG · 삐용](https://github.com/durian98/BBIYONG)

로봇이 현장의 RGB·열화상 정보와 상태를 수집하고, 화재나 설비 이상을 감지하면 관리자가 관제 화면에서 상황을 확인할 수 있도록 만든 모니터링 시스템입니다. 로봇의 현장 감지, 서버의 사건 관리, 웹 관제 화면을 연결하는 팀 프로젝트입니다.

Jetson에서 위험을 판정하면 서버가 이벤트를 저장하고 관제 화면과 외부 알림으로 전달합니다. 관리자는 로봇 상태와 현장 영상, 사건 이력을 확인할 수 있습니다. 로봇과 서버의 통신은 WSS, 관제 화면의 실시간 알림은 STOMP, 이력·설정 조회는 REST API로 구성했습니다.

**담당: 인프라, System 백엔드 일부, AI 운영 연동**

- **실행·배포 환경:** EC2, Nginx, Docker와 Jenkins를 구성했습니다. MR에서는 코드 검증을 수행하고, 병합 뒤에는 서비스를 배포하도록 CI와 CD 흐름을 나눴습니다.
- **이벤트·알림:** 로봇 위험 이벤트를 DB에 저장한 뒤 관제 알림과 외부 알림으로 연결했습니다. 재전송되는 이벤트는 `messageId`로 구분해 중복 저장을 방어했습니다.
- **관제 연동:** 로봇과 서버 사이의 이벤트 수신·회신, 서버와 관제 화면 사이의 실시간 알림을 연결하고 사건 이력 조회와 화면 표시를 연동했습니다.
- **AI·Jetson 연동:** AI 추론 평가와 Jetson 운영 검증에 참여했습니다. 팀원과 ONNX→TensorRT 변환 및 GPU 최적화를 진행하고 실제 주행 중 화재 모사 경보 시험에 참여했습니다.

`Java` `Spring Boot` `MySQL` `WebSocket` `STOMP` `Jenkins` `Docker` `Nginx` `AWS EC2`

[저장소](https://github.com/durian98/BBIYONG) · [System 백엔드 코드](https://github.com/durian98/BBIYONG/tree/main/BE_system)

## Tech Stack

**Backend**

<p>
  <img src="https://img.shields.io/badge/Java-437291?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white" alt="Django" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
</p>

**Infrastructure & Tools**

<p>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" alt="Jenkins" />
  <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white" alt="Nginx" />
  <img src="https://img.shields.io/badge/AWS%20EC2-FF9900?style=flat-square&logoColor=white" alt="AWS EC2" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/GitLab-FC6D26?style=flat-square&logo=gitlab&logoColor=white" alt="GitLab" />
</p>

## Learning & Records

| 저장소 | 내용 |
|:---|:---|
| [Algorithm](https://github.com/durian98/algorithm) | Python·Java 문제 풀이와 [알고리즘 기초](https://github.com/durian98/algorithm/tree/main/basics), [SWEA](https://github.com/durian98/algorithm/tree/main/SWEA), [백준](https://github.com/durian98/algorithm/tree/main/baekjoon), [프로그래머스](https://github.com/durian98/algorithm/tree/main/programmers) 풀이 |
| [TIL](https://github.com/durian98/til) | Spring, CS, AI, 웹 개발 학습과 문제 해결 기록 |
| [Developer Playbook](https://github.com/durian98/developer-playbook) | 개발 경험에서 정리한 설계 판단, 실패 패턴, 검증 체크리스트와 AI 활용 방법 |

## Earlier Projects

| 프로젝트 | 내용 | 기술 |
|:---|:---|:---|
| [Arctic](https://github.com/durian98/toyproject/tree/main/Arctic) | AI 기반 도서 추천·분석 및 창작 지원 커뮤니티 | Django, DRF, FastAPI, Vue.js |
| [money_hero](https://github.com/durian98/toyproject#money_hero) | 금융감독원 API를 활용한 예·적금 상품 추천 AI 챗봇 | FastAPI, Vue.js, Gemini API |
| [algoalgo_chatbot](https://github.com/durian98/toyproject/tree/main/algoalgo_chatbot) | 알고리즘 스터디용 Discord 봇 | Python |
| [todoapi](https://github.com/durian98/toyproject/tree/main/todoapi) | 할 일 목록 API | Spring, MySQL |

## GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=durian98&show_icons=true&theme=default&hide_border=true" height="165" alt="GitHub stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=durian98&layout=compact&theme=default&hide_border=true" height="165" alt="Top languages" />
</p>
