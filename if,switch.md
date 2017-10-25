### if

 ```javascript
if(boolean type 조건){	
	//조건이 참true일 때만 코드실행
}


console.log("Menu");
console.log("1. Ice Americano");
console.log("2. Cafe Latte");
console.log("3. Cappuccino");
console.log("4. Tea");

var choice = parseInt(prompt("메뉴를 선택 해 주세요."));
console.log(choice +"번 메뉴를 선택하셨습니다.");

if(choice == 1){
	console.log("아이스아메리카노는 1500원 입니다.");
}else if(choice == 2){
	console.log("카페라떼는 2000원 입니다.");
}else if(choice == 3){
	console.log("카푸치노는 2500원 입니다.");
}else if(choice == 4){
	console.log("tea는 1700원 입니다.");
}else{
	 console.log("메뉴를 다시 선택해주세요");
}

 ```





### switch

switch  구문의 경우 break; 를 사용하지않으면 코드가 계속 실행되게 되는데 

잘활용하면 오히려 효율적으로 프로그래밍을 할 수 있는 경우가 있다. 

```javascript
console.log("Menu");
console.log("1. Ice Americano");
console.log("2. Cafe Latte");
console.log("3. Cappuccino");
console.log("4. Tea");

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
```

