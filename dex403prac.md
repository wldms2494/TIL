# js crt 600



NO1. Refer to following code block : 

let array = [1,2,3,4,5,6,7,8,9,10,11];

let output = 0;

for ( let num of array) {

if(output > 10) {

break;

}

if(num%2 ==0) {

continue;

}

output += num;

}
What is the value of output after the code executes

A. 16
B. 36
C. 11
D. 25

- 
    
    break 문에 걸리면 for문이 아예 종료되고, 
    
    continue문에 걸리면 밑의 함수나 내용을 실행 안함.
    
    +=연산자는 
    왼쪽과 오른쪽을 더한 값을 왼쪽에 대입한다. 
    
    if(output>0){  break; }라면 1 들어가자마자  break걸리니까 답은 1이고, 
    
    output>10 이라면 
    
    1,3,5,7까지 홀수는 다 들어가고 
    여기서 아웃풋이 16까지 완성되고 다음에는 걸림
    그래서 16ㅋ
    

NO.2 A developer wants to set up a secure web server with Node.js. The developer creates a
directory locally called app-server, and the first file is app-server/index.js Without using any thirdparty libraries, what should the developer add to index.js to create the secure web server?
A. const tls = require('tls');
B. const https =require('https');
C. const server =require('secure-server');
D. const http =require('http');

- 
    
    b
    

NO.3 Refer to the following code that performs a basic mathematical operation on a provided input:
function calculate(num) {
Return (num +10) / 3;
}
How should line 02 be written to ensure that x evaluates to 6 in the line below?
Let x = calculate (8);
A. Return Number((num +10) /3 );
B. Return (Number (num +10 ) / 3);
C. Return Integer(num +10) /3;
D. Return Number(num + 10) / 3;

- 
    
    abd전부 6 나옴
    

**NO.4 Teams at Universal Containers (UC) work on multiple JavaScript projects at the same time.
UC is thinking about reusability and how each team can benefit from the work of others.
Going open-source or public is not an option at this time.
Which option is available to UC with npm?**
A. Private packages can be scored, and scopes can be associated to a private registries.

B. Private registries are not supported by npm, but packages can be installed via URL.
C. Private packages are not supported, but they can use another package manager like yarn.
D. Private registries are not supported by npm, but packages can be installed via git.

- 
    
    A
    
    registry 기재 
    

NO.5 a developer has an ErrorHandler module that contains multiple functions.

what kind of export be leverages so that multiple functions can be used? 

A. Named
B. All
C. Multi
D. Default

- 
    
    leverage : use to maximum advantage , exploit, make full use of and derive benifit from 
    
    A
    

**NO.6 Which option is a core Node,js module?**
A. Path
B. Ios
C. Memory
D. locate

- 
    
    node.js core modules  → http, url, querystring path, fs, util 
    
    A
    

NO.7 a developer has code that calculates a restaurant bill, but generates incorrect answers while testing the code, : 

```jsx
function caculateBill(items) {
let total = 0; 
total += findSubTotal(items);
total += addTax(items);
total += addTip(total);

return total;
}
```

which option allows the developer to step into each function execution within calculateBill?

Which option allows the developer to step into each function execution within calculateBill?
A. Using the debugger command on line 05.
B. Using the debugger command on line 03
C. Calling the console.trace (total) method on line 03.
D. Wrapping findSubtotal in a console.log() method.

- 
    
    a
    

NO.8 refer to the code below : 

```jsx
const exec = (item, delay) => {
	 new Promise (resolve => setTimeout(()=> resolve(item), delay);)
}

async function runParallel(){
const(resul1,resul2, resul3) = await Promise.all{
[exec('x','100'), exec('y', 500), exec('z', '100')]

return `parallel is done: $(result1) $(result2)$(result3)`;
}}
```

 which two statements coreectly execute the runParallel ( ) function ?

choose 2 answers

A. Async runParallel () .then(data);
B. runParallel ( ). done(function(data){
return data;
});
C. runParallel () .then(data);
D. runParallel () .then(function(data)
return data

- 
    
    b , d
    콜백을 같이 넣어줘란 말인듯
    

NO.9 Which three statements are true about promises ?
Choose 3 answers
A. The executor of a new Promise runs automatically.
B. A Promise has a .then() method.
C. A fulfilled or rejected promise will not change states .
D. A settled promise can become resolved.
E. A pending promise can become fulfilled, settled, or rejected.

- 
    
    a b c
    e → a pending promise can becom fulfilled or rejected
    

NO.10 Refer to the following array : 

```jsx
let arr1 = [ 1, 2, 3, 4, 5];
```

Which two lines of code result in a second array, arr2 being created such that arr2 is not a reference
to arr1?
A. Let arr2 = arr1.slice(0, 5);
B. Let arr2 = Array.from(arr1);
C. Let arr2 = arr1;
D. Let arr2 = arr1.sort();

- 
    
    arr2 가 arr1을 참조하지 않고 arr2가 만들어지는거..?
    arr1을 건들지 않는것을 말하는 듯
    a랑 b는 arr1의 배열을 복제해서 만든것이기 때문에 arr1는 건들이지 않음
    전부다 [1,2,3,4,5]는 출력
    a,b
    

**NO.11 refer to the code below :** 

```jsx
function changeValue(param) {
	param = 5;
}
let a = 10;
let b = a;
changeValue(b);
const result = a+ "-" + b;

```

A. 10 -10
B. 5 -5
C. 5 - 10
D. 10 - 5

- 
    
    왜 a값은 5로 변하지 않았는가? let의 scope때문이다.
    
    param은 function 안에서만 쓸 수 있다. 
    그래서 let a= 10 그대로 쓴다. 
    
    a
    

NO.69 
setTimeout (() => (

console.log(1);
). 0);
console.log(2);
New Promise ((resolve, reject )) = > (
setTimeout(() => (
reject(console.log(3));
). 1000);
)).catch(() => (
console.log(4);
));
console.log(5);
What is logged to the console?

A. 2 1 4 3 5
B. 2 5 1 3 4
C. 1 2 4 3 5
D. 1 2 5 3 4

- 
    
    b
    

NO.12 refer to the code

```jsx
function animal(size, type) {
    this.size = size || "small";
    this.type = type || "animal";
    this.canTalk = false;
}

let Pet = function (size, type, name, owner) {
    animal.call(this, size, type);
    this.name = name;
    this.owner = owner;
}

Pet.prototype = Object.create(animal.prototype);
let pet1 = new Pet();
console.log(pet1);
```

given the code above, which three properties are set pet1 ?

choose 3
A. Name

B. canTalk

C. Type

D. Owner
E. size

- 
    1. **canTalk**: false
    2. **name**: undefined
    3. **owner**: undefined
    4. **size**: "small"
    5. **type**: "animal"
    BCE

NO.13 a developer creates a class that represents a blog post based on the requirement that a Post should have a body author and view count.
the code shown below : 

```jsx
class Post {
//inser code here
this.body = body;
this.author = author; 
this.vewCount  = viewCount;
}
```

which statement should be inserted in the placeHolder on line 02 to allow for a variable to be set to a new instance of a Post with the three attribues correctly populated?

A. super(body, author, viewCount) { ... }

B. Function Post ( body, author, viewCount) { ... }

C. constructor ( body, author, viewCount) { ... }

D. constructor( ) { ... }

- 
    
    c
    

NO.15 A developer creates an object where its properties should be immutable and prevent
properties from being added or modified.
Which method should be used to execute this business requirement ?
A. Object.const()
B. Object.eval()
C. Object.lock()
D. Object.freeze()

- 
    
    d
    

NO.16  A developer wants to iterate throught an array of objects and count the objects and count the objects whose property value, name , starts with the letter N.

```jsx
const arrObj = [
{ "name" :"Zach"},
{"name" : "Kate"},
{ "name" : "Alise"},
{"name":"bob"},
{"name" : "Natham"},
{"name" : "nathaniel"}
]
```

refer to the code snippet below : 

```jsx
arrObj. reduce((acc, curr) => {
//missing line 2
//missing line 3
}, 0);
```

which missing linew 2, 3 return the correct count?

A. Const sum = curr.startsWith('N') ? 1: 0;

Return acc +sum
B. Const sum = curr.name.startsWith('N') ? 1: 0;
Return acc +sum
C. Const sum = curr.startsWIth('N') ? 1: 0;
Return curr+ sum
D. Const sum = curr.name.startsWIth('N') ? 1: 0;
Return curr+ sum

- 
    
    reduce ( ) 함수에 대해서 정확히 알아야 한다고 !! 일단
    
    커런트 밸류랑 썸이랑 쓸꺼면 acc는 왜 필요하겠냐 
    
    accumulator 는 누산기란 말이고, 컴퓨터 cpu에서 중간 산술 논리 장치 결과가
    저장 되는 레지스터임 
    누산기는 처음엔 0으로 설정되며, 각 숫자는 차례로 누산기 내에 있는 값에 더해진다.
    그리고 모든 숫자들이 다 더해졌을 때에만 그 결과가 주 기억장치로 기억된다. 
    
    B
    

**NO.17 Refer to the following object :** 

```jsx
const cat = {
firstName : 'Fancy',
lastName : 'Whiskers',
get fullName() {
	return this.firstName + ' ' + this.lastName;
}
}
```

How can a developer access the fullName property for cat ?

A. cat.fullName
B. cat.fullName()
C. cat.get.fullName
D. cat.function.fullName()

- 
    
    A
    
    b 는 fullName( ) is not a function 뜸ㅋ
    c 는 cannot read properties of undefined ( reading ‘fullName’)
    d.는 c랑 같은 맥락
    

NO.18 A developer needs to test this function : 

```jsx
const sum3 = (arr) => (
if(!arr.length) return 0,
if(arr.length ===1) return arr[0],
if(arr.length ===2) return arr[0]+arr[1],
return arr[0]+arr[1] + arr[2],

);
```

Choose 2 answers
A. console.assert(sum3(1, '2')) == 12);
B. console.assert(sum3(0)) == 0);
C. console.assert(sum3(-3, 2 )) == -1);
D. console.assert(sum3('hello', 2, 3, 4)) === NaN);

- 
    
    A. console.assert(sum3(1,’2’)==’12’); 스트링이 들어가기땜에 스트링으로 출력되어야 함
    
    B. console.assert(sum3(0) ==0);
    
    C. console.assert ( sum3 (-3, 2) =-1 맞음
    
    d는 정확하겐 모르겠음  근데 조건이 있다면 스트링으로 출력되겠는데..
    
    bc
    

No. 19 why would a developer specify a package.json as developed forge instead of a dependency?
A. it is required by the application in production

B. it is only needed for local development and testing

C. Other required packages depend on it for development

D. it should be bundled when the package is published 

- 
    
    b
    

**NO.20 A developer wrote the following code to test a sum3 function that takes in an array of numbers and returns the sum of the first three number in the arr, the test passes :** 

```jsx
let res = sum2([1,2,3]);
console.assert(res===6);
Res = sum3([1,2,3,4]);
console.assert(res == 6);
```

a different developer made changes to the behavior of sum3 to instead sum all of the numbers present in the array . 

The test passes : 

which 2 results occur when running the test on the updated 3 function ? 

A. The line 02 assertion passes.
B. The line 02 assertion fails
C. The line 05 assertion passes.
D. The line 05 assertion fails.

- 
    
    a d ㅋ  assertion 문제는 다 쉬운둣 ㅋ
    

NO. 21 refer to  code below : 

```jsx
async funct on functionUnderTest(isOK){
if(isOk) return 'Ok';
throw new Error('notOk');
}
```

A) console.assert( functionUnderTest(true), ‘OK’)
B) console.assert( await functionUnderTest(true), ‘not Ok’)
C) console.assert( await functionUnderTest(true), ‘not Ok’)
D) console.assert( await functionUnderTest(true), ‘OK’)

- 
    
    async 함수와 짝꿍 await를 붙혀줘야 하고 true라면 ok출력 맞음 D
    

NO. 22 Refer to the following code : 

```jsx
let sampleText = 'The quick brown fox jumps';
```

 a developer needs to determine if a certain substring is part of a string.

which three expressions return ture for the given substring

A. sampleText.includes('fox');
B. sampleText.includes(' quick ', 4);
C. sampleText.includes(' Fox ', 3)
D. sampleText.includes(' fox ');
E. sampleText.includes(' quick ') !== -1;

- 
    
    includes()  배열이 특정 값을 포함하고 있는지의 여부를 boolean값으로 반환함.
    arr.includes( valueToFind [ fromIndex ])
    b는 띄어쓰기 포함 되어 있으니까 3 임
    
    A, D, E
    
    text.include( ) 
    indexof( ) →
    
    배열안에서 찾으려난 값 (searchElement) 과 정확하게 일치(===)하는 첫번째 element의 index를 리턴한다. 
    만약, 찾으려는 값이 배열에 없으면 -1을 리턴한다. 
    arr.indexOf(searchElement[, fromIndex])
    arr = [’a’, ‘b’, ‘a’, ‘b’];
    
    arr.indexOf(’a’, 1); 
    하면 아웃풋은 2가 나온다 arr[1]부터 a를 찾는 것이고 arr[2]자리에 a가 있기 떄문에 2를 토해냄
    

NO.23 refer to the code below? 

```jsx
let searchString =' look for this ';
```

which 2 options remove the whitespace from the beginning of searchString ?

Choose 2 answers
A. searchString.trimEnd();
B. searchString.trimStart();
C. trimStart(searchString);
D. searchString.replace(/*\s\s*/, '');

- 
    
    searchString.trimEnd() = ‘look for this ‘ 마지막에 한자리 잘라버림
    seartchString.trinStart() = 첫번째 한자리 잘라버림
    c - not defined
    D는 js 정규식인데 몬가 잘못된것 같은데 나도 정확하게는 몰겠다. 
    

NO.25 Universal Container(UC) just launched a new landing page, but users complain that the
website is slow. A developer found some functions that cause this problem. To verify this, the
developer decides to do everything and log the time each of these three suspicious functions
consumes.
console.time('Performance');
maybeAHeavyFunction();
thisCouldTakeTooLong();
orMaybeThisOne();
console.endTime('Performance');
Which function can the developer use to obtain the time spent by every one of the three functions?
A. console.timeLog()
B. console.getTime()
C. console.trace()
D. console.timeStamp()

- 
    
    A
    

NO.26

Refer to the code below:
let greeting = 'Goodbye';
let salutation = 'Hello, hello, hello';
try{
greeting = 'Hello';
decodeURI('%%%'); // error 발생
salutation = 'Goodbye';
} catch(err) {
salutation = 'I say hello';
} finally {
salutation = 'Hello, Hello';
}
Line 05 causes an error.
What are the values of greeting and salutation once code completes?

(A). Greeting is Hello and salutation is Hello, Hello.
(B). Greeting is Goodbye and salutation is Hello, Hello.
(C). Greeting is Goodbye and salutation is I say Hello.
(D). Greeting is Hello and salutation is I say hello.

- 
    
    A
    

NO.27 Refer to the expression below:
Let x = ('1' + 2) == (6 * 2);
How should this expression be modified to ensure that evaluates to false?
A. Let x = ('1' + ' 2') ===( 6 * 2);
B. Let x = ('1' + 2) == ( 6 * 2);
C. Let x = (1 + 2) == ( '6' / 2);
D. Let x = (1 + 2 ) == ( 6 / 2);

- 
    
    A
    

NO.28 developer creates a new web server that uses Node.js. It imports a server library that uses events and callbacks for handling server functionality. The server library is imported with require and is made available to the code by a variable named server. The developer wants to log any issues that the server has while booting up.

given the code and the info the developer has, which code logs an error at boost with an evernt?

A. Server.catch ((server) => {
console.log('ERROR', error);
});
B. Server.error ((server) => {
console.log('ERROR', error);
});
C. Server.on ('error', (error) => {
console.log('ERROR', error);
});
D. Try{
server.start();
} catch(error) {
console.log('ERROR', error);
}

- 
    
    c
    

NO.29 Given the following code:
document.body.addEventListener(' click ', (event) => {
if (/* CODE REPLACEMENT HERE */) {
console.log('button clicked!');
)
});
Which replacement for the conditional statement on line 02 allows a developer to correctly
determine that a button on page is clicked?
A. Event.clicked

B. e.nodeTarget ==this
C. event.target.nodeName == 'BUTTON'
D. button.addEventListener('click')

- 
    
    c
    

NO.30 The developer wants to test this code:
Const toNumber =(strOrNum) => strOrNum;
Which two tests are most accurate for this code?
Choose 2 answers
A. console.assert(toNumber('2') === 2);
B. console.assert(Number.isNaN(toNumber()));
C. console.assert(toNumber('-3') < 0);
D. console.assert(toNumber () === NaN);

- 
    
    a, c
    
    NaN을 반환하는 연산 종류 
    b는 function toNumber() 에다가 아무것도 안넣은것인데 그렇게 되면 undefined 가 떠서 정확하게 값을 알 수가 없다. 
    
    - 숫자로서 읽을 수 없음 (`parseInt("어쩌구")`, `Number(undefined)`)
    - 결과가 허수인 수학 계산식 (`Math.sqrt(-1)`)
    - 피연산자가 `NaN` (`7 ** NaN`)
    - 정의할 수 없는 계산식 (`0 * Infinity`)
    - 문자열을 포함하면서 덧셈이 아닌 계산식 (`"가" / 3`)

NO.31 A developer wants to use a module named universalContainersLib and then call functions
from it.
How should a developer import every function from the module and then call the functions foo and
bar?
A. import * from '/path/universalContainersLib.js';
universalContainersLib. foo ()7
universalContainersLib.bar ();
B. import {foo,bar} from '/path/universalCcontainersLib.js';
foo():
bar()?
C. import all from '/path/universalContainersLib.js';
universalContainersLib.foo();
universalContainersLib.bar ();
D. import * as lib from '/path/universalContainersLib.js';
lib.foo();
lib. bar ();

- 
    
    d
    

NO.32 Universal Containers recently launched its new landing page to host a crowd-funding
campaign. The page uses an external library to display some third-party ads. Once the page is fully
loaded, it creates more than 50 new HTML items placed randomly inside the DOM, like the one in the
code below

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0c6f53d8-3323-4a00-88b3-35804fd9a17b/Untitled.png)

코드 안보임..

All the elements includes the same ad-library-item class, They are hidden by default, and they are
randomly displayed while the user navigates through the page.
A. Use the DOM inspector to prevent the load event to be fired.
B. Use the browser to execute a script that removes all the element containing the class ad-libraryitem.

C. Use the DOM inspector to remove all the elements containing the class ad-library-item.
D. Use the browser console to execute a script that prevents the load event to be fired.

- 
    
    b
    third -party is self-contained components, typically small scripts or widgets that add functionality to websiteds.써드파티 광고를 넣었는데 html 안에 50개의 아이템 생성? 그래서 다 직여라는 말인듯.
    

NO.33 Refer to the code below:
Const pi = 3.1415326,
What is the data type of pi?
A. Double
B. Number
C. Decimal
D. Float

- 
    
    b
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/089ad30b-471a-4447-b4f8-f746e73b56bb/Untitled.png)
    

**NO.34 developer is wondering whether to use , Promise.then or Promise.catch especially when a promise throws an error**

which 2 promises are rejected ? 

which 2 are correct? 

A. Promise.reject('cool error here').then(error => console.error(error));
B. Promise.reject('cool error here').catch(error => console.error(error));
C. New Promise((resolve, reject) => (throw 'cool error here'}).catch(error => console.error(error)) ;
D. New Promise(() => (throw 'cool error here'}).then(null, error => console.error(error)));

- 
    
    b,c
    

NO.35 given the following code : 

```jsx
let x = null;
console.log(typeof x);
```

is the output of line 02?
A. ''x''
B. ''null'''
C. ''object''
D. ''undefined''

- 
    
    c
    

**NO.36 Refer to the following code that imports a module named utils:
import (foo, bar) from '/path/Utils.js';
foo() ;
bar() ;
Which two implementations of Utils.js export foo and bar such that the code above runs without
error?
Choose 2 answers**
A. // FooUtils.js and BarUtils.js exist
Import (foo) from '/path/FooUtils.js';
Import (boo) from ' /path/NarUtils.js';

B. const foo = () => { return 'foo' ; }
const bar = () => { return 'bar' ; }
export { bar, foo }
C. Export default class {
foo() { return 'foo' ; }
bar() { return 'bar' ; }
}
D. const foo = () => { return 'foo';}
const bar = () => {return 'bar'; }
Export default foo, bar;

- 
    
    b, c ****
    

NO.37 Refer to the code below:
Function changeValue(obj) {
Obj.value = obj.value/2;
}
Const objA = (value: 10);
Const objB = objA;
changeValue(objB);
Const result = objA.value;
What is the value of result after the code executes?
A. 10
B. Nan
C. 5
D. Undefined

- 
    
    c
    근데 왜 c인지..
    

NO.38 Refer to the following code:

```jsx
function Tiger() {
    this.type = 'cat';
    this.size = 'large';
}

let tony = new Tiger();
tony.roar = () => {
console.log('they\'re great');
    
};

function Lion() {
    this.type = 'cat';
    this.size = 'large';
}
let leo = new Lion();
//insert code here
leo.roar();
```

Which two statements could be inserted at line 17 to enable the function call on line 18?
Choose 2 answers.
A. Leo.roar = () => { console.log('They\'re pretty good:'); };
B. Object.assign(leo,Tiger);
C. Object.assign(leo,tony);
D. Leo.prototype.roar = () => { console.log('They\'re pretty good:'); };

- 
    
    ac
    
    .protoType.은 typeError : Cannot set properties of undefined(”setting’roar’)
    prototype을 정의하려면 저기서 만들게 아니라 만들어져 있는것을 넣어야 할 듯
    

NO.39 Which function should a developer use to repeatedly execute code at a fixed interval ?
A. setIntervel
B. setTimeout
C. setPeriod
D. setInteria

- 
    
    a
    

**NO.40 A developer wants to leverage a module to print a price in pretty format, and has imported a
method as shown below:**
Import printPrice from '/path/PricePrettyPrint.js';
Based on the code, what must be true about the printPrice function of the PricePrettyPrint module
for this import to work ?
A. printPrice must be be a named export
B. printPrice must be an all export
C. printPrice must be the default export
D. printPrice must be a multi exportc

- 
    
    c
    

**NO.41 Refer to code below:
Let first = 'who';
Let second = 'what';
Try{
Try{
Throw new error('Sad trombone');
}catch (err){
First ='Why';
}finally {
Second ='when';
} catch (err) {
Second ='Where';
}**
What are the values for first and second once the code executes ?
A. First is Who and second is When
B. First is why and second is where
C. First is who and second is where

D. First is why and second is when

- 
    
    d
    

NO.42 In which situation should a developer include a try .. catch block around their function call ?
A. The function has an error that should not be silenced.
B. The function results in an out of memory issue.
C. The function might raise a runtime error that needs to be handled.
D. The function contains scheduled code.

- 
    
    d
    

NO.43 A developer is leading the creation of a new browser application that will serve a single page
application. The team wants to use a new web framework Minimalsit.js. The Lead developer wants to
advocate for a more seasoned web framework that already has a community around it.
Which two frameworks should the lead developer advocate for?
Choose 2 answers
A. Vue
B. Angular
C. Koa
D. Express

- 
    
    b, d
    

NO.44 A developer has two ways to write a function:
Option A:
function Monster() {
This.growl = () => {
Console.log ("Grr!");
}
}
Option B:
function Monster() {};
Monster.prototype.growl =() => {
console.log("Grr!");
}
After deciding on an option, the developer creates 1000 monster objects.
How many growl methods are created with Option A Option B?
A. 1 growl method is created for Option A. 1000 growl methods are created for Option B.
B. 1000 growl method is created for Option A. 1 growl methods are created for Option B.
C. 1000 growl methods are created regardless of which option is used.
D. 1 growl method is created regardless of which option is used.

- 
    
    b
    프로토 타입을 사용하면 클래스나 객체를 복사하지 않고도 상속의 효과를 구현할 수 있게 해줌 
    

NO.45 A developer wants to define a function log to be used a few times on a single-file JavaScript
script.
01 // Line 1 replacement

02 console.log('"LOG:', logInput);
03 }
Which two options can correctly replace line 01 and declare the function for use?
Choose 2 answers
A. function leg(logInput) {
B. const log(loginInput) {
C. const log = (logInput) => {
D. function log = (logInput) {

- 
    
    ac
    

**NO.46 Refer to HTML below:
<p> The current status of an Order: <span id ="status"> In Progress </span> </p>.
Which JavaScript statement changes the text 'In Progress' to 'Completed' ?**
A. document.getElementById("status").Value = 'Completed' ;
B. document.getElementById("#status").innerHTML = 'Completed' ;
C. document.getElementById("status").innerHTML = 'Completed' ;
D. document.getElementById(".status").innerHTML = 'Completed' ;

- 
    
    c ,
    .getElementById(’id’). 문자전환 innerHTML
    

NO.47 Which two console logs output NaN?
Choose 2 answers | |
A. console.log(10 / Number('5) ) ;
B. console.log(parseInt ' ("two')) ;
C. console.log(10 / 0);
D. console.loeg(10 / 'five');

- 
    
    b,d
    

NO.48 Universal Containers (UC) notices that its application that allows users to search for accounts
makes a network request each time a key is pressed. This results in too many requests for the server
to handle.

- Address this problem, UC decides to implement a debounce function on string change handler.
What are three key steps to implement this debounce function?
Choose 3 answers:

A. If there is an existing setTimeout and the search string change, allow the existing setTimeout to
finish, and do not enqueue a new setTimeout.
B. When the search string changes, enqueue the request within a setTimeout.
C. Ensure that the network request has the property debounce set to true.
D. If there is an existing setTimeout and the search string changes, cancel the existing setTimeout
using the persisted timerId and replace it with a new setTimeout.
E. Store the timeId of the setTimeout last enqueued by the search string change handle

- 
    
    debounce? DOM 이벤트를 기반으로 실행하는 자바스크립트를 성능상의 이유로 JS의 양적인 측면, 즉 이벤트(event)를 제어(제한)하는 방법이다 
    디바운스는 이벤트를 그룹화 하여 특정시간이 지난 후 하나의 이벤트만 발생하도록 하는 기술, 
    순차적 호출을 하나의 그룹으로 그룹화 한다.
    so 연이어 호출되는 함수들 중 마지막 함수 ( 또는 제일 처음) 만 호출하도록 하는 것.
    
    A, B, C
    

NO.49 Which two console logs outputs NaN ?
Choose 2 answers

A. console.log(10/ Number('5'));
B. console.log(parseInt('two'));
C. console.log(10/ ''five);
D. console.log(10/0);

- 
    
    B, C
    

NO.50 Refer to the code below:
console.log(''start);
Promise.resolve('Success') .then(function(value){
console.log('Success');
});
console.log('End');
What is the output after the code executes successfully?
A. End
Start
Success
B. Start
Success
End
C. Start
End
Success
D. Success
Start
End

- 
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4854c5bd-cf22-4c1a-aa21-37cbaacd5874/Untitled.png)
    

**NO.51 Refer to the following code:
function test (val) {
If (val === undefined) {
return 'Undefined values!' ;
}
if (val === null) {
return 'Null value! ';
}
return val;
}
Let x;
test(x);**
What is returned by the function call on line 13?
A. Undefined
B. Line 13 throws an error.
C. 'Undefined values!'
D. 'Null value!'

- 
    
    c
    

**NO.52 A developer implements and calls the following code when an application state change
occurs:
Const onStateChange =innerPageState) => {
window.history.pushState(newPageState, ' ', null);
}
If the back button is clicked after this method is executed, what can a developer expect?**
A. A navigate event is fired with a state property that details the previous application state.
B. The page is navigated away from and the previous page in the browser's history is loaded.
C. The page reloads and all Javascript is reinitialized.
D. A popstate event is fired with a state property that details the application's last state.

- 
    
    history.pushState (  ) 페이지를 reload 하지 않고, url만 변경할 경우 사용한다. 
    history.pushState( state, title, url);
    
    state : 세션 히스토리에 넣을 데이터, object 형식, 사용하지 않거나 마땅히 넣을것이 없다면 null로 해도 괜춘.
    
    title : 변경할 브라우저 제목 ( 변경 하지 않을거면 null로 입력)
    
    url :  변경할 브라우저 URL
    
    ```jsx
    var state  = {'page_id' = 1, 'user_id' : 5};
    var title = 'hello world';
    var url = 'hello-world.html';
    
    history.pushState ( state, title, url );
    ```
    
    위와 같이 적용하면 hello-world.html이라는 문서가 없어도 주소가 hello-world.html와 같이 변경 된다. 실제 페이지를 로드하는 것이 아니기 때문에 실제 문서 존재 여부는 중요하지 앟ㄴ음. 
    새로고침을 하면 없는 문서이니 페이지 못찾는다고 에러 뿜고, 뒤로가기 하면 원래 문서가 뜬다. 
    
    B
    

NO.53 Given the following code:
Let x =('15' + 10)*2;
What is the value of a?
A. 3020
B. 1520
C. 50
D. 35

- 
    
    a
    

NO.54 Which option is true about the strict mode in imported modules?
A. Add the statement use non-strict, before any other statements in the module to enable not-strict
mode.
B. You can only reference notStrict() functions from the imported module.
C. Imported modules are in strict mode whether you declare them as such or not.
D. Add the statement use strict =false; before any other statements in the module to enable notstrict mode

- 
    
    c
    

NO.55 developer is trying to convince management that their team will benefit from using Node.js
for a backend server that they are going to create. The server will be a web server that handles API
requests from a website that the team has already built using HTML, CSS, and JavaScript.
Which three benefits of Node.js can the developer use to persuade their manager?
Choose 3 answers:
A. Performs a static analysis on code before execution to look for runtime errors.
B. I nstalls with its own package manager to install and manage third-party libraries.
C. Ensures stability with one major release every few years.
D. User non blocking functionality for performant request handling .
E. Executes server-side JavaScript code to avoid learning a new language.

- 
    
    a, b, d
    

NO.56 A developer has a web server running with Node.js. The command to start the web server is

node server.js. The web server started having latency issues. Instead of a one second turnaround for
web requests, the developer now sees a five second turnaround.
Which command can the web developer run to see what the module is doing during the latency
period?
A. NODE_DEBUG=true node server.js
B. DEBUG=http, https node server.js
C. NODE_DEBUG=http,https node server.js
D. DEBUG=true node server.js

- 
    
    c
    

**NO. 57 developer publishes a new version of a packaage with new features that do not break backward compatibility . the previous version number was 1.1.3
following semantic versioning format, what should the new package version number be?** 

A. 2.0.0
B. 1.2.3
C. 1.1.4
D. 1.2.0

- 
    
    버전을 주.부.수 숫자로 하고
    1. 기존 버전과 호환되지 않게 API가 바꾸면 주 버전을 올리고, last digits to zero
    2. 기존 버전과 호환되면서 새로운 기능을 추가할 때는 부 버전을 올리고,  reset last digit to zero
    3. 기존 버전과 호환되면서 버그를 수정한 것이라면 수 버전을 올린다. 
    여기서는 기능 추가인데 백앤드 호환은 안건드리는 거니까 중간 숫자를 올린다. 그래서 D
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c2dd01c4-0a44-4bac-90b8-5efcd05afd12/Untitled.png)
    

**NO. 58 refer to the code below :** 

```jsx
function changeValue(param){
	param = 5;
}
let a = 10;
let b = a;

changeValue (b) ;
const result = a + '-' + b;

```

What is the value of result when the code executes?

A. 10-10
B. 5-5
C. 10-5
D. 5-10

- 
    
    a
    

NO.59 Refer to the code below:
Let car1 = new Promise((_ , reject) =>
setTimeout(reject, 2000, "car 1 crashed in" =>
Let car2 =new Promise(resolve => setTimeout(resolve, 1500, "car 2 completed") Let car3 =new
Promise(resolve => setTimeout(resolve, 3000, "car 3 completed") Promise.race(( car1, car2, car3))
.then (value => (

Let result = '$(value) the race.';)}
.catch(arr => {
console.log("Race is cancelled.", err);
});
What is the value of result when Promise.race executes?
A. Car 3 completes the race
B. Car 2 completed the race.
C. Car 1 crashed in the race.
D. Race is cancelled

- 
    
    b
    
    아핫 promise.race() 는 프로미스 객체를 반환하는디, 그 중에  iterable 안에서 가장 먼저 완료된 것의 결과값으로 이행하거나 거부(reject) 합니당.
    

NO.60 Refer to the code below:
Let str = 'javascript';
Str[0] = 'J';
Str[4] = 'S';
After changing the string index values, the value of str is 'javascript'. What is the reason for this value:
A. Non-primitive values are mutable.
B. Non-primitive values are immutable.
C. Primitive values are mutable.
D. Primitive values are immutable

- 
    
    원시값 ( primitive value) 
    String, Numbers, undefined, null, boolean, symbol 로 이루어 져있다. 
    이 원시값들은 자바스크립트에서는 영구적이다. 
    즉 가져갈 수는 있지만 변경하거나 삭제할 수는 없다. 
    
    참조값(  Reference Value)
    원시값을 제외하고 나머지 값들이다. 
    Object 포함,functions 포함
    
    원시값은 아주 멀어서 보고 꺼내 쓸 수만 있고
    참조값은 그나마 가까워서 보고 꺼내고 조작도 가능하다고 함..’’’
    
    D
    
    ![자바스크립트의 우주...](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ec75ea8f-7b61-487e-9c52-551f869e78d0/Untitled.png)
    
    자바스크립트의 우주...
    

**NO.61 Refer to the code below:
for(let number =2 ; number <= 5 ; number += 1 ) {
// insert code statement here
}
The developer needs to insert a code statement in the location shown. The code statement has these
requirements:**

1. Does require an import
2. Logs an error when the boolean statement evaluates to false
3. Works in both the browser and Node.js
Which meet the requirements?
A. assert (number % 2 === 0);
B. console.error(number % 2 === 0);
C. console.debug(number % 2 === 0);
D. console.assert(number % 2 === 0);
- 
    
    console.error()는 true 와 false 값을 반환하고, 
    console.assert()는 false인 경우에만 콘솔에 오류 메세지를 출력합니다. 참인 경우 아무것도 출력하지 않음
    
    2. Logs an error when the boolean statement evaluates to false
    
    false 인 경우에 에러를 출력하는 조건이니  console.assert()가 맞습니다. d
    
- 
    
    b
    
    console.table
    The **`console.table()`** method displays tabular data as a table.
    console.group()
    새로운 인라인 그룹을 생성해 , 이후 모든 출력을 한 단계 들여쓴다. 
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f6f00c97-10e8-4208-aced-f3cba9425af5/Untitled.png)
    
    console.grouptCollapsed( ) 
     웹콘솔에서 새로운 인라인 그룹을 생성한다. 
    collapsed 무너진...;;;
    however, the new group is created collapsed. The user will need to use the disclosure button next to it to expand it, revealing the entries created in the group.
    
    console.info( ) 
    **`console.info()`** method outputs an informational message to the Web console.
    
    ```
    info(obj1)
    info(obj1, /* ..., */ objN)
    info(msg)
    info(msg, subst1, /* ..., */ substN])
    ```
    

NO.62 Refer to the code below:
Let textValue = '1984';
Which code assignment shows a correct way to convert this string to an integer?
A. let numberValue = Number(textValue);
B. Let numberValue = (Number)textValue;
C. Let numberValue = textValue.toInteger();

D. Let numberValue = Integer(textValue);

- 
    
    no integer !! ㅋㅋ자바랑 헷갈리지 않기 
    타입변환 Number( ) , String ( ) or parseInt( ) , parseFloat( ), A
    

**NO.63 A developer at Universal Containers creates a new landing page based on HTML, CSS, and
JavaScript TO ensure that visitors have a good experience, a script named personaliseContext needs
to be executed when the webpage is fully loaded (HTML content and all related files ), in order to do
some custom initialization.**
Which statement should be used to call personalizeWebsiteContent based on the above business
requirement?
A. document.addEventListener(''onDOMContextLoaded', personalizeWebsiteContext);
B. window.addEventListener('load',personalizeWebsiteContext);
C. window.addEventListener('onload', personalizeWebsiteContext);
D. Document.addEventListener('''DOMContextLoaded' , personalizeWebsiteContext);

- 
    
    b
    

NO.64 Given HTML below:
<div>
<div id ="row-uc"> Universal Container</div>
<div id ="row-aa">Applied Shipping</div>
<div id ="row-bt"> Burlington Textiles </div>
</div>
Which statement adds the priority = account CSS class to the universal COntainers row ?
A. Document .querySelector('#row-uc').classes.push('priority-account');
B. Document .queryElementById('row-uc').addclass('priority-account');
C. Document .querySelector('#row-uc').classList.add('priority-account');
D. Document .querySelectorALL('#row-uc').classList.add('priority-account');

- 
    
    c, querySelector(’#’) 자세히 보세요ㅗ
    

**NO.65 Refer to the code below :** 

**function foo( ) {
const a = 2;**

**function bart() { 
console.log(a);
}**

**return bar;
}**

**why does the function bar have access to variable a ?** 

A. Inner function's scope
B. Hoisting
C. Outer function's scope
D. Prototype chain

- 
    
     
    
    anyway let과 const의 유효범위는 블록 스코프이다. C
    문제는 좀 이상ㅎㄴ것 같음 . . 나의 추축 코드
    
    ```
    function foo(){
    const a = 2;
    function bar(){
    console.log(a);
    }
    return bar()
    }
    console.log(foo());
    
    ```
    
    일단 var은 function scope를 가지게 되고, 함수 안에서만 사용이 가능 하다. 
     
    
    ```jsx
    
    function () {
    var a = 10;
    function ( ) {
     var = 20;
    console.log(a) ; // 20 
    
    }
    
    console.log(a) //10
    
    }
    console.log(a) //ReferenceError : a is not defined
    ```
    
    ```jsx
    function hawsValue(p){
    console.log(v); // undefined  호이스팅 되서 선언은 완료된 상태임
    if(p){
    	var v = 'blue'
    	console.log(v) // blue
    	} else {
    			var v = 'red'
    			console.log(v) 
    	}
    
    	console.log(v) //blue
    
    }
    ```
    
    let !
    block - scope(블록 유효 범위) 를 갖는 지역 변수를 선언하는데 사용 . 
    재선언이 불가능 
    
    ```jsx
    {let a = 10
    {
    
        let a =20
        console.log(a)
    }
    console.log(a)
    
    }
    console.log(a)
    
    //instrument.ts:113 20
    //instrument.ts:113 10
    //VM237:10 Uncaught ReferenceError: a is not defined
        at <anonymous>:10:13
    (anonymous) @ VM237:10
    ```
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/26f404db-4c1f-475a-852d-d71573ba7924/Untitled.png)
    

**NO.66 Refer to the following  code:** 

```jsx
<html lang = “en”>
<body>
	<div onclick  = "console.log('Outer message');">
<button id = "myButton"> click me</button>
	</div>
</body>
<script>
function displayMessage(ev) {
 ev.stopPropagation();
	console.log('inner message');
}
const elem = document.getElementById('myButton');
elem.addEventListener('click', displayMessage);
</script>
</html>

```

What will the console show when the button is clicked?
A. Outer message
B. Outer message
Inner message
C. Inner message
Outer message
D. Inner message

- 
    
    스크립트  부터 먼저 실행된다고 생각해랏
    근데 저기서 stopPropagation( ) 이 걸리기 때문에 html의 onclick은 실행되지 않고 inner Message만 출력한다. 
    만약에 stopPropagation( )이 없으면 inner message 다음에 outer Message 를 출력 함 
    

NO. 67 a team that works on a big project uses npm to deal with projects dependencies. 

a developer added a dependency does not get downloaded when they execute npm install.

which two reasons could be possible explanations for this?
choose 2 answer 

A. the developer missed the option —add when adding dependecy.

B. the developer added the dependency as a dev dependency, and NODE_ENV is set to production . 

C. The developer missed the option —save when adding the dependency

- 
    
    b,c
    

NO.69  given code below : 

```jsx
setTimeout( ()=>
(console.log(1);),0
);
console.log(2);
New Promise (()=>{
setTimeout(() => (
	reject(console.log(3));,1000
	);
	.catch(()=>
console.log(4);
)

);
})
console.log(5)
```

A. 2 1 4 3 5
B. 2 5 1 3 4
C. 1 2 4 3 5
D. 1 2 5 3 4

- 
    
    b
    

NO.70 Cloud Kicks has a class to represent items for sale in an online store, as shown below:
Class Item{
constructor (name, price){
[this.name](http://this.name/) = name;
this.price = price;
}
formattedPrice(){
return 's' + String(this.price);}}
A new business requirement comes in that requests a ClothingItem class that should have all of the
properties and methods of the Item class but will also have properties that are specific to clothes.
Which line of code properly declares the clothingItem class such that it inherits from Item?
A. Class ClothingItem implements Item{
B. Class ClothingItem {
C. Class ClothingItem super Item {
D. Class ClothingItem extends Item {

- 
    
    d
    

**NO.71 A class was written to represent items for purchase in an online store, and a second class
Representing items that are on sale at a discounted price. THe constructor sets the name to the first
value passed in. The pseudocode is below:**

class Item {
constructor(name, price) {
this.name = name;
this.price = price;
}
}

class SaleItem extends Item {
constructor(name, price, discount) {
super(name, price);
this.discount = discount;
}
}

let regItem = new Item('Scarf', 55);
let saleItem = new SaleItem('Shirt', 80, -1);

Item.prototype.description = function () {
return 'This is a ' + this.name;
}
console.log(regItem.description());

console.log(saleItem.description());

SaleItem.prototype.description = function () {
return 'This is a discounted ' + this.name;
}
console.log(regItem.description());
console.log(saleItem.description());

what is the output when executing the code above?

A. This is a Scarf
Uncaught TypeError: saleItem.description is not a function
This is aScarf
This is a discounted Shirt
B. This is a Scarf
This is a Shirt
This is a Scarf
This is a discounted Shirt
C. This is a Scarf
This is a Shirt
This is a discounted Scarf
This is a discounted Shirt
D. This is aScarf
Uncaught TypeError: saleItem.description is not a function
This is a Shirt
This is a did counted Shirt

- 
    
     js는 객체를 상속하기 위해서 프로토타입이라는 방식을 사용한다. 
    
    b
    

NO.72 developer wants to use a module named universalContainersLib and them call functions from it.
How should a developer import every function from the module and then call the fuctions foo and
bar ?
A. import * as lib from '/path/universalContainersLib.js';
lib.foo();
lib.bar();
B. import (foo, bar) from '/path/universalContainersLib.js';
foo();
bar();
C. import all from '/path/universalContaineraLib.js';
universalContainersLib.foo();
universalContainersLib.bar();
D. import * from '/path/universalContaineraLib.js';
universalContainersLib.foo();

universalContainersLib.bar();

- 
    
    a
    

**NO.73 Refer to following code:
class Vehicle {
constructor(plate) {
This.plate =plate;
}
}
Class Truck extends Vehicle {
constructor(plate, weight) {
//Missing code
This.weight = weight;
}
displayWeight() {
console.log('The truck ${this.plate} has a weight of ${this.weight} lb.');}} Let myTruck = new
Truck('123AB', 5000); myTruck.displayWeight(); Which statement should be added to line 09 for the
code to display 'The truck 123AB has a weight of 5000lb.'?**
A. Super.plate =plate;
B. super(plate);
C. This.plate =plate;
D. Vehicle.plate = plate;

- 
    
    b
    

**NO.74 Given two expressions var1 and var2. What are two valid ways to return the logical AND of
the two expressions and ensure it is data type Boolean ?**
Choose 2 answers:
A. Boolean(var1 && var2)
B. var1 && var2
C. var1.toBoolean() && var2toBoolean()
D. Boolean(var1) && Boolean(var2)

- 
    
    a, d
    

NO.75 Refer to code below:
console.log(0);
setTimeout(() => (
console.log(1);
});
console.log(2);
setTimeout(() => {
console.log(3);
), 0);
console.log(4);
In which sequence will the numbers be logged?

- 
    
    02413
    

NO.76 Refer to the code below:

```jsx
<html lang="en">
<table onclick="console.log(Table log');">
<tr id="row1">
<td>Click me!</td>
</tr>
<table>
<script>
function printMessage(event) {
console.log('Row log');
}
Let elem = document.getElementById('row1');
elem.addEventListener('click', printMessage, false);
</script>
</html>
```

Which code change should be made for the console to log only Row log when 'Click me! ' is clicked?

A. Add.event.stopPropagation(); to window.onLoad event handler.
B. Add event.stopPropagation(); to printMessage function.
C. Add event.removeEventListener(); to window.onLoad event handler.
D. Add event.removeEventListener(); toprintMessage function.

- 
    
    이벤트 리스너 - 
    `DOM 객체. addEventListener(이벤트명, 실행할 함수명, 옵션)` 
    
    B
    

**NO.77 Refer to HTML below:
<div id ="main">
<div id = " card-00">This card is smaller.</div>
<div id = "card-01">The width and height of this card is determined by its contents.</div>
</div>**
Which expression outputs the screen width of the element with the ID card-01?
A. document.getElementById(' card-01 ').getBoundingClientRest().width
B. document.getElementById(' card-01 ').style.width
C. document.getElementById(' card-01 ').width
D. document.getElementById(' card-01 ').innerHTML.lenght*e

- 
    
    a , getBoundingClientRect( )임.
    
    getBoundingClientRect() method returns the size of an element and its position relative to the viewport, returns a DOMRect object with eight properties: left, top, right, bottom , x, y width height ;
    

NO.78 Refer to the code below:
Let inArray =[ [ 1, 2 ] , [ 3, 4, 5 ] ];
Which two statements result in the array [1, 2, 3, 4, 5] ?
Choose 2 answers
A. [ ]. Concat.apply ([ ], inArray);
B. [ ]. Concat (... inArray);

C. [ ]. concat.apply(inArray, [ ]);
D. [ ]. concat ( [ ....inArray ] );

- 
    
    c랑 d는 
    > Array [Array [1, 2], Array [3, 4, 5]] 이렇게 출력함. 
    
    concat() 메서드는 인자로 주어진 배열이나 값들을 기존 배열에 합쳐서 새 배열을 반환합니다. 
    

NO.79 Which two code snippets show working examples of a recursive function?
Choose 2 answers
A. Let countingDown = function(startNumber) {
If ( startNumber >0) {
console.log(startNumber) ;
return countingDown(startNUmber);
} else {
return startNumber;
}};
B. Function factorial ( numVar ) {
If (numVar < 0) return;
If ( numVar === 0 ) return 1;
return numVar -1;
C. Const sumToTen = numVar => {
If (numVar < 0)
Return;
return sumToTen(numVar + 1)};
D. Const factorial =numVar => {
If (numVar < 0) return;
If ( numVar === 0 ) return 1;
return numVar * factorial ( numVar - 1 );
};

- 
    
    재귀함수란? 함수 안에 자신의 함수를 다시 호출하는 함수를 의미 . 이러한 재귀함수는 자신의 로직을 내부적으로 반복하다가, 일정한 조건이 만족되면 함수를 이탈하여 결과를 도출함. 
    
    근데 모르겠음 이 문제 ㅜㅜ 
    

NO.80 Which three actions can be using the JavaScript browser console?
Choose 3 answers:
A. View and change DOM the page.
B. Display a report showing the performance of a page.
C. Run code that is not related to page.
D. view , change, and debug the JavaScript code of the page.
E. View and change security cookies

- 
    
    a, c d
    

NO.81 

In the browser, the window object is often used to assign variables that require the broadest
scope in an application Node.js application does not have access to the window object by default.
Which two methods are used to address this ?
Choose 2 answers

A. Use the document object instead of the window object.
B. Assign variables to the global object.
C. Create a new window object in the root file.
D. Assign variables to module.exports and require them as needed

- 
    
    b,d
    

NO.82 Refer to the code snippet below:
Let array = [1, 2, 3, 4, 4, 5, 4, 4];
For (let i =0; i < array.length; i++){
if (array[i] === 4) {
array.splice(i, 1);
}
}
What is the value of the array after the code executes?
A. [1, 2, 3, 4, 5, 4, 4]
B. [1, 2, 3, 4, 4, 5, 4]
C. [1, 2, 3, 4, 5, 4]
D. [1, 2, 3, 5]

- 
    
    arr[i]가 4랑 같은 놈을 1개만 제거해랏
    
    plus ex) 
    var mine = [0,1,2,3];
    mine.splice(2,0,5);
    //배열 2번째 위치한 곳에 숫자 5를 추가한다.
    
    → [0.1.5.2.3]
    mine.splice(2 , 0 , 5 , 7);
    //배열 2째에 숫자 5랑 7추가
    
    splice(startNumber, deleteCount, insertValue)
    startnum부터 deletecound몇개 제거하고,  insertvalue 넣을 값
    

NO. 83 a developer has the following arr of student test grades :
let arr = [7,8,5,8,9,] ;
the teacher wants to double each score and then see an arr of the students who scored more than 15 points.
how should the developer implement the request?

A. Let arr1 = arr.filter(( val) => ( return val > 15 )) .map (( num) => ( return num *2 ))
B. Let arr1 = arr.mapBy (( num) => ( return num 2 )) .filterBy (( val ) => return val > 15 )) ;
C. Let arr1 = arr.map((num) => num* * 2). Filter (( val) => val > 15);
D. Let arr1 = arr.map((num) => ( num *2)).filterBy((val) => ( val >15 ));

- 
    
    map ( )  메서드는 배열 내의 모든 요소 각가에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환함.
    ex) 
    const arr = [1,4,9,16] ; 
    const map1 = arr. map(x ⇒ x*2);
    console.log(map1);
    // [2 , 8 , 18 , 32 ] ;
    
    Filterby (X) Filter ! 
    

NO.84 A developer wrote a fizzbuzz function that when passed in a number, returns the following:
* 'Fizz' if the number is divisible by 3.
* 'Buzz' if the number is divisible by 5.
* 'Fizzbuzz' if the number is divisible by both 3 and 5.
* Empty string if the number is divisible by neither 3 or 5.
Which two test cases will properly test scenarios for the fizzbuzz function?
Choose 2 answers

a ) let res = fizzbuzz(5);
console.assert( res ===’’);
b ) let res = fizzbuzz(15);
console.assert ( res ===’fizzbuzz’)
c ) let res = fizzbuzz(Infinity);
console.assert( res ===’’)

d ) let res = fizzbuzz(3);
console.assert ( res===’buzz’)

- 
    
    a → fizzbuzz(5) returns buzz
    d → fizzbuzz(3) returns fizz
    
    ```jsx
    unction fizzbuzz(a) {
        
        if(a%3==0 && a%5==0) {
            console.log("fizzbuzz");
        } else if (a%3 ==0) {
            console.log("fizz");
        } else if (a%5==0) {
            console.log("buzz");
        } else {console.log("no String");}
    }
    
    // fizzbuzz(3);
    // fizzbuzz(5);
    // fizzbuzz(15);
    // fizzbuzz(2);
    
    for(i=0; i<16;i++) {
        console.log(i + "의 값은");
        fizzbuzz(i);
    }
    console.log("++++++++");
    fizzbuzz(Infinity);
    
    ```
    

NO85. a developer implements a function that adds a few values.
function sum(num) {
if(num == undefined) {

num = 0;

} return function (num2 , num3) {

if( num3 === undefined) {
num3 = 0;

} return num + num2+ num3;

}
}
which 3 options can the developer invoke for this function to get return value of 10?

- 
    
    sum( fun(num) 이 들어감) ( fun(num2, num3) 이 들어감)
    a ) sum( ) (20)  : 첫번째 function은 undefiend, 두번째꺼는 20이 num2  이던 num 3이던 다 더한값만 알면 되는거니까 0 + 0 + 20  해서 20을 출력함
    
    b) sum(5, 5) ( )  → fist function은 파라미터를 1개만 받는다. NaN 을 출력 
    
    c) 10
    d ) 10
    e) sum(10)() 두번째 function 은 파라미터가 최소 하나는 있어야 함 
    

NO. 86

refer to code below:
Const objBook = {
Title: 'Javascript',
};
Object.preventExtensions(objBook);
Const newObjBook = objBook;
newObjectBook.author = 'Robert';
What are the values of objBook and newObjBook respectively ?
A. [title: "javaScript"] [title: "javaScript"]
B. {author: "Robert", title: "javaScript}
Undefined
C. {author: "Robert", title: "javaScript}
{author: "Robert", title: "javaScript}
D. {author: "Robert"}
{author: "Robert", title: "javaScript}

- 
    
    .preventExtensions 는 개체에 속성이 확장하지 못하도록 막음.  상속개념이아니라 프로퍼티를 더 못붙힘. 새로운 속성이 객체에 추가되는 것을 방지 . 
    

NO.87

refer to the code below : 
let foodMenu1 = [’pizza’ , ‘burger’, ‘french’];

let finalMenu = foodMenu1;

finalMenu.push(’garlic bread’);

what is value of foodMenu1 after the code execute? 

- 
    
    push 는 배열 끝에다가 매개변수를 집어 넣고, length를 반환함 
    
    ex) 
    const animals = [’pigs’ , ‘goats’ , ‘sheep’ ];
    const count = animals.push(’cow);
    console.log(count) //4
    console.log(animals);// [pigs, goats, sheep, cow]
    

NO88. Given the code below:
const copy = JSON.stringify([ new String(' false '), new Bollean( false ), undefined ]); What is the value
of copy?
A. -- [ \"false\" , { } ]--
B. -- [ false, { } ]--
C. -- [ \"false\" , false, undefined ]--
D. -- [ \"false\" ,false, null ]--

NO.89 Refer to code below:
function Person() {
this.firstName = 'John';
}
Person.prototype ={
Job: x => 'Developer'
};
const myFather = new Person();
const result =myFather.firstName + ' ' + myFather.job();
What is the value of the result after line 10 executes?

A. Error: myFather.job is not a function
B. Undefined Developer
C. John undefined
D. John Developer

- 
    
    function Person() {
    this.firstName = 'john';
    }
    // Person.prototype={
    //   job:x => 'developer'
    // };
    Person.prototype.job = function(){
    return "메롱";
    }
    const myFather = new Person();
    const result = myFather.firstName + myFather.job();
    console.log(result);
    
    proptotype 속성을 이용하여 멤버를 추가하였음. 프로토 타입이라는 객체에 job( )  이라는 함수를 추가하면 멤버를 추가하기 전에 생성된 객체에서도 추가된 멤버를 사용할 수 있음.
    같은 prototype  을 이용하여 생성된  myFather 역시 job ( )  을 이용할 수 있다. 
    
    만약 아빠를 이용하여 
    
    job () 을 수정한다고 하여도
    원형의 프로토타입에는 영향을 주지 않는다. 
    자바스크립트에서 기본 데이터 타입을 제외한 모든것은 객체이다. 객체가 만들어 지기 위해선 자신을 만드는데 사용된 ( 복제의 원본에서) 원형인 프로토 타입 객체를 이용해서 객체를 만든다. 이때, 만들어진 객체안에 프로토 속성이 자신을 만들어낸 원형을 의미하는 프로토 타입 원ㅇ형 객체를 참조하는 숨겨진 링크가 있음. 이 숨겨진 링크를 프로토 타입이라고 정의한다. 
    
    function Person() {
    this.firstName = 'john';
    }
    // Person.prototype={
    //   job:x => 'developer'
    // };
    Person.prototype.job = function(){
    return "메롱";
    }
    const myFather = new Person();
    const myMother = new Person();
    const result = myFather.firstName + myFather.job();
    console.log(result);
    
    myFather.job = function () {
    return "사장";
    }
    console.log( myFather.job());
    console.log( myMother.job());
    

NO.90 A developer is setting up a new Node.js server with a client library that is built using events
and callbacks.
The library:

- Will establish a web socket connection and handle receipt of messages to the server
- Will be imported with require, and made available with a variable called we.

The developer also wants to add error logging if a connection fails.
Given this info, which code segment shows the correct way to set up a client with two events that
listen at execution time?
A. ws.connect (( ) => {
console.log('connected to client'); }).catch((error) => { console.log('ERROR' , error); }};
B. ws.on ('connect', ( ) => {
console.log('connected to client'); ws.on('error', (error) => { console.log('ERROR' , error); });
});
C. ws.on ('connect', ( ) => { console.log('connected to client'); }}; ws.on('error', (error) => {
console.log('ERROR' , error); }};

D. try{
ws.connect (( ) => {
console.log('connected to client'); });
} catch(error) { console.log('ERROR' , error); };
}

- 
    
    ws.on(’connection’, ()  ⇒ { ... } );
    

NO.91 A test has a dependency on database. query. During the test, the dependency is replaced
with an object called database with the method, Calculator query, that returns an array. The
developer does not need to verify how many times the method has been called.
Which two test approaches describe the requirement?
Choose 2 answers
A. White box
B. Stubbing
C. Black box
D. Substitution

- 
    
    a, d
    

NO.92 Consider type coercion, what does the following expression evaluate to?
True + 3 + '100' + null
A. 104
B. 4100
C. '3100null'
D. '4100null'

- 
    
    d    
    

NO.93 Which statement accurately describes an aspect of promises?
A. Arguments for the callback function passed to .then() are optional.
B. In a.then() function, returning results is not necessary since callbacks will catch the result of a
previous promise.
C. .then() cannot be added after a catch.
D. .then() manipulates and returns the original promise.

NO.94 Refer to code below:
Let productSKU = '8675309' ;
A developer has a requirement to generate SKU numbers that are always 19 characters lon, starting
with 'sku', and padded with zeros.
Which statement assigns the values sku0000000008675309 ?
A. productSKU = productSKU .padStart (19. '0').padstart('sku');
B. productSKU = productSKU .padEnd (16. '0').padstart('sku');
C. productSKU = productSKU .padEnd (16. '0').padstart(19, 'sku');
D. productSKU = productSKU .padStart (16. '0').padstart(19, 'sku');

- 
    
    . padStart ( 자리수, ‘ 체울 문자’) 
    ex) .padstart(16, 0)은 16자리수를 0을 왼쪽부터 채워서 만들어랏
    
    ex2) 
    const fullNumber = ‘203492834298374’;
    const last4Digits = fullNumber.slice(-4);
     const makedNumber = last4Digits. padStart(fullNumber.length, ‘*’);
    
    // “********************8375”
    

NO.95 Which three options show valid methods for creating a fat arrow function?
Choose 3 answers
A. x => ( console.log(' executed ') ; )
B. [ ] => ( console.log(' executed ') ;)
C. ( ) => ( console.log(' executed ') ;)
D. X,y,z => ( console.log(' executed ') ;)
E. (x,y,z) => ( console.log(' executed ') ;)

- 
    
    A , C , E
    

NO.96 Refer to the code below:
let sayHello = () => {
console.log ('Hello, world!');
};
Which code executes sayHello once, two minutes from now?
A. setTimeout(sayHello, 12000);
B. setInterval(sayHello, 12000);
C. setTimeout(sayHello(), 12000);
D. delay(sayHello, 12000);

- 
    
    A
    

NO.97 Refer to the code below:
new Promise((resolve, reject) => {
const fraction = Math.random();
if( fraction >0.5) reject("fraction > 0.5, " + fraction);
resolve(fraction);
})
.then(() =>console.log("resolved"))
.catch((error) => console.error(error))
.finally(() => console.log(" when am I called?"));

- 
    
    fraction 분수 
    
    then 으로 가던 캐치로 가던 
    finally 는 무조건 출력 
    
    D
    
- 
    
    <!DOCTYPE html>
    <html>
    <head>
    <script type="text/javascript">
    var bDisplay = true;
    function doDisplay(){
    var con = document.getElementById("myDIV");
    if(con.style.display=='none'){
    con.style.display = 'block';
    }else{
    con.style.display = 'none';
    }
    }
    </script>
    </head>
    <body>
    <a href="javascript:doDisplay();">> 내용보기</a><br/><br/>
    <div id="myDIV">
    <h1>내용을 접거나 펴는 방법</h1>
    <p>display block 속성값은 내부 요소를 나타나게 하며 none 는 사라지게 합니다.</p>
    </div>
    </body>
    </html>
    
    NO.99 Which code statement below correctly persists an objects in local Storage ?
    A. const setLocalStorage = (storageKey, jsObject) => {
    window.localStorage.setItem(storageKey, JSON.stringify(jsObject));
    }
    B. const setLocalStorage = ( jsObject) => {
    window.localStorage.connectObject(jsObject));
    }
    C. const setLocalStorage = ( jsObject) => {
    window.localStorage.setItem(jsObject);
    }
    D. const setLocalStorage = (storageKey, jsObject) => {
    window.localStorage.persist(storageKey, jsObject);
    
    - 
        
        웹스토리지는 기본적으로 key value 로 이루어진 데이터를 저장할 수 있음 . 개념적으로 해시테이블 자료구조를 생각하면 쉽다. 
        키에 데이터를 쓰려면
        
        localStorage.setItem(”key, value);
        
        ```
        // 키에 데이터 쓰기
        localStorage.setItem("key", value);
        
        // 키로 부터 데이터 읽기
        localStorage.getItem("key");
        
        // 키의 데이터 삭제
        localStorage.removeItem("key");
        
        // 모든 키의 데이터 삭제
        localStorage.clear();
        
        // 저장된 키/값 쌍의 개수
        localStorage.length;
        ```
        

NO.100 Refer to the code below:
Function Person(firstName, lastName, eyecolor) {

this.firstName =firstName;
this.lastName = lastName;
this.eyeColor = eyeColor;
}
Person.job = 'Developer';
const myFather = new Person('John', 'Doe');
console.log(myFather.job);
What is the output after the code executes?
A. ReferenceError: eyeColor is not defined
B. ReferenceError: assignment to undeclared variable "Person"
C. Developer
D. Undefined

- 
    
    myFather 에 job을 넣어주려면 프로토타입으로 설정해야함. 
    

NO.101 A developer creates a simple webpage with an input field. When a user enters text in the
input field and clicks the button, the actual value of the field must be displayed in the console.
Here is the HTML file content:
<input type =" text" value="Hello" name ="input">
<button type ="button" >Display </button>
The developer wrote the javascript code below:
Const button = document.querySelector('button');
button.addEvenListener('click', () => (
Const input = document.querySelector('input');
console.log(input.getAttribute('value'));
When the user clicks the button, the output is always "Hello".
What needs to be done make this code work as expected

A. Replace line 04 with console.log(input .value);
B. Replace line 03 with const input = document.getElementByName('input');
C. Replace line 02 with button.addEventListener("onclick", function() {
D. Replace line 02 with button.addCallback("click", function() {

- 
    
    getAttribute 를 통해서 밸류값을 가져오나 .value 나 똑같음 ㅋ
    
    //A
    

NO.102 A developer receives a comment from the Tech Lead that the code given below has error:
const monthName = 'July';
const year = 2019;
if(year === 2019) {
monthName = 'June';
}
Which line edit should be made to make this code run?
A. 01 let monthName ='July';
B. 02 let year =2019;
C. 02 const year = 2020;
D. 03 if (year == 2019) {

- 
    
    a
    

NO.103 At Universal Containers, every team has its own way of copying JavaScript objects. The code
Snippet shows an implementation from one team:
Function Person() {
this.firstName = "John";
this.lastName = 'Doe';
[This.name](http://this.name/) =() => (
console.log('Hello $(this.firstName) $(this.firstName)');
)}
Const john = new Person ();
Const dan = JSON.parse(JSON.stringify(john));
dan.firstName ='Dan';
[dan.name](http://dan.name/)();
What is the Output of the code execution?
A. Hello Dan Doe
B. Hello John DOe
C. TypeError: [dan.name](http://dan.name/) is not a function
D. TypeError: Assignment to constant variable.

NO.104 Refer to the code below:
Const searchTest = 'Yay! Salesforce is amazing!" ;
Let result1 = searchText.search(/sales/i);
Let result 21 = searchText.search(/sales/i);
console.log(result1);
console.log(result2);
After running this code, which result is displayed on the console?

A. > true > false
B. > 5 >undefined
C. > 5 > -1
D. > 5 > 0

- 
    
    
    ```
    const searchText = 'Yay! Salesforce is amazing!';
    let result1 = searchText.search(/sales/i);
    let result2 = searchText.search(/sales/);
    console.log(result1);
    console.log(result2);
    
    ```
    문제가 위 처럼 나온다면 ,
    3번째 줄이 let resut21 이 아니라 result2 라고 선언하고 (/sales/ ) 가 들어가면
    대소문자를 구분하기 때문에  sales를 매치하는게 없어서
     -1을 출력합니다... search.(/텍스트/i ); 는 대소문자 구분 안함 <- insensitive 조심하세욧
    

NO.105 Given the code below:
const delay = sync delay => {

Return new Promise((resolve, reject) => {
setTimeout (resolve, delay);});};
const callDelay =async () =>{
const yup =await delay(1000);
console.log(1);
What is logged to the console?
A. 1 2 3
B. 1 3 2
C. 2 1 3
D. 2 3 1

- 
    
    모임?
    

NO.106 A developer is asked to fix some bugs reported by users. To do that, the developer adds a
breakpoint for debugging.
Function Car (maxSpeed, color){
This.maxspeed =masSpeed;
This.color = color;
Let carSpeed = document.getElementById(' CarSpeed');
Debugger;
Let fourWheels =new Car (carSpeed.value, 'red');
When the code execution stops at the breakpoint on line 06, which two types of information are
available in the browser console ?
Choose 2 answers:
A. The values of the carSpeed and fourWheels variables
B. A variable displaying the number of instances created for the Car Object.
C. The style, event listeners and other attributes applied to the carSpeed DOM element
D. The information stored in the window.localStorage property

- 
    
    c, d
    

NO.107 Refer to the code below:
const addBy = ?
const addByEight =addBy(8);
const sum = addBYEight(50);
Which two functions can replace line 01 and return 58 to sum?
Choose 2 answers
A. const addBy = function(num1){
return function(num2){
return num1 + num2;
}
B. const addBy = function(num1){
return num1 + num2;
}
C. const addBy = (num1) => num1 + num2 ;
D. const addBY = (num1) => (num2) => num1 + num2;

- 
    
    (a) function addBy(num1){
     return addBy(num2){
    
    return num1+num2;   
    
    }
    }
    
    화살표 함수로 바꾸자
    
    let addBy = (num1) ⇒ (num2) ⇒ (num1+num2);
    
    화살표 함수
    function addNum (num1 , num2) { return num1+ num2;} 
    
    let addNum = function(num1, num2) { return num1+num2;}
    
    let addNum ⇒( num1, num2 ) ⇒ {num1+ num2};
    
    // let addNum(num1, num2) ⇒ num1+ num2;
    

NO.108 Universal Containers (UC) just launched a new landing page, but users complain that the
website is slow. A developer found some functions any that might cause this problem. To verify this,
the developer decides to execute everything and log the time each of these three suspicious
functions consumes.
Which function can the developer use to obtain the time spent by every one of the three functions?

```jsx
console.time('perform');
maybeHeavyFunction();
thisCouldTakeTooLong();
orMaybethis();
console.entTime('perform');

```

A. console. timeLog ()
B. console.timeStamp ()
C. console.trace()
D. console.getTime ()

- 
    
    a
    

NO.109 Refer to the code below:
let timeFunction =() => {
console.log('Timer called.");
};
let timerId = setTimeout (timedFunction, 1000);
Which statement allows a developer to cancel the scheduled timed function?
A. removeTimeout(timedFunction);
B. removeTimeout(timerId);
C. clearTimeout(timerId);
D. clearTimeout(timedFunction);

NO.110 developer has a web server running with Node.js. The command to start the web server is
node server,js. The web server started having latency issues. Instead of a one second turn around for
web requests, the developer now sees a five second turnaround, Which command can the web
developer run to see what the module is doing during the latency period?
A. DEBUG = http, https node server.js
B. NODE_DEBUG =http, https node server.js
C. DEBUG =true node server.js

D. NODE_DEBUG =true node server.js

- 
    
    c
    

NO.111 developer removes the HTML class attribute from the checkout button, so now it is simply:

Checkout

.
There is a test to verify the existence of the checkout button, however it looks for a button with
class= "blue". The test fails because no such button is found.
Which type of test category describes this test?
A. True positive
B. True negative
C. False positive
D. False negative

- 
    
    D
    

NO.112 Refer to the code snippet:
Function getAvailabilityMessage(item) {
If (getAvailability(item)){
Var msg ="Username available";
}
Return msg;
}
A developer writes this code to return a message to user attempting to register a new username. If
the username is available, variable.
What is the return value of msg hen getAvailabilityMessage ("newUserName" ) is executed and
getAvailability("newUserName") returns false?
A. "Username available"
B. "newUserName"
C. "Msg is not defined"
D. undefined

- 
    
    D
    

NO113. developer uses the code below to format a date

```jsx
const date = new Date(2020, 05, 10);
const dateDisplayOptions = {
	year: 'numeric',
	month: 'long',
	day: 'numeric'
}

const formattedDate = date.toLocaleDateString('en', dateDisplayOptions);

```

After executing, what is the value of formattedDate?
A. May 10, 2020
B. June 10, 2020

C. October 05, 2020
D. November 05, 2020

- 
    
    new Date()를 이용하여 현재 날짜를 추출할 수 있고 
    
    date.toLocaleDateString()을 사용하여 날짜를 상세하게 표현할 수 있음. 
    ’en’을 넣으면 영어로 출력하고, ‘ko’는 한국어를 표시, numeric은 숫자를 추출, long 하면 글자를 표시 
    

NO.114 Refer to the code below:
const event = new CustomEvent(
//Missing Code
);
obj.dispatchEvent(event);
A developer needs to dispatch a custom event called update to send information about recordId.
Which two options could a developer insert at the placeholder in line 02 to achieve this?
Choose 2 answers
A. 'Update' , (
recordId : '123abc'
(
B. 'Update' , '123abc'
C. { type : 'update', recordId : '123abc' }
D. 'Update' , {
Details : {
recordId : '123abc'
}
}

- 
    
    a d
    

NO.115 The developer has a function that prints "Hello" to an input name. To test this, thedeveloper
created a function that returns "World". However the following snippet does not print " Hello
World".

```jsx
const sayHello = (name) =>{\
	console.log('hello', name());
};
const world = ()=> {
return "wordl";};

sayHello(world);
	

```

A. Change line 7 to ) () ;
B. Change line 2 to console.log('Hello' , name() );
C. Change line 9 to sayHello(world) ();
D. Change line 5 to function world ( ) {

NO.116 Given the following code:
document.body.addEventListener(' click ', (event) => {
if (/* CODE REPLACEMENT HERE */) {
console.log('button clicked!');
)
});
Which replacement for the conditional statement on line 02 allows a developer to correctly
determine that a button on page is clicked?
A. Event.clicked
B. e.nodeTarget ==this
C. event.target.nodeName == 'BUTTON'
D. button.addEventListener('click')

- 
    
    c
    

NO.117 Refer to the code below:
01 let car1 = new promise((_, reject) =>
02 setTimeout(reject, 2000, "Car 1 crashed in"));
03 let car2 = new Promise(resolve => setTimeout(resolve, 1500, "Car 2
completed"));
04 let car3 = new Promise(resolve => setTimeout (resolve, 3000, "Car 3
Completed"));
05 Promise.race([car1, car2, car3])
06 .then(value => (
07 let result = $(value) the race. `;
08 ))
09 .catch( arr => (
10 console.log("Race is cancelled.", err);
11 ));

- 
    
    Promise.race( )_ 는 Promise 객체를 반환함. 이 프로미스 객체는 iterable안에 있는 프로미스 중에 가장 먼저 완료된 것의 결과값으로 그대로 이행하거나 거부함. 젤빨리나오는것을 출력한다는 마링ㄴ듯ㅋ
    C
    

NO.118 

<input type=”file” onchange=”previewFile()”>

the JavaScript portion is : 
function previewFile( ) {
const preview = document.querySelector(’img’);
cosnt file = document.querySelector(’input[type=file]’).files[0];

//line 4

reader.addEventListener(”load”, () ⇒ {
preview.src = reader.result ; }, false);

//line 8

}
}

In lines 04 and 08, which code allows the user to select an image from their local computer , and to
display the image in the browser?
A. 04 const reader = new File();
08 if (file) URL.createObjectURL(file);
B. 04 const reader = new FileReader();
08 if (file) URL.createObjectURL(file);
C. 04 const reader = new File();
08 if (file) reader.readAsDataURL(file);
D. 04 const reader = new FileReader();
08 if (file) reader.readAsDataURL(file);

- 
    
    d
    

NO.119 A developer wrote the following code:
01 let X = object.value;
02
03 try {
04 handleObjectValue(X);
05 } catch (error) {
06 handleError(error);
07 }
The developer has a getNextValue function to execute after handleObjectValue(), but does not want
to execute getNextValue() if an error occurs.
How can the developer change the code to ensure this behavior?
A. 03 try{
04 handleObjectValue(x);
05 } catch(error){

06 handleError(error);
07 } then {
08 getNextValue();
09 }
B. 03 try{
04 handleObjectValue(x);
05 } catch(error){
06 handleError(error);
07 } finally {
08 getNextValue();
10 }
C. 03 try{
04 handleObjectValue(x);
05 } catch(error){
06 handleError(error);
07 }
08 getNextValue();
D. 03 try {
04 handleObjectValue(x)
05 ........................

- 
    
    d
    

NO.120 A developer wants to set up a secure web server with Node.js. The developer creates a
directory locally called app-server, and the first file is app-server/index.js Without using any thirdparty libraries, what should the developer add to index.js to create the secure web server?
A. const https =require('https');
B. const server =require('secure-server');
C. const tls = require('tls');
D. const http =require('http');

- 
    
    a
    

NO.121 A developer uses a parsed JSON string to work with user information as in the block below:
01 const userInformation ={
02 " id " : "user-01",
03 "email" : "user01@universalcontainers.demo",
04 "age" : 25
Which two options access the email attribute in the object?
Choose 2 answers
A. userInformation["email"]
B. userInformation.get("email")
C. userInformation.email
D. userInformation(email)

- 
    
    대괄호로 추철하거나, .마침표로 추출하거나 
    a.c
    

NO.123 GIven a value, which three options can a developer use to detect if the value is NaN?
Choose 3 answers !
A. value == NaN
B. [Object.is](http://object.is/)(value, NaN)
C. value === Number.NaN
D. value ! == value
E. Number.isNaN(value)

- 
    
    b,d,e
    

NO.124 A developer has the function, shown below, that is called when a page loads.
function onload() {
console.log("Page has loaded!");
}
Where can the developer see the log statement after loading the page in the browser?
A. Terminal running the web server.
B. Browser performance toots
C. Browser javaScript console

D. On the webpage.

- 
    
    c
    

NO.125 Refer to the code below:
01 const server = require('server');
02 /* Insert code here */
A developer imports a library that creates a web server. The imported library uses events and
callbacks to start the servers Which code should be inserted at the line 03 to set up an event and
start the web server ?
A. Server.start ();
B. server.on(' connect ' , ( port) => {
console.log('Listening on ' , port) ;})
C. server()
D. serve(( port) => (
E. console.log( 'Listening on ', port) ;

NO.125 Refer to the code below:
01 const server = require('server');
02 /* Insert code here */
A developer imports a library that creates a web server. The imported library uses events and
callbacks to start the servers Which code should be inserted at the line 03 to set up an event and
start the web server ?
A. Server.start ();
B. server.on(' connect ' , ( port) => {
console.log('Listening on ' , port) ;})
C. server()
D. serve(( port) => (
E. console.log( 'Listening on ', port) ;

- 
    
    b
    

NO.126 A developer wants to use a try...catch statement to catch any error that countSheep () may
throw and pass it to a handleError () function.
What is the correct implementation of the try...catch?

```jsx
a) try {
	setTimeout(function(){
countsheep();
}, 1000);
} catch (e) { handleError(e);}

b) 
try{ countSheep();} finally{ handleError(e);}

c)
setTimeout(function(){try{counterSheep();} catch(e){handleError(e)}}, 1000);
d)
try{ counterSheep();} handleError(e){catch(e)}
```

- 
    
    a
    

NO.127 A developer creates a simple webpage with an input field. When a user enters text in the
input field and clicks the button, the actual value of the field must be displayed in the console.
Here is the HTML file content:

Display

The developer wrote the javascript code below:
Const button = document.querySelector('button');
button.addEvenListener('click', () => (
Const input = document.querySelector('input');
console.log(input.getAttribute('value'));
When the user clicks the button, the output is always "Hello".
What needs to be done to make this code work as expected?
A. Replace line 04 with console.log(input .value);
B. Replace line 03 with const input = document.getElementByName('input');
C. Replace line 02 with button.addCallback("click", function() {
D. Replace line 02 with button.addEventListener("onclick", function() {

- 
    
    a
    

NO.128 A developer is required to write a function that calculates the sum of elements in an array
but is getting undefined every time the code is executed. The developer needs to find what is missing
in the code below.
Const sumFunction = arr => {
Return arr.reduce((result, current) => {
//
Result += current;

//
), 10);
);
Which option makes the code work as expected?
A. Replace line 02 with return arr.map(( result, current) => (
B. Replace line 04 with result = result +current;
C. Replace line 03 with if(arr.length == 0 ) ( return 0; )
D. Replace line 05 with return result;

- [https://www.zerocho.com/category/JavaScript/post/5acafb05f24445001b8d796d](https://www.zerocho.com/category/JavaScript/post/5acafb05f24445001b8d796d)

NO.129 A developer has a formatName function that takes two arguments, firstName and lastName
and returns a string. They want to schedule the function to run once after five seconds.
What is the correct syntax to schedule this function?
A. setTimeout (formatName(), 5000, "John", "BDoe");
B. setTimeout (formatName('John', ''Doe'), 5000);
C. setTimout(() => { formatName("John', 'Doe') }, 5000);
D. setTimeout ('formatName', 5000, 'John", "Doe');

- 
    
    C, 왼쪽에 함수 오른쪽에 몇초인지 넣고 인자 전달은 함수에다가 하는게 맞는듯..
    

NO.130 A developer is debugging a web server that uses Node.js The server hits a runtimeerror
every third request to an important endpoint on the web server.
The developer added a break point to the start script, that is at index.js at he root of the server's
source code. The developer wants to make use of chrome DevTools to debug.
Which command can be run to access DevTools and make sure the breakdown is hit ?
A. node -i index.js
B. Node --inspect-brk index.js
C. Node inspect index.js
D. Node --inspect index.js

- 
    
    d
    

NO.131 The developer wants to test the array shown:
const arr = Array(5).fill(0)
Which two tests are the most accurate for this array ?
Choose 2 answers:
A. console.assert( arr.length === 5 );
B. arr.forEach(elem => console.assert(elem === 0)) ;
C. console.assert(arr[0] === 0 && arr[ arr.length] === 0);
D. console.assert (arr.length >0);

- 
    
    new Array(5) 를 하게되면 길이가 5인 즉 Array.length = 5 배열을 만든다.
    
    fill(0)을 하면 그 5개가 들어가는 배열을 0으로 채워라는 말이며, [0,0,0,0,0]를 만들게 됨.
    
    a랑 b는 모두 true를 출력하며, C가 햇갈렸는데 생각해보니 arr[arr.length ]는 arr[5]인데 5는 없고 0부터 4까지 출력하는 것이니  false가 나옴 정확하지 않음.그래서 ab
    

NO.132 A developer is working on an ecommerce website where the delivery date is dynamically
calculated based on the current day. The code line below is responsible for this calculation.
Const deliveryDate = new Date ();
Due to changes in the business requirements, the delivery date must now be today's date + 9 days.

Which code meets this new requirement?
A. deliveryDate.setDate(( new Date ( )).getDate () +9);
B. deliveryDate.setDate( Date.current () + 9);
C. deliveryDate.date = new Date(+9) ;
D. deliveryDate.date = Date.current () + 9;

NO.133 A developer wrote the following code to test a sum3 function that takes in an array of
numbers and returns the sum of the first three numbers in the array, and the test passes.
A different developer made changes to the behavior of sum3 to instead sum only the first two
numbers present in the array

```jsx
let res = sum3([1,4,1]);
console.assert(res = ==6);
res = sum3( [1,5,0,5] );
console.assert(res ===6);
```

Which two results occur when running this test on the updated sum3 function?
Choose 2 answers
A. The line 05 assertion passes.
B. The line 02 assertion passes.
C. The line 02 assertion fails.
D. The line 05 assertion fails

NO.134 A developer wants to create an object from a function in the browser using the code below:
Function Monster() { [this.name](http://this.name/) = 'hello' };
Const z = Monster();
What happens due to lack of the new keyword on line 02?
A. The z variable is assigned the correct object.
B. The z variable is assigned the correct object but [this.name](http://this.name/) remains undefined.
C. [Window.name](http://window.name/) is assigned to 'hello' and the variable z remains undefined.
D. Window.m is assigned the correct object.

- 
    
    c
    

NO.135 Refer to the following array:
Let arr = [ 1,2, 3, 4, 5];
Which three options result in x evaluating as [3, 4, 5] ?
Choose 3 answers.

A. Let x= arr.filter (( a) => (a<2));
B. Let x= arr.splice(2,3);
C. Let x= arr.slice(2);
D. Let x= arr.filter((a) => ( return a>2 ));

- 
    
    .filter( )를 통해서 파라미터로 들어와 리턴되는 값 만 추출해준다. 
    (A)는 2보다 작은 값을 리턴하기 때문에 [1]
    
    (c)는 .slice( ) 함수는 배열 인덱스 구간을 (얕게 복사한) 배열의 객체를 반환한다. 
    지울 원소의 개수 추가할 원소들을 받아 원본 배열 객체를 직접 수정한다.
    
    array. slice( [ begin [ , end] ] )
    
    ```
    > nums = Array(20).fill().map((_, i) => i)
    < [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
    ```
    
     0부터 19까지의 숫자 배열이다, 이 숫자 배열에서 5부터 9까지 복사한 값을 담고 있는 새로운 배열을 만들어 보자 
    
    >num.slice(5, 10) //  [5,6,7,8,9]
    **여기서 주의할 점은 첫번째 인자로 넘어온 시작 인덱스가 가리키는 값은 포함하지만, 두번째 인자로 넘어온 종료 인덱스는 포함이 되지 않는다는 것. 
    두번째 인자를 넘기지 않으면 시작 인덱스가 가리키는 값부터 배열의 마지막 값까지 모두 복사해 줌. 
    c같은 경우에는 2 시작 인덱스 부터 끝까지 배열을 복사한 값을 담은 새로운 배열을 만든다. 
    그러면 2번째 3 포함 [3,4,5]
    
    **splice**( ) 는 다목적으로 사용이 가능하다. 배열로부터 특정범위를 삭제하거나 새로운 값을 추가 또는 기존 값을 대체할 수 있다. 
    
    첫번째 인자로 시작인덱스 
    두번째 인자로 몇개의 값을 삭제할 지
    세번재 인자로 부터는 추가할 값을 가변 인자로 넘길 수 있으며 삭제된 값을 담고 있는 배열을 반환한다.  
    
    > nums = Array(20).fill().map((_, i) => i)
    < [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
    > 
    
    이 숫자 배열에서 5가 가리키는 값 부터 3개 삭제 하기
    nums.splice(5, 3)
    // 
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bae72825-1946-4746-abf8-01827e8c4a22/Untitled.png)
    
    삭제된 3개의 값을 담고 있는 배열이 반환되며, 원본 배열로 3개의 값이 빠져나간 것을 알 수 있다. 
    값을 아무 값도 삭제하지 않고 -5, -6 , -7을 사라진 자리에 넣을 수 도 있다. 
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/767f9c90-a7ba-4c74-8639-c8119d337852/Untitled.png)
    
    0을 넣으면 삭제 하지 않는다. 
    그때신 3번째 인자로 부터 추가 할 값들이 채워진다. 
    
    숫자를 대체도 가능하다. 
    10번째 숫자로부터 10 11을 -10 -11 로 변경해 보겠다. 
    
    nums.splice(10,2,-10, -11); 하고 nums 를 출력하면 값이 나온다 . 
    
    10번째 숫자로 부터 2개 삭제하고 -10이랑 -11 로 채워넣는다. 
    
    그래서 b는 splice(2,3)두번째 숫자를 두번째 숫자부터 세개 삭제
    x를 출력하면 뜯어진 값 345가 나오고 arr을 출력하면 1과 2가 나온다 . 
    결론은 splice를 값을 뽑을때는 
    let x = nums.splice();를 출력할 것인지 
    
    아니면 nums를 출력할 것인지 헷갈리지 말아야 겠다. splice는 내가 변형하는 조각을 추출하는거고 전체 배열을 출력하는건 내가 조각을 뜯어냈거나 바꿔낸 최종 결과물을 출력하는 것이다/ 
    

NO.136 Refer to code below:
Let a ='a';
Let b;
// b = a;
console.log(b);
What is displayed when the code executes?
A. ReferenceError: b is not defined
B. A
C. Undefined
D. Null

- 
    
    c
    

NO.137 Which three browser specific APIs are available for developers to persist data between page
loads ?
Choose 3 answers
A. IIFEs
B. indexedDB
C. Global variables
D. Cookies
E. localStorage.

- 
    
    BDE
    

NO.138 Given the code below:
01 function GameConsole (name) {
02 [this.name](http://this.name/) = name;
03 }
04
05 GameConsole.prototype.load = function(gamename) {
06 console.log(  `$(this.name) is loading a game : $(gamename) ...`);
07 )
08 function Console 16 Bit (name) {
09 GameConsole.call(this, name) ;
10 }
11 Console16bit.prototype = Object.create ( GameConsole.prototype) ;
12 //insert code here
13 console.log(  `$(this.name) is loading a cartridge game : $(gamename) ...`);
14 }
15 const console16bit = new Console16bit(' SNEGeneziz ');
16 console16bit.load(' Super Nonic 3x Force ');
What should a developer insert at line 15 to output the following message using the method ?

> SNEGeneziz is loading a cartridge game: Super Monic 3x Force . . .
> 

A. Console16bit.prototype.load(gamename) = function() 

B. Console16bit.prototype.load = function(gamename) {
C. Console16bit = Object.create(GameConsole.prototype).load = function
(gamename) {
D. Console16bit.prototype.load(gamename) {

- 
    
    
    밑의 설명을 참조하고 만약에 
    
    Console16bit.prototype.load  = function () {} 을 재 설정해주지 않으면, 
    Console16bit의 객체 console16bit를 만들었을때, 이 객체는 GameConsole.prototype을 받게 되므로 is loading a game 으로 출력 됨
    
    그래서 뽀인트는 prototype을 재 설정해줘야 한다는 말 ..
    
    ```jsx
    function GameConsole(name){
        this.name = name;
    }
    
    GameConsole.prototype.load = function (gamename) {
        console.log(`${this.name} is loading a game : ${gamename}`);
    }
    
    function Console16Bit(name) {
        GameConsole.call(this, name);
    }
    
    Console16Bit.prototype = Object.create(GameConsole.prototype);
    
    Console16Bit.prototype.load = function (gamename) {
        console.log(`${this.name} is loading a cartridge game : ${gamename}...`);
    }
    
    const console16Bit = new Console16Bit(' SNE Genezizzz');
    console16Bit.load('Super Nonic 3xForce');
    ```
    
    fucntion . prototype. call ( ) 은 주어진 this값 및 각각 전달된 인수와 함께 함수를 호출한다. 
    
    무슨말.. 
    함수는 선언 후 호출이 되어야 실행이 된다.
    호출하는 방법으로는 함수 뒤에 ( ) 를 붙인다
    그리고 call 그리고 apply 하는 방법 이 있음.
    var example = function (a , b, c) {
    return a + b+ c;
    };
    example(1,2,3);
    example.call(null, 1 2, 3);
    example.apply(null, [1 , 2 , 3]);
    보통 call 은 보통 함수와 똑같이 인자를 넣고 , apply 는 인자를 하나로 묶어서 배열로 만들어 넣는다.
    그러면 call 과 apply가 공통적으로 가진 null 인자의 역할이 뭘까? 바로 this.를 대체하는 것이다
    [https://inpa.tistory.com/entry/JS-📚-Call-Bind-Apply](https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-Call-Bind-Apply)
    
    다시 보세영
    
    ```jsx
    var obj = {
    string : 'zero',
    yell : function () {
    	alert(this.string );
    }
    
    var obj2 = {
    string : 'what'
    };
    
    obj.yell() ;
    obj.yell().call(obj2); obj.yell()을 obj2로 바꾼거라는데...
    ```
    
    마지막 줄에서 obj.yell.call(obj2)로 this가 가르키는 것은 obj2로 바뀐거란다 무슨말이지..
    
    ywll 은 obj의 메소드 이지만 yell이 가르키는 this 는 string : zero였지만 바꼈다고 !!
    
    ```jsx
    var kim = { name : "kim", first:10, second: 20}
    var lee = { name ": "lee", first:100, second:200}
    
    function sum(num) {
    	return num + this.first. + this.second
    }
    
    sum.call(kim, 500);// sum 을 call 하는데 this값을 kim객체로 한다. 
    ```
    
    call을 사용해서 this를 정의 해준다면, 다른 객체의 파라미터나 메소드를 자기것 마냥 사용가능하다는 것임 
    
    object.create ( ) 
    Object.create( ) 메서드는 지정된 프로토타입 객체 및 속성(property) 을 갖는 새 객체를 만든다. 
    
    syntax :  
    
    ` Object.create(proto[, propertiesObject])`
    
    proto 는 새로 만든 객체의 프로토타입이어야 할 객체
    
    propertiesObject : 선택사항, 
    

[script 상속](https://www.notion.so/script-0fd02c62a28f44e3baf9249595f9f86b)

NO.139 Given the code below:
Setcurrent URL ();
console.log('The current URL is: ' +url );
function setCurrentUrl() {
Url = window.location.href:
What happens when the code executes?
A. The url variable has local scope and line 02 throws an error.
B. The url variable has global scope and line 02 executes correctly.
C. The url variable has global scope and line 02 throws an error.
D. The url variable has local scope and line 02 executes correctly.

NO.140 developer is trying to convince management that their team will benefit from using Node.js
for a backend server that they are going to create. The server will be a web server that handles API
requests from a website that the team has already built using HTML, CSS, and JavaScript.
Which three benefits of Node.js can the developer use to persuade their manager?
Choose 3 answers

A. I nstalls with its own package manager to install and manage third-party libraries.
B. Ensures stability with one major release every few years.
C. Performs a static analysis on code before execution to look for runtime errors.
D. Executes server-side JavaScript code to avoid learning a new language.
E. User non blocking functionality for performant request handling

- 
    
     a c e 
    

NO.141 Refer to the HTML below:

- Leo
- Tony
- Tiger

Which JavaScript statement results in changing " Tony" to "Mr. T."?
A. document.querySelectorAll('$main $TONY').innerHTML = ' Mr. T. ';
B. document.querySelector('$main li:second-child').innerHTML = ' Mr. T. ';
C. document.querySelector('$main li.Tony').innerHTML = ' Mr. T. ';
D. document.querySelector('$main li:nth-child(2)'),innerHTML = ' Mr. T. ';

- 
    
    querySelecotor로 선택자를 지정하고 . innerHTML 을 통해 내용을 바꾼다. 
    
    document.querySelector("#main li:nth-child(2)").innerHTML = " Mr. T. ";
    
    li 선택자는 
    li:nth=child(n)으로 선택 가능함
    
    D
    

NO.142 Which javascript methods can be used to serialize an object into a string and deserialize a
JSON string into an object, respectively?
A. JSON.stringify and JSON.parse
B. JSON.serialize and JSON.deserialize
C. JSON.encode and JSON.decode
D. JSON.parse and JSON.deserialize

- 
    
    serialize 직렬화 
    a
    

NO.143 A test has a dependency on database.query. During the test the dependency is replaced
with an object called database with the method, query, that returns an array. The developer needs to
verify how many times the method was called and the arguments used each time.
Which two test approaches describe the requirement?
Choose 2 answers
A. Integration
B. Black box
C. White box
D. Mocking

- 
    
    c ,d
    

NO.144 Refer to the code below:
Const myFunction = arr => {
Return arr.reduce((result, current) =>{
Return result = current;
}, 10};
}
What is the output of this function when called with an empty array ?
A. Returns 0
B. Throws an error
C. Returns 10
D. Returns NaN

NO.145 refer to the following code : 

```jsx
let obj = {
foo : 1, 
bar: 2
}
let output = [];
for(let something in obj) {
output.push(something);
}
console.log(output);
```

A. [1,2]
B. ["bar","foo"]
C. ["foo","bar"]
D. ["foo:1","bar:2"]

- 
    
    c
    

  

NO.146 What are two unique features of functions defined with a fat arrow as compared to normal
function definition?
Choose 2 answers
A. The function generated its own this making it useful for separating the function's scope from its
enclosing scope.
B. The function receives an argument that is always in scope, called parentThis, which is the
enclosing lexical scope.
C. If the function has a single expression in the function body, the expression will be evaluated and
implicit returned.
D. The function uses the this from the enclosing scope.

- 
    
    AC
    

NO. 147 give the code below : 

```jsx
function myFunction ( ) {

a=5;
var b = 1;
}

myFunction ();
console.log(a);
console.log(b);
```

What is the expected output?
A. Both lines 08 and 09 are executed, and the variables are outputted.
B. Line 08 outputs the variable, but line 09 throws an error.
C. Line 08 thrones an error, therefore line 09 is never executed.
D. Both lines 08 and 09 are executed, but values outputted are undefined.

- 
    
    b
    
    function  레벨로 hoisiting 현상이 발생하기 때문에 b는 myFunction 안에서만 쓸 수 있다. 
    

NO.148 Considering type coercion, what does the following expression evaluate to?
True + '13' + NaN
A. ' 113Nan '
B. 14
C. ' true13 '
D. ' true13NaN '

- 
    
    강제 형변환 문제, 
    
    string 이 들어가 있으면 모두 하나의 string으로 인식 한다.
    연산은 왼쪽에서 부터 오른쪽으로 연산이 일어남 
    

NO.149 Refer to the code below:
Const resolveAfterMilliseconds = (ms) => Promise.resolve (
setTimeout (( => console.log(ms), ms ));
Const aPromise = await resolveAfterMilliseconds(500);

Const bPromise = await resolveAfterMilliseconds(500);
Await aPromise, wait bPromise;
What is the result of running line 05?
A. aPromise and bPromise run sequentially.
B. Neither aPromise or bPromise runs.
C. aPromise and bPromise run in parallel.
D. Only aPromise runs.

- 
    
    b
    

NO.150 A developer writers the code below to calculate the factorial of a given number.
Function factorial(number) {
Return number + factorial(number -1);
}
factorial(3);
What is the result of executing line 04?
A. 0
B. 6
C. -Infinity
D. RuntimeErro

- 
    
    factorial 은 재귀 함수이기 때문에 조건을 잘못걸면 메모리초과 오류를 발생 시킨다. 
    
    factorial 함수를 한번 실행할 때 마다 execution context 가 생성되기 때문에, 재귀 함수는 이전 execution context 를 끝내지 못하고 계속해서 쌓이게 된다 . 
    

NO.151 Given the following code:
Let x =null;
console.log(typeof x);
What is the output of the line 02?
A. "Null"
B. "X"
C. "Object"
D. "undefined"

- 
    
    object
    

NO.152 Which statement accurately describes the behaviour of the async/ await keyworks ?
A. The associated class contains some asynchronous functions.
B. The associated function will always return a promise
C. The associated function can only be called via asynchronous methods
D. The associated sometimes returns a promise.

- 
    
    b
    

NO.153  Refer to the code below : 

```jsx
let o = {
    get js () {
        let city1 = String("st.Louis");
        let city2  = String ("new York");
        return {
            firstCity: city1.toLowerCase(),
            secondCity: city2.toLowerCase(),
        }
    }
}
```

What value can a developer expect when referencing o.js.secondCity?
A. Undefined
B. ' new york '
C. ' New York '
D. An error

- 
    
    b
    

NO.154 Given the requirement to refactor the code above to JavaScript class format, which class
definition is correct?
A. console.log(10/ Number('5'));
B. console.log(parseInt('two'));
C. console.log(10/ ''five);
D. console.log(10/0);

- 
    
    b → NaN
    
    c → NaN
    
    d → Infinity 
    a (o)
    

NO.156

function myFunction (reassign) {
let x=1;
var y = 1;
if(reassign){
let x = 2;
var y = 2;
console.log(x);
console.log(y);
}
console.log(x);
console.log(y);

}
what is displayed when myFunction (true) is called ?

A. 2 2 1 1
B. 2 2 undefined undefined
C. 2 2 1 2
D. 2 2 2 2

- 
    
    let은 변수 재 선언 불가능, 변수 재할당 가능. 
    
    블록스코프란, 변수가 선언된 {블록} 이 해당 변수를 사용할 수 있는 영역(스코프) 라는 뜻이다. 
    
    ```jsx
    let name = 'yoy'
    if(name ) {
    	let name = "rooney";
    	console.log("블록안에서",name);}
    console.log("블록 밖에서 ", name);
    ```
    
    이렇게 if문을 감싸고 있는 {블락} 이 변수를 사용할 수 있는 영역이 되어 변수가 구분되어 진다. 
    
    let을 쓰면 if 안과 밖으로 스코프가 달라지지만, (블록 안과 밖의 스코프가 달라져서 변수 이름이 같아도 대체되지 않아 스코프에는 같은 이름 사용이 불가하다) name 을 var로 선언했을 경우에는 안과 밖이 같은 스코프로 되어서 ‘Identifier ‘ name’ has already been declared ’라는 오류가 발생 
    
    그래서 결론은, 첫번째 와 두번째콘솔은 괄호 안에 있고  let x는 저안의 스코프로 잡아서 2출력, var는 호이스팅이 되어서 이제 안이든 밖이든 2로 출력되고, 3번째 콘솔은 x는 let x = 2의 영역 밖이기 때문에 2말고 1출력, 마지막 콘솔은  y이가 var hoisting 으로 2로 잡혀버림.
    
    NO.157 Given the following code:
    Counter = 0;
    const logCounter = () => {
    console.log(counter);
    );
    logCounter();
    setTimeout(logCOunter, 1100);
    setInterval(() => {
    Counter++
    logCounter();
    }, 1000);
    What is logged by the first four log statements?
    A. 0 0 1 2
    B. 0 1 2 3
    C. 0 1 1 2
    D. 0 1 2 2
    
    NO.158
    
    A developer is creating a simple webpage with a button. When a user clicks this button for
    the first time, a message is displayed.
    The developer wrote the JavaScript code below, but something is missing. The message gets
    displayed every time a user clicks the button, instead of just the first time
    
    ```jsx
    function listen (event){
    	alert('hey ! iam john doe');
    button.addEventListerner('click;, listen);
    }
    ```
    

A. On line 02, use event.first to test if it is the first execution.
B. On line 04, use event.stopPropagation ( ),
C. On line 04, use button.removeEventListener(' click" , listen);
D. On line 06, add an option called once to button.addEventListener()

- 
    
    이벤트 한번 발생시키고 지워버리기, 
    or 이벤트 걸때 옵션을 한번만 걸기 button.addEventListener('click', listen, {once : true});
    

NO.159 a developer creates a generic function to log custom messages in the console.
To do this, the function below is implemented.

```jsx
function logStatus(status) {
	console./*answer*/{'Item status: %s', status}
}
```

which three console loggging methods allow the use of string substitution in line 2?

A. Assert
B. Log
C. Message
D. Info
E. Error

- 
    
    a는console.assert()는 지정한 조건이 false인 조건에만 로그가 출력된다고 한다. ㅇㅅㅇ
    
     , message는 존재하는것인가? 
    
    anyway 
    사용 예시를 보면 쉽다
    
    ```jsx
    var user = new Object(); 
    user.first = "Fred"; user.last = "Smith";
     user.age = 10.01; console.log("Hi, %s %s!", user.first, user.last); 
    console.log("%s is %i years old!", user.first, user.age);
     console.log("%s is %f years old!", user.first, user.age);
     // Output: // Hi, Fred Smith!
     // Fred is 10 years old! 
    // Fred is 10.01 years old!
    
    ```
    
    지원되는 패턴 
    
     
    
    %s - 문자열
    
     %i - 정수 
    
    %d - 정수 
    
    %f - float 
    
    %o - 개체 
    
    %b - 이진 
    
    %x - 16진수
    
     %e - 지수
    
    console.log
    console.Info
    
    console.Error는 잘 출력됨 
    
    NO.160 Which code statement correctly retrieves and returns an object from localStorage?
    A. const retrieveFromLocalStorage = () =>{
    return JSON.stringify(window.localStorage.getItem(storageKey));
    }
    B. const retrieveFromLocalStorage = (storageKey) =>{
    return window.localStorage.getItem(storageKey);
    }
    C. const retrieveFromLocalStorage = (storageKey) =>{
    return JSON.parse(window.localStorage.getItem(storageKey));
    }
    D. const retrieveFromLocalStorage = (storageKey) =>{
    return window.localStorage[storageKey];
    }
    
    - 
        
        c
        
    
    JS flat( ) 함수 
    
    js flat 함수는 arr 배열 구조안에 또 다른 arr를 가질때 이 arr을 평평하게 만드는 함수이다. 
    
    예를 들어 arr1이라는 arr에 [ 1 , 2 , 3  , [4 , 5 , 6]] 값이 있을 때, arr1.flat()을 실행 시키면 
    
    [1 , 2 , 3 , 4 , 5,  6]을 반환한다. 
    만약  arr안의 arr값에 도 다른 arr가 존재할 경우, flat()을 실행시키면 2번째 하위에 있는 arr을 평평하게 한다. 
    
    예를 들어, arr1 이라는 arr에 [ 1 , 2 , 3  , [4 , [5 , 6]]]값이 있을때, arr1.flat( ) 을 실행시키면, 
    
    [ 1 , 2 , 3  , 4 ,[ 5 , 6]] 를 리턴
    
    - **'=='**는 비교하는 두 개의 값(피연산자)을 강제로 같은 형으로 변환한 후, 비교를 수행합니다.즉, 두 값의 타입이 다르더라도, 형 변환된 값이 같다면 true를 리턴합니다.
    - **'==='**는 비교하는 두 개의 값(피연산자)의 타입과 값이 모두 같을 경우에만, true를 리턴합니다.
    
    출처:
    
    [https://hianna.tistory.com/375](https://hianna.tistory.com/375)
    
    [어제 오늘 내일]
