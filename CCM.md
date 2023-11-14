Counter with Cipher Block Chaining-Message Authentication Code.
CBC-MAC
Encrypt then MAC 의 응용.
### MAC
![[Pasted image 20231114205524.png]]
- Nonce = 한번 쓰고 버리는 난수
- Ass. Data = 인증은 되지만 암호화되지 않는 관련 데이터 A. ex) 올바른 프로토콜 동작을 위해서 평문 형태로 전송되어야하지만 인증이 필요한 프로토콜 헤더
- Plaintext = 평문.

### Encryption
![[Pasted image 20231114210138.png]]

### 작동 방식 (암호화)
1) Nonce + Ass. Data + P를 $B_0$ 부터 $B_r$ 까지 일련의 블록으로 나눔
   - 첫번째 블록은 임시 값 및 N, A, P 의 길이를 알려주는 비트도 포함.
2) $Y_0 = E(K, B_0)$ 계산
3) i = 1 부터 r 에 대하여 $Y_i = E(K, (B_i \oplus Y_{i-1}))$ 을 계산한다.
4) 인증값 $T = MSB_{Tlen}(Y_r)$ 계산.
5) 카운터 생성 함수를 수행하여 카운터 블럭 $Ctr_0, Ctr_1, ..., Ctr_m$ 을 생성한다. 여기서 $m = \lceil \frac{Plen}{128}\rceil$ 이다.
6) j = 0 부터 m에 대하여 $S_j = E(K, Ctr_j)$를 수행한다.
7) $S = S_1||S_2||...||S_m$ 을 얻는다.
8) $C = (P \oplus MSB_{Plen}(S) || (T \oplus MSB_{Tlen}(S_0)))$ 을 반환한다.

복호화는 암호문 C, 임시 값 N, 관련 데이터 A, 키 K, 초기 카운터 $Ctr_0$ 을 가지고 역순으로 복호화한다.