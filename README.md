# 화폐
서울에서 페소, 달러 등의 외화는 거래 수단이 되지 못하지만, 원화는 모두가 인정하며 사용한다. **즉, 돈은 그 자체로 가치 있는 것이 아닌, 사용 되는 장소의 공동체가 그것을 '신뢰'하고 '보증'** 하기 때문에 ***가치 있는 것이다.***

- [Blockchain](#blockchain)
- [NFT](#nft)
- [Ethereum](#ethereum)
- [MetaMask](#metamask)
- [Solidity](#solidity)
- [코인 만들기](#코인-만들기)
---
## Blockchain
- block : 데이터를 저장하는 단위
- chain : block들을 해시함수로 연결한다. 합의 알고리즘 기반의 Linked List형태로 이어준다.
    - 비가역성 : 이미 일어난 일은 되돌리기 어려움.
        - y=f(x) 에서 x로 y를 찾는 것 보다 **y를 x로 찾기는 쉽지 않다.**
        - 빨간 색과 흰색을 섞으면 핑크색이 나오는데, **핑크색을 보고 무슨 색이 섞여서 만들어진 건지 찾기는 힘들다.**
    - 합의 알고리즘 : 다수의 참여자들이 통일된 의사결정을 하기 위해 사용. **결정론적 방식.** 
    - 정격체인 Canonical Chain : 블록체인의 마지막 체인을 의미하며 시작부터 일련의 거래를 유일하게 보증할 수 있다.
### 비잔틴 장애 허용 Byzantine Fault Tolerance, BFT
체인의 branch 중에, 위조된 노드가 전체의 3분의 1을 넘기지 않는다면, 이를 제외하고 정직한 합의에 성공할 수 있게끔 한다.

---

## NFT
Non-Fungible Token 으로 [블록체인](#블록체인)에 저장된 데이터 단위다. 이름 그대로 고유하며 사진, 비디오, 오디오 등 디지털 파일을 나타내는데 사용할 수 있다.

### 폴리곤
최초의 이더리움 호환 블록체인 네트워크 프로토콜이다. 이더리움의 확장 버전으로 기존의 낮은 처리량, 높은 가스비(폴리곤은 무료) 등 이더리움의 한계점을 보완해준다. 
- 직접 만든 폴리곤 기반의 NFT
    - [a](https://opensea.io/assets/matic/0x2953399124f0cbb46d2cbacd8a89cf0599974963/53652640495268935322357122152175540049246147142487809100132255691111630110721)
    - [b](https://opensea.io/assets/matic/0x2953399124f0cbb46d2cbacd8a89cf0599974963/53652640495268935322357122152175540049246147142487809100132255692211141738506)

---
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

## Solidity
계약 지향 프로그래밍 언어로 블록체인 프랫폼의 Smart Contract 작성 및 구현에 사용된다.
- 상태 변수 : DB의 데이터처럼, 이더리움의 블록체인(Contract 저장소)에 영구적으로 저장 된다.
    - `uint` : 부호 없는 정수로, 양수만 가능.
        ```solidity
        uint myUnsignedInteger = 100; 
        ```
- `**` : 지수 연산
    ```solidity
    uint myTest = 10**2;    // 100
    ```
- 구조체 : 사용자 정의 타입
    ```solidity
    struct 구조체명{
        타입 변수명,
        타입 변수명
    }
    ```
- 배열 : 정적/동적 배열, 구조체 배열, Public Arrays.
    ```solidity
    uint[2] fixedArray;     // 2개의 원소를 담을 수 있는 정적 배열
    uint[] dynamicArray     // 동적 배열
    Person[] people         // 동적 배열로써 원소를 계속 추가할 수 있다.
    
    Person[] public people  // public으로 배열 선언. 솔리디티가 자동으로 getter메소드 생성.
    // 다른 Contract가 해당 배열을 읽을(쓰기x) 수 있으며 공개 데이터를 저장할 때 사용.
    ```
    - push 참고
    ```solidity
    Person satoshi = Person(172, "Satoshi");
    people.push(satoshi);
    // 위 두 줄을 아래와 같이 사용 가능
    people.push(Person(16, "Vitalik"));
    ```

- 함수 : 기본적으로 public으로 선언된다.
    - 매개변수 관례 : 언더바(_)를 사용하여 전역 변수와 구별. 필수는 아님.
        ```solidity
        function order(string _name, uint _amount) {}
        ```
    - private 선언 : 함수명 다음에 작성하며, 함수명 또한 언더바(_)로 시작하여 public 함수와 구별한다.
        ```solidity
        uint[] numbers;

        function _addToArray(uint _number) private {
            numbers.push(_number);
        }
        ```
    - 반환값 : 반환 필요 시 `returns`과 자료형 선언
        ```solidity
        function Hello() public returns (uint) { 
            return 1;
        }
        ```
    - keccak256 : SHA3의 한 버전인 내장 해시 함수. 입력 스트링을 **256비트 16진수**로 매핑한다.
- 함수 제어자
    - `view` : 데이터를 조회만 할 뿐 변경하지 않음을 의미한다.
        ```solidity
        function sayHello() public view returns (string) {}
        ```
    - `pure` : 함수가 조회를 포함한 어떤 접근도 하지 않음을 의미하며 인자에 따른 반환값 변동만이 존재한다.
- 형 변환
    ```solidity
    uint8   a = 5;
    uint    b = 6;
    
    uint8 c = a * b;
    // a * b는 uint8이 아닌, uint를 반환하기 때문에 에러.
    
    uint8 c = a * uint8(b);
    ```
- 이벤트
    ```solidity
    // 이벤트 선언
    event IntegersAdded(uint x, uint y, uint result);
    
    ```
    
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
