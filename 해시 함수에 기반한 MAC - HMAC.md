![[Pasted image 20231114154312.png]]

$$HMAC_K(M) = Hash[(K^+\oplus opad) || Hash[(k^+\oplus ipad)||M)]]$$
$k^+$ 와 $ipad$를 xor 한 값을 M 과 붙인 뒤 해시하고
그 값을 $k^+$ 와 $opad$를 xor 한 값 뒤에 붙인 뒤 해시한다.
$k^+$ 의 의미 : k 값에 ipad, opad 값과 길이가 다르면 패딩을 붙인다는 의미
ipad : input pad 상수
opad : output pad 상수

인풋이 없어도 IV 가 있어서 해시가 계산된다.

해시는 일반적인 해시 함수 사용.
해시함수에 의해 보안이 검증된다.
키 사용에 대한 완전 탐색 공격과 [[생일 공격]] 에 면역이어야 한다.
해시는 속도와 안정성 사이에서 적절히 고려하여 결정한다.