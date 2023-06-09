### 7.3遍历对象属性

#### for...in

```
let person = {
  name: 'henry',
  age: 18,
};

for(let ley in person){
console.log('键名' + key + '; 键值:' + person[key]);

```


#### 借助Object.keys遍历属性

```
let person={

  name: 'henry',
  age: 18,
  };
  let keys = Object.keys(person);//Object.keys方法返回的是一个由对象中所有属性名称组成的数组
  
  for(let i = 0;i < keys.length;i++){
  console.log('键名：' + keys[i] + '; 键值：' + person[keys[i]]);//通过keys数组进行访问键名，通过perosn数组去访问键值

```
### 7.4对象的继承

Object是JavaScript提供的基本的对象。JavaScript的所有的其他对象都是继承自Object对象，那些对象都是object的实例。
因此，除了用字面量和自定义的构造方法创建对象外，还有一种方法
#### 创建对象的新方法

```
//字面量

let o1 = {
name:'alice',
};


//构造函数

let o2 = new Object();

//继承
function 04(){
};//构造函数

04.prototyoe = o1;
let o4 = new 04();

//最后一种方法创建的o4继承自o1
```

#### 属性是否存在

我们可以用in运算符来判断是否拥有某个属性

```
let person = {
name:'henry',
age:18,
};
 
'name' in person;
'gender' in person;
'toString' in person;
```
输出：

```
true;
false;
true;

```
*toString*是Object对象的属性。person继承自Object，所以也有这个属性

#### 自身属性是否存在

> hasOwnProperty

```
let person = {
  name: 'henry',
  age: 18,
};

person.hasOwnProperty('name');
person.hasOwnProperty('gender');
person.hasOwnProperty('toString');

```

输出：

```
true;
false;
false;
```

#### Object与JSON的区别

这几个是JavaScript中几个写法和对象长得相似的概念，了解即可

> JSON

JSON是一种轻量级的文本数据交换格式，采用js的语法书写，但是独立于这种语言，可以认为是不同编程语言之间用于传递数据而约定的数据格式

> JSON和js对象的转换

1.JSON.parse(): JSON => js对象

```
// 一个 JSON 字符串
const jsonStr =
  '{"sites":[{"name":"Runoob", "url":"www.runoob.com"},{"name":"Google", "url":"www.google.com"},{"name":"Taobao", "url":"www.taobao.com"}]}';

// 转成 JavaScript 对象
const obj = JSON.parse(jsonStr);

```

2.JSON.stringify(): js对象 => JSON格式

```
const jsonStr2 = JSON.stringify(obj)
```




### 7.5 内置对象——Math、Storage

该对象不是构造函数，不能生成实例，所有的属性和方法都必须在Math对象上调用

#### 常量
提供一些数学常数
```
Math.E // 常数e。
Math.LN2 // 2 的自然对数。
Math.LN10 // 10 的自然对数。
Math.LOG2E // 以 2 为底的e的对数。
Math.LOG10E // 以 10 为底的e的对数。
Math.PI // 常数π。
Math.SQRT1_2 // 0.5 的平方根。
Math.SQRT2 // 2 的平方根。

```

一般使用比较多的是常熟π，即`Math.PI`。


#### 静态方法

```
Math.abs() // 绝对值
Math.ceil() // 向上取整
Math.floor() // 向下取整
Math.round() // 四舍五入取整
Math.max() // 最大值
Math.min() // 最小值
Math.pow() // 指数运算
Math.sqrt() // 平方根
Math.log() // 自然对数
Math.exp() // e的指数
Math.random() // 随机数
```

> 以上方法除了Math.random()都需要传入合适的参数

注意几个取整方法

```
Math.ceil(4.6) // 向上取整，取大于等于 x，并且与它最接近的整数。
Math.floor(4.6) // 向下取整，取小于等于 x，并且与它最接近的整数。
Math.round(4.6) // 四舍五入取整，取与 x 最接近的整数。

```

输出：

```
5
4
5
```


#### Storage对象


Storage接口用于脚本在浏览器保存数据，两个对象部署了这个接口：window.sessionStorage和window.localStorage

sessionStoreage保存的数据用于浏览器的一次会话（session），当会话结束（通常是窗口关闭），数据被清空，localStorage保存的数据长期存在，在下一次访问的时候，可以读取以前保存的数据。

#### 数据的存入：setItem

写法：

```
window.localStorage.setItem('myLocalStorge','storeage Value');

```
window.localStorage.setItem('key','value');//键名和键值

两个参数都是字符串，不是字符串的参数会转成字符串后再存入浏览器

打开网页开发者工具（右键=>检查=>应用程序=>本地存储）,查看存储情况，如果是空的可以在console写一段代码（同上），再查看。

注意，入股要存入的数据不是字符型的数据，最好先转换成字符型比如：

```
const obj = {
  name: 'henry',
  age: 18
}
const value = JSON.stringify(obj);
window.localStorage.setItem('myLocalStorage', value);
```
>JSON.stringifly()方法可以将一个js值转换为JSON字符串


#### 读取数据：getltem
写法：

```
window.localStorage.getItem('myLocalStorage');


```

window.localStorage.getItem('key');接受一个参数，即为键名

操作方法同上，前提是浏览器中存有这个key


#### 清除存档：clear

写法：

```
window.localStorage.clear();
```

### 7.6内置对象——String

js原生提供三个包装对象之一就是String(另外两个是Number和Boolean)


包装对象
```
let v2 = new String('abc');

```

利于调用某些方法

#### 字符串长度：length

```
let len = 'here is an apple'.length;
```
字符串的空也是计算在内

#### 查找字符：indexOf()


从字符串中查找某个字符串是否存在：

```
let str = 'here is an apple';
const index = str.indexOf('an');
console.log(index);
```
返回值为8

当不存在子字符串的时候，返回-1

#### 去掉两端空格：trim（）

```
// 'here' 之前有一个空格，'apple' 之后有三个空格
let str = ' here is an apple   ';
const trimedStr = str.trim();//不会修改原来字符串，而是作为新的字符串返回
console.log(str.length);
console.log(trimedStr.length);
```

#### 截取字符串：substring/substr

```
let url = 'https://www.youkeda.com/userhome#collect';

// 首先找到 # 后第一个字母的下标
const index = url.indexOf('#') + 1;

// 有 hash 才能进行截取，没有就直接提示不存在
if (index) {
  // 用 substring 截取字符串
  const hash1 = url.substring(index, url.length);

  // 计算 hash 的长度
  const lenHash = url.length - index;
  // 用 substr 截取字符串
  const hash2 = url.substr(index, lenHash);

  console.log(hash1);
  console.log(hash2);
} else {
  console.log('不存在 hash');
}

```

>substring(star,end)
>substr(star,len)

#### 分割字符串：split

```
const splitedStr = 'a|b|c'.split('|');
console.log(splitedStr);
//返回一个数组
```


输出：

```
['a','b','c']
```














