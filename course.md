## 文档统一说明
>返回值为state:0,说明出错了。
>返回值为state:1,token错误或已过期，请重新登录
>返回值为state:2,操作成功，提示即可
## 获取课程列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/getCourseList | post|token,subject_id  | 课程信息
## 根据课程id获取视频列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/getVideoList | post|token,course_id  | 视频列表信息
## 根据视频id获取视频
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/getVideo | post|token,video_id  | 视频信息
## 将课程id插入学生表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/insertStudentCourseId | post|token,student_id,course_id  | 提示即可
## 获取学生课程列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/getStudentCourseId | post|token,student_id  | 课程id列表
## 创建订单
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/order/createOrder | post|token,student_id,student_name,order_name,order_price,picture  | 提示即可
order_name即课程的名字，图片也是
## 改变订单支付状态
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/order/changeOrderPay | post|token,student_id,order_id  | 提示即可
## 改变订单支付状态
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/order/getOrderList | post|token,student_id  | 订单列表信息
## 根据科目id获取练习题数目
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/practise/getSubjectNumber | post|token,subject_id  | 题目数量
## 根据科目id章节列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/practise/getChapterList | post|token,subject_id  | 章节列表
## 根据章节id获取题目数量
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/practise/getChapteNumber | post|token,chapter_id  | 题目数量
## 根据章节id获取练习题id列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/practise/getPractiseList | post|token,chapter_id  | 题目id列表
## 根据练习题id获取练习题内容
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/practise/getPractiseContent | post|token,practise_id  | 题目内容
