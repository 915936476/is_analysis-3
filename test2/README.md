# 实验二 图书管理系统用例建模

## 用例图
### PlantUML源码
```flow js

```
### UML截图
!(用例截图)[]

## 用例表

### 1.借出图书用例表
<table>
<caption>借出图书用例规范</caption>
<tr>
<td>用例名称</td><td>借出图书</td>
</tr>
<tr>
<td>参与者</td><td>图书管理员（主要参与者）、读者（次要参与者）</td>
</tr>
<tr>
<td>前置条件</td><td>图书管理员已被授权并已登录系统</td>
</tr>
<tr>
<td>后置条件</td><td>存储读者借书纪录，更新借出书本库存数量，所借图书状态更新为借出</td>
</tr>
<tr>
<td colspan="2">主事件流</td>
</tr>
<tr>
<td>参与者动作</td>
<td>系统行为</td>
</tr>
</table>