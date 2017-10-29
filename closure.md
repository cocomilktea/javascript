### closure 클로져

함수와 그 함수가 선언될때의 environment로 구성

```javascript
function makeCounterFunction(initVal){
	var count = initVal;
	function Increase(){
		count++;
		console.log(count);
	}
	return Increase; //makeCounterFunction함수내에서 Increase함수를 반환한다.
}

var counter1 = makeCounterFunction(0);
var counter2 = makeCounterFunction(10);

counter1(); //1
counter2(); //11
```

makeCounterFunction 함수에서는 count 변수에 initVal함수 인자로 받은 값을 저장하고,

함수 내에 Increase 함수를 선언한다. makeCounterFunction 함수는 결국 Increase 함수를 반환해주는 함수이다.

그리고 makeCounterFunction 함수를 두번 호출해서 counter1과 counter2변수에 저장한다.

그리고 그 함수를 담은 변수를 호출한다.

makeCounterFunction 함수 안에 있는 count 변수는 하나인것처럼 보이는데 Increase 함수가 실행될때마다

count의 값이 1이였다가 11이였다가 하는 것을 알수있다.

 counter1 함수가 호출되었을때 count 변수와  counter2 함수가 호출되었을때 count 변수가 다른것이다

이것이 바로 클로저 때문인데 makeCounterFunction 함수를 호출했을때 Increase 함수가 만들어지면서 

이때 count변수를 포함하는 environment가 하나의 클로저로 만들어 지기 때문이다

```javascript
makeCounterFunction(0);

//closure가 가르키는 함수
function Increase(){}

//closure의 environment
var count = 0;
```

그리고 다음에 makeCounterFunction 이 다시 호출되었을때 counter2();

makeCounterFunction 함수의 environment가 새로 만들어지고 Increase 함수가 만들어지면서 

이때 environment 가 새로운 클로저로 만들어 지게 되는 것이다.

```javascript
makeCounterFunction(10);

//closure가 가르키는 함수
function Increase(){}

//closure의 environment
var count = 10;
```

그렇기 때문에 counter1에 저장된 함수와 counter2에 저장된 함수를 호출하였을 때 count변수가 서로 다른것이다.

(둘다 count변수를 쓰지만 다른 값을 가짐) 

이런 클로저의 특성은 자바스크립트 고급프로그래밍에서 많이 사용되는데 

간단히 우리가 살펴본 예제에서만 보아도 counter1,counter2 함수를 가지고는 count변수의 값을 직접 제어할 수 없다.

왜냐하면 count변수는 makeCounterFunction 안에 있고 우리가 갖고있는것은 Increase 함수만 있는데 

Increase 함수에서는 count 접근할수 있지만 함수 바깥에서 count변수에 직접 접근할수 있는 방법은 없기 때문이다.

