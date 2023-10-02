![[Pasted image 20230929144008.png]]
Tweak 변수와 평문에 모두 AES를 적용하는 알고리즘

주로 대용량 저장 장치의 암호화에 사용(ex : Cloud sevice)

i 가 섹터 넘버, j가 블록 넘버라고 했을 때
블록 넘버 및 섹터 넘버를 Tweak 변수를 만드는데 활용하는 모습을 확인할 수 있다.

특징으로는
- 병렬 암호화
- 임의 접근
- 서로 다른 소유주의 동일한 데이터에 대하여 다른 암호문이 나오도록 할 수 있음
이 가능하다.