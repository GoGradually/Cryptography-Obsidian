[[동형]]을 깨트린 RSA 알고리즘
![[Pasted image 20231011211604.png]]
평문 m 뒤에 [[패딩]]용 0 비트와 랜덤한 난수 r을 붙여
해시함수 g와 h를 지난 뒤
x와 y를 함께 암호화한다.
장점
- deterministic -> probabilistic : r이 이를 구현해낸다
- all or nothing -> G와 H가 이를 구현해낸다


![[Pasted image 20231011211733.png]]
01 : 오리지널 메시지와 라벨 해쉬 구분용 (1byte)
PS : Padding string. 길이 조절
lHash : 라벨 해쉬. label을 붙이고 이를 해쉬 함수에 통과시킴
seed : 랜덤 넘버. 해쉬의 길이와 일치시킴(224비트 이상)
MGF : Mask Generation Function. 해쉬함수같은 일을 함.
	위 MGF : seed 값을 우측 블록과 길이가 같게 만듬
	아래 MGF : 우측 블록 길이의 값을 시드와 같은 길이로 만듬
	
맨 앞 00 : n보다 길이가 작도록 맞추기용 1바이트 설정

암호문의 길이 = n의 길이


복호화 -> 들어왔던 그대로 나감