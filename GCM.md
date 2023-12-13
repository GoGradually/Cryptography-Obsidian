Galois Counter Mode 
(Galois Counter Mode Message Authentication Code)

두가지 함수 GHASH 와 GCTR 을 통해 암/복호화 된다.

- [[GHASH]]
- [[GCTR]]

### 인증 암호 함수 구현
![[Pasted image 20231114223029.png]]
$[x]_s=$ 음이 아닌 정수 x 의 s 비트 이진 표현 
1. $H = E(K, 0^{128})$ 이라고 하자. (AES 로 암호화)
2. 블럭 $J_0$ 을 다음과 같이 정의하자.
   - $len(IV) = 96$ 이면, $$J_0 = IV || 0^{31} || 1$$
   - $len(IV) \ne 96$ 이면, $s = 128 \lceil \frac{len(IV)}{128} \rceil - len(IV)$ 라 할 때,$$J_0 = GHASH_H(IV||0^{s+64}||[len(IV)]_{64})$$
3. $C = GCTR_K(inc_{32}(J_0), P)$ 라 하자.
4. $u = 128 \lceil \frac{len(C)}{128} \rceil - len(C)$ 이고, $v = 128 \lceil \frac{len(A)}{128} \rceil - len(A)$라 하자.
5. 블럭 S를 다음과 같이 정의한다. $$S = GHASH_H(A||0^v||C||0^u||[len(A)]_{64}||[len(C)]_{64}$$
6. $T = MSB_t(GCTR_K(J_0, S))$ 라 할 때, (여기서 t 는 지원되는 태그 길이)
7. $(C, T)$ 를 반환한다.