## T-SQL编程

1. 变量与常量：常量：字符串类型的常量，DateTime类型常量，用单引号括起来

​                           bit类型：0或1

​                          变量：全局变量：以@@开头，由系统定义和维护，对用户而言只读

​                          print @@error  打印错误号     返回最近一条语句错误号

​                          局部变量：名称以@开头，由用户自定义与维护

​                          作用域：从变量声明开始到批处理或存储过程的结尾；

2. 声明变量：declare @Sno char(7),@Sname varchar(30)
3. 为变量赋值:set或select  @Sno='20150202 '    注意select与set区别

- print @Sno(消息)
- select @Sno （结果）                            
- begin与and语句块

4. 批处理：一组SQL语句作为一个整体发送到服务器进行编译，若编译成功，则会生成一个执行计划

- 选择结构：简单case
- select   Sno,Sname,Sdept,

​   case Sdept

​          when'cs'  then '计算机科学系'

​         when'ps'  then '还有啥系'

​       else 

​       end

搜索case

select Sno,Cno,Grade,

case 

​      when  Grade is null then '无成绩'

​      when Grade >=90 then '优秀'

​      else'成绩不及格'

​      end

from SC



waitfor

waitfor time '00:00'

select * from Student

go



waitfor time'00:00'

backup database Test to disk =''

go



delay'00:00:10'    //延迟10s运行

系统函数：与日期相关的函数

select DatAadd(add,82,GetDate())     //求8天以后的日期

select DateDiff(dd,getdate,'2018-05-19')   //求间隔日期

类型转换：cast

标量函数

cerate function func_Get(@Sno char(7))

return int 

as

begin 

