#### 日期选择组件
----
[GitHub地址](https://github.com/lanxiujuan/date)  <font  color=orange>demo请到GitHub下载</font>
----
##### 功能
1.支持开始时间及结束时间限制<br/>
2.支持默认值设置<br/>
3.支持禁用选择<br/>
----
##### 配置参数
属性|类型|描述|默认
--|:--:|--:|--:
timeType|String|'day' 选择日期  month 选择月份  year 选择年份 | day
disabled|Boolean| true 禁止 false 可选| false
placeholder|String|提示语 |请选择
childValue|String|组件值|无
minSelect|String|最小可选日期|'1900/01/01' 日期格式必须是YY/MM/DD 不支持YY-MM-DD格式
maxSelect|String|最大可选日期|'2050/12/31' 日期格式必须是YY/MM/DD 不支持YY-MM-DD格式
----
<!-- 属性|类型|描述|默认
--|:--:|--:|--:
value|String|组件值|‘’
iconshow|Boolean|是否显示图标：true 显示图标 false 不显|true
disabled|Boolean| true 禁止 false 可选| false
placeholder|String|提示语 |请选择时间
start|String|最小可选时间|'00:00'
end|String|最大可选时间|'23:59'
type|String|回显类型 'HH:MM'|'HH:MM'
isFixedInterval|String|固定时间间隔单位为分钟|‘’
fixedTimeOptions|固定时间选项 传入选项数组|[] -->
