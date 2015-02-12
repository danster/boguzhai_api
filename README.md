# 博古斋移动接口开发文档

### 一、接口规范

规范一：所有接口使用Markdown文档维护，Github更新
 
规范二：Http Request 为了安全考虑采用POST方式，UTF-8编码，key=value形式参数
 
规范三：Http Response 返回 json 数据格式信息，UTF-8编码
 
规范四：当需要从服务器获取图片、文档等文件时，提供URL，采用GET方式获取文件
 
规范五：

- 登录后服务器返回一个sessionid
- 访问需要登录的接口须带有sessionid字，访问不需要登录的接口则不用带上sessionid字段。 
- 当sessionid不正确或者失效时，需要重新登录，重新获取sessionid
- 当用户登出后，sessionid失效，该逻辑需要服务器实现

 
规范六：所有APP接口采用统一url，不同的接口间以参数m区分，例如：  

- http://url?m=login&phone=13812345678&password=123456
- http://url?m=resetpwd&sessionid=...&oldpwd=...&newpwd=...
- http://url?m=search&auctionid=MT0112

--- 

###附一：移动端session id逻辑
<br>

![session id逻辑](./res/sessionid_logic.png =700x)