#PHP基本语法要点整理#


###变量###
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

###函数###
1. echo vs. print
	- 共同点
		- 都是语言结构(language construct)，有无括号(parentheses)都可以使用
		- 都可以输出字符串
	- 不同点
		- echo可以输出