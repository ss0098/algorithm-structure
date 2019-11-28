 
# 동적계획법이란?

### 간단하게 생각하면 큰 문제를 작은 문제로 나눠서 푸는 알고리즘이다.
### 흔히 생각하는 피보나치 수열을 재귀함수를 이용하여 구현 할 경우 많은 중복이 발생한다.
***ex) 4의 경우 fi(3)+fi(2) 밑에 중복되는 fi(2)와 fi(1)들이 생겨나면서 중복되는 연산을 계속해서 해야한다.***

### 이 경우 중복되는 값에 대한 값들을 배열이나 hashtable에 저장하여 필요 할 때에는 꺼내어서 쓰면서 중복되는 연산을 막을 수 있다.

### 일반적인 재귀호출의 경우

```
int Fib(int n)
{
    return n <= 1 ? n : Fib(n - 1) + Fib(n - 2);
}
```

### 중복이 발생하지만 동적 계획을 사용한다면

```
int Fib(int n)
{
  int f;
  HashTable store=new HashTable();

  if(store.ContainsKey(n)) return (int)store[n];

  if(n<=1) f=n;
  else
  { 
    f = Fib(n - 1) + Fib(n - 2);  
  }
  
  store.Add(n,f);
  
  return f;
  
}
```
