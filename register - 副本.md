<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>

<body>
    用户名：<input name="uname" id="u_name" placeholder="请输入用户名" type="text"><br> 登录密码： <input name="upwd" id="u_pwd" placeholder="请输入密码" type="password"><br> 确认密码：
    <input name="upwd_2" id="u_pwd_2" placeholder="请确认密码" type="password"><br> 邮箱：
    <input name="email" id="e_mail" placeholder="请输入邮箱地址" type="email"><br> 手机号： <input name="phone" id="p_hone" placeholder="请输入您的手机号" type="tel"><br>
    <button onclick="reg()">提交注册信息</button>
    <script>
        function reg() {
            //异步对象
            var xhr = new XMLHttpRequest();
            //监听
            xhr.onreadystatechange = function() {
                    if (xhr.readyState == 4 && xhr.status == 200) {
                        var result = xhr.responseText
                        alert(result)
                    }
                }
                //open
            xhr.open('post', 'http://176.211.111.98/user/reg', true);
            //设置头文件
            xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
            var formdata = 'uname=' + u_name.value + '&upwd=' + u_pwd.value + "&upwd_2=" + u_pwd_2.value + '&email=' + e_mail.value + '&phone=' + p_hone.value
            xhr.send(formdata)
        }
    </script>

</body>

</html>