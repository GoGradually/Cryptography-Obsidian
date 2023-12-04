#### Key Distribution Center
1. 세션 키
	임시 키. 일회성. short term key 라고도 불림. 한번의 논리적 세션에서의 사용 이후 버린다
2. 마스터 키
	마스터 키. 다회성. 사용자와 키 분배 센터(KDC) 가 공유함.
##### 기본 시나리오
![[Pasted image 20231128000650.png]]
1. KDC 에 B와 통신할 키 요청.
    - $ID_A||ID_B||N_1$
    - 이때 $N_1$ = 메시지의 freshness 확인용 Nonce
2. KDC는 뒤에 $N_1$ 섞어서 A의 비밀키 $K_a$ 로 암호화해 보냄
    - $E(K_a, [K_s||ID_A||ID_B||N_1]) || E(K_b, [K_s||ID_A])$
    - B의 마스터키(비밀키)로 암호화된 $Ticket = E(K_b, [K_s||ID_A])$ 도 concatenate 하여 송신
3. $E(K_b, [K_s||ID_A])$ B에게 송신
4. $K_s$ 로 잘 동작하는지 확인 ($N_2$ 사용(nonce))
5. 잘 풀렸는지 확인
    이떄 $f(N_2) = N_2 + 1$ 
- $K_s$ 가 노출되면 공격자는 A의 행세가 가능해진다