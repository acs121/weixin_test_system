## 文档统一说明
>返回值为state:0,说明出错了。
>返回值为state:1,token错误或已过期，请重新登录
>返回值为state:2,操作成功，提示即可

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
## 获取课程列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getsubject | post|token  | 课程subject_id,subject_name,subject_introduce,paper_list,video_list
## 获取套题列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/getPaperList | post|token，subject_id  | 所有套题的paper_id，title_num，paper_title，difficulty，pay，paper_introduce，paper_type，paper_price，subject_id，subject_name,author
>paper_type可能表示该套题是同步训练题或是模拟训练题(暂时先试着显示其他内容，后面再具体定义它是什么)，subject_id表示该套题所属于的学科id
## 根据题目id获取小题内容
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/getQuestionContentByQuestionId | post|token，question_id  | 小题的question_id,question_title,content,paper_name，paper_id
>参数示例：
```
data{
  token:'很长',
  question_id: '11111'（测试用这个id，或者用你获取到的其他id）
}
```
## 根据套题id获取小题id列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/papergetPaperQuestionList | post|token，paper_id  | 套题的paper_content
>参数示例：
```
data{
  token:'很长',
  paper_id: '20190902220512'（测试用这个id，或者用你获取到的其他id）
}
```

## 提交考试结果
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/submmitResult | post|token，studen_id,paper_id,score,time,content  | 课程subject_id,subject_name,subject_introduce,paper_list,video_list
>参数示例：
```
data: {
        token: "很长",
        student_id: 'o5jvH5btczavYM_f-0STJbAKer-4',
        paper_id: '20190902220512',
        time: '2019-09-05-15:00',
        score: '78',
        subject_id:'2001',
        subject_name:'数据结构',
        paper_name:'2018年解剖科目试题',
        content: '[{question_id:11111,num:1,select_num:2},{question_id:11112,num:2,select_num:1},{question_id: 11113,num:3,select_num:3}]'
        }
```
## 提交错题id列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/submmitErrorList | post|token，studen_id,wrong_list,paper_type,subject_id  | 提示即可
>参数示例：
```
data: {
        token: "很长",
        student_id: 'o5jvH5btczavYM_f-0STJbAKer-4',
        paper_type:1,
        subject_id:'20001',
        wrong_list:'[11111,11112,11113]'
        }
```
## 获取学生已考试的套题列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getFinishPaperList | post|token,student_id  | 已考试套题id：did_paper_id,paper_id,score,paper_name,time
## 根据已考试套题id获取答题结果
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/getFinishPaper | post|token,did_paper_id  | 已考试套题id：did_paper_id,paper_id,score,paper_name,time,content
## 根据用户id和小题id删除学生错题
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/wrongQuestion/delWrongQuestionById | post|token,student_id,question_id  |提示即可
## 根据课程id、套题类型、学生id获取错题列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/wrongQuestion/getWrongList | post|token,student_id,subject_id,paper_type  |小题id及对应num
