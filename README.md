## 文档统一说明
>返回值为state:0,说明出错了。
>返回值为state:1,token错误或已过期，请重新登录
>返回值为state:2,操作成功，提示即可

## 登录接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/login | get|code(微信code)  | 微信openid、session—key、token
>token值设置的为一天，用户token过期需得请求该接口
## 获取主页两条新闻接口
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getHomeNewsList | post|token  | 新闻id,title,content,publisher,picture,time
## 根据新闻id获取新闻图片
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsPic | post|token,news_id  | 新闻id,title,content,publisher,picture,time
## 获取主页两条新闻接口无图片
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getHomeNewsListNoPic | post|token  | 新闻id,title,content,publisher,picture,time
## 根据新闻id获取新闻
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsById | post|token,news_id  | 新闻id,title,content,publisher,picture,time
## 根据新闻id获取新闻无图片
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsById | post|token,news_id  | 新闻id,title,content,publisher,picture,time
>picture我定义为新闻列表展示小图
## 获取新闻列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsList | post|token  | 新闻id,title,content,publisher,picture,time
## 获取新闻列表无图片
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsListNoPic | post|token  | 新闻id,title,content,publisher,picture,time
## 根据新闻id获取图片
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/news/getNewsPic | post|token，news_id  | 新闻id,title,content,publisher,picture,time
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
|http://www.heimdall2019.club:8081/paper/getPaperList | post|token，subject_id,paper_type  | 所有套题的paper_id，title_num，paper_title，difficulty，pay，paper_introduce，paper_type，paper_price，subject_id，subject_name,author
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
|http://www.heimdall2019.club:8081/paper/papergetPaperQuestionList | post|token，paper_id  | 套题的paper_content
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
|http://www.heimdall2019.club:8081/paper/submmitResult | post|token，studen_id,paper_id,score,time,content  | 课程subject_id,subject_name,subject_introduce,paper_list,video_list
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
        content: '[{"question_id":11111,"num":1,"select_num":2},{"question_id":11112,"num":2,"select_num":1},{"question_id": 11113,"num":3,"select_num":3}]'
        }
```
## 提交错题id列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/submmitErrorList | post|token，studen_id,wrong_list,paper_type,subject_id  | 提示即可
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
## 根据学生id修改学生用户名
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/personal/updateUsername | post|token,student_id,username |返回成修改功
## 根据课程id获取视频列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/video/getVideoList | post|token,student_id |视频的一些相关信息
>这里的url是教师端的相对路径，访问时在url前面加上http://www.heimdall2019.club:8083
## 获取学生用户名
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/personal/getStudentInfo | post|token,student_id |username
## 判断套题是否已经做了
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/paper/isFinishedPaper | post|token,student_id,paper_id |state：2表示没有做，state：-1表示已经做了
## 获取热书列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/video/getHotBookList | post|token |书籍列表
## 获取留言列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|https://www.heimdall2019.club:8081/leaveWord/getLeaveWordList | post|token,object_id |留言列表
>object_id指视频id或者套题id
## 学生留言
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|https://www.heimdall2019.club:8081/leaveWord/studentLeaveWord | post|token,object_id,student_id,student_name,student_content, |留言列表
>student_content表示留言内容
## 获取学生信息
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|https://www.heimdall2019.club:8081/personal/getStudentInfo | post|token,student_id |学生信息
