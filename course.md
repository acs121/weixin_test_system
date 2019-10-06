## 文档统一说明
>返回值为state:0,说明出错了。
>返回值为state:1,token错误或已过期，请重新登录
>返回值为state:2,操作成功，提示即可
## 获取课程列表
|url |method| 参数 | 返回值
|------------ | -------------| ------------- | ------------
|http://www.heimdall2019.club:8081/course/getCourseList | post|token  | 课程信息
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
|http://www.heimdall2019.club:8081/order/createOrder | post|token,student_id,student_name,order_name,order_price,picture  | 课程id列表
