##PHP Cookies & Sessions 篇##

###Cookies###

####定义####
A cookie is often used to identify a user. A cookie is a small file that the server embeds on the user's computer. Each time the same computer requests a page with a browser, it will send the cookie too. With PHP, you can both create and retrieve cookie values.

####创建和取回及删除####
1. setcookie(name,value, expire,path,domain)。用这个函数设置cookies，必须位于<html>标签之前。
2. 用$_COOKIES["name"]，用来取回cookie的值。
3. 删除cookies只需要将cookies的值设置为空即可。`注意：设置值为空是""，而不是NULL`。


###Session###

####定义####
When you work with an application, you open it, do some changes, and then you close it. This is much like a Session. The computer knows who you are. It knows when you start the application and when you end. But on the internet there is one problem: the web server does not know who you are or what you do, because the HTTP address doesn't maintain state.

Session variables solve this problem by storing user information to be used across multiple pages (e.g. username, favorite color, etc). By default, session variables last until the user closes the browser.

####机制####
Session variables hold information about one single user, and are available to all pages in one application.

####使用方法####
1. 开始 －－ 在session使用之前，必须开启session。而且，该函数必须用于<html>之前。session_start()
2. 读取 －－ 用$_SESSION['name']来存储和读取。把$_SESSIOM['name']当成一个不用声明的变量来用。
3. 停止 －－ 通过unset()或者session_destroy()函数来停止。unset()用于停止某一个session，而session_destroy()用于停止所有的session，与start正相反。