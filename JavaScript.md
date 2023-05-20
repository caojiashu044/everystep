### 7.3遍历对象属性

#### for...in

```
let person = {
  name: 'henry',
  age: 18,
}

for(let ley in person){
console.log('键名' + key + '; 键值:' + person[key]);

```


#### 借助Object.keys遍历属性

```
let person={

  name: 'henry',
  age: 18,
  
  let keys = Object.keys(person);//Object.keys方法返回的是一个由对象中所有属性名称组成的数组
  
  for(let i = 0;i < keys.length;i++){
  console.log('键名：' + keys[i] + '; 键值：' + person[keys[i]]);
的
```
 
