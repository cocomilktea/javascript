### 객체Object

**속성**(상태) **메소드**(행동)을 가진다.



#### 객체지향 프로그래밍

* 유지보수가 쉬워진다
* 대형프로그램을 짜기 쉬워진다
* 객체와 객체가 협력해서 일을 한다
* 객체는 일에 책임을 진다
* 객체는 객체에 메시지를 보낸다
* 객체는 자율적이고 능동적으로 일을한다



> 객체연습

```javascript
var m1 = {
name : "GongU",
hp : 100,
mp : 50,
power : 10,
attack : function(target){
target.hp -= this.power;
}
// eat : function(target){
// 	this.hp += target.energy; 
// }
};

var m2 = {
name : "Hyun",
hp : 90,
mp : 60,
power : 13,
attack : function(target){
target.hp -= this.power;
}
// eat : function(target){
// 	this.hp += target.energy; 
// }
};

var c1 = {
type : "coffee",
energy : 10
};

m1.attack(m2);


```

this 키워드 - 함수(메소드) 안에서 사용시 주로 함수를 소유한 객체. 객체 안에서 사용시 객체 자체를 가르킴

**this의 값은 바꿀수 없다**



> 함수생성자

```javascript
//생성자 함수
function Human(name, hp, mp, power){ //생성자함수는 첫글자 대문자
this.name = name;
this.hp = hp;
this. mp =  mp;
this.power = power;
} //no semicolon!

Human.prototype.attack = function(target){
target.hp -= this.power;
}; //not the best way!
Human.prototype.eat = function(target){
this.hp += target.energy;
};
Human.prototype.show = function(){
console.log("%s %d %d %d", 
	this.name, this.hp, this.mp, this.power);
};


function Food(name, energy){
this.name = name;
this.energy = energy;
this.show = function(){
console.log("%s %d", 
	this.name, this.energy);
}
}


var h1 = new Human("Honux", 100, 20 ,10);
var h2 = new Human("Crong", 999, 1, 99);
var f1 = new Food("coffee", 5);
var f2 = new Food("donut", 10);
h1.attack(h2);
h2.attack(h1);
h1.show();
h2.show();
h1.eat(f1);
h2.eat(f2);
h1.show();
h2.show();
```



기본생성자들

생성자를 이용해 생성된 객체는 프로토타입 속성을 가진다.  



> 모든 객체의 key 값 가져오기  Object.keys();

```javascript
//Human 객체를 하나 만들고모든 속성과 값을 출력해 봅시다. Object.keys(m1) 사용할 것.
function Human(name, hp, mp, money, item){
	this.name = name;
	this.hp = hp;
	this. mp =  mp;
	this.money = money;
	this.item = [];
	this.item.push(item);
} 

Human.prototype.eat = function(food){
this.hp += food.energy;
};

var h = new Human('jina',100, 20, 990, 'pen');
var chicken = {energy : 30};

h.eat(chicken);

var keys = Object.keys(h);
for(var i = 0; i < keys.length; i++){
var key = keys[i];
console.log(key + ":" + h[key]);
}
```



> 배열 연습1

```javascript
//배열을 만들고 1-100까지의 임의의 정수를 20개 넣는다
var arr = [];
var num;
console.log(num);
for(var i = 0; i < 20; i++){
	num = Math.floor(Math.random()*100);
	arr.push(num);
}
console.log(arr);
```



> 배열 연습2

```javascript
//배열의 주어진 위치의 원소를 교체하는 mySwap() 구현 var mySwap = function(arr, idx1, idx2)
var mySwap = function(arr, idx1, idx2){
	var temp = arr[idx1];
	arr[idx1] = arr[idx2];
	arr[idx2] = temp;
}
mySwap(arr, 0 , 1);
console.log(arr);

```



> 배열 연습3

```javascript
//이 배열을 정렬한다. MyArray.sort(arr)
//Array.sort()를 사용해서 내림차순 정렬
arr.sort(function(a, b){
	return b - a;
});
console.log(arr);


//Array.sort()를 사용해서 오름차순 정렬
arr.sort(function(a, b){
	return a - b;
});
console.log(arr);
```

