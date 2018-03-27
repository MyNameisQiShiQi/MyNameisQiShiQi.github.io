### 关于Function对象
function 函数声明 函数表达式 通过构造函数声明变量；由于函数名本身就是变量，所以函数也可以作为值来使用（也就是对象，对象，对象三遍）
该对象有length和prototype两个属性，前者代表函数希望接收参数个数,后者表示这个属性是一个指针,指向一个对象, 而这个对象的用途是包含可以由特定类型的所有实例共享的属性和方法 


function函数接收传参，函数内有个类Array的对象arguments来维护传参，即是保存函数参数，它是一个类数组对象,包含着传入函数中的所有参数。 
因此可以接收不与函数定义的传参长度一样 可以使用arguments[0],arguments[1]来访问 ，也可以使用argument.length来访问长度，严格模式下不允许设置arguments[1]的参数 报错，这个对象还有一个名叫 callee 的属性,该属性是一个指针,指向拥有这个 arguments 对象的函数 
函数属性和函数内部定义的变量不是同一个东西：函数属性在外部能够访问，而函数内部对象当函数执行完毕就会被清出内存，this和arguments是内部对象，length、prototype和caller属于属性。
<1>function Person(){}  < 2>var person1=new Person();
<3>person1.constructor == Person  //true



### 关于原型页码（隶属javascript高级程序设计）

理解原型  javascript高级程序设计第148页

### class与原型关系

类是原型、原型链的语法糖？ 
类的内部所有定义的方法，都是不可枚举的（non-enumerable）。


### 模块化

模块化：
ES6 模块的设计思想是尽量的静态化，使得编译时就能确定模块的依赖关系，以及输入和输出的变量。CommonJS 和 AMD 模块，都只能在运行时确定这些东西。比如，CommonJS 模块就是对象，输入时必须查找对象属性。ES6 模块不是对象，而是通过export命令显式指定输出的代码，再通过import命令输入。


### 闭包
闭包：
为了在即使父函数上下文结束的情况下也能访问其中的变量，内部函数在被创建的时候会在它的[[Scope]]属性中保存父函数的作用域链。

function foo() {
  var x = 10;
  return function bar() {
    console.log(x);
  };
}

var returnedFunction = foo();

var x = 20;

returnedFunction(); // 10, but not 20


闭包有两者：函数作为参数传到另一个函数中，函数作为通过另个一个函数返回，这也是由于函数本身也是一个对象的原因才可以做到。记住一点：万物皆对象。

主要关于闭包说明的连接 [http://ourjs.com/detail/529bc7e44c742ef031000002]