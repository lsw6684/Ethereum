# 화폐
서울에서 페소, 달러 등의 외화는 거래 수단이 되지 못하지만, 원화는 모두가 인정하며 사용한다. **즉, 돈은 그 자체로 가치 있는 것이 아닌, 사용 되는 장소의 공동체가 그것을 '신뢰'하고 '보증'** 하기 때문에 ***가치 있는 것이다.***

- [Blockchain](#blockchain)
- [Ethereum](#ethereum)
- [MetaMask](#metamask)
- [코인 만들기](#코인-만들기)
- [NFT](#nft)
---
## Blockchain
- block : 데이터를 저장하는 단위
- chain : block들을 해시함수로 연결한다. 합의 알고리즘 기반의 Linked List형태로 이어준다.
    - 비가역성 : 이미 일어난 일은 되돌리기 어려움.
        - y=f(x) 에서 x로 y를 찾는 것 보다 **y를 x로 찾기는 쉽지 않다.**
        - 빨간 색과 흰색을 섞으면 핑크색이 나오는데, **핑크색을 보고 무슨 색이 섞여서 만들어진 건지 찾기는 힘들다.**
    - 합의 알고리즘 : 다수의 참여자들이 통일된 의사결정을 하기 위해 사용. **결정론적 방식.** 
    - 정격체인 Canonical Chain : 블록체인의 마지막 체인을 의미하며 시작부터 일련의 거래를 유일하게 보증할 수 있다.
### 비잔틴 오류 허용 Byzantine Fault Tolerance, BFT
체인의 branch 중에, 위조된 노드를 제외하여 정직한 합의에 성공할 수 있음을 의미한다.

## Ethereum
이더리움은 계약을 만들어 주는 블록체인으로 **Smart Contract Flatform**이라 하며, 그 결과는 토큰으로 만들어진다. 이 토큰을 하나만 발행한 것이 [NFT](#nft)이고 **메타버스**의 거래 수단으로 사용된다. <br />

CS관점으로 설명하면, 이더리움은 경정론적이지만, 한정되지 않은 상태 머신이며, 이것은 전역적으로 접근 가능한 싱글톤 상태와 그 상태를 변화시킬 수 있는 가상 머신으로 구성된다.

우리는 이더리움 플랫폼으로 탈중앙화된, 안전하고 혁신적인 경제 수단을 만들 수 있다.
- 화폐 단위 : 이더, ETH
- 지갑 : 사용자의 키를 보유하고 트랜잭션을 생성하여 **브로드캐스트**를 한다.
- 보안 책임 : 계정은 하나의 개인키로 볼 수 있다. 즉, 분실하면 접근 권한을 회복해 줄 수 없으며 자금을 찾을 수도 없다.
- GAS : 계산할 때 필요한 컴퓨팅 자원으로 일종의 수수료다. 거래를 하기 위해 많은 계산을 할 수록 더 많은 gas비를 내야한다. 이 gas비는 계산을 수행한 채굴자가 취득한다.

---
## MetaMask
브라우저에서 실행되는 확장 지갑으로 다양한 이더리움 노드와 테스트 블록체인에 연결할 수 있는 웹 기반 지갑이다.

---

## 코인 만들기

### Remix
솔리디티 언어를 사용하여 **스마트 컨트랙트**를 컴파일/테스트/디버깅/배포할 수 있는 통합 개발 환경.

### OpenZeppelin
이더리움 네트워크의 모듈식 및 재사용 가능한 **Smart Contract** 세트에 대한 액세스를 제공하는 패키지.

### ERC-20
Ethereum Request for Comment 20 로 코인의 표준 중 하나다. 

```solidity
pragma solidity ^0.8.0; // 버전

// 오픈제플린 무설치
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol";

// is - 상속
contract MyToken is ERC20 {
    // 생성자. 이름, 심볼
    constructor(string memory name, string memory symbol) ERC20(name, symbol) {
        // mint 1000개
        // msg.sender 만든 사람
        // 10의 18승, 1 이더 단위
        _mint(msg.sender, 1000*10**uint(decimals()));
    }
}
```
- Deploy
    - Injected Web3로 크롬 기반의 메타마스크를 연동.
    - 메타마스크 승인.
    - 트랜잭션 진행.

## NFT
- [a](#https://opensea.io/assets/matic/0x2953399124f0cbb46d2cbacd8a89cf0599974963/53652640495268935322357122152175540049246147142487809100132255691111630110721)
- [b](#https://opensea.io/assets/matic/0x2953399124f0cbb46d2cbacd8a89cf0599974963/53652640495268935322357122152175540049246147142487809100132255692211141738506)