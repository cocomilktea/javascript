### 함수

함수는 return값이 있을 경우에만 변수에 값을 대입(할당) 할 수 있다.

객체는 참조를 전달한다. 기본타입의 경우 값을 넘긴다.

```javascript
var repeat = function(num, text){
	for(var i = 1; i <= num; i++){
		console.log(text);
	};
};

repeat(2, "hello");



var test1 = function(text){
	if (text === "exit"){
		return; //함수를 종료하겠다. break; 와 같음
	}
	console.log("이게 보여요?");
}

test1("hoho");
test1("exit");
```



> 연습문제

배열의 첫번쨰 원소와 마지막 원소의 순서를 바꾸는 함수를 작성해 보자.

```javascript
var arr = ["a", "b", "c", "d", "e"];

var mySwap = function(arr){

	var  temp = arr[0];
	arr[0] = arr[arr.length-1];
	arr[arr.length-1] = temp; 
};

mySwap(arr);
console.log(arr);
```

구구단을 출력하는 함수를 만들어 봅시다 디폴트는 2단 출력

```javascript
var gugudan = function(dan = 2){
	for(var i = dan; i <= dan ; i++){
		for(var j = 1; j < 10; j++){
			console.log("%d X %d = %d ", i, j, i*j);
		};
	};
};
gugudan();
gugudan(3);

```

