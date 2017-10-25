### for문

> for 문을 이용해 배열에 각 엘리먼트에 접근
>
> for 문을 실행하면 변수 i가 배열의 각 엘리먼트에 index값을 나타내면서 
>
> 각배열에 엘리먼트에 접근할 수 있다.

 ```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

for(var i = 0; i < arr.length; i++){
	console.log(arr[i]);
}
 ```

for문은 break;를 만나면 for문 바깥으로 빠져나가는 것은 while문과 동일하지만,

continue;를 만나면 i++(업데이트) 구문이 실행되고 다시 i<arr.length(조건식)을 비교하는 점이 다르다. 

while문에서 continue; 문을 만났다면 반복실행코드의 끝(중괄호 닫히는 부분)으로 이동한다음 조건식 검사한뒤에

반복여부를 결정. 다시말해 for문이 continue;를 만나면 

for문이 끝나는 (닫히는 중괄호)부분으로 간 다음에 조건식을 확인하기 전에 업데이트 구분을 먼저 실행하고

조건식을 검사한 후에 반복여부를 결정한다는 점이 차이점이다.

사소한 부분처럼 보이지만 이런 부분에 대해 정확하게 이해하고 프로그램을 작성해야 정확하게 원하는 기능을

구현할 수 있으니 꼭 확실하게 이해하고 숙지해야한다.



### for in 문

> 객체에 각 속성에 대해 접근
>
> var obj = {"속성1" : 1, "속성2 : 2, 속성3 : 3"}
>
> 객체에서 각 속성에 접근하기 위해서는 변수가 객체 속성의 이름을 나타낼수 있으면
>
> 된다. 이를 위해 Object.keys(obj);라는 함수를 이용할 수 있는데
>
> 이 함수는 객체를 인자로 받아서 객체의 속성들의 이름을 배열로 반환해준다.

```javascript
var obj = {
	name : "object",
	weight : 30,
	isObject : true,
	arr : [1, 2, 3],
	obj : {property : 1}
};

//console.log(Object.keys(obj)); //객체의 속성의 이름들이 배열로 반환된다 

console.log("for 구문으로 object property 반복하기");
var property_list = Object.keys(obj);
console.log("property List : ", property_list);

for(var i = 0; i < property_list.length; i++){
	var propertyName = property_list[i];
	console.log("\t", propertyName, ": ", obj[propertyName]);
}
//이 배열을 for문을 이용해 반복실행하면서 순차적으로 객체속성의 이름을 얻어내고
//그 이름으로 부터 객체의속성 값에 접근한다.
//Object.keys()함수를 이용해서 객체속성의 배열을 얻어내는 과정이 더 추가된것이다.
//하지만 for in 구문을 사용하면 이런 방법대신 간단하게 obj의 프로퍼티에 대해서
//반복된 코드를 수행할 수 있다.


console.log("\n\n for in 구문으로 object property 반복하기");
for(var propertyName in obj){
	console.log("\t", propertyName, ": ", obj[propertyName]);
}
//for in 구문은 따로 초기화코드나 업데이트코드가 존재하지 않는데 
//반복문이 실행되면서 in 앞에 적혀있는 변수에 in 뒤에 있는 객체의 속성 
//이름을 순차적으로 담아준다. 그러면 for문 안에 코드에서 객체 속성의 이름과 
//그 이름을 가지고 객체 속성의 값에 접근할수 있게된다.
//결과는 동일하지만 for문으로 작성한 코드에서는 Object.keys() 함수를 이용해서 
//객체 속성 리스트를 받아온것을 출력한 것이 추가적으로 표시된것을 볼수 있다.
//for in 구문은 배열에 대해서도 활용할 수 있는데 변수에 배열의 index가 순차적으로 저장된다. 
//for문으로도 같은 역할을 하는 코드를 작성할 수도 있지만 
//for in 구문을 사용하면 더효율적으로 코드를 작성 할수 있다. 
```



> for in 연산자 활용

```javascript
var obj = {
	name : "object",
	weight : 30,
	isObject : true,
	arr : [1, 2, 3],
	obj : {property : 1}
};

console.log("name" in obj); //true
console.log("age" in obj); //false
```

for in 구문이 아닌 곳에서 in은 연산자로써 동작한다. 
해당 속성의 이름이 객체에 존재하는지를 검사할 수 있는 연산자이다.
결과를 true false로 반환해준다. 
객체에 존재하지 않는 속성에 접근하면 undefined가 반환되는데 
속성이름에 접근하기 전에 in 연산자를 활용하면 객체에 해당 속성이 존재하는지 확인할 수 있다.



> for in 연습문제

```javascript
//for in 문을 이용해서 obj의 속성중, number 타입의 값을 모두 더해서 sum에 저장
var obj = {
	name: "object",
	age: 10,
	weight: 5
};

// console.log(obj.name);
// console.log(obj["name"]);

var sum = 0;
for (var key in obj ){
	console.log(obj.key); //undefined
	console.log(obj[key]); //object, 10, 5
    if( typeof( obj[key] ) == "number" ){
        sum = sum + obj[key];
    }
}
console.log(sum);
```

