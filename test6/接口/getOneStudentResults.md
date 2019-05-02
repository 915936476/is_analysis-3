# 接口：getOneStudentResults  [返回](../README.md)
用例： [查看成绩](../用例/查看成绩.md)，[评定成绩](../用例/评定成绩.md)

- 功能：
    返回一个学生的所有实验成绩和实验评价。
    
- 权限：
    学生：只能查看自己的成绩，即接口参数student_id必须等于登录学生的student_id
    老师：可以查看所有学生的成绩。
    
- API请求地址： 
    接口基本地址/v1/api/getOneStudentResults/<student_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学生的学号|
    
- 返回实例：

        {         
            "code":200,
            "msg":"查询成功",   
            "data":{
                "student_id": "201510315203", 
                "github_username": "chinajuedui", 
                "major_grade_class": "软件(本)16-4", 
                "name": "肖清宇", 
                "total": 6,
                "avgresult":90.5,       
                "test_data": [
                            {
                            "total_score_id":1,
                            "total_score": 91, 
                            "test_name":"实验1",
                            "test_url":"xxxx",
                            "total_memo":"本实验做得好",
                            "update_date": "2018-04-02 13:48:01",
                            web_exists:"true",
                            "detail_scores":[
                            "score":60,
                            "detail_memo":"文档存在一定问题",
                            "standard_name":"文档规范",
                            "standard_detail":"文档必须使用md格式编写，格式规范",
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
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |code|返回结果状态码|
  |msg|返回结果说明信息|
  |data|查询到的相应信息|
  |student_id|学号|
  |github_username|学生的gitHub用户名|
  |major_grade_class|专业班级|
  |name|真实姓名|   
  |total|实验总数|
  |avgresult|实验平均成绩|   
  |test_data|所有实验的成绩和评语|
  |total_score_id|总评分编号|
  |test_name|实验名称|
  |test_url|实验要求url|
  |web_exists|本实验的GitHub网页是否存在|
  |total_score|本实验成绩，可以为空，为空表示没有批改，没有批改的实验不入平均成绩，为0分则要计入平均成绩，所以成绩为空和为0是不一样的。|
  |total_memo|本实验老师的总评价，可以为空|
  |update_date|本实验老师的批改日期，可以为空|
  |detail_scores|详细评分项|
  |score|详细评分|
  |detail_memo|详细评分项评价|
  |standard_name|评分标准名称|
  |standard_detail|评分标准描述|
  |standard_mix|评分占比|

