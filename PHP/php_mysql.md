##PHP MySQL篇##

该篇不介绍SQL statements，主要侧重于如何通过PHP来使用MySQL。

###连接###
1. 在使用MySQL之前，脚本需要创建一个数据库连接。mysql_connect(servername,username,password)函数用于实现这个功能。
2. 同样mysql_close()函数用来关闭这个连接。
		
		$connect = mysql_connect(servername,username,password);
		mysql_close($connect);

###操作###
mysql_query(statement, connect)是用来执行SQL语句的函数

1. 创建一个数据库 mysql_query("CREATE DATABASE my_db", $connect)
2. 选择这个数据库 mysql_select_db("my_db",$connect)
3. 执行一个statement。mysql_query($statement,$connect)。这个$statement是一个string。将SQL Statement赋值给这个string，然后执行这个函数。
4. 当从数据表中Select数据后，需要用一下函数(常用的)进行获取结果：
	<table width="100%">
		<col width="25%">
		<col width="75%">
		<tr>
			<td>mysql_fetch_array()</td>
			<td>从结果集中国年取得一行作为关联数组或者索引数组，或者both</td>
		</tr>
		<tr>
			<td>mysql_fetch_assoc()</td>
			<td>从结果集中取得一行作为关联数组</td>
		</tr>
		<tr>
			<td>mysql_fetch_row()</td>
			<td>从结果集中取得一行作为索引数组</td>
		</tr>
		<tr>
			<td>mysql_fetch_object()</td>
			<td>从结果集中取得一行作为object</td>
		</tr>
		<tr>
			<td>mysql_num_rows()</td>
			<td>取得结果集中行的数目</td>
		</tr>
	</table>