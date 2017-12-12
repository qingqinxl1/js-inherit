# js六种继承方式

## 1. 原型继承

  * 原型继承是最简单的一种继承，若B想继承A，则需要将B.prototype = new A();即可。
  * 原理就是将B和A通过原型指向做了关联，这样当B的实例需要调用方法的时候会逐级向上查找。
  * 缺点：将A的私有属性也继承了过来不太符合逻辑
  
  ```
  function A() {
    this.x = 100;
  }
  A.prototype.showX = function(){
    console.log(this.x);
  }
  
  function B() {
    
  }
  
  B.prototype = new A;
  
  console.log(new B);
  
  ```
  
## 2. call继承

## 3. 混合继承（原型继承+call继承）

## 4. 冒充对象继承

## 5. 寄生组合式继承

## 6. 中间类继承
