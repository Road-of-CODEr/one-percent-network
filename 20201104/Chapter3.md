# Chapter 3. 케이블의 앞은 LAN 기기였다

> 허브와 스위치, 라우터의 탐험

1. 케이블과 리피터, 허브 속을 신호가 흘러간다

2. 스위칭 허브의 패킷 중계 동작

3. 라우터의 패킷 중계 동작

4. 라우터의 부가 기능

---



## 케이블과 리피터, 허브 속을 신호가 흘러간다.

### 하나하나의 패킷이 독립된 것으로 동작한다

- 컴퓨터에서 송신된 패킷을 허브나 라우터라는 중계 장치에 의해 중계되어 목적지를 향해 진행한다.

- 중계 장치는 데이터 부분을 보지 않고 패킷을 중계한다. 즉, 모든 패킷은 아무 관련도 없는 별개의 겻으로 간주하고 목적지를 향해 중계된다.



1. 클라이언트 PC의 LAN 어댑터
2. 리피터 허브
3. 스위칭 허브
4. 라우터
5. 인터넷 접속용 라우터
6. 인터넷



### LAN 케이블은 약화시키지 않는 것이 핵심이다

> LAN 어댑터에서 패킷이 송신되어 케이블로 나가는 부분부터 시작된다



1. LAN 버퍼 메모리
2. LAN 어댑터의 MAC
3. LAN 어댑터의 PHY(MAU)
4. LAN 어댑터의 RJ-45 커넥터
5. LAN 케이블
6. 리피터 허브의 RJ-45 커넥터
7. 리피터 허브의 PHY(MAU) 
8. 리피터 회로



- LAN 어댑터의 PHY(MAU) 회로에서 전기 신호로 형태를 바꾼 패킷은 RJ-45 커넥트를 통해 트위스트 페어 케이블에 들어간다 - [RJ-45 connector](https://www.fs.com/products/72934.html)
- LAN 어댑터의 PHY 회로는 RJ-45 커넥터에 직접 결선되어 있으므로 커넥터의 1번 핀과 2번 핀에서 케이블로 신호가 흘러나간다. 신호는 케이블 속을 흘러 리피터 허브의 커넥터 부분에 도착하고, 이 부분은 단순히 전기 신호가 케이블을 통해 전달 되는 것이다.
- 송출된 신호는 그대로의 모습으로 허브에 도착하는 것이 아니라 허브에 도착할 때는 신호가 약해져 있다. 케이블이 길어 질수록 신호가 약해진다.
- 약해진 신호는 변형되기에 0과 1을 잘 못 판단할수 있고, 이것이 통신 오류의 원인이 된다.



### '꼼'은 잡음을 방지하기 위한 방법이다

![2575C633529FCF4931](https://user-images.githubusercontent.com/46305139/97886266-baf11500-1d6b-11eb-928d-4d8d14240699.png)

**잡음의 원인**

- 잡음의 원인은 케이블의 주위에서 발생하는 전자파이다.
- 전자파가 금속 등의 도전체에 닿으면 그 안에 전류가 발생한다는 성질이 있다.
- 그래서 케이블의 주위에 전자파가 있으면 신호와는 다른 전류가 케이블 안에 흐른다. 그 결과 신호와 잡음의 전류가 뒤섞여서 신호의 파형이 변형된다.

**케이블에 영향을 받는 전자파 두 종류**

1. 모니터, 형광등에서 누설되는 전자파
   - 케이블의 밖에서 오는 것으로, 선을 꼼으로써 막을 수 있다.
   - 금속에 전자파가 닿으면 전자파 진행 방향의 오른쪽으로 전류가 생긴다. 신호선을 마주 꼬면 형태가 나선형이 되어 꼰 옆의 선에서 전류가 흐르는 방향이 반대가 된다. 그 결과 잡음에서 생긴 전류가 서로 상쇄되어 잡음에 의한 전류는 약해진다.

2. 같은 케이블 안의 인접한 신호선에서 누설되는 전자파
   - 신호도 전류이므로 전류에 의해 주위에 전자파가 생긴다. 이런 잡음에 대한 영향을 크로스토크라고 한다.
   - 한 개의 케이블에 넣은 신호선을 '꼬는' 간격은 모두 같은 것이 아니라 약간씩 다르다. 꼬는 간격을 미묘하게 변화시키면 어떤 부분에서는 플러스 신호가 가까이에 있고, 다른 부분에서는 마이너스 신호선이 가까워진다. 그러면 플러스와 마이너스에서는 잡음의 영향이 반대가 되므로 플러스와 마이너스의 균형이 잡히면서 잡음의 영향이 줄어든다.
   - 신호선 사이의 거리를 유지하기 위해 신호선 사이에 구분판을 넣거나 전자파를 차단하기 위해 금속성의 실드라는 피복을 입히는 등 여러 대책이 있다.



### 리피터 허브는 연결되어 있는 전체 케이블에 신호를 송신 한다

![리피터](https://user-images.githubusercontent.com/46305139/97891078-ae6fbb00-1d71-11eb-90cc-8acef803a2a0.jpg)

- 물리 계층에서 동작하는 장치

- 신호가 리피터 허브에 도착하면 LAN 전체에 신호가 흩어진다.

- 각 커넥터의 안쪽에 LAN 어댑터 내부에 있는 PHY(MAU) 회로와 역할이 같은 회로가 있다. 제대로 수신하려면 '송신 단자'에서 보낸 신호를 '수신 단자'로 받도록 해야한다. 이 때문에 허브 안에서 PHY의 회로와 커넥터 사이의 신호선을 교차시켜서 접속한다.

- 리피터 허브에서 PHY 회로의 수신부에 도달한 신호는 여기부터 리피터 회로에 들어간다. 리피터 회로의 기본은 들어오는 신호를 리피터 허브의 커넥터 부분에 뿌리는 데 있다. 기본적으로 들어온 신호를 그대로 커넥터 부분에 송출한다.

- 신호는 모든 커넥터에서 나가면서 리피터 허브에 접속한 전체 기기에 도달한다. 신호를 수신한 기기는 맨 앞에 있는 MAC 헤더에 쓰여 있는 수신처 MAC 주소를 조사하여 자신이 수신처에 해당하면 이것을 수신하고, 해당하지 않으면 수신한 신호를 무시한다.

- 리피터 회로의 기본은 신호를 그대로 뿌리는 것이다. 잡음의 영향을 받아 데이터가 변화한 것 같은 신호라도 그대로 흘려버린다.



## 스위칭 허브의 패킷 중계 동작

### 스위칭 허브는 주소 테이블로 중계한다

| MAC 주소          | 포트 | 제어 정보 |
| ----------------- | ---- | --------- |
| 00-60-97-A5-43-3C | 2    | ...       |
| 00-00-C0-16-AE-FD | 7    | ...       |
| 00-02-B3-1C-9C-F9 | 8    | ...       |
| ...               | ...  | ...       |



- 스위칭 허브는 이더넷의 패킷을 그대로 목적지를 향해 중계하도록 만들어져 있다.

- 신호가 커넥터 부분에 도달하여 PHY 회로에서 수신되는 부분까지는 리피터 허브와 같다. 트위스트 페어 케이블에서 신호가 들어오면 이것이 PHY 회로의 수신 부분에 들어간다.

- PHY 회로에서 케이블을 흐르는 신호의 형식부터 공통의 신호 형식으로 변환한 후 신호는 MAC 회로로 들어간다. 여기에서 디지털 데이터로 변환한 후 패킷의 맨 끝에 있는 FCS를 대조하여 문제가 없으면 버퍼 메모리에 저장한다.

- 커넥터와 안족에 있는 회로 부분을 포트라고 부른다. 스위칭 허브의 각 포트는 PC의 LAN 어댑터와 거의 같다.

- 반면 스위칭 허브의 포트는 수신처 MAC 주소를 검사하지 않고 모든 패킷을 수신하여 버퍼 메모리에 저장하기 때문에 스위칭 허브의 포트에는 LAN 어댑터와 달리 **MAC 주소가 할당되어 있지 않음**

- 패킷을 버퍼 메모리에 저장하면 다음에 수신처 MAC 주소와 일치하는 것이 MAC 주소표에 등록되어 있는지 조사한다.

- 송신 측의 포트에 패킷을 운반하면 MAC 회로나 PHY 회로가 송신 동작을 실행하고 케이블에 신호가 흘러간다

 

### MAC 주소 테이블을 등록 및 갱신한다

> 스위칭 허브는 패킷을 중계할 때 MAC 주소표의 내용을 갱신하는 동작도 실행한다.

**갱신동작**

1. 패킷 수신 시 송신처 MAC 주소를 조사하고, 이것을 수신한 입력 포트 번호와 하나의 세트로 MAC 주소표에 등록하는 것. 한번이라도 패킷을 송신하면 해당 기기의 MAC 주소가 MAC 주소표에 등록된다.

2. 등록되어 있는 내용을 지우는 동작. MAC 주소표에 등록한 정보는 그대로 두지 않고 사용 후 일정 시간이 경과하면 삭제한다.



### 예외 상황

- 주소표에 등록되어 있는 송신 포트가 패킷을 수신한 포트와 같을 경우 스위칭 허브는 패킷을 수신한 포트와 송신하는 포트가 같은 경우 패킷을 폐기한다.
- MAC 주소표에 수신처 MAC 주소와 일치하는 주소가 등록되어 있지 않은 경우, 패킷을 수신한 포트 이외의 전체 포트에서 패킷을 송신한다.

- 수신처 MAC 주소가 브로드캐스트 주소인 경우에도 수신 포트를 제외하고 모든 포트에서 패킷을 송신한다.

 

## 라우터의 패킷 중계 동작

### 라우터의 기본

- 리피터 허브나 스위칭 허브를 경유한 패킷은 라우터에 도착하고, 라우터에서 다음 라우터로 중계된다
- 구체적인 동작은 스위칭 허브와 다른데, 이것은 라우터의 바탕이 되는 **IP**라는 개념에 스위칭 허브의 바탕이 되는 이더넷과 다르기 때문이다.
- 라우터는 **중계 부분**과, **포트 부분**이라는 두 부분으로 구성되어있다.
  - 중계 부분 : 패킷의 중계 대상을 판단하는 동작을 담당 - 프로토콜 스택의 IP 담당 부분
  - 포트 부분 : 패킷을 송수신하는 동작을 담당 - LAN 어댑터
- 라우터의 각 포트에는 **MAC 주소**와 **IP 주소**가 할당되어 있다



### 경로표에 등록된 정보

| 수신처       | 넷마스크        | 게이트웨이 | 인터페이스 | 메트릭 |
| ------------ | --------------- | ---------- | ---------- | ------ |
| 10.10.1.0    | 255.255.255.0   | ---        | e2         | 1      |
| 10.10.1.101  | 255.255.255.255 | ---        | e2         | 1      |
| 192.168.1.0  | 255.255.255.0   | ---        | e3         | 1      |
| 192.168.1.10 | 255.255.255.255 | ---        | e3         | 1      |
| 0.0.0.0      | 0.0.0.0         | 192.0.2.1  | e1         | 1      |



- 라우터는 IP 헤더에 기재되어 있는 수신처 IP 주소로 중계 대상을 판단한다.

- 라우터의 테이블은 **라우팅 테이블** 또는 **경로표**라고 부른다.
- 라우터는 호스트 번호를 무시하고 네트워크 번호 부분만 조사한다

**라우터의 경로표에 경로 정보를 등록하는 방법**

- 사람이 수동으로 경로 정보를 등록/갱신
- 라우팅 프로토콜이라는 구조를 사용하여 라우터들끼리 경로 정보를 교환하고 라우터가 자체에서 경로표에 등록



### 라우터의 패킷 수신 동작

- 이더넷의 포트 부분의 구조는 PC의 LAN 어댑터와 거의 같으므로 패킷을 수신하여 버퍼 메모리에 저장하는 부분까지의 동작도 LAN 어댑터와 거의 같다.
- 신호가 커넥터 부분에 도착하면 안쪽에 있는 PHY 회로와 MAC 회로에서 신호를 디지털 데이터로 변환한다. 그리고 패킷 끝부분의 FCS를 대조하여 오류의 유무를 점검하고, 정상일 경우 MAC 헤더의 수신처 MAC 주소가 자신에게 해당하는지 조사하여 해당하면 패킷을 수신 버퍼 메모리에 저장한다. 해당하지 않을 경우 패킷은 폐기된다.



### 경로표를 검색하여 출력 포트를 발견한다

- 라우터는 패킷 수신 동작이 끝나면 맨 앞의 MAC 헤더를 폐기한다.
  - MAC 헤더의 역할을 이 라우터에 패킷을 건네주는 것이기 때문에 패킷을 수신하면 역할이 끝난다
- IP 헤더의 내용을 보고 패킷 중계 동작에 들어간다.
  - 라우팅 테이블을 조사하여 중계 대상을 선택한다
  - 복수의 후보가 발견될 때
    - 네트워크 번호의 비트수가 가장 긴것
    - 메트릭 값이 작은 쪽
  - 한 개도 발견 되지 않는 경우
    - 패킷을 폐기하고, ICMP 메시지로 송신처에 이 사실을 통지
      - 스위칭 허브와 달리, 라우터가 가정하는 네트워크는 매우 크므로, 모든 포트에 패킷을 뿌리면 네트워크 혼잡을 초래할수 있다



**해당하는 경로가 없는 경우**

- 넷마스크 0.0.0.0인 행은 '기본 경로'를 나타낸다



### 패킷은 유효 기간이 있다

- 패킷에는 IP 헤더에 TTL이라는 필드가 있다.
- 라우터를 경유할 때 마다 -1, 즉 0 이 되면 패킷을 폐기한다
- 패킷이 같은 장소를 순환하는 사태를 막기위해
- 주로 64또는 128로 설정한다
- 인터넷은 지구 반대편까지 액세스해도 경유하는 라우터 수가 많아야 수십개 정도이다



### 라우터의 송신 동작은 컴퓨터와 같다

- MAC 헤더를 부가한다
  - ARP로 IP 주소에서 MAC 주소를 조사하여 결과를 수신처 MAC 주소로 설정한다
- 송신패킷을 전기신호로 변환하여 포트에서 송신한다



## 라우터의 부가 기능

### 주소 변환으로 IP 주소를 효율적으로 이용한다

**IP 주소의 두가지 종류**

1. 프라이비트 주소 (private address)
   - 독립되어 있는 사내 네트워크

| RFC1918 이름 |         IP 주소 범위          | 주소 개수  | [클래스](https://ko.wikipedia.org/wiki/네트워크_클래스) 내용 | 최대 [사이더](https://ko.wikipedia.org/wiki/사이더_(네트워킹)) 블록 (서브넷 마스크) | 호스트 ID 크기 |
| :----------: | :---------------------------: | :--------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :------------: |
| 24비트 블록  |   10.0.0.0 – 10.255.255.255   | 16,777,216 |                        클래스 A 하나                         |                    10.0.0.0/8 (255.0.0.0)                    |    24 비트     |
| 20비트 블록  |  172.16.0.0 – 172.31.255.255  | 1,048,576  |                     16개의 인접 클래스 B                     |                 172.16.0.0/12 (255.240.0.0)                  |    20 비트     |
| 16비트 블록  | 192.168.0.0 – 192.168.255.255 |   65,536   |                    256개의 인접 클래스 C                     |                 192.168.0.0/16 (255.255.0.0)                 |    16 비트     |

2. 글로벌 주소(global address)
   - 고유한 주소



---



![pa](https://user-images.githubusercontent.com/46305139/97906483-167ccc00-1d87-11eb-8363-eee9a41ec345.jpg)

사내 네트워크에는 프라이비트 주소를 할당하고 인터넷과는 직접 패킷을 주고받지 않도록 특별한 구조를 사용하여 접속하는데, 이 구조가 주소 변환이다.



### 주소 변환의 기본 동작

- IP 주소와 포트 번호를 바꿔쓴다

| 글로벌 주소 | 포트 번호 | 프라이비트 주소 | 포트 번호 |
| ----------- | --------- | --------------- | --------- |
| 198.18.8.31 | 5436      | 10.10.1.1       | 1025      |
| 198.18.8.31 | 5437      | 10.10.1.2       | 1025      |
| 198.18.8.31 | 5438      | 10.10.1.3       | 2538      |
| ...         | ...       | ...             | ...       |





