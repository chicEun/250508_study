### EIP (Ethereum Improvement Proposal) vs KIP (Klaytn Improvement Proposal)

| 구분     | EIP (Ethereum)                                  | KIP (Klaytn → KAIA)            |
| ------- | ----------------------------------------------- | ------------------------------ |
| 주체     | 누구나 제출 가능 (탈중앙)                             | GRA 또는 개발자 중심의 협의체        |
| 승인 과정 | Community discussion → Core dev meeting → Merge | GRA 중심의 논의 → 내부 협의 → 승인    |
| 탈중앙성  | 매우 높음                                          | 제한적, 실용성과 속도 중심           |
| 철학     | 공통 인프라로서의 프로토콜 진화                          | 실사용 중심의 개선, 실생활 적용에 초점  |


즉, **EIP는 “공공 규격”**처럼 발전하며,**KIP는 “비즈니스 적용에 유연한 설계”**가 많다


## 기술 구조 비교: KIP-7 vs ERC-721

| 항목       | KIP-7 (KAIA)                                                       | ERC-721(Ethereum) (|                                              
| -------- | -------------------------------------------------------------- |              
| 토큰 타입    | **Fungible (대체 가능)**                                           | **Non-Fungible (대체 불가능)**                                         |
| 기준 인터페이스 | `totalSupply()`, `transfer()`, `approve()`, `transferFrom()` 등 | `ownerOf()`, `safeTransferFrom()`, `approve()`, `getApproved()` 등 |
| 주요 구조    | ERC-20과 거의 동일한 구조를 따름 + 추가 기능 (Klaytn 확장)                | 독립적인 구조, 개별 ID 관리(tokenId 기반)                                    |
| 메서드 중심성  | 금전/포인트의 **양 중심 토큰 전송**                                     | 고유 자산의 **소유권 중심                 전송**                                              |
| 토큰 추적 방식 | 토큰 수량 자체 추적 (balance)                                          | 각 tokenId의 소유자(owner) 추적                                          |
| 주요 목적    | 게임 머니, 포인트, KLAY 기반 유틸리티 토큰                                    | NFT 아트, 인증서, 부동산, 음악 등의 고유 디지털 자산                                 |

## 설계 철학과 접근 방식 차이

| 항목            | KIP (Klaytn, KAIA)        | EIP (Ethereum)                        |
| ------------- | ------------------------- | ------------------------------------- |
| 목적            | **실제 dApp 운영자가 쉽게 도입**    | **프로토콜 전체의 발전 우선**                    |
| 복잡도           | 상대적으로 단순하고 직관적            | 엄격하고 확장성 고려                           |
| 생태계 도입 장벽     | 낮음 (한국, 일본 기업들이 빠르게 도입)   | 높음 (커뮤니티 중심 채택 필요)                    |
| 공식 표준화 문서 스타일 | Klaytn Docs 기반, 사용성 중심 설명 | GitHub 기반 Proposal → 논의 → Core Dev 승인 |


## 확장성 측면에서의 차이
EIP는 매우 느리지만 탈중앙적이고 신중함이 특징
    예: ERC-4337 (Account Abstraction)은 논의만 몇 년 소요됨

KIP는 빠르게 dApp에 적용 가능한 방향으로 발전
    예: KIP-17 (NFT), KIP-37 (멀티 토큰), KIP-7 등은 KAIA 기반 dApp에 즉시 사용됨