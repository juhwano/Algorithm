# 목차

-   [그리디 알고리즘](#no_1)
-   [문제](#no_2)
-   [코드 예시](#no_3)

<br/>
<br/>

## 그리디 알고리즘

-   그리디 알고리즘(탐욕법)은 **현재 상황에서 지금 당장 좋은 것만 고르는 방법**을 의미합니다.
-   일반적인 그리디 알고리즘은 문제를 풀기 위한 최소한의 아이디어를 떠올릴 수 있는 능력을 요구합니다.
-   그리디 해법은 그 정당성 분석이 중요합니다.
-   단순히 가장 좋아보이는 것을 반복적으로 선택해도 최적의 해를 구할 수 있는지 검토합니다.
-   일반적인 상황에서 그리디 알고리즘은 최적의 해를 보장할 수 없을 때가 많습니다.
-   하지만 코딩 테스트에서의 대부분의 그리디 문제는 **탐욕법으로 얻은 해가 최적의 해가 되는 상항에서, 이를 추론**할 수 있어야 풀리도록 출제됩니다.

<br/>
<br/>

## 문제. 거스름 돈

당신은 음식점의 계산을 도와주는 점원입니다. 카운터에는 거스름돈으로 사용할 500원, 100원, 50원, 10원짜리 동전이 무한히 존재한다고 가정합니다. 손님에게 거슬러 주어야 할 돈이 N원일 때 거슬러 주어야할 동전의 최소 개수를 구하세요. (단, 거슬러 줘야 할 돈 N은 항상 10의 배수입니다.)

<br/>
<br/>

#### 아이디어

-   최적의 해를 빠르게 구하기 위해서는 **가장 큰 화폐 단위부터** 돈을 거슬러 주면 됩니다.
-   N원을 거슬러 줘야 할 때, 가장 먼저 500원으로 거슬러 줄 수 있을 만큼 거슬러 줍니다.
-   이후 100원, 50원, 10원짜리 동전을 차례대로 거슬러 줄 수 있을 만큼 거슬러 주면 됩니다.
-   N = 1,260일 떄의 예시를 확인해 봅니다.

<table style="border-collapse: collapse; width: 100%;" border="1" data-ke-align="alignLeft" data-ke-style="style13"><tbody><tr><td style="width: 20%; text-align: center;">화폐 단위</td><td style="width: 20%; text-align: center;">500</td><td style="width: 20%; text-align: center;">100</td><td style="width: 20%; text-align: center;">50</td><td style="width: 20%; text-align: center;">10</td></tr><tr><td style="width: 20%; text-align: center;">손님이 받은 개수</td><td style="width: 20%; text-align: center;">2</td><td style="width: 20%; text-align: center;">2</td><td style="width: 20%; text-align: center;">1</td><td style="width: 20%; text-align: center;">1</td></tr></tbody></table>

<br/>
<br/>

#### 정당성 분석

-   가장 큰 화폐 단위부터 돈을 거슬러주는 것이 최적의 해를 보장하는 이유??

가지고 있는 동전 중에서 **큰 단위가 항상 작은 단위의 배수이므로 작은 단위의 동전들을 종합해 다른 해가 나올 수 없기 때문**입니다.

-   만약에 800원을 거슬러 주어야 하는데 화폐 단위가 500원, 400원, 100원이라면 어떻게 될까요?
-   그리디 알고리즘 문제에서는 이처럼 문제 풀이를 위한 최소한의 아이디어를 떠올리고 이것이 정당한지 검토할 수 있어야합니다.

<br/>
<br/>

## 코드 예시

(python)

```python
n = 1260
count = 0

# 큰 단위의 화폐부터 차례대로 확인하기
array = [500, 100, 50, 10]

for coin in array:
  # 해당 화폐로 거슬러 줄 수 있는 동전의 개수 세기
  count += n // coin
  n %= coin

print(count)
```

(Java)

```java
public class Main {
	public static void main(String[] args) {
		int n = 1260;
	    int count = 0;
	    int[] coinTypes = {500, 100, 50, 10};

	    for(int i = 0; i < 4; i++){
	      count += n / coinTypes[i];
	      n %= coinTypes[i];
	    }
	    System.out.println(count);
	}
}
```
<br/>
<br/>

#### 시간 복잡도 분석

-   화폐의 종류가 K라고 할 때, 소스코드의 시간 복잡도는 **O(K)** 입니다.
-   이 알고리즘의 시간 복잡도는 거슬러줘야 하는 금액과는 무관하며, 동전의 총 종류에만 영향을 받습니다.
