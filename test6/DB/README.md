# 数据库设计

### 1.用户表 USER
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|user_id|NUMBER(10,0)|主键|否| | |用户id|
|name|VARCHAR2(128BYTE)| |否| | |真实姓名|
|github_name|VARCHAR2(128BYTE)| |是|空| |用户github账户名|
|update_date|DATE| |是|空| |github用户名修改时间|
|password|VARCHAR(512BYTE)| |是|空| |用户密码|
|status_id|Number(1,0)|外键|否| | |用户状态，用户状态表外键|

### 2.用户状态表 USER_STATUS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|status_id|NUMBER(10,0)|主键|否| | |状态id|
|status_name|VARCHAR2(64BYTE)| |否| | |状态名称|

### 3.教师表 TEACHERS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|teacher_id|NUMBER(10,0)|主键|否| | |教师id，为教师入职时职工号|
|user_id|NUMBER(10,0)|外键|否| | |用户id，用户表外键|
|department_id|VARCHAR2(400 BYTE)|外键|否| | |教师所属部门，部门表外键|

### 4.部门表 DEPARTMENTS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|department_id|NUMBER(10,0)|主键|否| | |教师id，为教师入职时职工号|
|department_name|VARCHAR2(128BYTE)| |否| | |部门名称|

### 5.学生表 STUDENTS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|student_id|NUMBER(12,0)|主键|否| | |学生id，学生学号|
|user_id|NUMBER(10,0)|外键|否| | |用户id，用户表外键|
|major_id|NUMBER(10,0)|外键|否| | |学生所属专业，专业表外键|
|grade_num|number(4,0)| |否| | |学生年级|
|class_num|number(4,0)| |否| | |学生班级|

### 6.专业表 MAJORS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|major_id|NUMBER(10,0)|主键|否| | |专业id|
|major_name|VARCHAR2(128BYTE)| |否| | |专业名称|

### 7.课程表 COURSES
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|course_id|NUMBER(12,0)|主键|否| | |课程id|
|course_name|VARCHAR2(512BYTE)| |否| | |课程名称|

### 8.学期表 TERMS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|term_id|NUMBER(6,0)|主键|否| | |学期id|
|term_name|VARCHAR2(64BYTE)| |否| | |学期名称|
|term_starttime|DATE| |否| | |学期开始时间|
|term_endtime|DATE| |否| | |学期结束时间|

### 9.课程教师关联表 COURSE_TEACHER
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|course_teacher_id|NUMBER(12,0)|主键|否| | |课程教师关联id|
|course_id|NUMBER(12,0)|外键|否| | |课程id|
|teacher_id|NUMBER(10,0)|外键|否| | |教师id|

### 10.课程专业学期关联表  COURSE_MAJOR_TERM
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|course_major_term_id|NUMBER(12,0)|主键|否| | |课程、专业与学期关联编号|
|course_id|NUMBER(12,0)|外键|否| | |课程id，课程表外键|
|major_id|NUMBER(10,0)|外键|否| | |专业id，专业表外键|
|term_id|Number(6,0)|外键|否| | |开课学期id，学期表外键|

### 11.实验表 TESTS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|test_id|NUMBER(6,0)|主键|否| | |实验id|
|test_name|VARCHAR2(256BYTE)|否| | |实验名称|
|teacher_id|NUMBER(10,0)|外键|否| | |发布实验老师id，教师表外键|
|course_id|NUMBER(12,0)|外键|否| | |课程id|
|test_url|VARCHAR(256BYTE)| |否| | |实验说明github地址|

### 12.评分标准表 STANDARDS
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|standard_id|NUMBER(6,0)|主键|否| | |评分标准id|
|test_id|NUMBER(6,0)|外键|否| | |实验id|
|standard_name|VARCHAR2(128BYTE)| |否| | |评分标准名称|
|standard_detail|VARCHAR2(512BYTE)| |否| | |评分标准描述|
|standard_mix|NUMBER(2,0)| |否| | |评分标准占总分比例|

### 13.详细评分表 DETAIL_SCORES
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|detail_score_id|NUMBER(6,0)|主键|否| | |详细评分id|
|test_id|NUMBER(6,0)|外键|否| | |实验id|
|standard_id|NUMBER(6,0)|外键|否| | |评分标准id|
|total_score_id|NUMBER(6,0)|外键|否| | |总评分id，实验总分表外键|
|score|NUMBER| |是|空|0-100|详细评分分数，分数为空为未批改|
|detail_memo|VARCHAR2(400BYTE)| |是|空| |评语|

### 14.实验总评分表 TEST_TOTAL_SCORES
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:---|:---|:---|:---|:---|:---|:---|
|total_score_id|NUMBER(6,0)|主键|否| | |总评分id|
|total_score|NUMBER| |是|空|0-100|总评分分数，分数为空为未批改|
|test_id|NUMBER(6,0)|外键|否| | |实验id|
|student_id|NUMBER(12,0)|外键|否| | |学生id，学生表外键|
|total_memo|VARCHAR2(400BYTE)| |是|空| |总评语|
|update_date|DATE| |是|空| |老师批改时间，为空为未批改|



