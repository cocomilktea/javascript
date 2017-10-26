### while

반복문은 특정조건이 만족하는동안 일정 코드를 반복적으로 실행

```javascript
console.log("Menu");
console.log("1. Ice Americano");
console.log("2. Cafe Latte");
console.log("3. Cappuccino");
console.log("4. Tea");

var  count = 0;
while(count < 3){

	var choice = parseInt(prompt("메뉴를 선택 해 주세요."));
	console.log(choice +"번 메뉴를 선택하셨습니다.");


	switch(choice){
		case 1 : 
			console.log("아이스아메리카노는 1500원 입니다.");
			break;
		case 2 : 
			console.log("카페라떼는 2000원 입니다.");
			break;
		case 3 : 
			console.log("카푸치노는 2500원 입니다.");
			break;
		case 4 : 
			console.log("tea는 1700원 입니다.");
			break;
		default : 
			console.log("메뉴를 다시 선택해주세요");
			break;
	}
	count++;

}
console.log("안녕히 가세요");

```

> while 연습

```javascript
//문제3개를 내고 틀리면 처음부터 다시 푸는 코드
var count = 0;

while(true){
	var ans;
	ans = parseInt(prompt ("1 + 1 = ?"));
	if(ans != 2){
		console.log((++count) + "번 틀렸습니다. 다시 도전하세요"); //++count로 틀린횟수를 증가시킴
		continue;
	}

	ans = parseInt(prompt ("7 - 3 = ?"));
	if(ans != 4){
		console.log((++count) + "번 틀렸습니다. 다시 도전하세요");
		continue;
	}

	ans = parseInt(prompt( "9 * 7 = ?"));
		if(ans != 63){
		console.log((++count) + "번 틀렸습니다. 다시 도전하세요");
		continue;
	}
	break; //반복문 종료하기 위해 break

	//continue 를 만나면 여기로 이동합니다.

}

//break 를 만나면 여기로 이동합니다.
console.log("참 잘했어요");
```

> while 연습1

```javascript
//1부터 n까지 더한 값을 return
function sumFrom1ToN(n){
    var count = 1;
    var sum=0;
    while( count <= n ){
        sum = sum + count;
        count++;
    }
    return sum;
}

var result = sumFrom1ToN(3);
console.log(result);
```

> while 연습2

```javascript
var i = 0;
while(i < 5){
	i++
	console.log(i); //5
}
console.log("firsti =", i); //5 

var i = 0;
while(i < 5){
	console.log(i); //4
	i++
}
console.log("lasti =", i); //5 근데 이렇게 잘안쓴다 i는 반복문에서만 사용
```



### do whlie

do while 은 반복 여부를 반복문 마지막에 검사한다.

반복문에 코드가 적어도 한번은 실행된다.

일단 반복문을 한번 실행한 후에 반복여부를 조건식에 따라 결정한다.

예를들어 퀴즈를 내고 맞출때까지 계속 문제를 반복하는 프로그램에 유용하다.

```javascript
var cond = false; 

while(cond){
	console.log("이 구문은 실행되지 않습니다.");
}
do{
	console.log("이 구문은 한번은 실행 됩니다.");
}while(cond);



//퀴즈
do{
	var ans = parseInt(prompt ("1 + 1 = ?"));
}while( ans != 2);

console.log("정답입니다.");
```

