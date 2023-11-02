### 준비
1) 평문 M을 $E$ 위의 점 $P_m$ 으로 바꾼다
   - M을 converting 하는 방법에는 여러가지가 있다.
   - 아직 다루지 않는다
2) 적절한 E와 G를 [[ECC Diffie-Hellman]] 방식으로 고른다
3) 각 유저는 비밀 키 $n_A < n$ 을 지정한다.
4) $P_A = n_AG$ 를 계산한다.

### 암호화
- $P_m : C_m = \{kG, P_m + kP_A\}$ 로 암호화
- k 값은 랜덤

### 복호화
- $P_m = P_m + kP_A-n_A(kG) = P_m + k(n_AG) - n_A(kG) = P_m$
- 단순 덧 뺄 곱 나 로 보이는 주제에 trapdoor one way다 ㄷㄷ