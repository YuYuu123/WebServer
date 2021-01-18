本版本独立完成用户登录功能

登录流程：
1:用户在首页点击登录的超链接来到登录界面
2:在登录页面中输入用户名和密码并点击登录按钮
3:服务端处理登录
4:响应登录结果页面(登录失败或者登录成功)

实现:
1:在webapps/myweb下准备页面
1.1:long.html 登录界面
    这个页面的form表单action="./loginUser"
    表单中要求两个输入框，分别输入用户名和密码
1.2：login_fail.html 登录失败提示页面
    居中显示一行字：登录失败，用户名或密码不正确
1.3：login_success.html 登录成功界面
    居中显示一行字：登录成功，欢迎光临！
2.在com.webserver.servlet中添加处理登录的业务类：LoginServlet并完成service方法
只有当用户名和密码都正确时响应登录成功页面
需要将登录信息与user.dat文件中的用户进行对比
3：在ClientHandler处理请求环节在添加一个分支，如果请求路径对应的是登录，则实例化
LoginServlet并调用其service方法并处理登录