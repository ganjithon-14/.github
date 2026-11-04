# 협업 규칙

모든 레포에 공통으로 적용합니다. 바꾸고 싶으면 이 파일을 PR로 고쳐 주세요.

## 1. 레포와 파트

| 레포 | 파트 | 리뷰어 |
|---|---|---|
| handeulpan-frontend | FE-A 들판(@Taemin217), FE-B 흐름(@seunguk925) | 같은 파트의 다른 한 명 |
| handeulpan-backend | BE-A 코어(@rohdaeyoung), BE-B 돌봄·운영(@sinjuno) | 같은 파트의 다른 한 명 |
| handeulpan-design | 기디·PM(@iyebin0301) | 리뷰 없이 바로 올려도 됨 |

- 각 레포 안의 담당 폴더는 레포 README의 **담당 영역** 표를 따릅니다. 남의 담당 폴더를 고칠 땐 PR 설명에 적고 담당자에게 리뷰를 받습니다.
- 백엔드의 `docs/api/`(API 명세)가 바뀌면 프론트 팀에도 자동으로 리뷰 요청이 갑니다.

## 2. 브랜치

```
main  ← 배포 (Vercel / 서버). 직접 push 금지, dev에서 PR로만.
dev   ← 통합. 기본 브랜치. 직접 push 금지, PR + 승인 1명.
feat/{파트}-{이슈번호}-{짧은-설명}   예) feat/fe-a-12-sheep-position
fix/{파트}-{이슈번호}-{짧은-설명}    예) fix/be-b-31-keyword-null
```
파트 표기: `fe-a`, `fe-b`, `be-a`, `be-b`, `design`

- 작업은 항상 `dev`에서 브랜치를 따서 `dev`로 PR을 보냅니다.
- `dev → main` 머지는 관문 날짜(11/6, 11/10, 11/13, 11/15, 11/18)에 맞춰 합니다.
- `feat/* → dev`는 **Squash and merge**, `dev → main`은 **Create a merge commit**으로 머지합니다. (dev→main을 squash하면 두 브랜치 기록이 어긋나 다음 PR에서 충돌이 납니다)
- 머지된 작업 브랜치는 자동 삭제됩니다. `main`, `dev`는 삭제가 막혀 있습니다.
- 급할 땐 조직 Owner가 승인 없이 PR을 머지할 수 있지만(우회), push 직접은 막혀 있습니다. 우회했다면 디스코드에 한 줄 남겨 주세요.

## 3. 커밋 메시지

```
{type}: {무엇을 했는지}  (#{이슈번호})
```
| type | 쓰는 때 |
|---|---|
| feat | 기능 추가 |
| fix | 버그 수정 |
| refactor | 동작 변화 없는 코드 정리 |
| style | 디자인·CSS·포맷 |
| docs | 문서, API 명세 |
| chore | 설정, 빌드, 의존성 |
| test | 테스트 |

예) `feat: 쓰다듬기 API 추가 (#7)`

## 4. 이슈와 라벨

- 이슈 하나 = PR 하나가 기본입니다. 이슈 템플릿(기능 / 버그 / API 요청)을 써 주세요.
- 라벨: `part: FE-A` 같은 **파트**, `F1`~`F8`·`D` 같은 **기능 번호**(기획서 5장), `P0`/`P1` **우선순위**
- 마일스톤: 관문 5개(11/6 명세 확정 ~ 11/18 최종 배포)

## 5. 용어 (코드 이름 통일)

프론트·백엔드·디자인 파일 이름을 아래 영어로 맞춥니다.

| 기획 용어 | 코드 이름 |
|---|---|
| 들판 | `field` |
| 양 | `sheep` |
| 쓰다듬기 (체크인) | `pat` |
| 말풍선 | `bubble` |
| 말풍선 반응 | `reaction` |
| 털 목도리 | `scarf` |
| 털 색 | `woolColor` |
| 다가가기 | `reachOut` |
| 거리 단계: 가운데 / 산책 중 / 가장자리 | `CENTER` / `WANDERING` / `EDGE` |
| 기기 토큰 | `deviceToken` |
| 위험 키워드 | `riskKeyword` |
| 데모 되감기 | `demo` / `rewind` |
| 낮잠 (쉬어가기) | `nap` |

## 6. 소통

- 매일 밤 디스코드에 한 줄 진행 공유
- 관문 날짜에만 짧은 회의
- API가 바뀌면 백엔드가 Swagger와 `docs/api/`를 먼저 고치고 프론트에 알립니다.
