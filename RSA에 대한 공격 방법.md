
- mathematical attacks
	직접 소인수 분해 하기
	->p와 q를 크게 설정하는것으로 막기 가능
- timing attacks (side channel attack)
	실제 암호가 풀리는 시간을 짐작하여
	p와 q의 크기를 추정함
	->항상 끝나는 시간을 상수처럼 만든다 : 딜레이 주기
	->랜덤한 딜레이를 추가한다
	->평문에 값을 곱하여 계산되는 값을 숨긴다 
- [[Chosen-ciphertext attacks - CCA]]
	-> 동형 특성 깨기
	->[[RSA-OAEP]]