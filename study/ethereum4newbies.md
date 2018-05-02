---
layout: default
---

## 이더리움이 뭔가요? 일반인을 위한 블록체인 강좌 
- 들으면서 필기한 내용
- 영상 출처: https://www.youtube.com/watch?v=uUC3hELa-Oo
- [이더리움 백서를 봅시다](https://github.com/ethereum/wiki/wiki/White-Paper#ethereum), [한글](https://github.com/ethereum/wiki/wiki/%5BKorean%5D-White-Paper)
- 비탈릭 뷰테린에 대한 장문 기사: http://fortune.com/ethereum-blockchain-vitalik-buterin/


### 비트코인의 문제점(이자 이더리움이 나오게 된 계기)
- 튜링 불완정성: 아주 단순한 언어, 중요한 단어만 이야기한다. 
- Value-blindness: 한 번에 한 트랙잭션만 가능. 100을 보내고 5를 받아야 하니까 95만 받자, 이런게 아니라 따로따로. (이건 비트코인/블록체인 책에 더 잘 나와있는 듯)
- Lack of state: 상태 저장이 불가능. 계약을 할 때 조건을 걸어서 진행하는 게 힘들다.

- 작업증명방식의 합의 매커니즘: ASIC 채굴장비를 통한 합의 매커니즘은 큰 에너지 소모, 채굴자 중앙화 초래.
- 이더리움은 비트코인의 스크립트 언어의 한계성을 극복하기 위해 시작되었다고 생각하자.

### 비트코인 VS 이더리움
- 화폐만 하지 말고 계약 조건 등 코인 이외의 것도 하자: 스마트 계약
- 이 스마트 계약을 위해서 튜링 완전한 언어가 필요했다.
- 튜링 완전: 복잡한 것을 표현할 수 있는 언어 - 다양한 계약 조건을 구현해야 해서.
- Casper 자산 증명(Proof of Stake)을 목표로 하고 있음

### 이더리움이란? 블록체인 기반의 distributed computing 분산 컴퓨팅 플랫폼
**1. 튜링 완전**

  - 스마트 계약, 분산 어플리케이션을 구현 가능하게 하는 언어
  - 다양한 계약 조건(if문, 시간 조건, 잔고 조건, 트럼프가 당선이 된다면...)을 달 수 있다.
  - 스마트 계약이 블록체인 위에 기록된 이후에는 조건을 바꿀 수 없다.
  - 비트코인은 그 자체로 DAPP (분산 어플리케이션), 드랍박의 DAPP 버젼이 비트토렌트..
  - 이더리움이라는 블록체인 플랫폼 위에 다양한 DAPP을 지을 수 있다. 다양한 스마트 계약을 만들 수 있다.
  - DAPP의 백엔드 코드는 분산화된 P2P 네트워크에서 실행된다.

**2. 이더리움 가상 머신: Ethereum Virtual Machine**

  - world computer라고도 불린다: 전 세계의 모든 참가자(노드)가 동일한 하나의 컴퓨터를 돌리는 것과 같다. 모두가 공유하는 하나의 컴퓨터 (다 똑같은 연산, 똑같은 내용을 저장)
  - 속도/효율성은 떨어지지만, 신뢰를 얻게 될 것
  - 오라클: 인간의 개입 - 어떤 조건을 걸었을 때 그 조건의 참/거짓에 대한 대답을 주는 매개체. '트럼프가 당선이 되었다'는 사실을 누군가는 시스템에 알려줘야 하니까.
  - 다 다른 성능의 컴퓨터들을 합친 개념이니까, 당연히 성능이 떨어진다..
    - 그래서 성능 고도를 위해, 유의미한 수준까지 확장시킬 수 있느냐..? 
      - 비탈릭 뷰테린: casper, sharding 제안
      - 중앙에 있는 이더리움 블록체인의 성능을 최대한 확장시켜서 모든 사람이 쓸 수 있게 할 생각이다.
      
**2-1. 상태 변화 시스템으로서의 비트코인/이더리움**

  - 상태가 변화하는, 내 계좌 금액이 왔다갔다, 
  - 비탈릭 뷰테린: 기존 아이디어를 가지고 와서 추상화시키고 개념화하는 걸 잘함.
  - 상태: 블록 하나하나 말고, 블록 체인 - 블록들이 연결되어 있는 큰 박스를 볼 것.
    - state1: [ㅁ-ㅁ-ㅁ], state2: [ㅁ-ㅁ-ㅁ-ㅁ] 
    - state1 --> 블록 하나 추가 --> state2
    - 이걸 상태 변화라고 생각.
    - 블록을 단순 데이터의 집합이 아니라 state transition function 상태 변화 함수로 생각해라.
    - 블록을 추가하면서 상태가 바뀌는 형식이니까.
  - 새로운 블록: 거래들의 내용을 보유. 이 거래 속의 비용이 state1에 업데이트 되면 state2로 상태(계좌 + 계약 상태)가 바뀐다.
  - state: 계좌 + 계약 상태 
    - 계약 상태: 계약 코드, 이더 amount, 데이터를 포함하고 있다.
  
**3. 이더와 가스**

  - 이더: 자체 암호화 화폐 토큰
  - 가스: 스마트 계약을 돌리기 위해 필요한 연료. 이더로 가스를 구입. 가스로 이더리움의 자원(연산력, 저장공간, 네트워크 사용량)을 사용
  - 
