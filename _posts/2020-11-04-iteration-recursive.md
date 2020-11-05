---
title:  "반복함수 & 재귀함수"
excerpt: ""

categories:
  - Blog
tags:
  - Blog
---

<br/><br/>

# 📌반복함수
---------------------------------------
- while or for 문법을 이용하여 특정한 처리를 반복하는 방식으로 문제 해결

<br/><br/>

### ✅ 숫자 피라미드
---------------------------------------

```c
 #include <stdio.h>
 
 // 반복함수를 이용하여 숫자 피라미드 출력 
 // 반복함수 같은 경우는 오직 for문, while문으로 구성 
 int print(int a)
 {
 	int i, j;
 	
 	for(i = 0; i < a; i++) {
 		for(j = 0; j <= i; j++) {
 			printf("%d", j + 1);
		}
		printf("\n");
	}
 }
 
 int main(void)
 {
 	int a;
 	scanf("%d", &a);
 	print(a);
 	return 0;
 }
```
![숫자피라미드](https://user-images.githubusercontent.com/68745073/98127888-8fe8fb80-1efa-11eb-9b87-e74d1d7cf558.png)

<br/><br/>


# 📌재귀함수
---------------------------------------
- 자신의 함수 내부에서 자기 자신을 스스로 호출함으로써 재귀적으로 문재 해결
- 경우에 따라 간결, 직관적 코드로 문제를 해결할 수 있지만 때에 따라 심각한 비효율성을 낳을 수 있기에 알고리즘을 작성할 때 유의해야한다.

<br/><br/>

### ✅ 문자열 반복
---------------------------------------

```c
 #include <stdio.h> 

// 재귀함수 (Recursive Function) 
void print(int count)
{
	if(count == 0) {
		return;
	} else {
		printf("%d) 문자열을 출력합니다.\n", count);
		print(count - 1);
	}
}

int main(void)
{
	int number;
	printf("문자열을 몇 개 출력할까요?");
	scanf("%d", &number);
	print(number);
	return 0;
}
```
![문자열반복](https://user-images.githubusercontent.com/68745073/98127936-9ecfae00-1efa-11eb-8a5e-c76795e18f45.png)

<br/><br/>

### ✅ 조합
---------------------------------------
- nCr
- 서로 다른 n개 중, r개를 선택하는 경우의 수 (순서 중요하지않음)
- nCr은 r이 0이거나 n이라면 1이며, nCr(n-1, r-1) + nCr(n-1, r)와 같다.
- [조합 개념](https://www.youtube.com/watch?v=8aJzzwzByLc)

```c
#include <stdio.h>

int nCr(int n, int r)
{
	if(r == 0 || r == n) {
		return 1;
	} else {
		return nCr(n - 1, r - 1) + nCr(n - 1, r);
	}
}

int main(void)
{
	int n, r;
	scanf("%d %d", &n, &r);
	printf("%d", nCr(n, r));
	return 0;
}
```
![조합](https://user-images.githubusercontent.com/68745073/98127938-a000db00-1efa-11eb-8d71-341873db18ab.png)

<br/><br/>

### 참고
[동빈나 - C언어 기초 프로그래밍 강좌](https://www.youtube.com/watch?v=dh4hdtZ00EU&list=PLRx0vPvlEmdDNHeulKC6JM25MmZVS_3nT&index=1&t=2s)