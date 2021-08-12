# 목차

-   [스택의 정의](#no_1)
-   [스택의 연산](#no_2)
-   [스택의 구현](#no_3)

<br/>
<br/>

<a name="no_1">

## 스택의 정의

-   **스택**(stack)은 목록 끝에서만 데이터가 들어오고 나가는 자료구조이다. **Python**으로 구현 할 때에는 **list**의 **append**와 **pop**을 이용하여 구현할 수 있으며, **Javascript**에서는 **Array**에 **push**와 **pop**을 이용하여 구현할 수 있다.
-   스택은 한 쪽 끝에서만 자료를 넣거나 뺄 수 있는 선형 구조(LIFO - Last In First Out)으로 되어 있다. 자료를 넣는 것을 '밀어넣는다' 하여 **푸쉬**(push)라고 하고 반대로 넣어둔 자료를 꺼내는 것을 **팝**(pop)이라고 하는데, 이때 꺼내지는 자료는 가장 최근에 푸쉬한 자료부터 나오게 된다. 이처럼 나중에 넣은 값이 먼저 나오는 것을 [LIFO](https://ko.wikipedia.org/wiki/LIFO) 구조라고 한다.
-   스택이 비었다면 1을 반환하고,그렇지 않다면 0을 반환한다.

![stack](https://user-images.githubusercontent.com/77667889/128314628-1c2c77fe-9dc2-4078-a4f3-d84acf577af6.gif)

</a>

<br/>
<br/>
  
  
  
<a name="no_2">  
  
## 스택의 연산

여기서 사용하는 메서드 이름은 실제 구현되어 있는 언어별 메서드와는 다른 개념, 즉 자료구조의 개념이다.

-   top() : 스택의 가장 윗(마지막) 데이터를 반환한다.
-   pop() : 스택의 가장 윗(마지막) 데이터를 삭제한다
-   push() : 스택의 가장 윗 데이터로 top이 가리키는 자리 위에(top = top + 1) 메모리를 생성, 데이터를 넣는다.
-   is\_empty() : 스택이 비었다면 True 를 반환하고,그렇지 않다면 False 를 반환한다.

</a>

<br/>
<br/>
  
  
  
<a name="no_3">  
  
## 스택의 구현

#### python

```python
class Stack(list) : 
    push = list.append
    pop = list.pop
    
        def is_empty(self) :
            if not self :
                return True
            else :
                return False

stack = Stack()
stack.push(1)
print("stack", stack)
stack.push(2)
print("stack", stack)
stack.push(3)
print("stack", stack)
stack.pop()
print("stack", stack)
```

```python
Out[-]

stack [1]
stack [1,2]
stack [1,2,3]
stack [1,2]
```

#### Javascript

```javascript
class Stack {
    constructor() {
      this.arr = [];
    }

    push(x) {
      this.arr.push(x);
    }
    pop() {
      return this.arr.pop();
    }
    empty() {
      if(arr.length == 0) {
        return 1;
      } else {
        return 0;
      }
    }
}

  const stack = new Stack();
  stack.push(1);
  stack.push(2);
  stack.push(3);
  console.log(stack.pop()); //3
  console.log('stack', stack); //[1, 2]
```

#### Java
  
```java
class Stack {

	int top;
	int[] stack;
	int size;

	public Stack(int size) {
		top = -1;
		stack = new int[size];
		this.size = size;
	}

	public int peek() {
		return stack[top];        
	}

	public void push(int value) {
		stack[++top] = value;
		System.out.println(stack[top] + " PUSH !");
	}

	public int pop() {
		System.out.println(stack[top] + " POP !");
		return stack[top--];
	}

	public void printStack() {
		System.out.println("-- STACK LIST --");
		for (int i = top; i >= 0; i--)
			System.out.println(stack[i]);
		System.out.println("-- END OF LIST --");
	}
}
  
  
```  
  
```java
public class MainStack {
	public static void main(String args[]) {
    // 스택 동작 테스트
		Stack st = new Stack(100);
		st.push(5);
		st.push(2);
		st.push(3);
		st.push(4);
		st.push(1);

		st.printStack();

		st.pop();
		st.pop();

		st.push(15);

		st.printStack();

		st.peek();
		
		st.pop();
		st.pop();
		st.pop();
		st.pop();
		
		st.push(30);
		
		st.peek();
	}

}  
```  
```java
//실행결과

5 PUSH !
2 PUSH !
3 PUSH !
4 PUSH !
1 PUSH !

-- STACK LIST --
1
4
3
2
5

-- END OF LIST --
1 POP !
4 POP !
15 PUSH !

-- STACK LIST --
15
3
2
5

-- END OF LIST --
PEEK : 15
15 POP !
3 POP !
2 POP !
5 POP !
30 PUSH !
PEEK : 30  
```  
 
</a>

<br/>
