# 목차

-   [큐의 정의](#no_1)
-   [큐의 용어](#no_2)
-   [큐의 종류](#no_3)

<br/>
<br/>

<a name="no_1">


# 큐의 정의

-   컴퓨터의 기본적인 자료 구조의 한가지, **Python** 은 **insert(0, 값)** 와 **pop(0)** 로 구현할 수 있으며, **Javascript** 는 **unshift** 와 **shift** 로 구현할 수 있음.
-   먼저 집어 넣은 데이터가 먼저 나오는 선입선출(FIFO - Frist In First Out)구조로 저장하는 형식
-   프린터의 출력 처리나 윈도우 시스템의 메시지 처리기, 프로세스 관리 등 데이터가 입력된 시간 순서대로 처리해야 할 필요가 있는 상황에 이용

![queue](https://user-images.githubusercontent.com/77667889/128315736-d4c40b20-dd91-448d-a095-b4bb2d554497.gif)

</a>
<br/>
<br/>
  
<a name="no_2">

# 큐의 용어

-   put : 큐에 자료를 넣는 것
-   get : 큐에서 자료를 꺼내는 것
-   front : 데이터를 get할 수 있는 위치
-   rear : 데이터를 put할 수 있는 위치
-   Overflow : 큐가 꽉 차서 더 이상 자료를 넣을 수 없는 경우
-   Underflow : 큐가 비어 있어 자료를 꺼낼 수 없는 경우

</a>

<br/>
<br/>
  
  
<a name="no_3">

# 큐의 종류

### 1\. 선형 큐

-   막대 모양으로 된 큐
-   크기가 제한되어 있고 빈 공간을 사용하려면 모든 자료를 꺼내거나 자료를 한 칸씩 옮겨야
-   한다는 단점이 있음
-   Data : A → B → C → D- insert

![image](https://user-images.githubusercontent.com/77667889/129465977-eb11571a-8e07-491a-812f-aad33d08418c.png)

### 2\. 환형 큐

-   배열로 큐를 선언할 시 큐의 삭제와 생성이 계속 일어났을때, 마지막 배열에 도달후 실제로는 데이터공간이 남아있지만 오버플로우가 발생하는 선형 큐의 문제점을 보완한 것
-   front(head)가 큐의 끝에 닿으면 큐의 맨 앞으로 자료를 보내어 원형으로 연결
-   Data : A → B → C → D → E

![image](https://user-images.githubusercontent.com/77667889/129465982-e592f2d0-126d-4a8a-8c62-aa9c5b013f7e.png)
  
  
</a> 
