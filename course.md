## 文档统一说明
>返回值为state:0,说明出错了。
>返回值为state:1,token错误或已过期，请重新登录
>返回值为state:2,操作成功，提示即可
## 登录接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/login | get|code(微信code)  | 微信openid、session—key、token
>token值设置的为一天，用户token过期需得请求该接口
