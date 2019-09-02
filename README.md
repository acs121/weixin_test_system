## 文档统一说明
>返回值为state:0,说明出错了。

## 登录接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/login | get|code(微信code)  | 微信openid、session—key、token
>token值设置的为一天，用户token过期需得请求该接口
## 获取新闻接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getnews | post|token  | 新闻id,title,content,publisher,picture,time
>picture我定义为新闻列表展示小图
## 获取新闻接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getbooks | post|token  | 图书id,name,author,picture,public,price,information
