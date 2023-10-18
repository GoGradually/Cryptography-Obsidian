Pseudorandom Number Generator (PRNG)

결정론적 알고리즘 테크닉을 사용하여 난수를 생성한다
- 트루 랜덤이 아니더라도
- 통계적으로 랜덤한 수열이 생성되지 않더라도

그래서 반드시 무작위성 검증이 매우 많이 이루어져야 한다.

### PRNG의 요구조건
- 통계적 랜덤성
	항상, 일관되도록, 균등하게, 확장성
- 예측 불가능성
	[[forward unpredictability]]
	[[backward unpredictability]]
- 시드의 테스팅이 가능해야 한다.
- 보안
	시드도 무작위성을 지녀야 전혀 예측할 수 없게 된다
