- 값을 미리 결정하지만 나중에 공표할 때까지 비밀로 하는 암호 기술.
- 중간에 값을 바꿀 수 없다.
- 해시 한 값을 공표해둔다? 안된다. 값의 조합이 이미 결정되어 있다.
- 그래서 뒤에 난수를 추가하고 해시한 값을 공표한다. 조합이 이미 정해진 형태가 되지 않도록
- 만약 생일공격 형태의 계산을 해놓고 나중에 따로 수정하면?
- 상대방이 붙일 숫자를 미리 정한다

### 해시 함수
- B->A : N1 "challenge"
- A->B : H(Value, N1, N2) "commit"
- A->B : Value, N2, "Verify"

N2 하고 Value를 이용해 생일공격 형태로 진행하면? -> 애초에 그렇게 긴 시간동안 묶어두지 않는다
짧은 시간안에 결정해야 한다.
해시함수의 강도에 보안성이 결정된다.

### 대칭 암호
- B->A : N"challenge"
- A->B : $E_K(value, N)$ "commit"
- A->B : Value, K "Verify"