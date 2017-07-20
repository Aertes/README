## JavaScript中五中常用的判断字符串中是否包含某字符或方法及比较

#### 7/20/2017 10:41:46 AM
---

### 一、五种判断方法

1. indexOf方法：

	代码：

    	var str = 'abc';
    	if(str.indexOf('bc') != -1){}

    
2. search方法：

	代码：

    	var str = 'abc';
    	if(str.search('bc') != -1){}


3. test方法：

	代码：

    	var str = 'abc';
    	var reg = new RegExp('^.*bc.*$');
    	if(reg.test(str){}


4. match方法：

	代码：

    	var str = 'abc';
    	var reg = new RegExp('^.*bc.*$');
    	if(str.match(reg)){}

5. exec方法：

	代码：

    	var str = '1a1b1c';
    	var reg = new RegExp('1.','g');
    	if(reg.exec(str){}


### 二、五种方法的比较 ###

1. indexOf与search：
	- search()方法用于检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串。indexOf()方法是用来判断一个字符串是否存在于一个更长的字符串中。从长字符串左端到右端来搜索，如果存在该子字符串就放回它所处的位置（即索引值）。如果在被搜索的字符串没有找到要查找的字符串则返回-1。 **注意：** 这里的位置应当填写索引值。所有的字符串索引值是从0开始的，第一个字符的位置就是0，终点位置就是字符串的长度减去1。

		- indexOf()与search()的区别：
		
			1. search()的参数必须是正则表达式，indexOf()的参数是普通字符串。
			2. indexOf()是比search()更加底层的方法。
			3. indexOf()系统资源消耗更小，效率更高；如果查找某些特征的字符串，那么则必须使用正则表达式和search()方法。

    2.match、test和exec的比较：
	
	- 创建正则表达式字面量，加上^和$，与不加是有区别的。
	- 对于test()方法，存在比正则多的字符的时候，依然返回比较成功true，这与我们仅仅想比较内容合预期的要求是相背离的。

		**比如：**
	
	        var regx = /\d{1,2}\/\d{1,2}\/d{4}/gi;
	    	regx,test('08/08/2014 5'); //会返回true,因为字符串中包含符合要求的字符串
	- match也可以获得匹配的内容，而regx。exec('08/08/2014 2')就会返回null，尽管字符串中有符合要求的内容。
	- match的调用对象是字符串，exec和test的调用对象是regx。
	- 如果你仅仅想在字符串中搜索，那么久不需要加开始和结束限定符。
	- regx的exec方法会每次返回1个匹配，如果不为空就进行下一次查找，因此可以使用while循环来写。
	- match返回一个匹配的数组，test返回字符串中是否包含指定的模式，exec返回字符串中该模式，并将下一次开始查找的位置保存在*lastIndex*属性中。


----------

Give them a try:

- **Bold** (`Ctrl+B`) and *Italic* (`Ctrl+I`)
- Quotes (`Ctrl+Q`)
- Code blocks (`Ctrl+K`)
- Headings 1, 2, 3 (`Ctrl+1`, `Ctrl+2`, `Ctrl+3`)
- Lists (`Ctrl+U` and `Ctrl+Shift+O`)

