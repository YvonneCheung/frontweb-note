# 变量声明

1. var可重复定义，变量提升

2. let不可重复定义，不能提升声明，块级作用域，暂时性死区。

   ```javascript
   for (var i = 0; i < 10; i++){
       setTimeout(function(){
           console.log(i) //10 10 10 10 10 …… 10
       },100*i)
   }
   // 使用立即执行函数（储存每次的i）
   for (var i = 0; i < 10; i++){
       (function(j){
           setTimeout(function(){
           console.log(j) //1 2 3 4 5 …… 10
       },100*j)
       })(i) 
   }
   //使用let（每次创建一个新的作用域）
   for (let i = 0; i < 10; i++){
       setTimeout(function(){
           console.log(i) //1 2 3 4 5 …… 10
       },100*i)
   }
   ```

   

# 解构

```tsx
let [first,...rest] = [1,2,3,4]
console.log(rest) //[2,3,4]

let o = {a:'foo',b:12,c:'bar'}
let {a,...pass} = o
console.log(pass) //{b:12,c:'bar'}

//属性的重命名
let {a:newName1,b:newName2} = o 
//类型定义
let {a,b}:{a:string,b:number} = o 

//函数解构对象
function f({a,b=0}={a:''}):void{
    
}
f({a:'yes'})✔
f()✔
f({})❌
```

# 展开

