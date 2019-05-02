# 接口：getCourseByStudent  [返回](../README.md)
用例： [查看课程](../用例/查看课程.md)

- 功能：
    查看学生自身已选择课程
- 权限：
    学生  
    
- API请求地址： 
    接口基本地址/v1/api/getCourseByStudent

- 请求方式 ：
    POST

- 请求实例：
    无
        
- 请求参数说明:        

  
- 返回实例：

        { 
            "code":200,
            "msg":"选择成功",
            "data":[{
            course_student_id:"123",
            "course_name":"软件",
            "major":"软件工程",
            "teacher_name":"XXX"
            }]   
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |code|返回结果状态码|
  |msg|返回结果说明信息|
  |data|查询到的相应信息|
