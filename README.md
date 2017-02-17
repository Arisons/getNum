### 生成指定范围制定个数的不重复的随机数

> 最近页面有这个需求，研究了一下发现这个方法还不错。
> 例：生成1-100范围内的10个不重复随机数

```js

	var arr = [];
	for(var i = 1; i <= 100; i += 1){
		arr.push(i);
	};

	arr.sort(function(){
		return 0.5 - Math.random();
	});
	
	arr.length = 10;
	
	console.log(arr);

```

> 关于sort方法
> [w3school对sort方法的说明](http://www.w3school.com.cn/jsref/jsref_sort.asp)

> 如果调用该方法时没有参数，将按照字母顺序对数组中的元素惊醒排序，说确切点，是按照字符编码的顺序排序，要实现这一点，首先应把数组的元素都转换成字符串（如果有必要），以方便进行比较。

> 如果想按照其他的标准进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明两个值相对顺序的数字。比较函数应该有两个参数a和b，期返回值如下：

>> 若a小于b，在排序后的数组中a应该出现在b之前，则返回一个小于0的值。

>> 若a等于b，则返回0。

>> 若a大于b，则返回一个大于0的值。

> 例1 我们将创建一个数组，并按字母顺序进行排序：

```js
	
	var arr = new Array(6)
	arr[0] = "George"
	arr[1] = "John"
	arr[2] = "Thomas"
	arr[3] = "James"
	arr[4] = "Adrew"
	arr[5] = "Martin"
	
	document.write(arr + "<br />")
	document.write(arr.sort())

```

> 输出：

```js
	
	// George,John,Thomas,James,Adrew,Martin,
	// Adrew,George,James,John,Martin,Thomas

```

> 例2：我们将创建一个数组，并按字母顺序进行排序：

```js

	var arr = new Array(6)
	arr[0] = "10"
	arr[1] = "5"
	arr[2] = "40"
	arr[3] = "25"
	arr[4] = "1000"
	arr[5] = "1"
	
	document.write(arr + "<br />")
	document.write(arr.sort())

```

> 输出：

```js
	
	// 10,5,40,25,1000,1
	// 1,10,1000,25,40,5

```

> 请注意，上面的代码没有按照数值的大小对数字进行排序，要实现这一点，就必须使用一个排序函数：

```js
	
	function sortNumber(a,b){
		return a - b
	}
	
	var arr = new Array(6)
	arr[0] = "10"
	arr[1] = "5"
	arr[2] = "40"
	arr[3] = "25"
	arr[4] = "1000"
	arr[5] = "1"
	
	document.write(arr + "<br />")
	document.write(arr.sort(sortNumber))

```

> 输出：

```js
	
	// 10,5,40,25,1000,1
	// 1,5,10,25,40,1000

```

