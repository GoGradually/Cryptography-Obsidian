### 메시지 M에 대하여 기밀성과 무결성을 모두 제공하는 접근방식
- Hash-then-encrypt : 해시 후 암호화. $E(K, M||H(M))$
- MAC-then-encrypt : MAC 후 암호화. 두개의 키를 사용한다. 먼저 MAC 값을 $T=MAC(K_1, M)$ 으로 계산하여 평문을 인증한 뒤 메시지와 태그를 묶어서 암호화한다 : $E(K_2, (M||T))$.
- Encrypt-then-MAC : 암호화 후 MAC. 두개의 키를 사용한다. 먼저 메시지를 암호화하여 암호문 $C = E(K_2, M)$ 을 생성하고, $T=MAC(K_1, C)$ 로 암호문을 인증하여 쌍 (C, T)를 생성한다.
- Encrypt-and-MAC : 암호화 & MAC. 두개의 키를 사용한다. 메시지를 암호화하여 암호문 $C=E(K_2, M)$ 을 생성하고, 평문을 $T=MAC(K_1, M)$으로 인증하여 쌍 (C, T)를 생성한다.

- [[CCM]] : Encrypt-then-MAC 의 변형.
- [[GCM]] : Encrypt-and-MAC 의 변형.