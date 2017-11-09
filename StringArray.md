###String

> 문자열길이 확인, 문자열 합치기

```javascript
var str1 ="Hello";
console.log(str1.length); //문자열 길이확인 
var str2 = "World";
var str3 = str1.concat(str2)//문자열 합치기
console.log(str3); 
var str4 = str1.concat(str2).concat("!"); //문자열 이어서 합치기
console.log(str4);
var str5 = str1 + str2;
console.log(str5);
var str6 = "Hello" + "Javascript";
console.log(str6);
var str7 = "Pi is " + 3.14 //문자 숫자 더하기
console.log(str7);
var str8 = 3.14 + " is Pi"; //숫자 문자 더하기
console.log(str8);
```

> 여러가지 문자열 다루기

```javascript
//.charAt 문자열 특정위치에 있는 한글자에 접근
var str = "abcdeabcde";
console.log(str.charAt(0)); //접근할 index번호 입력 (범위를넘어가면 "" 빈문자열)
console.log(str.length);
console.log(str[1]); //charAt대신 대괄호로도 접근 가능 (범위를넘어가면 undefined)
console.log(str.substring(2,4)); //부분문자열 구하기 2~3까지 반환  "cd"
console.log(str.substr(2,4)); //"cdea" 2번째 문자열부터 길이 4까지 반환 
console.log(str.substring(2)); //두번째를 생략할경우 문자열 끝까지 반환
console.log(str.substr(2)); //두번째를 생략할경우 문자열 끝까지 반환
console.log(str.substr(-7)); //첫번째숫자가 음수인경우 뒤에서부터 부분문자열 반환 "deabcde"
console.log(str.substr(-7,2)); //두번째 숫자를 이용해서 길이를 제한 "de"
console.log(str.indexOf("bc"));//문자열 안에서 주어진 문자열이 존재하는 첫번째 위치를 반환 "1"
console.log(str.lastIndexOf("bc"));//문자열 안에서 주어진 문자열이 존재하는 마지막 위치를 반환 "6"
console.log(str.lastIndexOf("f"));//존재하지 않는 문자열일 경우 -1 반환
```



### Array

리스트와 함께 많이 사용하는 **자료구조**의 하나.

값element 가 연속된 저장공간

배열을 이용하면 여러개의 변수를 저장하고 index 주소를 이용해 접근할 수 있다.

객체와 비교해보면 객체는 이름과 값들의 집합이라면 배열은 값들의 나열이라고 보면 된다.

객체와달리 이름이 따로 존재하지 않고 숫자로 이뤄진 index가 있다.

 객체에서 속성에 저장될 값들이 어떤 자료형이든 가능했던 것처럼 

배열도 배열안에 들어가는 값element에는 어떤 자료형(배열이나 객체도 가능) 이든 들어갈 수있다. 

각각 element가 같은 자료형이 아니여도 된다.

```javascript
var arr1 = []; //빈배열 생성
var arr2 = [1, 2, 3, 4, 5];//속성대신 값들을 콤마로 구분
//한 배열에선 같은 타입만 쓰기(권장)
var mixedArr = [1, true, 3.14, "String", {name : "object"}, [1, 2, 3]]; 
console.log(mixedArr); 
console.log(mixedArr.length);
console.log(mixedArr[5]);
console.log(mixedArr[6]); //범위를 넘어가면 undefined
```



> 배열에 사용가능한 명령어

* pop : 배열의 마지막 값을 반환하고 기존 배열에 값은 삭제
* shift : 배열의 0번째 index 값을 반환하고 기존 배열에 값은 삭제
* push : 배열의 마지막에 값을 추가
* unshift : 배열의 0번째 index에 값을 추가
* reverse : 배열의 값을 뒤집을 수 있다
* sort : 배열의 값을 정렬
* concat :  배열 합치기 (더하기 연산자는 배열에서 사용안됨)
* indexof : 주어진 문자열이 존재하는 첫번째 위치를 반환
* lastIndexof : 주어진 문자열이 존재하는 마지막 위치를 반환
* split : 문자열을 구분자로 나눠서 각각의 문자열을 배열에 넣어 반환
* join : 배열을 문자열로 바꿈
* slice(0, 2) : 0~1 값 반환. 변수에 값 저장안됨
* splice(0, 2) : 0 index시작, 개수2 반환. 남은값은 바꿔서 변수저장 String에서는 사용할수 없다.
* delete : object에서 속성을 제거할때만 사용 **배열에서 쓰지않기**

```javascript
var arr = [1, 2, 3, 4, 5];
console.log(arr.pop()); //1, 2, 3, 4]
console.log(arr);
console.log(arr.shift()); //[2, 3, 4]
console.log(arr);

console.log(arr.push(6)); //[2, 3, 4, 6]
console.log(arr);
console.log(arr.unshift(0)); //[0, 2, 3, 4, 6]
console.log(arr);

console.log(arr.reverse()); //[6, 4, 3, 2, 0]
console.log(arr); //배열에 상태도 실제로 변화함
console.log(arr.sort()); //[0, 2, 3, 4, 6]
console.log(arr); 

var arr1 = [1, 2, 3];
var arr2 = [4, 5, 6];
console.log(arr1.concat(arr2)); //단지 합쳐진 배열만 반환 [1, 2, 3, 4, 5, 6]
console.log(arr1); //값 변화가 없다 [1, 2, 3]
console.log(arr2); //[4, 5, 6]

var arr3 = arr1.concat(arr2); //추후에 concat배열값을 활용하려면 변수에 저장
console.log(arr3); //[1, 2, 3, 4, 5, 6]

var arr4 = [1, 2, 3, 1, 2, 3];
console.log(arr4.indexOf(2)); //1 index번호 반환
console.log(arr4.lastIndexOf(2)); //4 index번호 반환


var str = "1,2,3,4,5";
console.log(str.split(",")); //베열안에 들어간채 반환 ["1", "2", "3", "4", "5"]

```



> 배열 실습 append

```javascript
var append = function(arr, data) {
  arr[arr.length] = data;
}
var arr = [1,2];
append(arr,3);
console.log(arr);

var a = [1, 2, 3];
//프로토타입 
Array.prototype.append = function(data){
  this[this.length] = data;
}
a.append(4);
console.log(a);
```

> 배열 실습 shift, unshift

```javascript
var myShift = function(arr){
  var ret = arr[0];
  for(var i = 0; i < arr.length -1; i++){
    arr[i] = arr[i+1];
  }
  arr.length--; //???????????
  return ret; //리턴을 언제 해야되고 안해야되는지 잘 감이 안잡힘
}
var arr = [1, 2, 3];
myShift(arr);
console.log(arr);

var myUnshift =  function(arr, data){
  var ret = arr.length + 1;
  for(var i = ret; i > 0; i--){
    arr[i] = arr[i-1];
    arr[0] = data;
  }
  return ret;
}
var unshiftArr = [1, 2, 3, 4, 5];
myUnshift(unshiftArr, 10);
console.log(unshiftArr);

var myUnshift = function(arr, v){
  var temp = [];
  for(var i = 0; i < arr.length; i++){
    temp[i] = arr[i];
  }
  var n = arr.length;
  for(var i = 0; i < n; i++){  //변하는 값을 넣어주면 무한루프
    arr[i + 1] = temp [i];
  }
  arr[0] = v;
}

var a = [1, 2, 3, 4, 5];
myUnshift(a, 10);
console.log(a);
```

> 배열 연습문제 임의의 위치의 원소를 바꾸기 

```javascript
var swapArray = function(arr, a, b) {
  var tempA = arr[a];
  var tempB = arr[b];
  arr[a] = tempB;
  arr[b] = tempA;  
}

var arr = [1, 2, 3, 4, 5];

swapArray(arr, 0, 3); //4, 2, 3, 1, 5
console.log(arr);
```

> 배열 연습문제 배열 뒤집기

```javascript
var num = [1, 2, 3, 4, 5];

var myReverse = function(arr){
  
  var temp = [];
  
  var lastNum = num.length
  for(var i = lastNum; i > 0; i--){
    temp.push(i);
  } 
  
  for(var i = 0; i < num.length; i++) {
    num[i] = temp[i];
  }
}

myReverse(num);
console.log(num);
```



> 2차원 배열이란?

배열 안에 배열이 들어있는것

2차원, 주로 3차원까지 사용한다.

```javascript
var arr = []
arr.push([1,2,3]);
arr.push([4,5,5]);
```

2차원 배열의 순회

```javascript
var arr = [[1,2,3,],[4,5,6]];
for(var i = 0; i < arr.length; i++){
	for(var j = 0; j < arr[i].length; j++){
		console.log(arr[i],[j]);
	}
}
```

> 연습문제

```javascript
//연습문제 5*10 배열에 1부터 50까지 채우세요 루프 두개 사용 push는 사용하지 말것
var a = [];
var n = 5;
var m = 10;
//var x = 0;
for(var i = 0; i < n; i++){
	a[i] = [];
	for(var j = 0; j < m; j++){
		//x++;
		//a[i][j] = x;
		a[i][j] = i * m + j + 1;
	}
}
console.log(a);


//위에서 만든 배열을 다시 1차원 배열로 저장 역시 push 사용하지말기 
var b = [];

for(var i = 0; i < n; i++){
	for(var j = 0; j < m; j++){
		b[i * m + j] = a[i][j];
	}
}
console.log(b);

```

> 특정 원소의 주변 값 읽기

```javascript
// 4 * 4 배열에 1부터 1000까지 무작위로 값을 넣고 
// 2차원 배열과 값을 인자로 입력받아서 해당 값이 존재하면 상하좌우값을 출력하는 함수를 작성
// 1. 배열에 값이 있는지 검색
// 2. 값이 없으면 리턴
// 3. 값이 있다면 위쪽 값 검색 및 출력
// 4. 왼쪽, 오른쪽, 아래 출력

var arr = [];

function generateArray(arr){
	for(var i = 0; i < 4; i++){
		arr[i] = [];
		for(var j = 0; j < 4; j++){
			var x = Math.floor(Math.random()*1000 + 1);
			arr[i][j] = x; 
		}
	}
}

function printArr(arr){
	for(var i = 0; i < 4; i++){
		var str = "";
		for(var j = 0; j < 4; j++){
			str += arr[i][j] + " ";
		}
		console.log(str);
	}
}


function printNeighbor(arr, n){
	var x = -1, y = -1;
	for(var i = 0; i < 4; i++){
		var k = arr[i].indexOf(n);
		if(k !== -1){
			//찾았다
			x = i;
			y = k;
			break;
		}
	}
	if(x !== -1){
		//print above 
		if(x > 0){
			console.log("up" + arr[x - 1][y]);
		}
		if(y > 0){
			console.log("left" + arr[x][y - 1]);
		}
		if(x < 3){
			console.log("down" + arr[x + 1][y]);
		}
		if(y < 3){
			console.log("right" + arr[x][y + 1]);
		}
		return; //꼭필요 안하면 못찾음까지출력됨		
	}
	console.log("못찾음");
}


//4*4 배열을 만들어준다 리턴불필요
generateArray(arr);
//배열을 출력 리턴불필요 출력만
printArr(arr);
//배열의 이웃을 출력 리턴불필요 
printNeighbor(arr, arr[2][2]);
printNeighbor(arr, arr[0][0]);
printNeighbor(arr, arr[3][3]);

```

> 배열의 swap

```javascript
//배열의 스왑 구현
var arr = [];
for(var i = 0; i < 4; i++){
	var n = 4 * i;
	arr;
	arr.push([n + 1, n + 2, n + 3, n + 4]);
}
arr[3][3] = 'x';
console.log(arr);

function arrSwap(arr, x1, y1, x2, y2){
 // a[x1][y1] <--> a[x2][y2]
 	var temp = arr[x1][y1];
 	arr[x1][y1] = arr[x2][y2];
 	arr[x2][y2] = temp;
}
arrSwap(arr, 0, 0, 3, 3);

```

> 2차원 배열의 원소 한 칸 옮기기

```javascript
//2차원 배열의 원소 한 칸 옮기기
function arrayMove(arr, x1, y1, pos){
	if(pos == 'up' && x1 > 0){
		arrSwap(arr, x1, y1, x1 - 1, y1);
		return true;
	} else if (pos == 'down' && x1 < 3){
		arrSwap(arr, x1, y1, x1 + 1, y1);
		return true;
	} else if (pos == 'left' && y1 > 0){
		arrSwap(arr, x1, y1, x1, y1 - 1);
		return true;
	} else if (pos == 'right' && y1 < 3){
		arrSwap(arr, x1, y1, x1, y1 + 1);
		return true;
	} else{
		return false;
	}
}


var ok = arrayMove(arr, 3, 3, 'right'); //postion:"left", "right", "up", "down" 예외 : 못옮길경우 false리턴 옮겼을경우 true리턴
console.log(ok); //false
ok = arrayMove(arr, 3, 3, 'left');
console.log(ok); //true
```

