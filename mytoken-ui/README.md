## 오늘은 뭐할까?

**BaseballGame 흐름 TDD**

| 순번 | 주제                                                                                                                                         | 목적                       |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| 1    | 어제 배운 `ERC-20` 흐름 정리 – `mint`, `transfer`, `approve`, `transferFrom`                                                                 | 개념 리마인드 및 흐름 정리 |
| 2    | "우리 어제는 ETH로 티켓을 냈었지?" → "오늘은 **토큰으로 티켓을 내는 구조**로 바꿔볼 거야!"                                                   | 도메인 전환 인식           |
| 3    | 베이스볼 게임 유저 플로우 다시 그려보기 – 화면 없이 전체 흐름을 말로 풀어 설명해보자                                                         | 전체 구조 각인             |
| 4    | **TDD #1:** `mint()` 테스트 – 오너만 토큰 발행 가능해야 한다                                                                                 | 오너 권한 체크             |
| 5    | **TDD #2:** `transfer()` 테스트 – 발행된 토큰을 유저에게 보상처럼 줄 수 있어야 한다                                                          | 초기 유저 셋업             |
| 6    | **TDD #3:** `approve()` → `transferFrom()` 테스트 – 유저가 CA에게 참가비 권한을 위임하고, <br>CA는 그걸 실제로 사용해 참가비를 가져가야 한다 | 핵심 흐름 체득             |
| 7    | **TDD #4:** `gameStart()` 테스트 – 유저가 입력값을 넣고 게임을 시작할 때, 정답이면 성공 / 틀리면 실패                                        | 게임 분기 흐름             |
| 8    | **TDD #5:** 실패한 경우 – 참가비는 누적되어 보상 풀로 들어가야 한다 (`reword += ticket`)                                                     | 보상 누적 구조 확인        |
| 9    | **TDD #6:** 정답을 맞췄다면? – 누적 보상을 유저에게 `transfer`로 지급하고 게임은 종료되어야 한다                                             | 보상 지급 + 종료 확인      |
| 10   | **TDD #7:** 10번 다 틀렸을 경우 – 게임 종료 + 오너가 `withdrawToOwner()`로 토큰을 인출할 수 있어야 한다                                      | 실패 루트 정리             |
| 11   | 전체 테스트 흐름 다시 점검 – "이 시점에서는 어떤 메서드가 호출되어야 하지?"                                                                  | 흐름 재구성                |
| 12   | **내일 수업 예고:** 오늘 구현한 흐름이 Remix + Metamask + 화면에서 어떻게 연결될지 미리 살짝 보여주기                                        | 시각적 체험 예고           |

---

## 오늘 수업의 핵심

- 오늘은 오직 **손과 머리로 흐름을 구조화하는 날**
- `approve → transferFrom → gameStart → transfer` 로 이어지는
  **토큰 기반 행동 흐름**을 직접 테스트 코드로 구현해보고,
- 내일은 이 구조를 눈으로 확인하고, 클릭으로 실행하는 수업으로 이어간다.
