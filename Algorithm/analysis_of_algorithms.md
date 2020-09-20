 # 알고리즘의 수행시간 분석
* 해당 알고리즘을 프로그래밍 언어로 구현하여 직접 컴퓨터에서 실행,수행시간을 측정한다.
* 프로그램으로 구현해야 하는 비용이 든다. 
* 프로그래밍언어, 프로그래머와 수행 환경(컴퓨터)에 따라 수행시간이 다르다.
>   >ex) 알고리즘을 프로그래밍 언어로 구현하여 직접 컴퓨터에서 실행하여 수행시간을 측정하는 예제 프로그램 (by C) 
<pre>
<code>
#include <time.h>
#include <stdio.h>
int main()
{
	…
	clock_t start, finish; 
	double  duration; 
	start = clock(); 
	…
	finish = clock(); 
	duration = (double)(finish - start) / CLOCKS_PER_SEC; 
	printf("%f\n", duration); 
	return 0;
}
</code>
</pre>

- - -

알고리즘 수행시간 분석 목적
-------------
* 프로그램 수행시간이 얼마나 걸리는지 추정.

* 프로그램이 적당한 시간내에 수행이 끝나는 최대 입력 크기를 추정.

* 주어진 문제의 해를 구하는 여러 알고리즘의 효율성을 비교하여 보다 효율적인 알고리즘을 선정할 수 있다.

입력에 따른 수행시간 분석
-------------
* 수행시간은 입력의 크기 n에 좌지우지된다. (입력이 클수록 시간이 많이 걸림)
* 크기 n인 모든 입력에 대한 평균적인 수행시간 (_average-case running time_)
>   ><span style="color:red">평균적인 수행시간을 분석하는 것은 매우 어렵다.</span>
* 크기 n인 모든 입력 중 최악의 경우에 대한 수행시간(_worst-case running time_)
>   >장점: 최악의 입력이 무엇인지는 비교적 쉽게 추정 가능하므로 수행시간 측정이 용이하다.   
단점: 정확한 수행시간이 아닌 일종의 **수행시간의 최대값**만을 제시.
실제 상황에 최악의 수행시간이 중요한 경우가 많다. (항공기 제어, 교통 제어, IP lookup 등에서 실제로 유용함)
* 보통 _worst-case running time_ 을 분석한다.
* 알고리즘의 수행시간은 유사(Pseudo) 코드에서 실행되는 기본 연산의 개수로 정의된다.
>   >기본 연산: 알고리즘의 수행시간에 가장 큰 영향을 미치는 연산
              (비교연산, 사칙연산 등)
- - -
최악의 경우 수행 시간 (_worst case running time_)
-------------
  
* 수행되는 작업의 양(기본 연산의 수)은 입력의 크기 n에 비례한다.
* 입력의 크기가 n일 때, 실행되는 기본연산의 수는 입력 형태(구현된 코드)에 따라 달라진다.
* 최악의 경우 수행시간: 크기가 n인 모든 가능한 입력에 대하여 실행되는 기본연산 수의 최대값
  * W(n)으로 표기.
> 알고리즘의 수행시간 (_running time_)은 T(n)으로 표기.

>   >T(n) = 실행되는 기본연산의 개수  ≤  W(n)

평균적인 경우 수행 시간 (_average case running time_)
-------------
  
* 모든 입력에 대한 분석(Analysis for all inputs)
* 크기가 n인 모든 입력에 대하여 실행되는 기본 연산의 수의 평균
  * A(n)으로 표기.
- - -
### ex) 순차탐색_Sequential Search
```
int seqSearch(int A[], int n, int K) { 
  int ans;
  ans = -1;
  for(int index = 0; index < n; index++)
    if (K == A[index]) {
      ans = index;
      break;
    }
  return ans;
}
```

>   >기본 연산: K와 배열 원소와의 비교   
입력크기 n: 배열에 있는 원소들의 수
* 최악의 경우 수행 시간: W(n) = n
* 알고리즘 수행시간: T(n) ≤ n
- - -
점근적(Asymptotic) 분석
-------------
* 데이터의 개수 n → ∞ 일때 수행시간이 증가하는 growth rate로 시간복잡도를 표현하는 기법.
* Θ-표기, Ο-표기 등을 사용

### 함수의 증가율 비교 ex) 1

<img src="C:\Users\hsryu\Desktop\TIL\Algorithm\growth-rate.JPG" width="450px" height="300px" alt="growth-rate"></img><br/>

### 함수의 증가율 비교 ex) 2
<img src="C:\Users\hsryu\Desktop\TIL\Algorithm\growth-rate표.JPG" width="450px" height="300px" alt="growth-rate표"></img><br/>

증가율에 의한 함수 표기법
-------------
* “Big-O” 표기(notation)
  * O(f(n)) : 어떤 실수 c와 음이 아닌 정수 n0에 대하여, n ≥ n0인 모든 n에 대하여 g(n) ≤ c f(n)을 만족하는 함수 g의 집합

    직관적 의미: 함수 g는 함수 f 보다 빠르게 증가하지 않는다. 상수 비율의 차이는 무시
>   >ex) 5n^2+4n의 증가율은 n^2의 증가율과 점근적인 의미에서 같으므로 5n^2+4n = O(n^2)이다.   
O(n^2)은 n^2, 3n^2-50, 5n, 2nlogn+3n, 500 등을 포함한다.   
=> O(f(n))은 최고차항의 차수가 f(n)과 일치하거나 더 작은 함수의 집합이다.






