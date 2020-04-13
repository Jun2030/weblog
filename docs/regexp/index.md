#### 01、一张图整理正则表达式

![](../../_images/reg/reg_001.jpg ':size=300')



#### 02、什么是正则表达式

正则表达式就是处理字符串的，也可以用它来处理一些复杂的字符串。

```javascript
// 找出这个字符串中的所有数字
const str = 'abc123de45fgh6789ijk0';
const reg = /\d+/g
console.log(str.match(reg)); // > ["123", "45", "6789", "0"]
```



#### 03、正则表达式的创建方式

创建正则表达式有两种方式：

+ 字面量创建方式（常用方式）： `const reg = /pattern/flags;`
+ 实例创建方式: `const reg = new RegExp(parttern, flags);`

其中 `pattern` 为正则表达式，`flags` 为标识（修饰符）。

其中修饰符有3中：

+ `i`: 忽略大小写匹配
+ `g`: 全局匹配，应用于所有字符串，而非在找到第一个匹配项时停止
+ `m`: 多行匹配，到达一行文本末尾时不停止，继续下一行匹配



#### 04、元字符

**代表特殊含义的元字符**

+ `\d`: 0-9之间的任意数字，`\d`只占一个位置
+ `\w`: 数字，字母，下划线 0-9，a-z，A-Z
+ `\s`: 空格或者空白
+ `\D`: 除了数字
+ `\W`: 除了数字，除了字母，除了下划线
+ `\S`: 除了空格，除了空白
+ `\n`: 匹配换行符
+ `.`: 处理换行符的任意一个字符
+ `\`: 转义字符
+ `|`: 或者
+ `()`: 分组
+ `^`: 限定开始位置，本身不占用位置
+ `$`: 限定结束位置，本身不占位置
+ `[a-z]`: 任意字母，`[]`表示任意一个
+ `[^a-z]`: 非字母， `[]` 中 `^`表示除了
+ `[abc]`: abc三个字母中的任何一个
+ `[^abc]`: 除了abc这三个字母中的任何一个字符

**代表次数的量词元字符**

+ `*`: 0到多个
+ `+`: 1到多个
+ `?`: 0次或者1次，可有可无
+ `{n}`: 正好n次
+ `{n,}`: n到多次
+ `{n, m}`: n到m次



> !!注意：
>
> + 量词出现在元字符后面，如 `\d+`， 表示限定出现在前面的元字符的次数
> + 一般 `[]` 中的字符没有特殊含义
> + `()`具有提高优先级的功能，凡是有 `|` 出现的时候，我们一定需要 `()` 来提高优先级

```javascript
const str = '1223334444';
const reg = /\d{2}/g; // 限定元字符的量级
const res = str.match(reg);
console.log(res); // > ["12", "23", "33", "44", "44"]
const str2 = '  我这里是空格  ';
const reg2 = /^\s+|\s+$/g;
const res2 = str2.replace(reg2, '');
console.log(res2); // > 我这里是空格

// 一般[]中的字符没有特殊含义
const str1 = 'abc';
const str2 = 'dbc';
const str3 = '.bc';
const reg = /[ab.]bc/;
console.log(reg.test(str1)); // > true
console.log(reg.test(str2)); // > false
console.log(reg.test(str3)); // > true

// 匹配18-65年龄段
const reg2 = /(18|19)|[2-5]\d|6[0-5]/;
console.log(reg2.test(66));

// ()提高优先级
const str = 'aaabbb';
const reg = /(a+)(?:b+)/;
const res = str.match(reg);
console.log(res); // > ["aaabbb", "aaa", index: 0, input: "aaabbb", groups: undefined]
```



#### 05、正则的特性

+ 贪婪性：所谓的贪婪性就是正则在捕获时，每一次会尽可能多的去捕获符合条件的内容。如果我们想尽可能的少去捕获符合条件的字符串的话，可以在量词元字符后加 `?`
+ 懒惰性：懒惰性则是正则在成功捕获一次后不管后面的字符串有没有符合条件的，都不再捕获。如果要捕获目标中所有符合条件的字符串，可以用标识符 `g` 标明全局捕获

```javascript
const str = '123aa456';

const reg = /\d+/; // 懒惰性：只捕获一次，贪婪性：一次尽可能多的捕获
const res = str.match(reg);
console.log(res); // > ["123", index: 0, input: "123aa456", groups: undefined]

const reg2 = /\d+/g; // 解决懒惰性，但有贪婪性
const res2 = str.match(reg2);
console.log(res2); // > ["123", "456"]
const reg3 = /\d+?/; // 解决贪婪性，但有懒惰性
const res3 = str.match(reg3);
console.log(res3); // > ["1", index: 0, input: "123aa456", groups: undefined]

const reg4 = /\d+?/g; // 解决贪婪性、懒惰性
const res4 = str.match(reg4);
console.log(res4); // > ["1", "2", "3", "4", "5", "6"]
```



#### 06、正则相关的方法

1. `reg.test(str)`: 验证字符串是否符合正则，符合返回 `true`， 否则返回 `false`
2. `reg.exec(str)`: 用来捕获符合规则的字符串
3. `str.match(reg)`: 如果匹配成功，就返回匹配成功的数组，如果匹配不成功，就返 `null`
4. `str.replace(reg)`: 替换字符串

```javascript
// reg.test(str)
const str = 'abc';
const reg = /\w+/;
console.log(reg.test(str)); // > true

// reg.exec(str)
const str = 'abc123cba456aaa789';
const reg = /\d+/;
console.log(reg.exec(str)); // > ["123", index: 3, input: "abc123cba456aaa789", groups: undefined]


// str.match(reg)
const str = 'abc123cba456aaa789';
const reg = /\d+/g;
console.log(str.match(reg)); // > ["123", "456", "789"]

// str.replace(reg)
const str = 'a111bc222de';
const reg = /\d+/g;
const reg2 = /\d/g;
const res = str.replace(reg, '?');
const res2 = str.replace(reg2, '?');
console.log(res); // > a?bc?de
console.log(res2); // > a???bc???de
```



#### 07、零宽断言

用于查找在某些内容（但不包括这些内容）之前或之后的东西，这个位置应该满足一定的条件（即断言），因此也被称为零宽断言。

+ 零宽度正预测先行断言 `(?=exp)` 字符出现的位置的右边必须匹配到exp这个表达式
+ 零宽读负预测先行断言 `(?!exp)` 字符出现的位置的右边不能是exp这个表达式
+ 零宽度正回顾后发断言 `(?<=exp)` 字符出现的位置的前边是exp这个表达式
+ 零宽度负回顾后发断言 `(?<!exp)` 字符出现的位置的前边不是exp这个表达式

```javascript
// (?=exp)
const str = "i'm singing and dancing";
const reg = /\w+(?=ing)/g;
const res = str.match(reg);
console.log(res); // > ["sing", "danc"]

// (?!exp)
const str2 = 'nodejs';
const reg2 = /node(?!js)/g;
console.log(reg2.test(str2)); // false

// (?<=exp) 
const str3 = '￥998$888';
const reg3 = /(?<=\$)\d+/g;
console.log(str3.match(reg3)); // > ["888"]

// (?<!exp)
const str4 = '￥998$888';
const reg4 = /(?<!\$)\d+/g;
console.log(str4.match(reg4)); // > ["998", "88"]
```

