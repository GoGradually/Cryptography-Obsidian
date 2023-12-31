ECB는 Electronic Codebook Mode의 약어로, 대칭 키 암호화에서 사용되는 암호화 모드 중 하나입니다. ECB 모드는 각 평문 블록을 독립적으로 암호화하는 가장 간단한 블록 암호화 모드 중 하나이며, 평문 블록과 동일한 크기의 암호문 블록을 생성합니다.

ECB 모드의 작동 방식은 다음과 같습니다:

1. **평문 분할**: 평문을 일정한 크기의 블록으로 분할합니다. 예를 들어, 128비트 블록 크기를 사용하는 경우, 평문은 128비트 블록으로 분할됩니다.
    
2. **블록 단위 암호화**: 각 평문 블록은 독립적으로 암호화됩니다. 즉, 평문 블록마다 동일한 암호화 알고리즘과 키를 사용하여 암호문 블록이 생성됩니다.
    
3. **암호문 생성**: 암호화된 각 블록은 암호문을 형성하며, 암호문 블록의 순서는 평문 블록의 순서와 동일합니다.
    

ECB 모드의 주요 특징 및 단점은 다음과 같습니다:

장점:

- 구현이 간단하며 병렬 처리에 용이합니다.
- 동일한 평문 블록은 항상 동일한 암호문 블록으로 변환되므로 암호화 및 복호화가 간편합니다.

단점:

- 동일한 평문 블록은 항상 동일한 암호문 블록으로 변환되므로 패턴이 있는 데이터의 경우 암호문에서 패턴을 유지하게 됩니다. 이로 인해 보안성이 저하될 수 있습니다.
- ECB 모드를 사용할 경우, 서로 다른 블록 간의 상호 작용이 없으므로 암호문의 품질이 좋지 않을 수 있습니다.
- 블록 크기를 넘어가는 데이터의 암호화에 적합하지 않습니다.

ECB 모드는 간단한 데이터 암호화에 사용될 수 있지만, 보안 요구 사항이 더 높은 경우 다른 암호화 모드를 고려하는 것이 좋습니다. 예를 들어, [[CBC]] (Cipher Block Chaining) 모드나 GCM (Galois/Counter Mode)과 같은 모드는 더 높은 보안성과 무결성을 제공합니다.![[ECB.jpeg]]