# js六种继承方式

## 1. 原型继承

  * 原型继承是最简单的一种继承，若B想继承A，则需要将B.prototype = new A();即可。
  * 原理就是将B和A通过原型指向做了关联，这样当B的实例需要调用方法的时候会逐级向上查找。
  * 缺点：将A的私有属性也继承了过来不太符合逻辑
  
  ```javascript
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

   *  call继承只会继承私有属性和方法，不包含父类原型上的方法
   *  克隆了一份一模一样的作为子类的私有属性和方法
  
```javascript
function A() {
    this.x = 10;
    this.y = 20;
    this.getX = function() {
        console.log(this.x);
    }
}
A.prototype.getY = function() {
    console.log(this.y);
}
function B() {
    A.call(this);
}
var b = new B();
b.getX(); // 10
b.getY(); // Uncaught TypeError: b.getX is not a function
```
## 3. 混合继承（原型继承+call继承）


## 4. 冒充对象继承

## 5. 寄生组合式继承

## 6. 中间类继承
