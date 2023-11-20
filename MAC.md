Message Authentication Code

"해시 함수 + 대칭 키 암호"
보낼 때 "적절한 타이밍"에 해시 함수를 메시지 뒤에 붙인다.

![[Pasted image 20231107093725.png]]

Keyed hash function 라고도 불리우며
대칭 키 암호를 이용하여 중간자 공격을 막는다.
키를 알지 못하면 문서를 아무도 모르게 가로챌 수 없다.

무결성과 인증 기능을 부여한다.

### MAC 의 표현
$MAC = C(K, M)$
$MAC = C_K(M)$
![[Pasted image 20231114153430.png]]


### MAC 의 특징
1) 암호학적 checksum이다.
2) 비밀 키 k 를 이용한다
3) 인증값이 고정된 크기로 되어있다(해시 함수의 특징)
4) many-to-one 함수이다
   - 같은 MAC 값을 가지는 메시지들이 매우 많다.
   - 그러나 현재 메시지와 같은 MAC 값을 가지는 메시지를 찾는 것이 매우 어렵다.

### MACs 의 요구사항
- 같은 MAC 값을 가지는 다른 메시지를 찾기 어려워야 한다.
- MAC값들의 분포가 균등분포여야 한다.
- MAC값은 모든 비트에 균등하게 영향받아야 한다.
### 주의할 점
MAC 는 디지털 서명이 아니다.