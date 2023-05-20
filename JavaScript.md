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


















































