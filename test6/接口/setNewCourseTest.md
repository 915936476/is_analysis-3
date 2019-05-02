# 接口：setNewCourseTest  [返回](../README.md)
用例： [发布实验](../用例/发布实验.md)

- 功能：
    教师发布新实验
    
- 权限：
    老师，需先登录
    
- API请求地址： 
    接口基本地址/v1/api/setNewCourseTest

- 请求方式 ：
    POST

- 请求实例：

        {
            "test_name":"xxxx",
            "test_url":"xxxx",     
            "course_teacher_id":"xxxx",
            "standards":[{
                "standard_name":"xxx",
                "standard_detail":"xxx",
                "standard_mix":20
            }]       
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |test_name|实验名称|
  |test_url|实验描述的github连接| 
  |course_teacher_id|关联开课课程、教师关联信息id|
  |standards|评价标准|
  |standard_name|评价标准名称|
  |standard_detail|评价标准描述|
  |standard_mix|占总成绩比例|
- 返回实例：

        {         
            "code": 200,
            "msg": "添加成功"
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |code|返回结果状态码|
  |msg|返回结果说明信息|