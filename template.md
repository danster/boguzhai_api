#用户登录接口

- Author : 黄茂峰
- Modified Time : 2014-2-10
- Version : 1.0

---
### Http 请求 

**请求参数列表**
 
- m=login
- phone=13812345678  #11位手机号码
- password=123456   #密码(暂不考虑加密)
 
---
### Http 回复  

- code=0 : 登录成功，返回用户信息和seesionid
- code=1 : 登录失败，无此用户名
- code=2 : 登录失败，密码错误

**几种情况如下**

``` 
{ 
    "code": 0;
    "account": {
    	"sessionid": "1h283019400031n22hhu22313145252";
    	"username": "zhangsan01";
    	"name": "张三";
    	"phone": "13813431352";
    	"birthday": "19870710";
    	"sex": "1";     # 1代表男，0代表女
    	"photo": "http://www.boguzhai.com/res/user/13813431352/photo.png";  # 图片url
		"email": "zhangsan@126.com";         
	}
}
```
``` 
{ 
    "code": 1;
}
```
``` 
{ 
    "code": 2;
}
```
