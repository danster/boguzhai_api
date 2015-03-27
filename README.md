# 博古斋移动接口开发文档
  
**注：[所有接口的详细目录](接口目录.md)**  
**注：[接口开发进度](接口进度.md)**  
**注：[接口参考](接口参考.md)**  

### 一、接口规范

规范一：所有接口使用Markdown文档维护，Github更新
 
规范二：Http Request 为了安全考虑采用POST方式，UTF-8编码，key=value形式参数, 图片和文件等经过base64编码字符串后POST
 
规范三：Http Response 返回 json 数据格式信息，UTF-8编码，json数据中的数字尽量用字符串代替，如"20","20150109","30.00"等
 
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

###附一：移动端sessionid逻辑图

<img src="res/sessionid_logic.png" width="650"></img> 

###附二：sessionid时序图

<img src="res/sessionid_time_logic.png" width="650"></img> 