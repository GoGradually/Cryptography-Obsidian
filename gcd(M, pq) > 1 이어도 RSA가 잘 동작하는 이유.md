1. [[중국인의 나머지 정리]]를 이용하여 해의 존재성을 증명하고 싶다.
   - gcd(M, pq) = 1 일때는 오일러 정리에 의해서 해가 존재한다
   - gcd(M, pq) > 1 일때는?
     만약 $M^{e^d} \equiv M \,(mod\, pq)$ 이려면  
     $M^{e^d} \equiv M \, (mod\, p)$와 
     $M^{e^d} \equiv M \, (mod\, q)$ 가 모두 성립해야 함.
2. $M^{e^d} \equiv M \, (mod\, p)$일 때
   - M = kp 이므로
     (gcd(M, pq) > 1 이면 gcd(M, pq) = p 또는 q 이어야 함. 여기선 p라고 가정)
   - $0 \equiv 0 \, (mod \, p)$ 가 성립함
3. $M^{e^d} \equiv M \,(mod\,q)$ 일 때
   - $M^{ed} \equiv M \, (mod\, q)$
   - $M^{ed - 1} M \equiv M\,(mod\,q)$
   - $ed \equiv 1 \, (mod\, \phi(n))$
     e와 d는 $modulo \, \phi(n)$ 에서 역수관계
   - 그러므로 $ed = k(p-1)(q-1) + 1$ (k는 임의의 정수)
   - $M^{k(p-1)(q-1)}M \equiv M \,(mod\,q)$
   - $M^{(q-1)^{k(p-1)}} M \equiv M(mod\, q)$
   - $1^{k(p-1)}M\equiv M(mod\, q)$
     $gcd(M, q) = 1$이므로
     페르마의 작은 정리 적용 가능
     - $M \equiv M(mod q)$
4. 그러므로 중국인의 나머지 정리에 의해
   $M^{e^d}\equiv M \,(mod\, pq)$ 을 만족하는 해가 존재한다.
Q.E.D.
