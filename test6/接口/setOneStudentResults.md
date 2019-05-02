# 接口：setOneStudentResults  [返回](../README.md)
用例： [评定成绩](../用例/评定成绩.md)

- 功能：
    设置一个学生的部分实验成绩和评语。
    
    输入参数result不为空，自动设置update_date为当前日期，表示同时设置批改日期。
    
    输入参数result为空，自动设置update_date为空，表示未批改。
    
- 权限：
    老师：可以查看所有学生的成绩。
    
- API请求地址： 
    接口基本地址/v1/api/etOneStudentResults

- 请求方式 ：
    POST
 
```javascript
- 请求实例：  
{ 
            "student_id": "201510315203", 
            "total": 6,
            "test_data": [
                {
                    "total_score_id":1,
                    "total_score": 91, 
                    "total_memo":"本实验做得好",
                    "detail_scores":[
                        "score":60,
                        "detail_memo":"文档存在一定问题",
                        "standard_mix":"40"
                        },
                        ...其他评分项
                    ]
                }, 
                {
                    ...其他实验
                }
            ] 
        }
```
- 请求参数说明:       
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学号|
    |github_username|学生的gitHub用户名|
    |major_grade_class|专业班级|
    |name|真实姓名|   
    |total|实验总数|
    |test_data|所有实验的成绩和评语|
    |total_score_id|总评分编号|
    |total_score|本实验成绩，可以为空，为空表示没有批改，没有批改的实验不入平均成绩，为0分则要计入平均成绩，所以成绩为空和为0是不一样的。|
    |total_memo|本实验老师的总评价，可以为空|
    |update_date|本实验老师的批改日期，可以为空|
    |detail_scores|详细评分项|
    |score|详细评分|
    |detail_memo|详细评分项评价|
    |standard_mix|评分占比| 
 
- 返回实例：

        {         
            "code": 200,
            "msg": "评定成功"
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |code|返回结果状态码|
  |msg|返回结果说明信息|

