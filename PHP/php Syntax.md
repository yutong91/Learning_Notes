<script type="css/style">
div.block{
	background:#f7f7f7; 
	padding: 16px; 
	word-wrap:normal; 
	font-size:85%; 
	line-height: 1.45; 
	border-radius:3px; 
	margin-top:0; 
	margin-bottom:16px;
}
</script>

#PHP基本语法要点整理#


###变量与常量###
####变量####
1. 用 **$** (Dollar Sign) 开头，没有创建命令，在首次赋值的时候创建变量
2. 以字母或者下划线(underscore character)开始命名变量，变量名字只能是字母、数字(alpha-numeric)或者下划线
3. 变量的名字是case-sensitivity的，但是php中关键字、函数以及类都是not case-sensitivity
4. 不需要声明变量 -－> PHP is a loosely typed language
5. Scope
	- local：声明在Function内部，只能在函数内部使用和访问
	- global：声明在Function外部，只在函数以外进行访问（顾名思义，函数内部**不能使用**！如果需要在函数内部使用，那么需要在Function内部重新声明变量，不需要赋值，需要用global关键字；也可以不声明直接使用$GLOBALS['变量名']）
	- static：在函数结束后，并不删除该变量；下次调用函数时，该变量继续使用。
比如：
		
		<?php
	
		function myTest() {
  			static $x=0;
  			echo $x;
  			$x++;
		}

		myTest(); // print 0
		myTest(); // print 1
		myTest(); // print 2

		?>
6. 超全局变量(Superglobals)：在任何脚本的全部作用域中都可以直接访问，不需要用global关键字。这些超全局变量是从PHP 4.1.0中引进的。
	- $GLOBALS:用于引用全局变量
	- $_SERVER：用于获取报头、路径、脚本位置等等
	- $_REQUEST：用于收集HTML表单提交的数据。
	- $_POST：用于收集表单提交后的表单数据(method = "post")
	- $_GET：用于收集提交HTML表单之后的表单数据(method ="get")，也用于收集URL中发送的数据
	- $_FILES
	- $_ENV
	- $_COOKIE
	- $_SESSION
####常量####
1. 常量是具有某个固定值的标识符，在脚本中无法改变，默认自动全局。
2. 与变量不同，常量没有Dollar Sign。
3. 用define()函数来定义。define(常量名称，常量的值，大小写敏感=false)。

###函数###
1. echo vs. print
	- 共同点
		- 都是语言结构(language construct)，有无括号(parentheses)都可以使用
		- 都可以输出字符串
	- 不同点
		- echo可以输出一个以上的字符串，没有返回值；
		- print也是一个函数，只能输出一个字符串，并且始终返回1。
		- print_r是递归打印，用于打印数组。

2. 常用字符串函数
	- strlen()获取字符串长度；注意：如果用count()，返回的是1，因为count是用于返回数组长度的。这个函数会把整个string当作array里的一个元素处理，无论string有多长，都是一个元素，返回值为1.
	- strpos()检索字符串中是否有指定的字符或者文本，找到则返回首个匹配的位置；否则返回false。
3. 用户定义函数
	- 用function开头，函数名必须用字母或者下划线开头，数字不可以。通常，函数名要能反映出函数的功能。
	- 对大小写不敏感
	- 参数用逗号隔开。可以设置参数的默认值，如果没有调用该参数，那么参数自动获取默认值。
	- 返回值用return，可以返回多种类型。


###运算、循环###
####运算####
1. 算数运算符：＋，－，＊，／，％
2. 赋值运算符：＝，+=，-=，＊＝，／＝，％＝
3. 字符串运算符：. ，.=
4. 递增递减运算符： ++$x(前递增),$x++(后递增), --$x(前递减), $x--(后递减)
5. 比较运算符
	- ==, !=, <>, >, <, >=, <=
	- === 完全相同，不光是数值相等，类型也要相同
	- !== 完全不同，数值和类型都不相同
6. 逻辑运算符
	- and, or, &&, ||, !
	- xor异或 有且仅有一个为true是，才会返回true
7. 数组运算符
	- + 联合。$x + $y 为两个联合，不覆盖重复的key。
	- == 相等，有相同的key=>value
	- === 全等，包括相同的key=>value也对，顺序也相同，类型也相同
	- !=, <> 不相等
	- !== 完全不同。搞不太懂和不相等的区别。

####循环####
**此处不说明 if...else语句，while语句，do..while语句,for语句和switch语句**
foreach：遍历数组中的每一个元素并循环代码块。只是用于数组。
	
	foreach($array as $value){
		echo $value."<br>";
	}
	
	foreach($array as $key => $value){
		echo $key."=>".$value."<br>"
	}
	
	
###数组###
1. 数组有三种类型：索引数组Indexed array（key是数字），关联数组Associative array（自定义key），多维数组Multidimentsional array
2. 索引数组和关联数组都有两种定义方式
	- 	array("a","b","c") ->索引数组
		array("aKey"=>""aValue","bKey"=>"bValue") -> 关联数组
	- 	$array[0] = "a"; $array[1] ="b"; 索引数组
		$array["aKey"] = "aValue"; $array["bKey"] = "bValue"; 关联数组
		
3. 用for和foreach来遍历数组
4. 排序
	- 有六种需要排序方法
		- sort() 按照字母或数字升序排序(in ascending alphabetical order)－－索引数组
			当value都是string的时候排序后，数字会是这种情况：
						
				$temp=array("temp1","temp20",
				"temp10","temp15",
				"temp4","temp22");
				
				sort($temp);
				echo "\$temp: <br>";
				foreach($temp as $x_value)
    			{
    				echo "Value=" . $x_value;
    				echo "<br>";
    			}
    			
    			
    			$age=array("1","20",
				"10","15",
				"4","22");
				sort($age);
				echo "\$arg: <br>";
				foreach($age as $x_value)
    			{
    				echo "Value=" . $x_value;
    				echo "<br>";
    			}
    			结果是：
    			$temp: 
				Value=temp1
				Value=temp10
				Value=temp15
				Value=temp20
				Value=temp22
				Value=temp4

				$arg: 
				Value=1
				Value=4
				Value=10
				Value=15
				Value=20
				Value=22

		- rsort() 按照字母或者数字降序排序(in descending alphabetical order)－－索引数组
		- asort() 根据**value**对关联数组升序排序－－关联数组
		- ksort() 根据**key**对关联数组升序排序 -- 关联数组
		- arsort() 根据**value**对关联数组降序排序－－关联数组

		- krsort() 根据**key**对关联数组降序排序－－关联数组
	- natsort() 自然顺序排序。即数字从1-9的排序方法，字母从a－z排序。短者优先。

			$temp_files = array("temp15.txt",
			"temp10.txt", "temp1.txt",
			"temp22.txt", "temp2.txt");

			natsort($temp_files);
			echo "Natural order: ";
			print_r($temp_files);
			
			输出
			Natural order: Array
			(
				[0] => temp1.txt
				[3] => temp2.txt
				[1] => temp10.txt
				[2] => temp15.txt
				[4] => temp22.txt
			)


###表单###
1. Get vs. Post
	- 相同点
		* 都通过创建关联数组来传递数据。key时表单控件的名称，value时来自用户的输入数据
		* $_GET 和 $_POST都是superglobals
	- 不同点
		- 可见性
			* GET对任何人可见，所有的key和value都显示在URL中。
			* POST对其他人时不可见的，key和value都嵌入在HTTP请求的主体中。
		- 容量
			* GET对发送的信息数量是有限制的，2000个字符左右，一般不超过2MB（1一个字符通常是1kb）。
			* 发送的信息数量没有限制。
	- 通常情况下，在做网络开发时，使post来发送表单数据。在MVC架构中，view中的form会标记method = post，用post发送表单数据，而在获取数据内容用以显示的时候，会用get来获取，显示在url里。
	
2.  $_SERVER["PHP_SELF"]

	讲表单数据发送到页面本身，用于验证，这样就可以直接从表单页面获取错误提示信息。但是这个变量极容易被黑客利用攻击。

	用户能够输入斜线后执行跨站点脚本（XSS），即可以通过用户自己输入的代码而改变网站内容。
	
<div class="block">XSS－> Cross-site scripting，是跨网站脚本。是网站应用程序的安全漏洞攻击，算代码注入的一种。它允许用户将代码注入到网页上，其他用户在观看网页时就会收到影响，这种攻击通常包含HTML以及用户端脚本语言。

攻击者使被攻击者在浏览器中执行脚本后，如果需要收集来自被攻击者的数据，可以自行架设一个网站，让被攻击者通过Javascript等方式把手机号的数据，作为参数提交，随后以数据库等形式记录在攻击者自己的服务器上。常用的XSS的攻击手段和目的有
	- 盗用 cookie ，获取敏感信息。
	- 利用植入 Flash ，通过 crossdomain 权限设置进一步获取更高权限；或者利用Java等得到类似的操作。
	- 利用 iframe、frame、XMLHttpRequest或上述Flash等方式，以（被攻击）用户的身份执行一些管理动作，或执行一些一般的如发微博、加好友、发私信等操作。
	- 利用可被攻击的域受到其他域信任的特点，以受信任来源的身份请求一些平时不允许的操作，如进行不当的投票活动。
	- 在访问量极大的一些页面上的XSS可以攻击一些小型网站，实现DDoS攻击的效果。</div>
			
> <pre><code>在PHP当中，通常使用htmlspecialchars()来避免。<br>
The htmlspecialchars() function converts special characters to HTML entities. This means that it will replace HTML characters like < and > with &lt; and &gt;. This prevents attackers from exploiting the code	by injecting HTML or Javascript code (Cross-site Scripting attacks) in forms.
						－－Referenced from w3cSchools </code></pre>
						
3.  几种验证方式
	- 验证名字: <pre><code>preg_match("/^[a-zA-Z ]*$/",$name)</pre></code>
	- Email:<pre><code>preg_match("/([\w\-]+\@[\w\-]+\.[\w\-]+)/",$email)</pre></code>
	- URL:<pre><code>preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0&-9+/%=~_|]/i",$website)</pre></code>
			
