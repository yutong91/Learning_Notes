##PHP 服务器篇##


###Server###
<table width="100%" border=0 cellpadding=0 cellspacing=0 style='border-collapse:
 collapse;table-layout:fixed;'>
 <col width="40%" span=1>
 <col width="60%">
 <tr>
  <td><span style="font-weight:bold">元素/代码</span></td>
  <td><span style="font-weight:bold">描述</span></td>
 </tr>
 <tr>
  <td>$_SERVER['PHP_SELF']</td>
  <td>返回当前执行脚本的文件名。</td>
 </tr>
 <tr>
  <td>$_SERVER['GATEWAY_INTERFACE']</td>
  <td>返回服务器使用的 CGI 规范的版本。</td>
 </tr>
 <tr>
  <td>$_SERVER['SERVER_ADDR']</td>
  <td>返回当前运行脚本所在的服务器的IP 地址。</td>
 </tr>
 <tr>
  <td >$_SERVER['SERVER_NAME']</td>
  <td>返回当前运行脚本所在的服务器的主机名（比如www.w3school.com.cn）。</td>
 </tr>
 <tr>
  <td>$_SERVER['SERVER_SOFTWARE']</td>
  <td>返回服务器标识字符串（比如 Apache/2.2.24）。</td>
 </tr>
 <tr>
  <td>$_SERVER['SERVER_PROTOCOL']</td>
  <td>返回请求页面时通信协议的名称和版本（例如，“HTTP/1.0”）。</td>
 </tr>
 <tr>
  <td>$_SERVER['REQUEST_METHOD']</td>
  <td>返回访问页面使用的请求方法（例如 POST）。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['REQUEST_TIME']</td>
  <td>返回请求开始时的时间戳（例如 1577687494）。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['QUERY_STRING']</td>
  <td>返回查询字符串，如果是通过查询字符串访问此页面。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['HTTP_ACCEPT']</td>
  <td>返回来自当前请求的请求头。</td>
 </tr>
 <tr>
  <td>$_SERVER['HTTP_ACCEPT_CHARSET']</td>
  <td>返回来自当前请求的 Accept_Charset 头（ 例如
  utf-8,ISO-8859-1）</td>
 </tr>
 <tr>
  <td>$_SERVER['HTTP_HOST']</td>
  <td>返回来自当前请求的 Host 头。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['HTTP_REFERER']</td>
  <td>返回当前页面的完整 URL（不可靠，因为不是所有用户代理都支持）。</td>
 </tr>
 <tr>
  <td>$_SERVER['HTTPS']</td>
  <td>是否通过安全 HTTP 协议查询脚本。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['REMOTE_ADDR']</td>
  <td>返回浏览当前页面的用户的 IP 地址。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['REMOTE_HOST']</td>
  <td>返回浏览当前页面的用户的主机名。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['REMOTE_PORT']</td>
  <td>返回用户机器上连接到 Web 服务器所使用的端口号。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['SCRIPT_FILENAME']</td>
  <td>返回当前执行脚本的绝对路径。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['SERVER_ADMIN']</td>
  <td>该值指明了
  Apache 服务器配置文件中的
  SERVER_ADMIN 参数。</td>
 </tr>
 <tr>
  <td>$_SERVER['SERVER_PORT']</td>
  <td>Web 服务器使用的端口。默认值为</td>
 </tr>
 <tr>
  <td>$_SERVER['SERVER_SIGNATURE']</td>
  <td>返回服务器版本和虚拟主机名。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['PATH_TRANSLATED']</td>
  <td>当前脚本所在文件系统（非文档根目录）的基本路径。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['SCRIPT_NAME']</td>
  <td>返回当前脚本的路径。</td>
  
 </tr>
 <tr>
  <td>$_SERVER['SCRIPT_URI']</td>
  <td>返回当前页面的 URI。</td>
  
 </tr>
</table>
