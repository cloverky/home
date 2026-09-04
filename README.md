# cloverky.cloud

`cloverky.cloud` 루트에 올라가는 포트폴리오 랜딩. 프로젝트는 서브도메인에서 각각 돌아가고,
이 페이지는 그 목록을 보여주는 역할만 한다.

빌드 없음. `index.html` 한 파일이 전부다.

## 로컬에서 보기

`index.html`을 브라우저로 열면 끝.

## 프로젝트 추가하기

`index.html`의 `<a class="record">` 블록을 통째로 복사해서 값 5개만 바꾼다.

| 바꿀 곳 | 예시 |
|---|---|
| `href` | `https://ats.cloverky.cloud` |
| `.record-host` | `ats` + `<span class="sub">.cloverky.cloud</span>` |
| `.record-name` | `Eval-ATS` |
| `.record-desc` | 한 줄 설명 |
| `.stack` | `Jekyll · GitHub Pages` |

카드를 4개 이상으로 늘리면 등장 애니메이션 딜레이(`.record:nth-of-type(...)`)도 한 줄 추가한다.

## 도메인 구성

| 호스트 | 호스팅 | 내용 |
|---|---|---|
| `cloverky.cloud` | Vercel | 이 레포 |
| `fridge.cloverky.cloud` | Vercel | FridgeAI (Next.js) |
| `ats.cloverky.cloud` | GitHub Pages | Eval-ATS 문서 |

DNS는 Cloudflare. 서브도메인 추가는 Cloudflare에서 CNAME 레코드를 만들고,
Vercel 쪽은 프록시를 꺼야 한다(DNS only, 회색 구름).

## 디자인 메모

- 콘셉트: 페이지 자체가 DNS 존 파일. 좌측 트리 선이 apex → 서브도메인 관계를 그린다.
- 서체: 제목·호스트명은 IBM Plex Mono, 한글 본문은 IBM Plex Sans KR.
- 다크 모드는 `prefers-color-scheme`으로만. 토글 없음.
