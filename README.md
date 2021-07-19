# known-RxJs

### 了解RxJs的核心概念
* Observable （可观察物件\环境）
* Observer  （观察者想要的结果\处理过程）
* Subscription （进行订阅subscribe\取消订阅unsubscribe）
* Operators   （运算符）
* Subject   （广播收到事件）
* Schedulers (排程控制器)

#### 简单例子
```javascript


   // 引入
    <script src="https://cdn.bootcdn.net/ajax/libs/rxjs/7.1.0/rxjs.umd.js"></script>


   // html
     <button id="setThing">建立一个可观察事件</button>
     <button id="cancol">取消订阅</button>

   // js
    // 建立一个可观察
    const setThingDom = document.getElementById("setThing");
    // 建立一个Observable 可观察物件
    let click$ = fromEvent(setThingDom, 'click');
    // 建议Observer
    let observer = {
      next: () => console.log("建立一个可观察对象并循环监听")
    };
    // 建立订阅 （订阅Observable,传入Observer观察者物件）
    let subs$ = click$.subscribe(observer);
   
     // 取消订阅按钮  setThingDom订阅会关闭将不会再点击打印console.log；
    const cancolDom = document.getElementById("cancol");
    fromEvent(cancolDom,"click").subscribe(()=>subs$.unsubscribe())
 ```

