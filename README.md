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
## 获取书籍接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getbooks | post|token  | 图书id,name,author,picture,public,price,information,link
## 获取套题列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/getPaperList | post|token  | 所有套题的paper_id，title_num，paper_title，difficulty，pay，paper_introduce，paper_content，message，paper_type，paper_price，subject_id，author
>paper_type可能表示该套题是同步训练题或是模拟训练题，subject_id表示该套题所属于的学科id
## 根据套题id获取套题内容
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/getPaperList | post|token，paperid  | 套题的paper_id，title_num，paper_title，difficulty，pay，paper_introduce，paper_content，message，paper_type，paper_price，subject_id，author
>参数示例：
```
data{
  token:'很长',
  paperid:'20190902220512'（测试用这个id，或者用你获取到的其他id）
}
```
