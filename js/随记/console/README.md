# 你不知道的console

### All

<img src="img/console.all.png" alt="img/console.all.png" />


### type

> console.log(), console.error(), console.warn(), console.info()

<img src="img/console.type.png" alt="img/console.type.png" />

### 断言(assert)

```javaScript
console.assert(expression, message)
```
> 参数：
> expression: 条件语句，语句会被解析成 Boolean，且为 false 的时候会触发message语句输出
> message: 输出语句，可以是任意类型


<img src="img/console.assert().png" alt="console.assert().png" />

### 计数(count)

```javaScript
console.count(label)
```

> 参数：
> label: 计算数量的标识符

<img src="img/console.count().png" alt="console.count().png" />

### 目录(dir)

```javaScript
console.dir(object)
```

> 参数：
> object：被输出扎实的DOM对象

<img src="img/console.dir().png" alt="console.dir().png" />

### xml目录(dirxml)

```javaScript
console.dirxml(object)
```

>该函数将打印输出XML元素及其子孙后代元素，且对HTML和XML元素调用 console.dirxml() 和 调用 console.log() 是等价的。

<img src="img/console.dirxml().png" alt="console.dirxml().png" />

### 表格(table)


```javaScript
console.table(Array or Object);
```
> table方法可以将一个数组数据或是对象展示为一张表格。

```javaScript
console.table(['Javascript', 'PHP', 'Perl', 'C++']);
```
<img src="img/console.table(arr).png" alt="console.table(arr).png" />

> 数组的索引或对象属性名称位于左侧索引列下。 而值将显示在右侧列中。

```javaScript
const superhero = { 
    firstname: 'Peter',
    lastname: 'Parker',
}
console.table(superhero);
```
<img src="img/console.table(obj).png" alt="console.table(obj).png" />

Chrome下需要通过将项目放入数组或数组对象来解决此问题:

```javaScript
console.table([['Javascript', 'PHP', 'Perl', 'C++']]);
const superhero = { 
    firstname: 'Peter',
    lastname: 'Parker',
}
console.table([superhero]);
```
<img src="img/console.table(arr-or-obj)-Chrome.png" alt="console.table(arr-or-obj)-Chrome.png" />

### 开始时间：console.time([label])，结束时间：console.timeEnd([label])

> label: 用于标记计时器的名称，不填的话，默认为 default

> console.time() 会开始一个计时器，并当执行到 console.timeEnd() 函数时（需要两个函数的lable参数相同），结束计时器，并将计时器的总时间输出到控制台上。

```javaScript
	console.time();
	var arr = new Array(10000);
	for (var i = 0; i < arr.length; i++) {
	  arr[i] = new Object();
	}
	console.timeEnd();
	// default: 3.696044921875ms
```

> 对 console.time(label) 设置一个自定义的 label 字段，并使用console.timeEnd(label) 设置相同的 label 字段来结束计时器。

```javaScript
	console.time('total');
	var arr = new Array(10000);
	for (var i = 0; i < arr.length; i++) {
	  arr[i] = new Object();
	}
	console.timeEnd('total');
	// total: 3.696044921875ms
```

> 设置多个 label 属性，开启多个计时器同步计时。

```javaScript
	console.time('total');
	console.time('init arr');
	var arr = new Array(10000);
	console.timeEnd('init arr');
	for (var i = 0; i < arr.length; i++) {
	  arr[i] = new Object();
	}
	console.timeEnd('total');
	// init arr: 0.0546875ms
	// total: 2.5419921875ms
```

### 追踪(trace)

```javaScript
console.trace(object)
```

> 该函数将在控制台打印出从 console.trace() 被调用的位置开始的堆栈信息。

<img src="img/console.trace().png" alt="console.trace().png" />

> 标准浏览器在控制台输入下面的代码可以实现所有DOM可编辑

```javaScript
document.body.contentEditable=true
```