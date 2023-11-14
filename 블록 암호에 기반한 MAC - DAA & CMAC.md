## DAA (Data Authentication Algorithm)
![[Pasted image 20231114155717.png]]

IV = 0
마지막 $D_N$은 길이가 맞지 않으면 0으로 패딩한다
최종 출력 $O_N$ 중 MSB 16~64bit 만 활용한다.


## CMAC
M에 패딩 안해도 될 때
![[Pasted image 20231114160329.png]]

M에 패딩 필요할 때![[Pasted image 20231114160357.png]]

$k_1, k_2$ 는 $k$ 로 만든 추가 키.
$L = E(K, 0^n)$ 이라고 할 때
$K_1 = L\cdot x$ 
$K_2 = L \cdot x^2$
여기서 이 모든 연산은 $GF(2^n)$ 내에서 이루어지게 된다
-> $L\cdot x =$ 왼쪽으로 1번 쉬프트