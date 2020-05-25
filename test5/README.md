<h1>实验5：图书管理系统数据库设计与界面设计 </h1>

|  学号  |  班级  |  姓名  |
|:---:|:---:|:---:|
|201710414312|软件17-3|马聪

<h2>1.数据库表设计</h3>

<h3>1.1图书表</h3>

|  字段  |  类型  |  主键，外键  |  可以为空  |  默认值  |  约束  |  说明  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|book_id|varchar2(100)|主键，外键|否||唯一标识||
|book_name|varchar2(100)||否||||
|book_author|varchar2(100)||否||||
|book_type|varchar2(100)||否||||

<h3>1.2用户表</h3>

|  字段  |  类型  |  主键，外键  |  可以为空  |  默认值  |  约束  |  说明  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|user_id|varchar2(100)|主键，外键|否||唯一标识||
|uname|varchar2(100)||否||||
|upwd|varchar2(100)||否||||
|user_name|varchar2(100)||否||||
|user_phone|varchar2(100)||否||||
|user_site|varchar2(100)||是||||

<h3>1.3借书表</h3>

|  字段  |  类型  |  主键，外键  |  可以为空  |  默认值  |  约束  |  说明  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|user_id|varchar2(100)|外键|否||||
|book_id|varchar2(100)|外键|否||||
|book_count|varchar2(100)||否||||
|lend_time|datetime(0)||否|||系统自动获取|

<h3>1.4还书表</h3>

|  字段  |  类型  |  主键，外键  |  可以为空  |  默认值  |  约束  |  说明  |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|user_id|varchar2(100)|外键|否||||
|book_id|varchar2(100)|外键|否||||
|repay_time|datetime(0)||否|||系统自动获取|

<h2>2.界面设计</h2>

<h3>2.1借书界面设计</h3>

链接：<https://NMSL-MC.github.io/is_analysis_pages/test5/mc/login.html>

![test5](1.png)

![test5](2.png)

#### 1 登录

+ 功能：用于用户登录
+ 请求地址： <https://NMSL-MC.github.io/is_analysis_pages/test5/mc/login.html>
+ 请求方法：POST
+ 请求参数：

|  参数名称  |  必填  |  说明  |
|:---:|:---:|:---:|
|uname|是|用于验证身份|
|upwd|是|用于验证身份|


+ 返回实例：

```
{
	"info": "欢迎登录",
		"data": {
				"user_name":"***",
				"book_name":"***",
                "book_type":"***",
                "book_count":"***",
				},
	"code":200
}
```

+ 返回参数说明：

|参数名|说明|
|:---|:---:|
|user_name|用户名称|
|book_name|图书标题|
|book_type|图书类型|
|book_count|图书余量|


