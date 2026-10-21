# 강병구 <sub>byegu</sub>

Java와 Spring을 중심으로 인증·인가, 검색, 외부 서비스 연동을 개발해 왔습니다.<br>
정상 동작뿐 아니라 **데이터 접근 권한과 실패 이후의 흐름**도 함께 확인합니다.

[프로젝트](#프로젝트) &nbsp; · &nbsp; [기술 스택](#기술-스택) &nbsp; · &nbsp; [수상·자격](#수상자격) &nbsp; · &nbsp; [학습 기록](#학습-기록)

<img src="assets/profile-accent.svg" width="100%" height="28" alt="">

## 프로젝트

제가 맡은 구현과 판단을 중심으로 정리했습니다.

<table>
<tr><td>
<a href="https://github.com/byegu/dodam"><img src="assets/dodam-service-logo.png" width="56" height="56" align="right" alt="도담 서비스 로고"></a>
<sub>01 &nbsp; · &nbsp; 2026.07 — 2026.08 &nbsp; · &nbsp; 백엔드</sub>
<h3><a href="https://github.com/byegu/dodam">도담</a></h3>
<p>아이의 그림과 AI 대화를 보호자가 함께 돌아보는 서비스입니다.<br>분석은 이해를 돕는 참고 정보이며, 심리 진단·치료를 제공하지 않습니다.</p>
<ul>
<li><b>인증·인가</b> — 보호자와 아동·그림 활동의 소유 관계를 공통 Validator로 검사하고, Redis Lua 기반 Refresh Token 회전·재사용 감지를 구현했습니다.</li>
<li><b>AI 연동</b> — 60초 단일 사용 이미지 접근, 응답 검증, 오류 분류와 멱등 재시도 경계를 구현했습니다.</li>
<li><b>리포트</b> — PDFBox와 openhtmltopdf를 비교하고, HTML/CSS 템플릿과 저장소 이미지 자산을 이용한 서버 PDF 생성을 구현했습니다.</li>
</ul>
<p><code>Java</code> <code>Spring Boot</code> <code>Spring Security</code> <code>Redis</code> <code>MySQL</code></p>
<p><a href="https://github.com/byegu/dodam"><b>소스 저장소 ↗</b></a> &nbsp; · &nbsp; <a href="projects/dodam.md">구현 내용 →</a></p>
</td></tr>
</table>

<table>
<tr><td>
<a href="https://github.com/byegu/bulleoyo"><img src="assets/bulleoyo-service-logo.svg" width="126" height="54" align="right" alt="불러요 서비스 로고"></a>
<sub>02 &nbsp; · &nbsp; 2026.08 — 2026.10 &nbsp; · &nbsp; 프론트엔드·팀장</sub>
<h3><a href="https://github.com/byegu/bulleoyo">불러요</a></h3>
<p>여러 밴드의 공동 공연을 위한 티켓 예매·입장·수익 정산 플랫폼입니다.<br>Kaia Kairos 테스트넷을 사용하는 시연용 서비스입니다.</p>
<ul>
<li><b>결제 상태</b> — 서명 대기·처리 중·성공·실패를 구분하고, 최신 상태에서 성공을 확인한 뒤에만 완료 화면으로 이동하도록 구현했습니다.</li>
<li><b>실패 후 복구</b> — 재시도 전 주문·결제를 재조회하고 처리 중 중복 실행을 막았습니다. 실패한 작업을 복원하지 않고 새 멱등키로 서명 절차를 재개했습니다.</li>
<li><b>검증</b> — 상태 충돌·반영 지연·재서명·연속 재시도를 회귀 테스트로 확인했습니다. 스마트컨트랙트·백엔드 체인·인프라는 다른 팀원 담당입니다.</li>
</ul>
<p><code>React</code> <code>TypeScript</code> <code>Web3Auth</code> <code>Kaia</code></p>
<p><a href="https://github.com/byegu/bulleoyo"><b>소스 저장소 ↗</b></a> &nbsp; · &nbsp; <a href="projects/bulleoyo.md">구현 내용 →</a></p>
</td></tr>
</table>

<table>
<tr><td>
<a href="https://github.com/nhnacademy-be5-no24/no24-shop"><img src="assets/no24-service-logo.png" width="140" height="48" align="right" alt="No24 서비스 로고"></a>
<sub>03 &nbsp; · &nbsp; 2024.03 — 2024.05 &nbsp; · &nbsp; 백엔드</sub>
<h3><a href="https://github.com/nhnacademy-be5-no24/no24-shop">No24</a></h3>
<p>도서를 찾고 주문하는 온라인 서점입니다. 검색·카테고리 등 백엔드 기능을 담당했습니다.</p>
<ul>
<li><b>검색</b> — Elasticsearch로 도서명·저자·ISBN 등 여러 필드와 자소·n-gram 하위 필드, 페이지네이션을 사용하는 검색 흐름을 구현했습니다.</li>
<li><b>데이터와 테스트</b> — 자기참조 카테고리 구조와 용도별 응답 DTO를 다루고, CRUD·예외 처리 및 Controller/Service/Repository 테스트에 기여했습니다.</li>
</ul>
<p><code>Java</code> <code>Spring</code> <code>Elasticsearch</code> <code>QueryDSL</code> <code>Redis</code></p>
<p><a href="https://github.com/nhnacademy-be5-no24/no24-shop"><b>서버 저장소 ↗</b></a> &nbsp; · &nbsp; <a href="https://github.com/nhnacademy-be5-no24/no24-frontend">검색 구현 저장소 ↗</a> &nbsp; · &nbsp; <a href="projects/no24.md">구현 내용 →</a></p>
</td></tr>
</table>

<br>

## 기술 스택

프로젝트에서 직접 사용한 기술을 영역별로 정리했습니다.

| 영역 | 기술 |
| :--- | :--- |
| **백엔드** | <img src="assets/stack-java.svg" alt="Java" height="28"> <img src="assets/stack-spring-boot.svg" alt="Spring Boot" height="28"> <img src="assets/stack-spring-security.svg" alt="Spring Security" height="28"><br><img src="assets/stack-jpa.svg" alt="JPA" height="28"> <img src="assets/stack-querydsl.svg" alt="QueryDSL" height="28"> |
| **데이터·검색** | <img src="assets/stack-mysql.svg" alt="MySQL" height="28"> <img src="assets/stack-redis.svg" alt="Redis" height="28"> <img src="assets/stack-elasticsearch.svg" alt="Elasticsearch" height="28"> |
| **프론트엔드** | React · TypeScript |
| **개발·협업 도구** | <img src="assets/stack-docker.svg" alt="Docker" height="28"> <img src="assets/stack-jenkins.svg" alt="Jenkins" height="28"> <img src="assets/stack-git.svg" alt="Git" height="28"> <img src="assets/stack-github-actions.svg" alt="GitHub Actions" height="28"> |

<br>

## 수상·자격

- **우수상** · SSAFY 공통 프로젝트 도담 — 팀 수상
- **대상** · SW아카데미 NHN Academy 프로젝트 최종발표회 No24 — 팀 수상
- **장려상** · 2024 한국소프트웨어종합학술대회 학부생/주니어 논문경진대회 — ROADAI 관련 논문 공동저자 · 2025.02.03

정보처리기사 · SQLD · TOEIC Speaking IH<br>
SSAFY SW 역량평가 **A등급** · 2026.03.06

<br>

## 학습 기록

Java로 푼 알고리즘 문제와 풀이 코드를 기록하고 있습니다.

**[알고리즘 저장소 ↗](https://github.com/byegu/Algorithm)** &nbsp; · &nbsp; **[solved.ac ↗](https://solved.ac/profile/rkdqudrn07)**

<a href="https://solved.ac/profile/rkdqudrn07">
  <img src="https://mazassumnida.wtf/api/v2/generate_badge?boj=rkdqudrn07" alt="rkdqudrn07의 solved.ac 프로필" width="320">
</a>

<details>
<summary>GitHub 활동 기록</summary>
<br>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/activity-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/activity-light.svg">
  <img src="assets/activity-light.svg" alt="GitHub 기여 기록을 바탕으로 생성한 잔디 애니메이션" width="100%">
</picture>
<sub>기여 기록은 매일 갱신됩니다. <a href="https://github.com/Platane/snk">snk</a> 사용.</sub>
</details>
