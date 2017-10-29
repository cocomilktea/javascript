### scope 

변수의 scope : 선언된 변수가 어느 위치에서 유효한가.

```javascript
function a(){
	var v_a = "a";
	function b(){
		var v_b = "b";
		console.log("b() : ", typeof(v),typeof(v_a),typeof(v_b)); //string string string  
	}
	b(); //a함수 안에서 b함수 호출
	console.log("a() : ", typeof(v),typeof(v_a),typeof(v_b)); //string string undefined 
}

var v = "v";
a(); //a함수호출
//b(); //여기서 b함수는 호출안됨
console.log("out : ", typeof(v),typeof(v_a),typeof(v_b)); //string undefined undefined
```

변수의 scope는 function의 scope를 따른다.

객체(변수)는 선언된 함수 안에서만 접근이 가능하다.



### 변수의 shadowing

서로 다른 함수에서 같은 변수를 선언했을때 발생하는 shadowing 효과

```javascript
function shadowingEx(){
	console.log("F", val); //0
	val++;
}

var val = 0; //처음에 val이 0으로 초기화가 되고
shadowingEx(); //함수가 호출되었을때 함수안에 scope에 따라 바깥에서 선언된 val변수에 접근할수있고 그변수의값을 
//console.log("F", val); f 0 으로 출력한뒤 그리고 그 변수의 값을 val++; 1증가하기 떄문에 바깥에 선언된 변수의 값이 1로변경됨
console.log("out ", val); //1 함수가 종료되고 나서 콘솔명령을 통해 val출력하면 1이 출력 되는 것이다.
```

```javascript
//만약 같은 이름의 변수를 shadowingEx 함수 안에서 선언하면 어떻게 될까?
function shadowingEx(){
	var val = 0; //함수 안에서 출력한 val은 함수안에 변수의 값을 따라간다
	console.log("F", val); //0
	val++;
}

var val = 0; // 함수 밖에서 출력한 val은 함수 밖에서 선언한 변수의 값을 따라간다
shadowingEx(); 
console.log("out ", val); //0
```

필요에 따라 한 함수 안에서만 값이 유지되어야 하는 변수는  var 키워드를 이용해 함수 안에서 선언해서 사용하고 

여러 함수에 걸쳐 값이 유지되면서 사용되어야 하는 변수는 함수들을 포괄하는 곳에서 var키워드를 선언해 사용한다.



> 연습 문제

```javascript
function printTimesTable(a){
	for( i = 1 ; i <= 9 ; i++ ){
		console.log( a + " * " + i + " = " + a*i );
	}
}

for( var i = 2 ; i <= 9 ; i++ ){
	printTimesTable(i);
}
```

다음 코드는 구구단을 2단부터 9단까지 출력하는 코드입니다. 하지만 이대로 실행하면 정상적으로 구구단을 출력하지 않습니다.
아래의 코드에 shadowing 효과를 추가해 구구단이 잘 출력되도록 하세요.

```javascript
function printTimesTable(a){
	for(var i = 1 ; i <= 9 ; i++ ){
		console.log( a + " * " + i + " = " + a*i );
	}
}

for( var i = 2 ; i <= 9 ; i++ ){
	printTimesTable(i);
}
```



 