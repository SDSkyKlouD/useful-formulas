정수론 관련
===========

최대공약수 (GCD<sup>Greatest Common Divisor</sup>)
----------------
0이 아닌 정수들의 공약수 가운데 가장 큰 하나.  
예시로, $24$와 $18$의 공약수는 $1, 2, 3, 6$인데, 이 중 가장 큰 수인 $6$이 $24$와 $18$의 최대공약수이다.

### 알고리즘
최대공약수를 구하기 위한 알고리즘으로 보통 [유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)을 사용한다. 이 알고리즘은 반복에 의존한다.

#### C언어
```C
// 재귀 함수 형태
int gcd(int a, int b) {
    return b ? gcd(b, a % b) : a;
}
```

```C
// while 반복문 형태
int gcd(int a, int b) {
    int temp;
    while(b) {
        temp = a % b;
        a = b;
        b = c;
    }
    return a;
}
```

#### 파이썬
```Python
# 재귀 함수 형태
def gcd(a, b):
    return gcd(b, a % b) if b else a
```

```Python
# while 반복문 형태
def gcd(a, b):
    while b != 0:
        if a < b:
            a, b = b, a
        if b == 0:
            return a
        if a % b == 0:
            return b
```

#### 트리비아
나머지를 활용한 방법을 주로 쓴다. 유클리드 호제법은 원래 뺄셈을 이용하는 방식이였는데, 이 경우는 시간 복잡도가 $O(n)$이 되어 잘 사용하지 않는다.  
나머지를 이용한 유클리드 호제법은 시간 복잡도가 $O(log(a + b))$이다.