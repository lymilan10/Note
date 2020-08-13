```javascript
console.log("start");
setTimeout(function(){
    console.log("timeout");
},5000);
console.log("end");
```

```
start
end
//等待5秒后
timeout
```



```
console.log("start");
setTimeout(function(){
    console.log("timeout");
},5000);
for(let i = 0;i <= 500000;i++){
    console.log("i:",i);
}
console.log("end");
```

```
start
i:1 
(...) //一直输出到500000
//耗时14秒左右
end
//没有等待
timeout
```

​        由于执行代码只有1个线程，所以在任何同步代码中出现死循环，那么它后续的同步代码以及异步的回调函数都无法执行

```text
console.log("start");
setTimeout(function(){
    console.log("timeout");
},5000);
console.log("end");
for(;;){}
```

​        没有输出

回调地狱

```
setTimeout(function(){
    console.log("first");
    setTimeout(function(){
        console.log("second");
        setTimeout(function(){
            console.log("third");
            setTimeout(function(){
                console.log("fourth");
            },2000);
        },2000);
    },2000);
},2000);
```

```
let pm = new Promise(function(resolve,reject){
    resolve();
});
console.log("go on");
pm.then(function(){
    console.log("异步完成");
});
```

```
let pm = new Promise(function(resolve,reject){
    resolve("this is data");

});
console.log("go on");
pm.then(function(data){
    console.log("异步完成",data);
});
```

```
let err = false;
let pm = new Promise(function(resolve,reject){
    if(!err){
        resolve("this is data");
    }else{
        reject("fail");
    }

});
console.log("go on");
pm.then(function(data){
    console.log("异步完成",data);
});
pm.catch(function(err){
    console.log("出现错误",err);
});
```













