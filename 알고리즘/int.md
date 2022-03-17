## 숫자 관련 알고리즘

### 소수
1보다 큰 자연수 중 1과 그 수 자기 자신만을 약수로 갖는 자연수

소수가 중요한 이유는 암호화 때문이다.

#### RSA 암호화 방식


### 소인수분해
소수로 이루어진 곱으로 표현하는 방법

### 유용한 함수
```java
// 소수 판별
public boolean isPrime(int num) {
    
    // 0, 1은 소수가 아니다.
    if(num < 2) return false;

    // 주어진 자연수의 제곱근 까지만 for문을 실행하면 된다.
    for(int i = 2; i <= Math.sqrt(num); i++){
        if (num % i == 0) {
            return false;
        }
    }

    return true;
}
```