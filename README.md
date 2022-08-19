##### 1.数组数据去重

```js
1.Set特性的使用
const arr = [1, 2, 3, 2, 3];
[...new Set(arr)]; // [1, 2, 3]
Array.from(new Set(arr)); // [1, 2, 3]

2.利用indexOf去重
function sole(arr) {
  var Array=[]
  for (var i = 0; i < arr.length; i++)
  {
       if (Array.indexOf(arr[i]) === -1)
        {
          Array.push(arr[i])
        }
  }
  return Array
}
var arr = [1, 2, 3, 4, 1, 23, 4, 21, 2, 4, 1, 5]
sole(arr)

3.filter过滤器
var arr =['aa','aa',1,2,2,1];
var r = arr.filter(function(element,index,self){
    return self.indexOf(element) === index;
});
console.log(r);


```

##### 2.数组返回新的结构

```js
1.返回新的数据结构
let arr = [{a:1,b:2},{a:2,b:3}];
let newArr = arr.map(v => {
    let objN = Object.assign({},v);
    objN.a += 1;
    objN.b += '1';
    return objN
});
console.log(arr); // [{a:1,b:2},{a:2,b:3}]
console.log(newArr); // [{a:2,b:'21'},{a:3,b:'31'}]

2.只需要某一个数据结构
const arrayUsers = [
    {
        id: 1,
        username: "Magic",
        address: "Johnson",
    },
    {
        id: 2,
        username: "Kobe",
        address: "Bryant",
    }]
const newUsers = arrayUsers.map((item) => item.username);
console.log(newUsers); // [ 'Magic', 'Kobe']
```

##### 3.数据查找

```js
1.Array.filter()

const array = [10, 11, 3, 20, 5];
const greaterThanTen = array.filter(element => element > 10);
console.log(greaterThanTen) //[11, 20]

2.Array.find()
只需要一个符合条件的元素

const array = [10, 11, 3, 20, 5];
const greaterThanTen = array.find(element => element > 10);
console.log(greaterThanTen)//11

3.Array.includes()
includes() 方法确定数组是否包含某个值，并在适当时返回 true 或 false。

const array = [10, 11, 3, 20, 5];
const includesTwenty = array.includes(20);
console.log(includesTwenty)//true

4.Array.indexOf()
indexOf() 方法返回可以在数组中找到给定元素的第一个索引。如果数组中不存在该元素，则返回 -1

const array = [10, 11, 3, 20, 5];
const indexOfThree = array.indexOf(3);
console.log(indexOfThree)//2

如果你想找到在符合特定条件的阵列中的所有项目，使用 filter。
如果你想检查是否至少有一个项目符合特定的条件，请使用 find。
如果你想检查一个数组包含一个特定的值，请使用 includes。
如果要在数组中查找特定项目的索引，请使用indexOf
```

##### 4.数组增加

```js
1.arr.push() 从后面添加元素，返回值为添加完后的数组的长度
let arr = [1,2,3,4,5]
console.log(arr.push(5))   // 6
console.log(arr) // [1,2,3,4,5,5]

2.arr.unshift() 从前面添加元素, 返回值是添加完后的数组的长度
let arr = [1,2,3,4,5]
console.log(arr.unshift(2))    // 6
console.log(arr)  //[2,1,2,3,4,5]

3.arr.concat() 连接两个数组 返回值为连接后的新数组
let arr = [1,2,3,4,5]
console.log(arr.concat([1,2]))  // [1,2,3,4,5,1,2]
console.log(arr)   // [1,2,3,4,5]

4.str.split() 将字符串转化为数组
let str = '123456'
console.log(str.split('')) // ["1", "2", "3", "4", "5", "6"]
```

##### 5.数组删除

```js
1.arr.pop() 从后面删除元素，只能是一个，返回值是删除的元素
let arr = [1,2,3,4,5]
console.log(arr.pop())     // 5
console.log(arr)  //[1,2,3,4]

2.arr.shift() 从前面删除元素，只能删除一个 返回值是删除的元素
let arr = [1,2,3,4,5]
console.log(arr.shift())  // 1
console.log(arr)   // [2,3,4,5]

3.arr.splice(i,n) 删除从i(索引值)开始之后的那个元素。返回值是删除的元素 (参数：i 索引值  n 个数)
let arr = [1,2,3,4,5]
console.log(arr.splice(2,2))     //[3,4]
console.log(arr)    // [1,2,5]

```



##### 6.其他问题(排序)

```js
1.arr.sort() 将数组进行排序,返回值是排好的数组，默认是按照最左边的数字进行排序，不是按照数字大小排序的，见例子
let arr = [2,10,6,1,4,22,3]
console.log(arr.sort())   // [1, 10, 2, 22, 3, 4, 6]
let arr1 = arr.sort((a, b) =>a - b)  
console.log(arr1)   // [1, 2, 3, 4, 6, 10, 22]
let arr2 = arr.sort((a, b) =>b-a)  
console.log(arr2)  // [22, 10, 6, 4, 3, 2, 1]

2.arr.reverse() 将数组反转,返回值是反转后的数组
let arr = [1,2,3,4,5]
console.log(arr.reverse())    // [5,4,3,2,1]
console.log(arr)    // [5,4,3,2,1]

```



##### 7.是否全满足

```js
1.arr.every(callback) 依据判断条件，数组的元素是否全满足，若满足则返回ture
let arr = [1,2,3,4,5]
let arr1 = arr.every( (i, v) => i < 3)
console.log(arr1)    // false
let arr2 = arr.every( (i, v) => i < 10)
console.log(arr2)    // true

2.arr.some() 依据判断条件，数组的元素是否有一个满足，若有一个满足则返回ture
let arr = [1,2,3,4,5]
let arr1 = arr.some( (i, v) => i < 3)
console.log(arr1)    // true
let arr2 = arr.some( (i, v) => i > 10)
console.log(arr2)    // false
```





##### 8.数据浅拷贝的问题

```js
1._clone浅拷贝
import _ from "lodash";
var obj1 = {
    a: 1,
    b: { f: { g: 1 } },
    c: [1, 2, 3]
};
var obj2 = _.clone(obj1);
console.log(obj1.b.f === obj2.b.f);// true

2.cloneDeep深拷贝
var obj2 = _.cloneDeep(obj1);
console.log(obj1.b.f === obj2.b.f);// false

3.深拷贝的效果
var newObj = Object.create(oldObj)


```

