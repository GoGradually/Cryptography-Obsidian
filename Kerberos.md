KDC 를 두개의 서버로 운영하는 방법.
- Authentication Server (AS)
- Ticket Granting Server  (TGS)
두개로 나뉘어서 운영한다.

두 서버가 같은곳에 있으면 : 사실상 KDC


![[Pasted image 20231204155009.png]]![[Pasted image 20231204155031.png]]

1. AS에서 TGS 용 Ticket을 받아와서
2. TGS 에서 V용 Ticket을 받아온 뒤
    Authenticator 를 이용하여 본인의 신원을 인증함.
3. V에게 인증 요청을 보낸다.
    Authenticator 를 이용하여 본인의 신원을 인증함.

$$Authenticator_c = E(K_{c, v},\, [ID_C||AD_C||TS_n])$$
$K_{c,v}$ :  상대방과 C 사이의 세션 키
$TS_n$  :  n번째 작업의 타임 스탬프
$AD_c$ : c의 고유 번호 (MAC Address or IP주소)