# PROMISE


```
const promise1  = new Promise((resolve, reject) => { // 비동기 작업}) ;
```

1. 변수설정  promise1, const로 선언해서 다시 변수 재할당 안됨. ( 하나의 변수로 끝까지 해당 Promise를 관리하는 것이 가독성도 좋고 유지보수 하기도 좋음)  
2. new Promise(..)  를 동해 프로미스 객체를 만들었다. 생성자 역시 함수이므로 ( ) 를 사용하여 함수를 호출하는것 과 똑같은 모습임..  
3. 근데 여기서! 생성자는 특별한 함수를 하나 받음 . 요기서 인자로 들어가는 함수는 화살표 함수를 사용한당  

 특별한 함수 ? 무슨말이얏
 
 excutor ! 얘는 인수를 두가지 맛음 resolve랑 reject ! 

resolve - 는 executor내에서 호출할 수 있는 또다른 함수 이다. resolve를 호출하게 된다면 " 이 비동기 작업이 성공했어 ! " 라는 뜻이라 함 ㅋㅋ귀욥  
reject 또한 executor내에서 호출할 수 있는 또 다른 함수 인데,.  reject를 호출하면 " 이비동기 작업은 실패.."라는 뜻ㅋ
생성자 내의 함수 내에 또 다른 함수를 호출하는 격. 
여튼 Promise의 객체 promise1을 하나 만들었다.  
Promise 의 특징은, new Promise(...) 를 하는 순간 여기에 할당된 비 동기 작업은 바로 시작된다.  
비동기 작업의 특징은 작업이 언제 끝날지 모르기 때문에 일단 배를 떠나 보내라고 하는데...  
근데 여기서 뽀인트는 ! 너가 작업이 성공할 수도 있고 실패할 수도 있는데 ! 그 작업이 성공하든 실패하든 우리가 뒷처리를 해줘야한다는 것이다.  
Promise가 끝나고 난 다음의 동작을 우리가 설정해줄 수 있는데, 그게 바로 then 메소드랑 catch 메소드이다.  

- `then`메소드는 해당 Promise 가 성공했을 때의 동작을 지정함. 인자는 성공했을때 실행했으면 하는 함수를 받는다.  


- `catch`메소드는 해당 Promise가 실패했을 때의 동작을 지정함.  역시 인자는 실패했을때 실행할 함수를 받음. 

위 함수들은 체인 형태로 활용할 수 있다고 한다.  흠 연속적으로 호출할 수 있다고 함.  

executor로 새로운 Promise 를 만들어서 then이랑 catch를 써서 후속 동작까지 착착 지정해줘야 
아핫 기본 프로미스 틀이라고 한다.  

예쩨
```
const promise1 = new Promise((resolve, reject) => {
  resolve();
});
promise1
  .then(() => {
    console.log("then!");
  })
  .catch(() => {
    console.log("catch!");
  });
  
  //then 출력
```

이 Promise에서는 바로 resolve()가 호출되어서 성공으로 간주하고 then 의 동작을 실행시킴

```
const promise1 = new Promise((resolve, reject) => {
 reject();
});
promise1
  .then(() => {
    console.log("then!");
  })
  .catch(() => {
    console.log("catch!");
  });
  
  //catch 출력
```

이 예제들은 비동기 작업이라고 해도 뭔가 기다리는 일은 하나도 없다.  
기다리는 작업은 인터넷으로부터 데이터를 가져오는 작업이라든지,,(?) 파일을 읽고 쓰는 작업을 의미함 무슨말이지..
anyway   
기다리는 작업이 하나도 없다면 비동기를 쓸 이유는 없다 !  

### 재사용
new Promise하고 객체 만드는 순간 비동기 작업이 시작되는데, 비슷한 비동기 작업을 수행할 때 마다 매번 new Promise(..)를 해줘야하나?  
new promise 를 한것 을 그대로 리턴하는 함수를 만들어 사용하면 된다. 만들어 보잣 ㅎㅋ

```
function startAsync(age) {
return new Promise((resolve, reject) => {
if(age>20) resolve();
  else reject();
});
}


setTieout( () => {

const promise1 = startAsync(25);
promise1
.then (() => {
  console.log("1 then!");
});
.catch(()=>{
  console.log( "1 catch ! ");
});


const promise2 = startAsync(19);
promise2
.then (() => {
  console.log("3 then!");
});
.catch(()=>{
  console.log( "4 catch ! ");
});

}, 1000
);



```

startAsync 함수를 통해서 new Promise를 return 하는 함수를 만들었고   
이 함수가 호출하는 순간 비동기 작업이 시작된다 .   


### 작업결과 전달 

```
function startAsync(age) {
return new Promise((resolve, reject) => {
if(age>20) resolve( `${age} success` );
  else reject( new Error (`${age} is not over 20 ` ));
});
}


setTimeout( () => {

const promise1 = startAsync(25);
promise1
.then ((value) => {
  console.log(value);
})
.catch(()=>{
  console.error(error);
});


const promise2 = startAsync(19);
promise2
.then ((value) => {
  console.log(value);
});
.catch((error)=>{
  console.error(error);
});

}, 1000
);



```

프로미스는 3가지 상태를 지닌다. 
pending, fulfilled, rejected

이행상태일때 then, 거부상태일때 catrch로 등록한 동작들이 실행된다. 
지금까지 성공이라고 이야기한것들은 사실 이행상태 fulfilled와 연관되고, 실패는 rejected와 동일함.  

so Promise의 의의를 한마디로 이야기 하자면, promise는 비동기 작업을 생성 시작하는 부분과 작업 이후의 동작 지정 부분 then , catch를 분리함으로써  
기존의 러프한 비동기 작업을 보다 유연한 설계로 가능토록 한다.  


## async
async 함수는 위의 executor로부터 몇가지 규칙만 적용하면 new Promise객체를 리턴하는 함수를 아까 재사용하기위해 만든 함수 async로 쉽게 바꿀 수 있음.

1. 함수에 async를 붙인다
2. new Promise 부분을 없애고 executor만 남긴다. 
3. resolve(value); 부분을 return value;로 변경한다.
4. reject(new Error(...)); 부분을 throw new Error(..) 로 변경한다. 


프로미스 객체를 리턴하는 재사용 가능한 함수를 만들어 보장
```
function startAsync(age) {
return new Promise ((resolve, reject) =>{
 if(age>20) resolve(`성공했을때는 말이야 $(age)`); else reject(new Error(`실패했을때는 말이야 $(age)`));
});
}


//만들어온 startAsync객체 만들어 보깅
const promise1 = startAsync(100);
promise1
.then((value) => console.log(value))
.catch((error)=> console.error(error));
```

async로 바꾸기
```
async function startAsync(age){

    if(age>30) return `${age} hihihihi`;
    else throw new Error(`${age} byebye`);
}

const pr = startAsync(50);
pr
.then((value) => console.log(value))
.catch((error) => console.error(error));


.then((value) => console.log(value))
.catch((error) => console.error(error));
```
so async의 리턴값은 promise라는거! 
우리가 리턴한것은 분명히 문자열인데, 프로미스라는거

# await
await 는 Promise가 fulfilled 가 되든지 rejected가 되든지 아무튼 간에 끝날 때 까지 기다리는 함수이다.  
쓸때 조건이 있는데, 무조건 async 함수에서만 사용할 수 있다.  



```
function setTimeoutPromise(ms) {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(), ms);
  });
}

async function startAsync(age) {
  if (age > 20) return `${age} success`;
  else throw new Error(`${age} is not over 20`);
}

async function startAsyncJobs() {
  await setTimeoutPromise(1000);
  const promise1 = startAsync(25);
  try {
    const value = await promise1;
    console.log(value);
  } catch (e) {
    console.error(e);
  }
  const promise2 = startAsync(15);
  try {
    const value = await promise2;
    console.log(value);
  } catch (e) {
    console.error(e);
  }
}

startAsyncJobs();
```

await가 하는 일은 setTimeout을 Promise버전으로 하여 setTimeoutPromise라는 함수를 새로 만들었음 .  
이 함수는 setTimeout 함수를 활용하여 지정된 ms초만큼 기다린 후 resolve를 호출한다.  
이렇게 만든 Promise의 then 으로 다음 동작을 정의할 수 있다.  then 동작은 resolve함수가 호출되면 실행됬었쥐? ms초만큼 기다린 후 다음 동작으로 넘어간다. 




















참고 : https://elvanov.com/2597


