![[Pasted image 20231114215135.png]]

해쉬 키 H와 비트 스트링 X를 입력으로 하여 128비트 MAC 값을 생성하는 함수.

1) $X = X_1 || X_2 || \cdots || X_M$ 인 고유한 일련의 블럭이라고 할 때
2) $Y_0$ 은 128개의 0으로 구성된 블럭, 즉 $0^{128}$ 이라고 하면
3) i = 1 부터 $Y_i = (Y_{i-1} \oplus X_i)\cdot H$ 라고 할 때, 여기서 곱셈은 $GF(2^{128})$ 위에서의 곱셈이다.
4) $Y_m$을 반환한다.

해당 함수는 다음과 같이 표현된다.
$$Y_m = ((\cdots(X_1 \cdot H \oplus X_2)\cdot H \oplus X_3)\cdots \oplus X_m)\cdot H$$
$$= X_1\cdot H^M \oplus X_2\cdot H^{m-1} \oplus \cdots \oplus X_M\cdot H$$
이를 이용해 $GHASH_H(X)$ 값을 병렬 연산으로 구할 수 있게 된다.
