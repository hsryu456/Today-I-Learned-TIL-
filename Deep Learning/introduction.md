# 딥러닝(Deep Learning)

## 딥러닝 이란?
<img src="https://user-images.githubusercontent.com/62328584/94544407-271cbc80-0286-11eb-91ad-16f9c768d86e.JPG" width="750px" height="430px"></img><br/>

* 인공지능(Artificial Intelligence)

    >어떤 문제를 사고하고 해결할 수 있는 지능을 만드는 기술  
       
* 머신러닝(Machine Learning)

    >기계 스스로 학습을 통해 지능을 습득하는 것에 관한 기술

* 딥러닝(Deep Learning)

    >인공 신경망을 이용한 **머신러닝 기법**

- - -

## 인공 신경망(Artificial Neural Network)
<img src="https://user-images.githubusercontent.com/62328584/94545092-0d2fa980-0287-11eb-994a-53f867fdfb7b.JPG" width="750px" height="430px"></img><br/>
* 생체 신경망의 작동 원리를 모방해서 만든 인공 신경망으로, 인공 뉴런들이 서로 복잡하게 연결되어 있는 네트워크이다.    
* 뉴런은 신호를 받아 임계치 이상이 되면 신호를 발화한다.

<img src="https://user-images.githubusercontent.com/62328584/94636727-b79fdf00-0310-11eb-96dd-d7e319638aba.JPG" width="800px" height="430px"></img><br/>  

>   >여러 함수들이 네트워크를 형성하고 있는 합성 함수

<img src="https://user-images.githubusercontent.com/62328584/94637110-b0c59c00-0311-11eb-8299-b0ec40eae3da.JPG" width="800px" height="430px"></img><br/>



/* 정렬 알고리즘은 크게 **간단한 정렬 알고리즘**과 **고급 정렬 알고리즘**으로 나뉜다.
    >간단한 정렬 알고리즘: 선택 정렬, 버블 정렬, 삽입 정렬   

    >고급 정렬 알고리즘:

      (1) 분할과 정복 알고리즘(Divide and Conquer): 병합정렬(merge sort), 퀵정렬(quick sort)
      (2) 힙정렬(heapsort): 우선순위 큐(priority queue)와 힙, 힙정렬
      (3) 기수정렬(radix sort) 


정렬 알고리즘 분류
-------------
* Stable 정렬 알고리즘
    >정렬 할 자료들(입력 자료) 중 동일한 두 자료의 상대적인 위치가 정렬 후에도 유지되는 정렬 알고리즘   
    >ex) C5, **A1**, T8, B4, **A3** => **A1**, **A3**, B4, C5, T8

* In-place 정렬 알고리즘
    >정렬 할 자료를 저장하는 메모리 공간이외에 추가로 사용하는 메모리 공간이 O(1)인 정렬 알고리즘   
    >ex) C5, **A1**, T8, B4, **A3** => **A3**, **A1**, B4, C5, T8


선택 정렬(_Selection Sort_)
-------------
**(1)** 정렬하고자 하는 배열 A[1 … n]에서 가장 큰(작은) 원소를 찾는다.   
**(2)** (1)과정에서 찾은 가장 큰(작은) 원소와 배열의 끝자리A[n](작은 원소의 경우 A[0])와 자리를 바꾼다.   
**(3)** 교환되어 배열을 맨 뒷자리(앞자리)로 간 원소는 자기 자리를 찾으므로 제외시키고, 나머지 원소들로 위와 같은 작업을 반복한다. => 원소가 하나 남으면 정렬 작업을 종료한다.

>ex) [30 12 15 **57** 17] -> [30 12 15 17 **57**] -> [**30** 12 15 17 57] ->[17 12 15 **30** 57] -> [15 12 **17** 30 57] -> [12 **15** 17 30 57] -> [**12** **15** **17** **30** **57**]

### ex) 선택 정렬(_Selection Sort_)*/

