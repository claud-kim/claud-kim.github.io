---
layout: splash
title: "expert c/c++"
date: 2019-05-15T14:44:00+09:00
excerpt_separator: "<!--more-->"
categories:
  - coding
tags:
  - export
  - study
  - c/c++
---

//#define DEBUG
#ifdef DEBUG
#define debug   printf
#else
#define debug(...)
#endif
# Expert study
selflink : https://subinium.github.io/euler/

```cpp
//now 4
/* 4. */
// original
// A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99.
// Find the largest palindrome made from the product of two 3-digit numbers.
// 간략해석
// 세자리수 * 세자리수를 한 결과값 중 팰린드롬이 되는 최댓값을 구하시오.

```


```cpp
/* 3. */
// 600851475143 의 가장 큰 소인수.
// 작은 소인분해 2,3,5,7 소수로 나눠봄
// 6*10^13< 25*10^12-> 루트 값까지 소수 나옴 5*10^6
//-> 6857 
	long long num = 600851475143;
	long long p = 2;
	long long maxp = 2;

	while(num>=p && p<5000000){
		if(num%p==0){
			maxp = p;
			num /= p;
		}else {
			p++;
		}
	}
	printf("maxp %lld",maxp);
```
	
```cpp
/* 2. */
// 피보나치 수열 구하기 1,2,3,5,8... 에서
// 4,000,000 이하 짝수항의 합구하기.
//-> 4613732 
	long long st = 1, snd=2;
	long long tot = 0;
	while(snd<4000000){
		if ( snd%2==0) tot += snd;
		
		long long tmp = snd; //a2->a1
		snd = st+snd;
		st = tmp;
	}

	printf("%lld \n", tot);
```

```cpp
/* 1. */

//1000 미만의 3 또는 5의 배수의 합을 구하는 문제입니다.
//-> 233168 

// n 배수의 [0,last) 까지의 합
int nTotal(int last, int n) {
	int data = (last-1)/n;
	return n*data*(data+1)/2;
}

int main(void){
	int tot = 0;

	int tot3 = nTotal(1000,3);
	int tot5 = nTotal(1000,5);
	
	int tot15 =  nTotal(1000,15);
	
    tot = tot3+tot5-tot15;
    printf("%d \n",tot);
    return 0;
}
```



