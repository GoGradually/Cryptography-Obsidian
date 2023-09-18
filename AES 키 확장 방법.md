![[Key Expansion.jpeg]]
$$g(w_3) = SBox(LRotWord(w_3))  \oplus  RCon_i$$
$$w_4 = w_0\oplus g(w_3)$$
$$w_5 = w_1 \oplus w_4$$
$$w_6 = w_2 \oplus w_5$$
$$w_7 = w_3 \oplus w_6$$
이후 재귀적으로 적용
$Rot$ = 로테이션
$LRot$ = 왼쪽으로 Rot

$RCon_i$ = 라운드 상수(라운드마다 정해진 상수)
-> 라운드 상수 테이블이 존재함.

키 확장이 제대로 됐나 -> 테이블 존재

ex)
w3 = af 7f 67 98
w0 = 0f 15 71 c9

LRotWord(w3) = 7f 67 98 af = x1
S-Box(x1) = d2 85 46 79