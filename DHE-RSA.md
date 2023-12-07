Ephemeral Diffie-Hellman with RSA
일회용 디피 헬만 + RSA

static Diffie-Hellman 과 반대

중간자 공격을 막을 수 있다...? 어째서 ? 난수 넣나?
-> RSASSA-PSS 를 사용해서 인증을 한다!!


- Client -> Server : Client hello
- Server -> Client : $g, p, g^x, nonces, RSASign, Certificate_s$
    - RSASign : 인증값 넣어서 보내기
    - Certifiate :인증서(공개키와 내 공개키가 맞다는 인증서)
- Client->Server : $g^y$

- pre-master secret : $g^{xy} \, mod\, p$
- 근데 이걸 바로 비밀키로 쓰지 않고 Pseudo Random Function 에 집어넣음 
- PRF(pre-master key) : master secret
- PRF(master secret, nonce) : session key

### 전방향 안정성(Perfect Forward Secrecy)
- long term secrets 가 드러나더라도 그동안 만든 세션 키는 여전히 비밀로 유지되는 성질
- DHE-RSA 는 이 성질을 가지고 있다.