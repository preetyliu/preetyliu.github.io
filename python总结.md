
# 一、快捷键

>1. ctr+b           执行
>2. ctr+/            单行注释
>3. ctr+c            拷贝
>4. ctr+v            粘贴
>5. ctr+z            撤销
>6. ctr+shift+z  反撤销
>7. ctr+a           全选
>8. ctr+x           剪切
>
#二、注释

注释：注释是穿插在代码中的说明文字，对于代码实现功能无任何作用，注释也不会参与执行。

##1、单行注释

* 在注释的内容前加#

##2、多行注释

* a、 在每一行前面加 #    
* b、使用'''和"""括起来
        '''
        这是多行注释1
        这是多行注释2
        '''
        """
        这是多行注释1
        这是多行注释2
        """

#三、标识符

标识符：在开发中使用的所有名字都是标识符（包括变量名、函数名、类名、对象名等）
* 标识符的硬性要求：
    >1. 由字母、数字、下划线（_）组成。 
    >2. 数字不能开头。 
    >3. 不能是保留字（关键字）。
        a2_=1
        abc=1
        ac2=2
        a+b=3 # 报语法错误
        2s=3  # 报语法错误
        for=2 # 报语法错误
* 规范：
    >1. 见名知意。
    >2. PEP 8规范（变量名）:全部小写，如果名字是由多个单词组成，单词之间以_分开。

        cat_name=1
* 驼峰式命名：如果是由多个单词组成，第一个单词首字母小写。后面的每个单词第一个字母大写。
        catName=1
* python中大小写敏感：Key和key是不一样的

#四、关键字（保留字）

* 在python中有自己独特功能的一些单词，程序员在使用标识符的时候不能使用关键字。
       import keyword  #导入内置keyword模块
       print(keyword.kwlist)
       ['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for','from', 'global', 'if', 'import', 'in', 'is', 'lambda','nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

#五、行与缩进

* 在python中，语法对缩进有严格的规范。同一级的代码要写在一个缩进下（缩进->空格和制表符tab）。
* 行：可以通过换行将代码分块。要求函数定义和其他代码之间要有一个换行。类的声明和其他代码之间要有两个换行。（不按要求来不会报错）
         abc=1  #abc前多了一个空格，报IndentationError（缩进错误）
         if 10>20:
         abc=1
* 注意:语法相关的所有的符号，都必须是英文输入法下的符号

#六、多行语句

* 一行代码很长，需要多行显示。
* python中，如果一行只有一个语句，那么语句后面可以不写分号。（写了也不会报错）
* 如果一行中有多条语句，那么语句中需要用（;）分开。
        aaa=1  ; abc=2
        bbb=2
        ccc=3
        sum1=aaa+bbb+ccc
* 将一行代码写成多行
        sum2=aaa+\
        bbb+\
        ccc
* 列表、字典、元祖、集合的元素在多行显示的时候，可以不用\连接
        dict1={
        'name':'yuting',
        'age':18,
        'gender':'女'
        }

#七、数据类型

* python中标准的数据类型有6种：Number(数字)、Str(字符串)、List（列表）、Tuples（元祖）、Setes（集合）、Dict（字典）
* 可以通过type（）函数查看值得类型，例如：
        print(type(10))
        print(type(12.5))
        print(type(True))
        print(type(10+2j))

##1、数字

python中的数字分为：整型（整数）、浮点型(小数)、布尔、复数（实部+虚部）
   >a、整型（int）:python3中只有长整型int,python2中有long。
    	例如：23、100、-25
   >b、浮点型(float):python3中只有float类型。
    	例如：12.9、1.0、0.0、-10.5、2e2
   >c、布尔(bool):表示真假（是否）的值，值只有True（真）和False（假）两个值，True是1，False是0。
   >d、复数(complex):由实部和虚部组成。
    	例如：10+1j，11.5+2j

##2、字符串

* 由单引号或者双引号括起来的数据就是字符串（推荐使用单引号）（python中没有字符类型，所说的字符就是用引号括起来的长度是1的字符串）
        'hello world'    # 字符串中单独的一个符号就是一个字符串
        '123'
        '!2dfs'
        ' '  #这些都是字符串，空格字符是有意义的字符串
        ''   #空串，长度是0
* python需要转义字符来表示一些特殊的字符串：包括一些有特殊意义和特殊功能的字符串
        '\''
        print('\'')  #'
        print('\\')  #\
        str1='\t床前明月光,\n疑是地上霜'  # \n -->换行  \t -->制表符tab
        print(str1)
* 在字符串前面加r/R,阻止转义字符转义
        print('a\\nb')
        print(r'a\nb')
        print(R'a\nb')

#八、进制转换

* 进制：十进制、二进制、八进制、十六进制（要求：会认识和转换）
* 其他进制转换成十进制：相乘求和
* 十进制转换成其他进制：整除取余法
        100(2)->1100100  100(8)->144  100(16)->64
* 二进制和八进制（每三位二进制转换成一位八进制）、十六进制（每四位二进制转换成以为16进制）的转换。
        (2)1100100->(8)144   001 100 100->1 4 4
        (8)571->(2)101111001  (2)a1b->(2)101000011011

##1、十进制

* 基数：0、1、2、3、4、5、6、7、8、9
* 逢十进一
        123:100+20+3  1*10^2+2*10^1+3*10^0
        12 #直接写数字，就是十进制
        print(12)
        print(0o654)

##2、二进制

* 计算机存储数据的时候，存的都是二进制数
* 基数：0、1
* 逢二进一（10-->2）
* 二进制转十进制（相乘求和）：每一位上的数乘以当前位上的2的幂次数（从低位到高位，幂次数从0开始一次加1）
        1101：1*2^0+0*2^1+1*2^2+1*2^3=13
        0b1101 #在二进制数前加“0b”
        print(0b1101)
        bin(10)  #将括号中的数字转换成二进制数，返回的是字符串形式的数据
        print(bin(10))
        print(bin(0o64))
        print(bin(0xa3))  

##3、八进制

* 基数：0 1 2 3 4 5 6 7
        26:6*8^0+2*8^1=22
        0o10  #在八进制数前加“0o”
        print(0o10)
        oct(10) #将括号中的数据转换成8进制
        print(oct(10))
        print(oct(0b11100110))
        print(oct(0xab3))
        
##4、十六进制

* 基数：0 1 2 3 4 5 6 7 8 9 a(10) b(11) c(12) d(13) e(14) f(15) (A B C D E F)
        1f: 15*16^0+1*16^1=31
        ab: 11*16^0+10*16^1=171
        0xa1 #在十六进制数前加"0x"
        print(0xa1)
        hex(100) #将括号里面的数据转换成十六进制
        print(hex(100))
        print(hex(0o654))
        
#九、变量

* 变量是用来存储数据的。
* 在python中声明变量不用指定类型，一个变量可以存储任何类型的数据。

##1.声明变量

* 变量名=初值
    >a、变量名：a、标识符  b、PEP 8的命名方式  c、见名知意
    >b、=：赋值符号，要求赋值符号的左边必须是变量，右边是有值的表达式;
        a=10+20
        10=20  #语法错误（SyntaxError）
    >c、初值：python中声明变量必须赋值
        name='liuzhilong'  #声明一个变量，并且赋了初值为'liuzhilong'
        a=b=c=10  #同时声明三个变量a b c ，他们的初值都是10
        a1,b1,c1=10,12.4,'aaa'  #同时声明了三个变量a1,b1,c1;他们分别对应的初值分别是10,12.4，'aaa'
        name=100  #一个变量可以存储多种类型的值（python是动态语言）

#十、运算符

* python中的运算符：算数运算符、比较运算符、赋值运算符、逻辑运算符

##1、算数运算符

* 算数运算符： +(加)  —(减)  *(乘)  /(除)  %(取余)  //(整除)  **(幂运算)
* +-*/%和数学里面的运算一模一样
        print(12+10.0)    #22.0
        print(12+10)   #22
        print(50-33)   #17
        print(10*3)   #30
        print(7/2)   #3.5
        print(10%3)   #1
* //(整除)：可以对浮点数做整除的操作，只是结果只保留整数的部分(直接去掉小数部分)
        print(10.0//3)   #3.0
        print(16/10)   #1.6
        print(16//10.0)  #1.0
* **（幂运算）
        print(2**3)   #计算2的3次方
* 对任意数取各个位数的值
        n=7896
        print('百位数：',n%1000//100)
        print('百位数：',n//100%10)
        print('十位数：',n%100//10)
        print('十位数：',n//10%10)
        print('个位数：',n%10)
* 通过import关键字可以导入python中内置的模块。
* math是python内置的一个提供数学运算的模块。
        import math
        1、fabs(n):求n的绝对值
        num=math.fabs(-20)
        print(num)   # 20.0
        2、pi:圆周率
        print(math.pi)  # 3.141592653589793
        3、log：返回x的自然对数，默认以e为基数。
        print(math.log(30))  # 3.4011973816621555
        4、log10:返回x的以10为底的对数
        print(math,log10(60))  #1.7781512503836436
        5、log2:返回x的基2对数
        print(math.log2(8))  # 3.0
        6、tan:返回x(x为弧度)的正切值
        print(math.tan(10))   # 0.6483608274590866
        7、floor:取小于等于x的最大的整数值，如果x是一个整数，则返回自身
        print(math.floor(34.6))  # 34
        8、gcd:返回x和y的最大公约数
        print(math.gcd(24,80))  # 8
        9、trunc:返回x的整数部分
        print(math.trunc(31.34))  # 31
        10、sqrt:求x的平方根
        print(math.sqrt(16))  # 4.0

##2.比较运算符：>、<、>=、<=、==、!=

* 所有比较运算符的结果都是布尔值
* x>y:比较x是否大于y.如果是,结果就是True,否则就是False.
        print(10>5)     # True
        print(6<19)     # False
* 比较字符串大小的时候，不是比较两个字符串的长度；而是从两个字符串的第一个字符开始比较。如果第一个字符串的第一个字符大于第二个字符串的第一个字符，结果就是True，否则就是False。如果两个字符串的第一个字符相等采取比较第二个字符，依次类推。
        print('abcdef'>'bcd')  # False 
        print('abc'>'abcd')    # False
* x>=y:比较x是否大于或者等于y.x大于y或者等于y，结果都是True;否则就是False.
        print(10>=5)          # True
        print(10>=10)         # True
        print('abc'>='abc')   # True
* x<=y:比较x是否小于或者等于y.x小于y或者等于y，结果都是True;否则就是False.
        print(10<=5)    # False
        print(10<=10)   # True
* x==y:比较x是否等于y.如果是，结果就是True,否则就是False.
        print(6==3)  # False
        print(5==5)  # True
        a=8
        b=3
        print(a==8)  # True
        print(a==3)  # False
        print(a==b)  # False
* x!=y:比较x是否不等于y.如果是，结果就是True,否则就是False.
        print(a!=8)   # False
        print(a!=b)   # True

##3、赋值运算符：=、+=、-=、*=、/=、%=、//=、**=

* 所有的赋值运算符左边都必须是变量，右边是表达式。
* 表达式(本身有值的语句)： 10，a，10+a，10>20,10+20/4*3等
        a=10
        b=a  # 如果a的值是基本数据类型（数字、字符串），直接将a里面存的值赋给b;如果值是对象，传递的是变量中存储的地址。
        a+10=10  # 语法错误（SyntaxError）
    >a、=
        num=a+30
    >b、+=、-=、*=、//=、**=
        a+10
        print(a)   # a=10
        a+=10      # a=a+10
        print(a)   # a=20
        a-=10      # a=a-10
        print(a)   # a=10
        a*=2       # a=a*2
        print(a)   # a=20
        a/=4       # a=a/4
        print(a)   # a=5.0
        a//=2      #a=a//2
        print(a)   # a=2.0
        a**=5      # a=a**5
        print(a)   # a=32.0
        a%=10      # a=a%10
        print(a)   # a=2.0

##4、逻辑运算符：and（与）,or（或）,not（非）

* 逻辑运算符中表达的值都是布尔值
* 给变量赋值的时候，后面赋的值会覆盖前面的。
* 运算表达式中，加（）可以改变运算的顺序
    >a、表达式1 and 表达式2：两个表达式的值都是True，结果才是True;否则是False.
        print(True and True)     # True
        print(False and True)    # False
        print(True and False)    # False
        print(False and False)   # False
        例：
        age=40
        face=90
        进网吧要求:年龄大于18并且小于50，颜值还不能低于80.
        result=age>18 and age<50 and face>90
        print(result)           # True
    >b、表达式1 or 表达式2：两个表达式的值都为False时，结果为False，否则都是True。
        print(True or True)     # True
        print(False or True)    # True
        print(True or False)    # True
        print(False or False)   # False
        例：
        grade=8.0
        score=80
        奖学金要求：绩点大于8.0，或者操评大于90
        result=grade>8.0 or score>90
        print(result)           # False
        奖学金要求：1、绩点大于9.7  2、绩点8.5-9.7，操评分大于85
        result=grade>9.7 or (8.5<=grade<=9.7 and score>85)
        print(result)           # False
    >c、not 表达式：如果表达式的值为True，结果为False;表达式的值为False，结果为True。
        print(not True)                             # False
        print(not False)                            # True
        成绩及格要求：绩点不小于6。
        grade=8.0
        result=not grade<6
        print(result)                                  # True
        进入游乐场的年龄要求：不大于12岁并且不小于2岁
        age=10
        result=(not age>12) and (not age<2)
        print(result)                                  #True

#十一、运算优先级

* 赋值运算符<逻辑运算符<比较运算符<加、减<乘、除、取余、整除、幂运算<+（正号）、-（负号）
* 可以加括号改变运算的运算顺序（遇到括号先算括号里的）

#十二、字符串

* 字符串：有单引号或者双引号括起来的文本
        'acds'
        '234'
        '---=334ff'
        '我是@ss'

##1、Python中的字符串都是Unicode字符串

* Unicode编码：是一种对字符的编码方式（将字符编码成对应的数字，方便计算机存储）
* Unicode编码又叫万国码，支持目前几乎所有的语言文字编码
* Unicode包含ASCII码
* 字符串比较大小的时候，实质就是比较字符的Unicode编码的大小
* 数据存储到计算机中是以2进制的形式存的
        将Unicode码转换成字符
        print(chr(0x4E00))   # 一
        将字符转换成Unicode码（结果是十进制的形式）
        print(ord('刘'))     #21016
        print(chr(21016))    #刘

##2、字符串的长度

* 字符串的长度：指字符串中字符的个数（空格也算）
        'abc'  #长度为3
        ' yu'  #长度为3
* len（字符串）：获取字符串的长度
        str1='你好，Python'
        length=len（str1）
        print(length)     #长度为9
        print('str')      #长度为3

##3、获取字符/子串

>a、获取某一个字符
* 格式：字符串变量[下标]
* 下标：从0开始的数字，代表的是某一个字符在字符串中的偏移量（位置）(范围：0~字符串长度-1)
* 注意：下标不要越界，否则会报错（IndexError: string index out of range）
        str1='Hello,Python!'
        print(str1[0])    # H 获取第0个字符 
        print(str1[5])    # , 获取第5个字符 
        print(str1[20])   # 报错（IndexError: string index out of range）
* 下标也可以是负数（负数也不可以越界）
        print(str1[-1])   # ！ 获取倒数第一个字符（最后一个） 
        print(str1[-2])   # o 获取倒数第二个字符  
        print(str1[len(str1)-1])   # n 获取最后一个字符
>b、获取字符串中某一部分的字母（获取子串）
* 格式：字符串变量[开始下标:结束下标] -->获取从开始下标到结束下标前的所有字符
* 注意：开始下标对应的字符可以取到，结束下标对应的字符取不到
        str1='Hello,Python!'
        print(str1[1:4])   # ell  获取从下标是1对应的字符开始，到下标是（4-1）对应的所有字符 
        print(str1[6:10])  # Pyth  获取从下标是6对应的字符开始，到下标是9对应的所有字符
* 开始下标不写，默认就是0
        print(str1[:5])    # Hello 获取从开始到下标是4为止的所有的字符
* 结束下标不写，就会取到最后一个字符
        print(str1[-4:])   # hon！
        print(str1[:])     # Hello,Python! 取所有的字符
* 如果结束下标在开始下标的前面，就会取不到字符（不能倒着取）
        print(str1[5:1])  # 取不到字符

##4、字符串的运算符

* 字符串的运算符：+ , *  , in , not in
  >a、+:字符串中的+操作，就是字符串连接
        str2='aaa'+'bcd'
        print(str2)  # aaabcd
        str1='hello'
        str2='world'
        str3=str1+' '+str2
        print(str3)   # hello world
        str2+='!'
        print(str2)  # world!
  >b、 *  : 字符串中的 * 操作，就是字符串重复多少次
        str1='abc'*3
        print(str1)  #abcabcabc
  >c、字符串1 in 字符串2：判断字符串2中是否包含字符串1
        str1='Hello'
        print('he' in str1)  # False  判断he是否在str1中（判断str1中是否包含'he'）
        print('He' in str1)  # True
  >d、字符串1 not in 字符串2：判断字符串1是否不在字符串2中
        print('He' not in str1)  # False

#十三、print函数

* print()函数可以打印括号中的任何内容
* 调用print函数打印完后会换行
        print(10)   # 10
        str1='aaa'
        print(str1)   # aaa
* 同时打印多个内容（多个内容间用逗号隔开）;打印的时候，多个内容之间是用一个空格隔开。
        print('aa',100,str1)  # aa 100 aaa
  >1、格式化输出
*  print('%s %d'% (变量1，变量2))：输出字符串的时候，在字符串中使用字符串格式符表示变化的内容。在%后面的括号里面，一次使用表达式给前面的字符串格式符赋值。
* %s:字符串   %d:整数   %f:浮点数   %c:字符   %o:八进制数
         name='张三'
         age=18
         我是xxx，今年xx岁
         print('我是%s,今年%d岁'%(name,age))  # 我是张三，今年18岁
     a、%f：浮点数占位符
         print('余额：%f万元'%(10.25))  # 余额：10.250000万元
     b、%.2f:保留小数点后两位  %.3f:保留小数点后三位
         print('余额：%.2f万元'%(10.25)) # 余额：10.25万元
     c、%c：字符占位符（python中的字符，指得是长度为1的字符串）
         print('%c'%('a'))     # a
         print('%c'%('abc'))   # 报错
         print('%c'%(97))      # a（a对应的Unicode码是97）
         print('%c'%(0x4e00))  # 一（一对应的Unicode码是0x4e00）
     d、%o：八进制数占位符
         print('%o'%(10))      # 12
     e、%x/%X:十六进制数占位符（x的大小写决定打印出的十六进制数是大写还是小写）
         print('%x,%X'%(15,15))  # f  F
  >2.设置print函数的sep参数，可以改变print函数在同时打印多个内容时的分隔符（默认是空格）
* 注意：加号两边只能都是数字或者都是字符串，不能一个数字一个字符串
         name='张三'
         age=18
         我是xxx，今年xx岁
         print('我是',name,',今年',age,'岁')  # 我是 张三 ,今年 18 岁（打印多个数据时，数据之间默认以空格隔开）
         print('我是',name,',今年',age,'岁',sep='')  # 我是张三，今年18岁(打印多个数据时，数据之间没有间隙)
         print('aa',100,str1,sep=',')  # aa,100,aaa（打印多个数据时，数据之间以','隔开）
  >3.设置print的结束字符串，默认是'\n'（换行）。
* 注意：设置sep和end参数，只是当次有效
         print('hello',end=' ')
         print('world')  # hello world(设置以空格结束，而不是换行)
         
         print('hello',end=' ')
         print('world')      
         print('aaa')    # hello world
                           aaa

#十四、字符串的内置函数

* 单词的区分，和英语区分单词的方式是一样的（以空格）
  >1、capitalize():将字符串中的第一个字符转化为大写（不会改变原来的字符串，而是返回一个新的字符串）
        str1='hello student'
        print(str1,str1.capitalize())  # python student Python student 
  >2、title():将字符串中每个单词的首字母变成大写（不会改变原来的字符串，而是返回一个新的字符串）
        newstr=str1.title()
        print(str1,newstr) # python student Python Student
  >3、center(width,fillchar):将字符串变成指定的长度，并且原字符串内容居中，剩余的位置使用指定的字符fillchar填充。
        str1='abc'
        newstr=str1.center(5,'*')
        print(str1,newstr)   # abc *abc*
  >4、upper()：全部大写
        name='liuzhilong'
        print(name.upper())  #LIUZHILONG
  >5、lower():全部小写
        name1='LIUZHILONG'
        print(name1.lower())  # liuzhilong
  >6、swapcase():大小写互换
        name2='LiuZhilong'
        print(name2.swapcase()) # lIUzHILONG
  >7、ljust(width，fillchar):获取固定长度，右边不够用指定的fillchar填充
        name='liuzhilong'
        print(name.ljust(16,'*'))  # liuzhilong******
  >8、find('t'):搜索指定字符串中特定字符的个数
        zifu='adfggtg'
        print(zifu.find('g'))  # 3
  >9、strip（）：去掉字符串两边的空白字符，但是不会去除中间的
        name='\tliu'+'zhilong  \n'
        name3=name.strip()
        print(name3)
  >10、lstrip（）：去掉字符串左边的空白字符
        name='\tliu'+'zhilong  \n'
        name1=name.lstrip()
        print(name1)
  >11、rstrip（）：去掉字符串右边的空白字符
        name='\tliu'+'zhilong  \n'
        name2=name.rstrip()
        print(name2)

#十五、条件语句

* if  elif  else都是关键字，需要能读和写（背）
* 基本格式：
        if 条件语句1：
          执行语句块1
        elif 条件语句2：
          执行语句块2
        else：
          执行语句块3
* 执行过程：
  >a.先判断条件语句1是否为True，如果为True就执行冒号后边的执行语句块1，整个条件结构就执行完了;如果是False，就去判断条件语句2是否为True。
  >b.如果是True就执行执行语句块2，再执行其他语句;如果是False,就直接执行语句块3，再执行其他语句。

* 注意：冒号后边语句块和冒号所在得语句要保持一个缩进。
##1.if
* 判断条件语句的值是否为True，如果为True，就只执行执行语句块。否则就直接执行if语句后面的其他语句。
        if 条件语句：
        	执行语句块
        
        age=20
        要求判断年龄是否大于18，如果大于18就输出'成年人'
        if age>18:
        	print('成年人')
        
        练习：判断一个数是否是偶数，如果是就打印'xxx是偶数'
        n=18
        if n%2==0:
        	print('%d是偶数'%(n))

##2.if-else

* 判断条件语句是否为True，如果为True，就执行语句块1;否则就执行语句块2.
        if 条件语句：
        	执行语句块1
        else：
        	执行语句块2
        n=17
        if n%2==0:
        	print('%d是偶数'%(n))
        else:
        	print('%d是奇数'%(n))
        练习：输入一个数，如果这个数大于10，就输出他的2倍值。否  则输出这个数的2次幂。
        input():从控制台获取键盘输入的一个字符串，以回车结束。
        
        inputvalue=input('请输入一个数：')
        print(inputvalue)
        n=int(inputvalue)
        比较运算符和+以及*，在运算的时候，两边可以都是字符串，也可以都是数字，但是不可以一样一个。
        if n>10:
        num=n*2
        	print(num)
        else:
        num=n**2
        	print(num)

##3.if-elif-elif-else

* 总结:
  >a.如果要求中需要多个判断，可以使用多个elif的if语句。
  >b.一个if/elif/else语句中可以嵌套其他的if语句。
      （1）给一个成绩，判断成绩是优秀(90-100)、良好(80-89)、        中等(60-79)、不及格(60以下)
      方法一：
      grade=96
      if grade>=90:
          if grade>100:
              print('成绩有误')
          else:
              print('优秀')
      elif grade>=80:
          print('良好')
      elif grade>=60:
        	print('中等')
      elif grade>=0:
        	print('不及格')
      else:
        	print('成绩有误')
      方法二：
      grade=67
      if 100>=grade>=90:
      	print('优秀')
      elif 90>grade>=80:
      	print('良好')
      elif 80>grade>=60:
      	print('中等')
      elif 60>grade>=0:
      	print('不及格')
      else:
      	print('成绩有误')
      	
      （2）给个年龄，判断年龄处于：婴儿（0-1岁）、儿童（2-4         岁）、少年（5-12岁）、青年（13-18岁）、成年（19-40）、       中年（41-60）、老年（60以上）
      age=1
      if age<2:
      	if age<=0:
      		print('年龄输入错误')
      	else:
      		print('婴儿')
      elif age<5:
      	print('儿童')
      elif age<13:
      	print('少年')
      elif age<19:
      	print('青年')
      elif age<41:
      	print('成年')
      elif age<61:
      	print('中年')
      else:
      	print('老年')
* 说明：Python中没有switch语法。
* pass：占位，防止因为没有写块结构而出现语法错误。
      if n==10:
          pass

#十六、转换函数

##1.int()

* int():将其他的数据转换成int类型的数据
      num=12.56
      print(int(num))    # 12 将浮点数转换成整数（直接去掉小数部分）
      bool1=True
      print(int(bool1))  # 1 将布尔值转换成整数，True->1  False->0
      str1='123'
      print(int(str1))   # 123 只有纯数字字符串或者纯数字字符串前有正负号的字符串才能转换成相应的整数。

##2.flot()

* flot():将其他数据转换成浮点型

##3.bool()

* bool()：将其他的数据转换成布尔值
* 数字转换成布尔，非0是True，0是False。
      print(bool(12))     # True
      print(bool(-12.3))  # True
      print(bool(0))      # False
* 字符串转换成布尔，除了空串是False，其他的都是True。
      print(bool('abc'))  # True
      print(bool(''))     # False
* 注意：在if或者while循环后的条件语句，可以不是结果为True/False的表达式，也可以是值是其他类型的表达式.判断的是时候就看这个值转换成bool后的结果是True还是False。
      if 10:
      	print('aaa')   # aaa （10转换成bool后是True) 
      if 0:
      	print('aaa')   #  （0转换成bool后是False）
      练习：判断一个字符串是否是空串，如果不是就直接打印这个字符       串，否则打印“空串”
      方法1：
      str1=''
      if str1:
      	print(str1)
      else:
      	print('空串')
      方法2：
      str1='abc'
      if str1!='':
      	print(str1)
      else:
      	print('空串')

##4.str()

* str()：将其他的数据转换成字符串。所有的数据类型都可以转换成字符串。

#十七、循环

* python中循环：for循环、while循环（一个操作需要重复执行多次，这个时候就要考虑使用循环）

##1、for循环

* python中的for循环只有for-in循环：
      格式：
      for 变量名 in 列表：
      	循环体
* 执行过程：使用变量去依次获取列表中的数据直到获取完为止;没获取一个数据，执行一次循环体。
* 循环次数：由列表中的数据的个数决定。
      去获取字符串中的每一个字符
      str1='abcdef'
      for char in str1:
      	print(char)
      
      去统计字符串中'a'出现的次数
      str1='avaadafvaavafaaa'
      n=0
      for char in str1:
      	if char=='a':
      		n=n+1	    
      print(n)
* range（）函数：可以生成一个数值范围
      打印1-100
      for n in range(1,101):
      	print(n)
      用法1：range(n),生成0~n-1的值
      for x in range(9):
      	print(x)
      
      用法2：range(m,n),生成m~n-1的数
      for n in range(5,9):
      	print(n)
      打印0-100之间所有的偶数
      for x in range(101):
      	if x%2==0:
      		print(x)
      
      用法3：range(m,n,step):从m开始每step取一个数，取到n前       一个数为止。
      for x in range(1,8,2):
      	print(x)   # 1,3,5,7 
      
      不通过字符串相乘，打印10次“=”,并且打印在同一行。
      for _ in range(10):
      	print('=',end=' ')
      求1+2+3...+100
      n=0
      for x in range(1,101):
      	n=n+x
      print(n)
* 注意：如果循环中的变量取到的值没有意义，循环只是单纯的控制次数，这个时候for后面的变量名一般用“_”代替。

##2.while循环

     格式：
     while 条件语句：
     	循环体
* 执行过程：判断条件语句结果是否为True，如果为True就执行一次循环体。执行完循环体后再判断条件语句是否为True，如果为True继续执行循环体。重复这个过程，直到条件语句结果为False
* for循环可以实现的操作，while循环都可以
      打印1-100
      方法1：
      x=0
      while x<100:
      	x+=1
      	print(x) 
      方法2：
      x=1
      while x<=100:
      	print(x)
      	x+=1
      
      计算1+2+3+...+100
      x=0
      n=0
      while n<100:
      	n+=1
      	x+=n
      	print(x)
      
      求1-100中所有偶数的和
      方法1：
      n=0
      x=0
      while n<=100:
      	if n%2==0:
      		x=x+n
      		n=n+1
      	print(x)
      方法2：
      n=0
      x=0
      while n<100:
      	n+=2
      	x=x+n
      print(x)


#十七、break和continue

##1、break

* break是一个让循环提前结束的关键字
* 如果在for循环或者while循环中遇到了break，那么循环就在break的位置直接结束。结束后程序执行循环后边的代码。
      练习:找到1000~9999中第一个能够被13整除的数，打印出来
      for x in range(1000,10000):
      	if x%13==0:
      		print(x)
      		break    
       	
      for x in range(1,100):
      	if x==50:
      		break
      		print(x)     # 1 2 3 ...  49
* 用while循环实现：不断的让用户去输入数字，直到用户输入的数字是0为止。最后在打印之前输入的数的和。
* input()函数：程序执行到input()函数的时候，程序就会停下来，等待用户从键盘输入并且以回车结束，然后才会往下执行。
* 注意：break只能写在循环中
        sum1=0
        while True:
        num=int(input(">>>"))   # 获取键盘输入的内容，并且转换成int类型
        	sum1+=num   # 将当次输入的数字加起来
        	if num==0:   #  判断输入的数字是否是0，如果是就让循环结束
        		break   
        	print(num)
        print(sum1)
* for循环的特点：次数确定，可以在序列中取数据
* while循环：循环次数不确定的（while True + break）
* randint(m,n):产生一个m到n的随机整数
* 产生随机数：random模块是python内置用来产生随机数的模块，里面提供了很多产生随机数的函数。
        猜数字：随机生成一个整数。用户输入数字。如果用户输入的数字大于这个随机数就提示：“大了”;如果用户输入的数小于随机数就提示：“小了”。直到用户输入的数和这个随机数大小一样游戏结束。
        import random
        num=random.randint(0,100)   # 产生一个0到100的随机数
        n=0
        while True:
        num1=int(input("请输入你猜的数字："))
        n=n+1
        if num1>num:
        	print('大了')
        elif num1<num:
        	print('小了')
        else:
        	print('恭喜你，猜对了！')		
        	print('一共猜了：%d次'%(n),end='  ')
        	if n<=5:
        		print('你太棒了，只猜了%d次就猜对了'%(n))
        	else:
        		print('下次加油！')
        	break

##2、continue

* continue:结束当次循环，进入下次循环
        for x in range(1,10):
        	print('=')
        	continue   # 遇到continue就不再执行循环体后面的内容，直接进入下一次循环的判断
        	print(x)
        
        求1~100中所有奇数的和
        sum=0
        for x in range(1,100):
        	if x%2==0:
        		continue
        	sum=sum+x
        print(sum)
        
        打印100~999中十位数上不是3的所有数：
        for x in range(100,1000):
        	if x//10%10==3:
        		continue
        	print(x)   
        
        统计输入的数字中，偶数的个数。如果输入0，就结束。（必须使用continue）
        flag=True
        n=0
        while True:
        	num=int(input('请输入一个数：'))  # 输入数据
        	if num%2==1:  # 判断是否是奇数
        		continue
        	if num==0:
        		flag=False
        	n=n+1
        print(n)

#十八、else

* python中循环语句后面可以加else语句。这个else语句会在循环结束后执行。
       for 变量 in 序列：
       	循环体
       else：
       	循环结束后会执行的语句块
       
       1*2*3...*10
       sum1=1
       for x in range(1,11):
       	sum1*=x
       else:
       	print(sum1)
* 注意：如果再循环语句中使用break，那么else语句不会执行。（continue不存在这个问题）
        1*2*3...*10，当乘积大于10000就不在执行
        sum1=1
        for x in range(1,11):
        	if sum1*x>10000:    
        		break
        	sum1*=x
        print(sum1)
        else:
        	print(sum1)  # 如果在循环中执行了break，那么else中的语句不会执行

#十九、多重循环

* 在循环体里面可以有其他的循环语句，结构为：
       for 变量 in 序列：
           for 变量1 in 序列2：
       		循环体2
       	其它的循环语句
       
       for 变量 in 序列：
       	其他的循环语句1
       	while 条件语句：
       		循环体2
       	其他的循环语句2
       
       while 条件语句1：
       	while 条件语句2：
       		循环体2
       	其他的循环语句2
* 例如：
        如果n=5 打印
        1
        12
        123
        1234
        12345
        
        n=5
        for x in range(1,n+1):   # 控制行数
        	for b in range(1,x+1):  # 控制当前行的数值
        		print(b,end='')
        	print()   # 一行结束换行
        
        *****
        ****
        ***
        **
        *
        n=5
        for x in range(1,n+1):
        	for b in range(x,n+1):
        		print('*',end='')
        	print()
        
        n=10
        for x in range(1,n+1):
        	for b in range(x,n+1):
        		print('*',end='')
        	print()


#二十、列表

* python 中的数据类型：数字（不可变）、字符串（不可变）、列表（可变）、元祖（不可变）、字典（可变）、集合（可变）
* 容器类型的数据：列表、元祖、字典、集合（序列）
* 列表（数组）：一个列表中可以存储多个不同类型的数据
* 列表存储数据的方式：将多个数据放到一个[]中，多个数据之间用逗号隔开。
* 列表特点：列表是可变的（值得是里面的元素的个数和值可变）
* []是列表的标志
* 列表是有序的（可以通过下标去获取元素）

##1、声明一个列表

    声明了一个列表list1,有5个元素，分别是：1,2,3,10.2，'abc'。
    list1=[1, 2, 3, 10.2, 'abc']
    print(list1)
    声明一个空的列表：
    list[]

##2、获取列表元素

>a、获取某单个元素（通过元素对应的下标）
* 下标的范围：0~元素的个数-1；
* 注意：列表通过下标获取列表元素的时候，下表不能越界。
        list1=[1, 2, 3, 10.2, 'abc']
        print(list1[0])   # 1 获取下标是0的元素
        print(list1[3])   # 10.2 获取下标是10.2的元素
        print(list1[-1])  # abc 获取最后一个元素
        # print(list1[5]) # IndexError: list index out of range
>b.获取列表中的部分元素（切片）
* 列表名[开始下标：结束下标]:获取到的是从开始下标到结束下标前的所有的元素组成的列表。
        list3=[2, 1, 4, 56, 'cv', 3, 2.2]
        print(list3[1:4])  # [1, 4, 56] 获取下标为1开始到下标为3的所有的元素
        print(list3[:3])   # [2,1,4] 获取从第一个元素开始到下标为2的所有的元素
        print(list3[3:])   # [56, 'cv', 3, 2.2] 获取从第3个下标开始到最后的所有的元素
        print(list3[:])    # [2, 1, 4, 56, 'cv', 3, 2.2] 获取列表从开始到结束的所有元素
* 列表名[开始下标：结束下标：步长]
        print(list3[:4:2]) # [2, 4] 从第一个元素开始到下标为3，每两个元素取一个
        获取列表中所有下标是偶数的元素
        print(list3[::2])  # [2, 4, 'cv', 2.2]
>c.遍历列表
        list4=[1, 22, 31, 2, 42, 24, 12]
        打印列表中所有的偶数
        for item in list4:
        	if item%2==0:
        		print(item)
        计算列表中所有元素的和：
        方法一：
        s=0
        for item in list4:
        	s+=item
        print(s)
        方法二：
        n=0
        s=0
        while n<len(list4):
        	s=s+list4[n]
        	n+=1
        print(s)
        获取下标为奇数的元素
        方法一：
        n=1
        for item in list4:
        	while n%2!=0:
        		print(item)
        		break
        	n+=1
        方法二：
        n=0
        while n<len(list4):
        	if n%2!=0:
        		print(list4[n])
        	n+=1
        方法三：
        n=1
        while n <len(list4):
        	print(list4[n])
        	n+=2

##3、在列表中添加元素

>a、append()方法：列表名.append(元素)
* append()是将元素添加到列表的最后
        list1=[1]
        list1.append('abc')
        print(list1) # [1, 'abc']
        练习：找出列表中[2,3,23,13,45,24,21,26]所有的偶数,并且保存起来
        list2=[2,3,23,13,45,24,21,26]
        list3=[]
        for item in list2:
        	if item%2==0:
        		list3.append(item)
        print(list3)  # [2, 24, 26]
>b、insert:列表名.insert(下标,元素)
* 在指定的下标前插入指定的元素
* 注意：这儿的下标可以越界
        list4=[1,2,3,4,5,6,7,8]
        list4.insert(3,9)
        print(list4)  # [1, 2, 3, 9, 4, 5, 6, 7, 8]
        通过insert在4和5之间插入元素'b',在8的后面插入元素'c'。
        list4.insert(5,'b')  # [1, 2, 3, 9, 4, 'b', 5, 6, 7, 8]
        list4.insert(10,'c') # [1, 2, 3, 9, 4, 'b', 5, 6, 7, 8, 'c']当下标大于等于列表的长度，会插入到列表的最后
        list4.insert(0,'d')  # ['d', 1, 2, 3, 9, 4, 'b', 5, 6, 7, 8, 'c']在列表的最前面插入一个元素

##4、修改列表中的元素

* 修改元素：通过下标拿到对应的元素，然后重新赋值
        list1=[1,2,3,4,5,6]
        list1[1]=20  # [1, 20, 3, 4, 5, 6] 将下标是1的元素变成20
        让列表中的所有元素变为原来的2倍：
        方法一：
        for b in range(0,len(list1)):
        	list1[b]*=2
        print(list1)
        方法二：
        n=0
        for item in list1:
        	list1[n]=item*2
        	n+=1
        print(list1)
        让列表中偶数位上的元素变为原来的2倍:
        for n in range(0,len(list1):
        	if n%3==0:
        		list1[n]*=2
        print(list1)

##5、删除列表中的元素

>a、del语句：在python中，del可以删除任何内容
* del语句删除列表元素：del列表名[下标]
        list1=['a', 'b', 1, 2, 'c', 10+20, True]
        del list1[3]  # 删除下标为3的元素
* 注意：删除的时候下标不能越界
        del list1[20]  # 报错
* 通过下标删除要注意下标的重新分配的问题
        删除列表中所有的偶数元素:
        list1=[1,2,3,4,12,6]
        n=0
        while n<len(list1):
        	if list1[n]%2==0:
        		del list1[n]
        	else:
        		n+=1
        print(list1)
* isinstance(变量，类型)：判断指定的变量/值是否是指定的类型
        re=isinstance('aa',str)  # 判断'aa'是否是字符串
        print(re)    # True
* str(字符串)、int（整型）、float（浮点型）、bool（布尔）
        删除列表中所有的字符串元素:
        list2=['a',3,'c','d',55,23]
        n=0
        while n<len(list2):
        	if isinstance(list2[n],str):
        		del list2[n]
        	else:
        		n+=1
        print(list2)
>b、通过remove方法删除指定元素
* 格式：列表名.remove(元素)
        list3 = [1, 'c', 23, 'c', 'aa', 424, 'ewd']
        list3.remove('aa') # 删除列表中的'aa'
* 使用remove删除元素的时候，如果指定的元素在列表中有多个，只删除第一个
        list3.remove('c') 
        print(list3)  # [1, 23, 'c', 424, 'ewd']
        删除列表[1,3,4,7,8,2,3,4,1]中所有的奇数:
        list4=[1,3,4,7,8,2,3,4,1]
        n=0
        while n<len(list4):
        	if list4[n]%2!=0:
        		list4.remove(list4[n])
        	else:
        		n+=1
        print(list4)
>c、使用pop()方法删除指定下标的元素
* 格式1：列表名.pop(下标) 。从列表中取出指定下标对应的元素
* 格式2：列表名.pop()   从列表中取出最后一个元素
        list5=[1,2,24,5,5,6,'w','f']
        delitem=list5.pop(5) # 将下标是5的元素从list5中取出，并且存到变量delitem中
        print(delitem,list5) # 6 [1, 2, 24, 5, 5, 'w', 'f']
        del_item =list5.pop()
        print(del_item,list5)  # f [1, 2, 24, 5, 5, 'w']
        将一个列表[1,2,3,4,5,6]中的元素全部取出放到另外一个列表里面变成[6,5,4,3,2,1]：
        list6=[1,2,3,4,5,6]
        list7=[]
        while len(list6)>0:
        	x=list6.pop()
        	list7.append(x)  # 从后往前取
        	# list7.insert(0,list6.pop(0))  # 从前往后取
        print(list7)

##6、列表的操作

>a、求列表的长度
        list1=[1,2,34,1,4,51]
        print(len(list1))  # 6
>b、列表的+操作
* 列表1 + 列表2：将列表1和列表2中的元素组合成一个新的列表
        list2=[1,2,3]+['a','b','c']
        print(list2)  # [1, 2, 3, 'a', 'b', 'c']
>c、列表的 * 操作
* 列表 * 整数:将列表中的元素重复指定的次数，然后组合成一个新的列表
        list3=[10,4]*3
        print(list3)  # [10, 4, 10, 4, 10, 4]
>d、元素 in 列表：判断指定的元素是否在指定的列表中
        list4=['abc',33,'a',2,1]
        print('abc' in list4)  # True
>e、元素 not in 列表：判断指定的元素是否不在指定的列表中
        list5=['abc',33,'a',2,1,'asa']
        print('asa' not in list5)   # False
>f、获取列表中的最大的元素
* 格式：max（列表）
        list6=[2,5,6,3,8,242,34]
        print(max(list6))
        list7=['abc', 'b', 'c', 'd']
        print(max(list7))  # d
* 注意：获取最大值或者最小值的时候，列表中的元素类型要么都是数字，要么都是字符串
        list8=['abc',33,'a',2,1,'asa']
        print(max(list8))     # 报错 TypeError: '>' not supported between instances of 'int' and 'str'
>g、获取列表中的最小元素
* 格式：min(列表)
* sum(列表)：计算列表中所有元素的和
        list6=[2,5,6,3,8,242,34]
        print(min(list6))   # 2
        练习：求表演的平均分数（5个裁判，给表演打分。去掉一个最高分和一个最低分，再求平均分）
        import random
        list1=[]
        for i in range(1,6):
        	fenshu=random.randint(1,11)
        	list1.appdend(fenshu)
        list1.remove(max(list1))
        list1.remove(min(list1))
        print(sum(list1)/len(list1)
>h、list将其他的数据转换成列表
* 个数：list(数据)
        list8=list('abdnvfmg')
        print(list8) # ['a', 'b', 'd', 'n', 'v', 'f', 'm', 'g']
* 将range()转换成列表
        list2=list(range(10))
        print(list2)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
* 将列表转换成字符串（不仅仅是将列表中的元素拼接成字符串，而是将整个列表的所有结构都作为字符串的字符）
        print(str(list2),len(str(list2)),str(list2)[2])   # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] 30 ,

* 列表的值[a、c]，类型是对象
        person = [True,False,True]
        for index, person in enumerate(persons):
        	print(f'{index}:{"基"if person else "非"}')  # 0：基  1:非   2：基
* 对象类型：列表、字典、集合、元素、通过类创建的对象

* 变量在存储对象数据的时候，存的对象保存在内存中的地址。如果用存对象的变量给另外一个对象赋值，赋的是地址。

* 如果变量里存的是对象，要注意赋值的时候，如果不想要两个变量互相影响，就不要直接赋值，而是拷贝对象产生新的对象然后赋值。
        list1 = [1, 2, 3, 4]
        list2 = list1
        list2[0] = 10
        print(list2)   # [10, 2, 3, 4]
        print(list1)   # [10, 2, 3, 4]
        
        list1 = [1, 2, 3, 4]
        list2 = list1[:]
        list2[3]=10
        print(list1)  # [1, 2, 3, 4]
        print(list2)  # [1, 2, 3, 10]

#二十一、元组（tuple）

* 元组就是不可变的列表
* 列表中除了增加、修改和删除相关的操作，其他都适用于元组。
* 什么时候用？  就是存储到容器中的数据不能被修改的时候使用。
* 例如：星期几对应的值

##1、声明元组

    tuple1=(1, 2, 3, 4, 'aa', True)
    print(tuple1)

##2、查

    print(tuple1[0])
    print(tuple1[-1])
    
    print(tuple1[:3])
    
    for item in tuple1:
    	print(item)
    
    for index in range(len(tuple1)):
    	print(tuple1[index])

##3、 + ，*

    print((1, 3, 5, 6)+('q', 'b', 'c'))
    print((1, 2, 3)*3)

##4、in  ,  not in

    a=10
    print(a in (1, 4, 10, 5))
    print(a not in (2, 3, 10, 5))
    
    tuple2 = (1, 3, 5, 2, 7)
    tuple2[2] = 10   # 报错（TypeError: 'tuple' object does not support item assignment）
    del tuple2[1]    # 报错（TypeError: 'tuple' object does not support item assignment）
    
    练习，输入1-7的数字，然后对应输出是星期几。例如：输入1，就输出“星期一”。
    tuple3=('一', '二', '三', '四', '五', '六', '日')
    while True:
    num=int(input('请输入数字:'))
    print('星期%s' % (tuple3[num-1]))

#二十二、字典(dict)

* 字典是一个容器类的数据类型,以键值对（key:value）的形式来存储数据
* 键值对：  键：值的形式存在。 值：可以是任何类型的数据； 键：理论上只能是不可变的数据类型，实际开发中一般将字符串作为key。
* 字典是可变的（说明可以增、删、改、查），但是是无序的（不能使用下标来访问元素）

##1、声明/定义 字典(dict)

    声明了一个字典对象，有两个键值对
    dict1 = {'name': '骆昊', 'age': 18}
    dict2 = {'score': 100, 10: 'aaa', (1, 2): [1, 2]}
    print(dict2)
* 注意：可变的数据不能作为字典的key
        dict3={[10,12]:'abc'}  #  报错 （TypeError: unhashable type: 'list'）
        声明一个字典，存储小明的姓名、年龄、成绩、颜值：
        dict4={'name': '小明', 'age': 18, 'score': 80, 'face': 80}

##2、查

>a.获取单个元素的值
* 通过key去获取值：字典名[key值]
        print(dict4['age'])
        print(dict4['face'])
* 注意：使用字典名[key]的形式去获取字典中元素的值的时候，key值必须是字典中存在的，否则会报错
        print(dict4['abc'])   # 报错（KeyError: 'abc'）
* 通过get方法获取值：字典名.get(key值)
* 获取字典中不确定key对应的键值对是否存在时使用。
* None：python中一个特殊的值，表示没有，类似C语言中的NULL
        print(dict4.get('face'))
        print(dict4.get('abc'))   # None
        
        获取字典中'grade'对应的值，如果grade不存在就打印'不存在'，否则直接打印grade对应的值。
        if dict4.get('grade')==None:
        	print('不存在')
        else:
        	print(dict4.get('grade'))
>b、遍历字典
* 直接遍历字典拿到的是字典中所有的key值
* 在开发中使用这种方法去遍历字典
        dict5 = {'a': 12, 'b': 33, 'c': 66}
        for key in dict5:
        	print(key, dict5[key])
* 这个在开发中不建议使用，因为在获取键值对前需要一些转换的操作，消耗CPU。
        for (key, value) in dict5.items():
        	print(key, value)

##3.修改

* 通过key去拿到对应的元素，重新赋值
        dict5 = {'a': 12, 'b': 33, 'c': 66}
        dict5['a']=22
        print(dict5)
        
        练习：将上面的字典中所有的值变为原来的3倍。
        for key in dict5:
        	dict5[key] *= 3
        print(dict5)

##4.增加

* 通过key取值，然后赋值（如果这个key不存在，就是添加键值对。如果key存在，就是修改这个key）
* 注意：字典里的key是唯一的。
        dict6={'a': 1, 'b': 2, 'a': 3}
        print(dict6)  # {'a': 3, 'b': 2}

##5.删除(删除的是键值对)

>a、del语句
* 格式：del 字典[key]
        dict5 = {'a': 12, 'b': 33.4, 'c': [1, 2, 3]}
        del dict5['b']   # 删除'b'对应的键值对
        print(dict5)  # {'a': 12, 'c': [1, 2, 3]}
>b、pop（）方法
* 格式: 字典.pop(key)
        dict5 = {'a': 12, 'b': 33.4, 'c': [1, 2, 3]}
        result = dict5.pop('a')  # 结果是被删除的键值对的值
        print(result, dict5)  # 12 {'b': 33.4, 'c': [1, 2, 3]}
* dict5.popitem()方法：随机删除（取出）一个元素
        dict5 = {'a': 12, 'b': 33.4, 'c': [1, 2, 3], 'e': 22}
        dict5.popitem()
        
        练习：将字典中，值为字符串的全部删除
        dict5 = {'a': 12, 'b': True, 'c': [1, 2, 3], 'e': 'string'}
        n=0
        for key in dict5.copy():
        	if isinstance(dict5[key], str):    # 判断是否是字符串
        		del dict5[key]      # 移除key对应的键值对
        print(dict5)

##6、keys和values方法

    dict1 = {'a': 1, 'b': 2, 'c': 3}
>a、字典.keys():获取字典中所有的key,结果是一个列表
    print(dict1.keys())  # dict_keys(['a', 'b', 'c'])
>b、字典.values():获取字典中所有的值，结果是一个列表
    print(dict1.values())   # dict_values([1, 2, 3])

##7、update

* 字典1.update(字典2)：用字典2中的元素去跟新字典1中的元素（如果字典2中的键值对在字典1中不存在，直接添加；如过存在则直接修改）
        dict1.update({'d': 12, 'e': 123, 'a': 10})
        print(dict1)  # {'a': 10, 'b': 2, 'c': 3, 'd': 12, 'e': 123}

##8、in 和 not in

* 判断字典中是否有指定的key
        print('a' in dict1)  # True
        print(12 in dict1)   # False

#二十三、集合（set）

* 集合是一种容器类型，并且是无序，元素的值是唯一的（不能重复）,是可变的。
* 是通过{}去存储元素，多个元素之间用逗号隔开。

##1、声明一个集合

    set1 = {1, 2, 3, 4, 1}
    print(set1)   # {1, 2, 3, 4}
    将字符串转换成集合：
    set2 = set('abcdfreea')
    print(set2)  # {'e', 'f', 'r', 'b', 'c', 'a', 'd'}
    将列表转换成集合：
    set3 = set([1, 2, 3, 4, 5, 6, 5, 3])
    print(set3)  # {1, 2, 3, 4, 5, 6}
    将字典转换成集合（是将字典的key取出来作为集合的元素）：
    set4 = set({'a': 1, 'b': 2, 'c': 3})
    print(set4)  # {'b', 'a', 'c'}
    
    练习：将字符串str1='abcdffaaaaaffs'去重
    str1='abcdffaaaaaffs'
    set5 = set(str1)
    str2=''
    for x in set5:
    	str2=str2+x
    print(str2)

##2、查

* 不能单独的获取某一个元素，只能通过遍历的方式去获取每一个元素
        set1 = {1, 2, 3, 4, 5}
        for item in set1:
        	print(item)

##3、增加

>a、update（）
* 集合1.update(集合2)：将集合2中的内容添加到集合1中
        set1 = set('1223')
        set2 = set('abcd')
        set2.update(set1)
        print(set2)  # {'a', '2', '1', 'd', 'c', '3', 'b'}
>b、add
* 集合.add(元素)：将指定的元素添加到集合中
        set2.add('aaa')
        print(set2)  # {'b', 'd', '3', '1', 'aaa', '2', 'c', 'a'}

##4、删除

* 集合.remove(元素)：将指定的元素从集合中删除
        set2.remove('1')
        print(set2)  # {'3', 'aaa', 'c', '2', 'a', 'd', 'b'}

##5.判断包含关系： >= 、 <=

* python中的集合除了拥有作为容器相关的操作以外，还拥有数学中集合的相关操作
* 集合1>=集合2：判断集合1中是否包含集合2，结果是布尔值
* 集合1<=集合2：判断集合2中是否包含集合1.
        set1 = set('abcdef')
        set2 = set('abc')
        print(set1 >= set2)   # True
        
        set1 = set('abcdef')
        set2 = set('abcg')
        print(set1 >= set2)   # False

##6. | ， & ， - ， ^

        set1 = set('12345')
        set2 = set('456789')
>a、  |:求并集，求set1和set2中所有的元素
    print(set1 | set2)  # {'2', '8', '9', '5', '7', '4', '6', '3', '1'}
>b、  &:求交集，求在set1和set2的公共部分
    print(set1 & set2)  # {'4', '5'}
>c、  -:求差集,求在set1中，但是不在set2中的元素
    print(set1 - set2)  # {'1', '3', '2'}
>d、  ^：获取set1和set2中除了公共部分以外的所有元素
    print(set1 ^ set2)  # {'6', '2', '9', '7', '8', '1', '3'}

##7.copy

* 将set1中所有的元素取出来创建一个新的集合
        print(set1.copy())
* 什么时候用集合？  功能涉及到数学集合相关的操作的时候，就要想到用集合


#二十四、函数

##1、认识函数

* 函数：函数就是实现某一特定功能的代码块，在类中，函数又叫方法（对某一个功能的封装）
* 函数的作用：
>a.让界面更简洁（同样的功能对应的代码只写一遍）
>b.如果功能发生改变，使用函数只需要修改一个地方的代码
>c.让代码模块化

##2、函数的声明（定义）

>a、格式
    def 函数名（参数列表）：
    	说明文字
    	函数体
* def:是python中声明函数的关键字
* 函数名：标识符，PEP8，见名知义（根据函数名大概知道函数的功能）
* ():固定格式，不能省略
* 参数列表（形参）：参数的作用就是从外面往函数中传值。一个函数可以没有参数，也可以有多个参数。如果有多个参数，参数间用逗号隔开。
* 形参：获取从外面传递给函数内部的值（形参就是变量名）
* 冒号：固定的格式
* 说明文字：对函数功能进行说明
* 函数体：实现函数功能的代码段
>b、对于初学者来说，声明函数的步骤：
>>1.确定函数的功能（确定函数是做什么的）
>>2.确定函数名（根据功能确定函数名）
>>3.确定参数（确定是否有参数，确定参数有几个，看实现这个功能需不需要从外面传值进去）
>>4.确定是否需要返回值（返回值：就是函数返回给调用者的数据。python中所有的函数都有返回值，默认是None）
>>5.实现函数的功能
* 注意：函数只有在调用的时候才会执行
        写一个函数，打印'hello python'
        def da_yin():
        	""" 打印'hello python' """
        	print('hello python')
        调用函数da_yin:
        da_yin()
* 注意：1.一个函数声明后，可以调用多次 2.python中所有的函数调用表达式都有值
        写一个函数，去打印10的阶层
        def jie_ceng():
        	""" 打印10的阶层 """
        	s = 1
        	for i in range(1, 11):
        		s = s*i
        	print(s)
        jie_ceng()

##3、函数的调用

* 格式：
        函数名（参数列表）
* 函数名：你声明的需要调用的函数（已经声明过的函数才可以调用）
* 参数列表：实参（调用函数的时候给函数传的值）
* 函数的调用过程：就是用实参给形参赋值，并且执行函数体获取返回值
        写一个函数，打印两个数的和：
        def my_sum(num1,num2):
        	""" 打印num1+num2的和"""
        	print(num1+num2)
* 带参的函数的调用
* 注意：函数调用的时候一定要保证每个形参都有值
>a.位置参数（用实参依次给形参赋值）
    my_sum(2,3)  # 5 执行这句代码：先将num1=2，在将num2=3.在执行my_sum的函数
>b.关键字参数
    my_sum(num2=5, num1=10)   # 15
    练习：写一个函数，打印一个数的立方
    def lifang(num):
    	""" 打印num的立方"""
    		print(num**3)
    lifang(5)   # 125
>c.参数的默认值
* 在python中，函数的参数可以设置默认值。(函数声明的时候给参数赋值)
* 如果参数设置了默认值，那么调用函数的时候，这个参数可以传参，也可以不传。
        写一个函数，问候某人（打印：XXX，how are you!）
        def wen_hou(name='xxx'):
        	""" 问候 """
        	print('%s,how are you!'%(name))
* 函数调用的要求：保证每个参数有值
        wen_hou()   # xxx,how are you!
        wen_hou('Liu Zhilong')  # Liu Zhilong,how are you!
* 注意：声明函数的时候，如果函数中有多个参数，有默认值的参数必须放到没有默认值的参数的后面
        def wen_hou(message, name='xxx'):
        	""" 问候 """
        	print('%s,how are you! %s'%(name,message))
        wen_hou('lalala')  # xxx,how are you! lalala
>d.参数个数不定
* 参数个数不确定的时候，就在参数列表中声明一个变量，前面加一个“ * ”；这个时候这个变量就变成了元组。

* 命名关键字参数:写在 * ,后面的参数；在调用时必须要给出参数名和参数值

        def roll_dice(*, num = 1):
        	函数体
        roll_dice(num = 3)  # num =必须写上，不能直接写数字，否则会报错
* 函数调用的时候，所有的实参都会添加到这个元组中。
        写一个函数，求多个数的和
        def my_sum(*nums):
        	"""求多个数的和"""
        	s=0
        	for i in nums:
        		s += i
        	print(s)
        my_sum(2, 3, 5, 6, 7)  # 23
        my_sum(34, 21)  # 55

##4、函数的返回值

* 函数的返回值：
>a.就是函数调用表达式的值；
>b.就是return关键字后的表达式的值；
>c.就是函数返回给调用者的值。
* 如何看一个函数的返回值是多少：就看return后面的结果，如果没有return就是None

##5、函数调用

* 函数调用表达式：就是调用函数的那个表达式（这个表达式是有值的，默认是None）
        func1()就是一个函数
        def func1():
        	print('hello world!')
* func1()就是函数调用表达式，它是一个值。
* 普通的值能做的事情，函数调用表达式都能做；例如：给变量赋值，打印（可以作为实参传给函数），运算等
        result = func1()
        print(result, func1())  #  hello world!   hello world!   None None

##6、return

* return：
>a.将值传给函数调用者（函数调用表达式） 
>b.结束函数
* 如果函数中没有return,就相当于在函数结束的时候后面加了一个return None
        def func2():
        	print('hello world!')
        	return None   
        
        	return 100
        	result = func2()
        print(result, func2())  # hello world!  hello world!  100 100
        练习：写一个函数，获取两个数的乘积
        def cheng_ji(num1, num2):
        	return num1 * num2
        print(cheng_ji(5, 4))  # 20

##7、函数的结束

* 函数的结束：
>a.没有return，函数体执行完毕，函数结束；
>b.如果函数中有return，遇到return函数就结束，程序直接回到函数调用的位置，接着往下执行。
    练习：写一个函数，找出100-200之间第一个能被13整除的数
    def zhao_shu():
    for i in range(100, 201):
    	if i % 13 == 0:
        	return i
    print(zhao_shu())   # 104

##8、将列表作为参数

* 注意：将列表的变量作为实参传递给函数。如果在函数中改变了列表的元素，那么原来的列表元素也会变。
        def shan_chu(list1):
        n=0
        while n < len(list1):
        	if list1[n] % 2 ==0:
            	del list1[n]
        	else:
            	n+=1
        print(list1)
        list2 = [2,1,5,6,2,44,5,6]
        shan_chu(list2)  # [1, 5, 5]
        print(list2)  # [1, 5, 5]

##9、函数变量

* 我们在声明函数的时候，其实就是在声明一个类型是函数类型（function）的变量。
* 普通变量能做的事情，函数变量都可以做。
>a.函数名就是函数类型的变量（类型名：function），存的是函数入口的地址
    def func1():
    	print('aaa')
>b.可以用一个变量给另外一个变量赋值
    a = func1()    # 这样赋值。是将函数func1的返回值赋给a
    a = func1      # 将函数变量func1赋给啊，a就会变成一个函数
    a()  # 心在就可以用函数变量a，去调用函数func1
    def func2(num):
    	return num * 2
    b = func2
    print(func2(10))  # 20
    print(b(10))      # 20
>c.函数变量作为函数的参数
    def calculate(num1,num2,fn):
    	if not(isinstance(num1,int) or              isinstance(num1,float)):
        	print('num1不是数字')
        	return  None
    	if not(isinstance(num2,int) or isinstance(num2,float)):
        	print('num2不是数字')
        	return None
    	return fn(num1, num2)
    def func_add(n,m):
    	return n + m
    def func_sub(n, m):
    	return n - m
    print(calculate(20,10,func_sub))  # 10
>d.函数作为返回值
* 写一个函数，func3('+')-> 返回求和的功能；finc3(' * ')-> 返回求乘积的功能
        def func3(char):
        	if char == '+':
        	# python中，是可以在函数中声明函数
        		def fn(*n):
            		sum=0
            		for x in n:
                		sum += x
             		return sum
            	return fn
        	if char == '*':
        		def fn(*nums):
                	sum1 = 1
            		for i in nums:
                 		sum1 *= i
                	return sum1
         		return fn
         result = func3('+')  # result是一个求个功能的函数的函数变量
         print(result(1,2,4,5))  # 10
         print(func3('*')(10, 20))   # 200
         
         def func4():
         	list1=[1,2,3]
         	return list1
         print(func4()[0])  # 1

##10.匿名函数

* python中使用lambda关键字来声明一个匿名函数
         格式：lambda 参数列表：返回值
         参数列表：多个参数之间用逗号隔开
         
         使用函数实现求两个数的和：
         def func1(num1, num2):
         	return num1 + num2
         print(func1(10,20))   # 30
         使用匿名函数实现求两个数的和：
         func2= lambda num1, num2: num1 + num2
         print(func2(10, 20))  # 30
         
         练习：使用匿名函数求指定列表中，指定的两个下标对应的元素的和
         func3= lambda list1, num1, num2: list1[num1]+list1[num2]
         print(func3([1, 2, 3, 4, 5], 2, 3))  # 7
         
         使用指定的功能去计算num1和num2（例如求和）
         def calulate(num1,num2,fn):
         	return fn(num1, num2)
         print(calulate(10,20,lambda a,b: a+b))  # 30

##11、递归函数

在python中递归函数的深度只能在1000以内，可以用sys模块里的一个函数改变递归深度
动态规划（优化）：
    def main(n: int, m = {}) -> int:
        if n < 0:
            return 0
        elif n == 0:
            return 1
        else:
            try:
                return m[n]
            except:
                m[n] = main(n - 1) + main(n - 2) + main(n - 3)
                return m[n]
    if __name__ == '__main__':
        print(main(100))
>a.递归函数：在函数的声明中调用函数本身
    这儿的func1就是一个递归函数
    def func1():
    	print('aaa')
    	func1
    func1()
>b.递归作用：理论上循环能够做到的事情，递归都可以做。（但实际除非是非用不可的情况，一般不用递归）
>c.步骤：
* <1>确定临界值（结束函数的时刻）
* <2>假设函数的功能已经实现，然后找到f(n)和f(n-1)的关系
* <3>使用f(n-1)和f(n)的关系去实现f(n)的功能
        计算1+2+3+....+n(使用递归)
        def func1(n):
        	# 1.确定临界值
        	if n ==1:
        		return 1
        # 2.假设func1的功能实现了，找func1(n-1)和func1(n)的关系
        # func1(n-1)=1+2+3...+n-1
        # func1(n)=1+2+3...+n-1+n
        # 3.通过func1(n-1)去实现func1(n)的功能
        	return func1(n-1)+n
        print(func1(10))
        
        用递归实现：2*4*6...*n(要求n是偶数)
        def func2(n):
        	if n == 2:
        		return 2
        	return func2(n-2) * n
        print(func2(6))
        
        打印图形:n=5
        *****
        ****
        ***
        **
        *
        不用递归:
        def func3(n):
        	for x in range(1,n+1):
        		print('*'*(n+1-x))
        print(func3(5))
        用递归:
        def func4(n):
        	if n == 1:
        		print('*')
        		return
        	print(n*'*')
        	func4(n-1)
        func4(5)
        
        打印图形：n=5
        *
        **
        ***
        ****
        *****
        def func5(n):
        	if n == 1:
        		print('*')
        			return
        	func5(n-1)
        	print(n*'*')
        func5(5)

##12.函数的调用

* 函数调用的过程是一个压栈的过程：
>a.调用函数的时候，首先会在栈中开辟一块内存空间，用来保存函数调用过程中产生的数据（包括函数的参数和在函数中声明的变量）
>当函数执行完成后，被调用函数对应的内存空间会被回收（释放）
* 栈：是内存中的一块特殊的区域。数字和字符串的值是存在栈里面的。
* 堆：对象是存在堆里面的
* 总结：递归要慎用！（能用循环做的，就不要用递归。递归消耗内存也消耗CPU资源）

##13、使用模块管理函数

* 模块：指一个.py文件（一个.py文件就是一个模块）
* 可以在一个模块中使用其它模块的函数和类
* 怎么使用其他模块中的函数？
>a.通过import关键字导入模块，然后通过模块名.函数的方法去使用模块中的函数
        通过 import 模块名
        import random
        s=random.randint(1,10)
        print(s)
>b.通过from-import直接导入指定的函数或者类。导入后就可以直接调用函数
* 格式：from 模块名 import 函数名1，函数名2
        from 模块名 import 函数名
        from random import randint
        s=randint(1,9)
        print(s)
>c.通过 as关键字:通过as给导入的模块或者函数重命名
        1.通过as改变模块名
        import  random as my_random
        s=my_random.randint(1,10)
        print(s)
        2.通过as改变模块中的函数名
        from random import randint as my_randint
        s=my_randint(1,9)
        print(s)
* 注意：当我们导入其它模块的时候，会将其它模块中的所有内容都会导入到当前文件中
* 判断模块的内置属性 _ _ name _ _ 的值是否是' _ _ main _ _',将不需要被其它模块导入的代码写到这个if语句中
        if __name__=='__main__':
        	print('aaa')
* 关于_ _ name _ _ 属性：_ _ name _ _ 是每个模块都有的属性，作用是用来存储模块的名字。
* 当模块不是正在执行的模块，_ _ name _ _ 属性的值是模块对应的文件的文件名；当模块正在执行的时候，_ _ name _ _ 的值就是一个固定值'_ _ main _ _'


#二十五、作用域

* python中只有模块、函数和类会产生作用域。在作用域中声明的变量我们叫局部变量
* 在产生作用域外的位置声明的变量叫全局变量
* 不管是局部变量还是全局变量，都是从声明开始起作用的。

##1、全局变量

* 全局变量：声明在产生作用域外。
* 使用范围：从声明开始到整个文件结束的任何位置都可以使用
* if语句、for/while循环体，是不会产生作用域的；相当于写在if、循环体中的变量不改变其变量属性
        a=10  # 全局变量
        print(a)
        if True:
        	print(a)
        for x in range(3):
        	print(a)

##2、局部变量

* 局部变量：在python中声明在函数和类中的变量都是局部变量。
* 注意：在函数中不能修改全局变量的值，只能使用。
        def func3():
        	d = 'a'   # d就是一个局部变量，使用范围就是从声明开始到函数结束
        print(d)
        func3()      # 'a'
>a、global关键字的使用
    b=100
    def func5():
    #想在这个地方去修改全局变量b的值为200
    	global b
        b = 200
    func5()
    print(b)  # 200

#二十六、文件操作

* 文件都有后缀，不同的后缀表示不同的存储方式
* 文本文件（存文字信息）---- .txt , .word,  .md 等...
* 二进制文件：视频文件、音频文件、图片---- .mp4, .mov, .avi, .jpg, .mp3   等...
* 可执行文件等--- .exe , . api, .dmg 等...
* 文件操作（对文件进行读写）步骤（对所有文件都有效）：
>1.打开文件
>2.对文件进行读/写操作（读：获取文件内容  写：修改文件内容）
>关闭文件

##1、文本文件

>a.打开文件
* open(文件路径，打开的模式='r'，编码方式)
* open函数有一个返回值：返回的就是被打开的文件句柄对象
* 文件句柄：就是文件的代言人，对文件句柄对象进行的操作就相当于对文件进行操作
* 文件路径：文件在电脑中对应的地址
> (1)直接写全路径（不推荐使用）： 'E:/Python资料/python作业/上课笔记/6.24/code/aaa.txt'
> (2)一般将涉及到的文件放到工程中:'lalala.txt'
> >a.文件和代码对应的.py文件在一个目录下面：路径直接写文件名
> >在工程文件夹下，但是不直接和代码文件在一个目录里面： ./文件对应的文件夹名/文件名
* 打开的模式：
>'r'(文本读，以读的形式打开，只能获取文件内容，不能修改文件内容)
>'w'(文本写，以写的形式打开，只能修改文件内容，不能获取文件内容)
>'a'(文本写)
>'rb'(二进制读)
>'wb'(二进制写)
>'ab'(二进制写)
* 编码方式(encoding)：'utf-8'(pythond的文本编码方式)
* utf-8：一种文本编码方式，就是使用1-6个字节对Unicode进行编码；utf-8就可以编码所有国家的语言对应的字符。
* gbk：只支持中文文本编码
* 注意：'r'打开文件，如果文件的路径错了会报错
        f=open('./fils/lalala.txt', 'r', encoding='utf-8')
* f：就是被打开的文件对应的文件句柄
>b.读操作
* 注意：对同一个句柄对象进行读操作，每读一次内容，下次在读的时候，从上次读的结束的位置往下读
* f.read():获取文件中所有的内容并且返回
* 文本文件读取的结果是字符串
* read(n):指定读取的文本长度（默认-1：读全部内容，n大于长度读所有）
        result=f.read()
        print(result)
        f.close()
* f.readline()：每次读一行内容
        f= open('aaa.txt','r',encoding='utf-8')
        result1 = f.readline()
        print(result1)
* 关闭文件:f.close()
        练习：1.读取指定文件的所有内容 2.读取指定文件的所有内容（一行一行的读）
        f=open('./fils/lalala.txt', 'r', encoding='utf-8')
        print(f.read())
        while True:
        	result1 = f.readline()
        	if result1=='':
        	# if not result1:
        	# if len(result1)==0:
        		break
        	else:
        		print(result1)
        f.close()
* readlines():让文件中所有的内容读出来（将每一行的内容作为列表的元素返回）
>c.修改读取的位置
* 读写文件，每次读完，下次再读的时候，是接着上次读完的位置往下进行读操作。
* 避免这个问题的方法：1.从新打开文件，然后再读  2.设置读写位置
         f = open('aaa.txt', 'r', encoding='utf-8')
* 读取文件中所有的内容,下次再读就是从文件结束的位置往后读
* seek(偏移量)：偏移量是字节数（一个字母是一个字节，“utf-8”中一个汉字是3个字节，“gbk”中一个中文汉字是两个字节）
* 注意：偏移量一般设置为0
* 设置读写位置为文件的开始：后面进行读操作的时候，就是从文件开始的位置往后读
         f.seek(0)
         print('====', f.read())
         f.close()
>d.写操作
    f = open('aaa.txt', 'w', encoding='utf-8')
* 注意：'w'或者'a'打开文件，如果这个文件不存在，会创建一个新的文件
* write(写的内容)：文本文件中，写的内容是字符串
* 注意：'w'->写的时候会覆盖原文件的内容.  'a'->在原来的内容后面追加内容
         f.write('我的哥！')
         f.seek(0)  # 后面写的时候，会以覆盖前面写的内容的形式去写
         f.writelines(['aaa', 'bbb', 'ccc'])
         f.close()
* python中可以使用以下结构来进行文件操作过程：
         with open() as 文件变量:
         	在文件打开后关闭前执行的代码段
         例如：
         with open('aaa.txt', 'r', encoding='utf-8') as f:
         print(f.read())

##2、二进制文件

>a.二进制文件的读
* bytes类:python中的二进制数据对应的类型bytes
        with open('./fils/懒洋洋小黄猫.mov', 'rb') as f:
        	data=f.read()
        	print(data)
>b.二进制文件的写
* 'ab':无追加效果
        with open('./fils/new.mov', 'wb') as f:
        	# data需要是bytes类型的数据
        	f.write(data)

##3、json文件

* json文件：就是后缀是.json的文件，用来存储文本数据（以特殊的语法结构来存储文本信息）
>最外层：要么是字典结构，要么是数组（列表）结构,要么是字符串
>里面的数据：字符串、二进制、数字、字典、数组(列表)
    {}->字典结构
    {
    	"name":"aa",
    	"age":18,
    	"score":[100,22,44]
    }
    
    []->数组结构
    [
    	100,
    	"name"
    ]
    
    ->字符串
    “
    	name，awdf，[1,2,3]
    ”
* json文件的读写：python中使用python内置模块json来对json数据进行操作
        import json
>a.读取json文件中的内容
* json.load(f):读取的结果只有两种情况（要么是字典，要么是列表）
* json.loads(json字符串，编码方式)：将字符串转换成字典或者列表
        with open('./fils/json文件.json', 'r', encoding='utf-8') as f:
        # print(f.read())
        result = json.load(f)
        # print(type(result))  # dict
        print(result)
        resolt=json.loads('{"name":"lala","age":17}' encoding='utf-8')
        print(resolt)  # {'name':'lala','age':17}
>b.json文件的写操作
* json.dump(写的内容，写到那个文件):写的内容只能是一个字典/一个数组（列表）/一个字符串/一个元组（写进去是列表）
* json.dumps(对象)：将字典或者列表转换成字符串
        with open('./fils/myjson.json', 'w', encoding='utf-8') as f:
        # dict1 = {'aaa': 100, 'abc': 'aaw', 'person': {'name': 'lalala', 'age': 50}}
        # list1 = [1, 22, 'www', [1, 3, 'e']]
        # str1 = 'avffad'
        tuple1 = (1, 2, 3)  # 写进去还是列表
        json.dump(tuple1, f)
        
        写一个添加学生的功能，将添加的学生信息持久化:
        1.添加学生
        2.查看学生
        import json
        # 1.
        name1= input('请输入添加的学生姓名：')
        age1= int(input('请输入学生的年龄：'))
        tel1= int(input('请输入学生的电话号码：'))
        try:
        	with open('./fils/学生信息.json', 'r', encoding='utf-8') as f:
        		dict2 = json.load(f)
        except:
        	dict2 = {}
        dict1 = {"name": name1, "age": age1, "tel": tel1}
        dict2[name1] = dict1
        with open('./fils/学生信息.json', 'w', encoding='utf-8') as f:
        	json.dump(dict2, f)
        # 2.
        name2 = input('请输入要查找的学生姓名')
        with open('./fils/学生信息.json','r',encoding='utf-8') as f:
        	result = json.load(f)[name2]
        	print(result)

#二十七、异常的捕获

* 格式：
        格式1：
        try:
        	代码块1（需要捕获异常的代码块）
        except:
        	代码块2（出现异常后执行的代码块）
        # finally:
        	# 代码块3（不管有没有异常都要执行的代码块）
        
        格式2：
        try:
        	代码块1
        except 错误类型列表：
        	代码块2
        # except:
        	# 代码块3（出现异常后执行的代码块）
        # finally:
        	# 代码块4（不管有没有异常都要执行的代码块）
        出现指定错误类型的异常才捕获
* 执行过程：先执行代码块1，如果执行代码块1的时候出现异常，就执行代码块2；如果代码块1不出现异常，就执行try结构外的其它语句
        try:
        	print(int('12fef'))
        except:
        	print('出现异常了！')
        
        try:
        	with open('./fils/la.json', 'r', encoding='utf-8') as f:
        		pass
        except FileNotFoundError:
        	print('出现文件找不到异常！')

#二十八、面向对象编程

##1、编程思想：

    面向过程编程：c（只有逻辑和过程）
    a=1
    b=2
    print(a+b)
    
    面向对象编程java 、c++、oc、python（有类语法）-->(以对象为工具实现功能)
    对象.sum(1,2)
    
    函数式编程：c、java、python （以函数为工具实现功能）
    def sum(num1,num2):
    	return num1+num2
    sum(1,2)

##2、类和对象

* 类：具有相同属性和相同功能的对象的集合，是抽象的。
* 对象：就是类的实例，是具体的。
        如果说电脑是一个类，我桌上这台电脑就是一个对象。
* 声明类的格式：
        class 类名：
        	类的内容
>a.class：python中声明类的关键字
>b.类名：标识符(1.首字母大写！！ 2.见名知义)
>c.冒号：固定格式，冒号后一个缩进的内容就是类的内容
>d.类的内容：
>>1.类变量:声明在类中，方法外的变量；要通过类去获取（通过类能够让其具体的属性）
>>2.对象属性
>>3.方法（构造方法、对象方法、类方法、静态方法）：声明在类中的函数就叫方法
    声明一个人对应的类：
    class Person:
        count = 61  
        def __init__(self):
        	# 我们一般在这个地方去声明对象的属性
        	self.name = '啦啦啦'
        	self.age = 18
        	self.gender = '男'
        def run(self):
        	print('跑起来')
* count：就是类变量(通过类去使用)，是局部变量，作用域是整个类
* _ _ init _ _ ：构造方法 _ _ init _ _ ，名字固定；通过类创建对象的时候，系统会自动的调用这个方法去初始化对象的属性。
* self：
    >1.类中所有的对象方法都会默认有一个self参数，用来指向调用方法的对象（谁调用当前这个方法就指向谁）
    >2.调用带有self的方法不需要给self传参，系统会自动将方法调用者传给它
* name、age、gender就是人这个类的对象的属性
* 对象方法：
    >1.所有的对象方法都有一个默认的参数self
    >2.直接声明在类中的函数，都是对象方法
    >3.对象方法必须使用对象去调用
* a.使用类变量:通过 类名.类变量 的形式在类外去使用类变量
        print(Person.count)  # 61
* b.name、age、gender都是对象属性，对象属性的使用：对象.属性名
        # print(Person.name)  # 报错（AttributeError: type object 'Person' has no attribute 'name'）
* c.对象方法run：对象方法只能通过对象去调用-->对象.方法名（）
        # run()  # 报错（NameError: name 'run' is not defined）
        # Person.run()  # 报错（TypeError: run() missing 1 required positional argument: 'self'）
* d.怎么声明对象：类名（参数）
* >通过类创建对象：会自动调用类的 _ _ init _ _ 方法去初始化对象的属性
* >类名（参数），这个参数有没有，有几个就看 _ _ init _ _ 方法
         p1 = Person()  # 通过Person类，创建了一个对象p1
* >创建完对象后，就可以通过对象获取对象属性：对象.属性名
         print(p1.name) # 啦啦啦
* >通过对象给属性赋值
         p1.age = 18
         print(p1.age)  # 18
* >通过对象去调用对象方法（也叫给对象发送消息）
         p1.run()
* e.一个类可以拥有多个对象
         p2 = Person()
         p2.name = 'hehe'
         p2.age = 20
         print(p2.age)   # 20
         print(p2.name)  # hehe


#二十九、类的定义

* 类：具有相同属性和功能的对象的集合；抽象的
* 对象：类的实例；具体的
* 类的声明
        class 类名（父类）：
        	属性
        	方法
        class 类名：
        	属性
        	方法
>a.class：python中声明类的关键字
>b.类名：标识符。  首字母大写、见名知义。
>c.属性：分类的字段和对象的字段。---->属性
>d.方法：对象方法（构造方法）、类方法、静态方法。---->功能
>*  方法：就是声明在类中的函数（都有一个默认参数，不需要调用的时候给他传值）
>*  对象方法：在类中直接声明的函数，带一个参数self；要使用对象来调用。
    # 声明类
    class Person:
        """人类"""    # 说明文档
        # 在类中声明了eat方法，默认有一个参数self，调用eat方法的时候，不需要给self传参
        # 在类中直接声明的函数都是对象方法，对象方法必须使用对象来调用
        # 直接写在类中的函数，必须带参数self
        def eat(self):
        	print('吃饭~')
        # 注意：如果要在类中声明带参的对象方法，那么其它的参数必须写在self后面
        def run(self,num):
        	print('跑了%d米'%(num))
    # 创建对象
    p1 = Person()
    # p1就是Person类的一个实例（对象）
    # 可以通过对象去调用类中的对象方法、和使用类中声明的对象属性（字段）
* 调用对象方法:
        p1.eat()  # 吃饭~
        p1.run(100)  # 跑了100米
* 一个类可以创建多个对象:
        p2 = Person()
        p2.eat()  # 吃饭~
        p2.run(80)  # 跑了80米

#三十、对象属性和init方法

>1. 示例一：init方法会自动调用
    class Person:
* _ _ init  _ _ 方法又叫构造方法。是在通过类创建对象的时候自动调用的方法
* _ _ init _ _ 方法的作用就是在创建对象的时候初始化对象的属性
* _ _ init _ _ ：对象的属性就是声明在这个方法中
        def _ _ init _ _ (self):
        	# 在这个地方声明对象的属性
        	print('这个是init')
* 在声明对象的时候会自动调用init方法
         p1 = Person()
         p2 = Person()
>2.示例二：带参的init方法
    class Dog:
    	"""狗"""
*  init方法的方法名固定： _ _ init _ _ 。 但是参数是可以随意改变的（但是self不变）
        def __init__(self, name):
        	print('名字是：%s'%(name))
* 通过类创建对象的时候，要保证init方法里面的每一个参数都有值。通过给类名后面的括号里传参来保证。
        dog1 = Dog('xiaohui')
        dog2 = Dog(name='xiaobai')
>3.示例三：对象属性
* 属性：声明在类中的变量
* 对象属性：要通过对象去使用；不同的对象可能会有不同的值；声明在init方法中的变量。
        class Person2:
        	"""人类"""
        	# 在init中声明对象属性：self.属性名 = 初值
        	def __init__(self):
        	# 声明一个对象属性name，初始值为空串
        	self.name = ''
* 通过Person2类创建对象P3
        P3 = Person2()
* 通过P3对象去修改P3的name属性
        P3.name = 'XIAOBAI'
* 通过P3对象去使用P3的name属性
        print(P3.name)   # XIAOBAI
* 通过Person2类创建对象P4
        P4 = Person2()

        # 练习：声明一个学生类，拥有属性：名字、年龄和电话。拥有方法：学习
        class Student:
        	def __init__(self):
        		self.name = ''
        		self.age = ''
        		self.tel = ''
        	def study(self):
        		print('%s在学习'%(self.name))
        student1 = Student()
        student1.name = 'dage'
        student1.age = 20
        student1.tel = 123456789
        print(student1.age,student1.name,student1.tel)   # 20 dage 123456789
        # 调用对象方法（给对象发送消息）
        student1.study()      # dage在学习
>4.示例四：
    class Student1:
    	def __init__(self, name1='', age1='', tel1=''):
    		self.name = name1
    		self.age = age1
    		self.tel = tel1
* 在创建对象的时候给对象属性赋初值
        student2 = Student1('xiaoming','20','1234556781')
        print(student2.name, student2.age, student2.tel) # xiaoming 20 1234556781

#三十一、self

* 类中的对象方法都有一个默认参数self
  >a.调用带有默认参数self的方法，不需要给self传参。系统会自动将调用当前方法的对象传给self
  >b.在方法中使用self就相当于使用调用方法的对象（只能使用self，不能重新给self赋值）
      class Person:
      	"""人类"""
      	def __init__(self, name='', age=0):
      		# 声明对象属性
      		self.name = name
      		self.age = age
      	def eat(self):
      		print('吃饭')
      	# 声明一个对象方法run
      	def run(self):
      		# 在对象方法中使用对象的属性，直接用self去获取属性
      		print('%s跑起来'%(self.name))
      		self.eat()
      # 创建一个Person对象
      p1 = Person('小明',10)
* 通过对象p1去调用run方法，系统会将self=p1
* 这个时候在run方法中，p1和self是一个东西
      p1.run() # 小明跑起来
        		# 吃饭
      
      练习：声明一个圆类，拥有属性：半径 ，拥有方法：计算圆的面积、计算圆的周长
      from math import pi
      class Circle:
      	def __init__(self, radius=0):
      		self.radius = radius
      	def area(self):
      		return (self.radius)**2 * pi
      	def perimeter(self):
      		return 2*pi*self.radius
      circle1 = Circle(3)
      print('%.2f' % circle1.area()) # 28.27
      print('%.2f' % circle1.perimeter()) # 18.85

#三十二、属性的增删改查

    class Dog:
    	"""狗"""
    	# Dog类有name和age两个属性
    	def __init__(self,name='',age=0):
    		self.name = name
    		self.age = age
    dog1 = Dog('恭喜发财',20)

##1.查

>a.方式一：对象.属性
>>特点：如果属性存在就获取属性的值。如果属性不存在就会报AttributeError错误
    print(dog1.name)  # 恭喜发财
    # print(dog1.score)  # 报错（AttributeError: 'Dog' object has no attribute 'score'）
>b.方式二：getattr(对象，属性名，默认值)--->获取指定对象的指定属性
>>如果不设置默认值：属性如果存在就获取属性值，如果属性不存在就报错
>>如果设置默认值：属性如果存在就获取属性值，如果属性不存在，不报错，并且将默认值作为结果
    print(getattr(dog1, 'name'))  # 恭喜发财
    # print(getattr(dog1, 'score'))  # 报错（AttributeError: 'Dog' object has no attribute 'score'）
    print(getattr(dog1, 'score', 100)) # 100
>c.方式三：对象. _ _ getattribute _ _ (属性名)
>>获取指定对象的指定属性。如果属性不存在就会报错。
    print(dog1.__getattribute__('name'))  # 恭喜发财

##2.改（修改）

>a.方式一：对象.存在的属性=新值
    dog1.name = '小黄'
    print(dog1.name)  # 小黄
>b.方式二：setattr(对象，存在的属性名，新值)
    setattr(dog1, 'name', '小白')
    print(dog1.name)  # 小白
>c.方式三：对象. _ _ setattr _ _ (存在的属性名，新值)
    dog1.__setattr__('name', '小黑')
    print(dog1.name) # 小黑

##3.增（对象添加属性）

* python中可以动态的给对象添加属性。
>a.方式一：对象.不存在的属性=值
    dog1.sex = '公'
    print(dog1.sex)  # 公
>b.方式二:setattr(对象，不存在的属性名，值)
    setattr(dog1, 'he', 'dagoou')
    print(dog1.he)  # dagoou
>c.方式三：对象. _ _ setattr _ _ (不存在的属性名，值)
    dog1.__setattr__('hehe', '无语')
    print(dog1.hehe)  # 无语

##4.删除属性

>a.方式一：del 对象.属性
    # 将dog1的age属性删除
    del dog1.age
>b.方式二：delattr(对象，属性名)
    delattr(dog1, 'hehe')
>c.方式三：对象._ _ delattr _ _ (属性名)
    dog1.__delattr__('he')

##5.判断对象是否拥有某个属性

* 方式：hasattr(对象，属性名)--->判断指定的对象是否拥有指定的属性
        print(hasattr(dog1, 'age'))   # False
        print(hasattr(dog1, 'name'))  # True
* 示例1：对象属性的操作只对当前那一个对象有效
        class Person:
        	def __init__(self,name ='',age=0,id_num='',sex=''):
        		self.name = name
        		self.age = age
        		self.id_num = id_num
        		self.sex = sex
        p1 = Person('小明', 10)
        # 给不存在的属性赋值，就是添加属性
        p1.score = 100
        print(p1.score+100)   # 200
        p2 = Person('小黄', 20)
* 注意：
  >1.对对象属性的增、删、改、查是针对指定的那一个对象，不会影响其它的对象。
  >2.实际开发用的时候，一般只用获取对象属性的值和修改对象属性的值。想要添加和删除属性一般都是在init方法中去操作。
* 通过给 _ _ slots _ _ 赋值，可以限制类中对象的属性有哪些，防止一些不必要的属性被添加
        class Dog:
        	__slots__ = ('name', 'age', 'color')
        	def __init__(self, name='',age=0,color=''):
        		self.name = name
        		self.age = age
        		self.color = color
        		# self.sex = '公'  #报错，因为__slots__中没有'sex'
        dog1 = Dog('小白',3,'yellow')
        
        练习题看6.27课堂笔记

#三十三、内置类属性

    class Dog:
    	"""狗"""
    	def __init__(self,name='',age=0,color=''):
    		self.name = name
    		self.age = age
    		self.color = color
    	def run(self):
    		print('%s跑起来了'%(self.name))
    	def shout(self):
    		print('%s在叫唤'%(self.name))
    dog1 = Dog()
* 内置类属性是属于类的，需要通过类去使用
>a. 类. _ _ name _ _ :获取类的名字(只有类有这个属性)
    print(Dog.__name__)   # Dog
>b. 类. _ _ doc _ _ :获取类的说明文档
    print(Dog.__doc__)   # 狗
>c. _ _ dict _ _
>> 类. _ _ dict _ _ :获取类中所有的类属性（类字段）和对应的值的键值对--->结果是字典
>> 对象. _ _ dict _ _ :以键值对的形式获取指定对象的所有的属性和值
    print(Dog.__dict__)
    print(dog1.__dict__)  # {'name': '', 'age': 0, 'color': ''}
>e. 类. _ _ module _ _ :获取类所在的模块的名字
    print(Dog.__module__)  # __main__
>f. 类. _ _ bases _ _ :获取指定类的基类
    print(Dog.__bases__)   # (<class 'object'>,)

#三十四、类和对象

##1、属性私有化

* 属性的访问权限：公开、保护(python中没有)、私有
* 公开: 指的是在类的外部可以直接使用（默认）
* 公开属性：属性名是普通单词(就是不以两个下划线开头的属性)
* 私有：只能在类的内部直接使用
* 私有属性：属性名以两个下划线开头（不以两个下滑线结束）
* 私有属性不能在类的外部去使用
        class Person:
        	"""人"""
        	def __init__(self, name='', age=0):
        		# name属性是公开的属性
        		self.name = name
        		# __age属性是私有的属性
        		self.__age = age
        	def show(self):
        		print(self.name)
        		# 私有属性可以类的内部使用
        		print(self.__age)
        p1 = Person('小明')
        print(p1.name)
        # print(p1.__age)  # AttributeError: 'Person' object has no attribute '__age'
        p1.show()

##2、假的私有属性

* 实际开发中，声明类的属性，很少会使用真正的私有属性和公开属性(前面加两个下滑线的)。
* 实际对属性的要求：
  >a.可以通过点语法方便的来给属性赋值或者拿到它的值（不能是私有的） 
  >b.给属性赋值的时候，需要对赋过来的值进行规范，不能直接就让值赋给属性(不能是直接的公开属性)
* 满足要求: 就使用假的私有属性 + getter和setter
  >a.声明属性，属性名前加一个下划线（这个是规范，不是语法：带一个下划线的属性，不要直接通过一个下划线对应的属性名去访问这个属性）
  >b.通过给属性添加getter和setter来限制赋值和获取值的过程
  >>添加getter: --> 限制获取属性值的操作
* getter的作用：返回属性的值
        @property
        def 属性名去掉下划线(self):
        	其他任何操作
        	return self.带下划线的属性名
        	
        @属性名去掉下划线.setter
        def 属性名去掉下划线(self, 参数):
        	其他任何操作
        	self.带下划线的属性名 = 参数
  >c.在类的外部通过不带下划线的属性去获取属性的值，或者给属性赋值
    class Person:
        def __init__(self, name='', age=0):
        	# 声明属性的时候，在属性名前加_,是为了告诉别人，这个属性不要直接访问，要通过getter或者setter去访问
        	self._name = name
        	self._age = age
        # 给_name属性添加getter
        @property
        	def name(self):
         		if len(self._name) == 0:
            		return '无名氏'
        		return self._name
        # 给_name属性添加setter
        @name.setter
        def name(self, name1):
        	# 可以在给属性赋值前做其他操作
        	if isinstance(name1, str):
            	self._name = name1
        	else:
            	self._name = ''
         @property
        	def age(self):
         		return self._age
    p1 = Person('小明')
    # print(p1._name)  # 是不会报错的，但是不推荐使用
    # p1._name = '路飞'
    print(p1.name)
    p1.name = '娜美'
    print(p1.name)
* getter一般要添加， setter可以不用写
* 如果要添加setter必须添加getter
        示例二：getter和setter的使用以及关系
        class Cat:
        	"""猫"""
        	def __init__(self, name='', color=''):
        		self._name = name
        		self._color = color
        	@property
        	def name(self):
        		if isinstance(self._name, str):
            		return self._name
        		else:
            		return ''
         	@name.setter
         	def name(self, name):
        		self._name = name
         cat1 = Cat('小花', 'yeloow')
         cat1._name = '喵喵'  # 推荐
         print(cat1._name)  # 不推荐

##3、类字段和类方法

* 类字段就是类属性：通过类去获取
  > 类字段是声明在类里面，函数外面的变量
* 类方法：通过类去调用
  > 开发中怎么确定声明称方法是对象方法还是类方法：看实现的功能是否需要对象属性来支持，如果需要就必须声明称对象方法
* @classmethod来说明下面的函数是一个类方法 --> 函数修饰符
* 所有的类方法都有一个默认参数cls,这个参数不需要传参，系统会自动将调用方法的类传给它(谁调用指向谁)
        class Person:
         	"""人类"""
        	# 这个person_num就是一个类字段
        	person_num = 0
        	@classmethod
        	def hurt_earth(cls):
        		print(cls)
        		print('人类伤害破坏环境，伤害地球',  Person.person_num, cls.person_num)
* 类字段要用类去使用
         print(Person.person_num)
         Person.hurt_earth()
         print(Person)
         练习：写一个数学类，提供数据的加、减、乘、除的功能
         class Math:
         	@classmethod
         	def add(cls, *num):
         		sum1 = 0
         		for x in num:
            		sum1 += x
         		return sum1
         sum1 = Math.add(10, 2, 3)
         print(sum1)

##4、静态方法

* 静态函数：在类中声明，由类来调用的方法
        示例一： 静态方法
        class Math:
        	"""数学类"""
        	# multiply就是一个静态方法
        	@staticmethod
         	def multiply(num1, num2):
         		return num1 * num2
* 静态方法需要使用类来调用
         print(Math.multiply(10, 4))
* 静态方法和类方法的区别：
  >a.类方法都有一个默认参数cls指向调用方法的类，但是静态方法没有
  >类型不一样，静态方法的类型是function，类方法的类型是method

##5、类的继承

* 继承：继承就是让子类去拥有父类的属性和方法
  >子类：继承者
  >父类(超类)：被继承者
* 什么时候用继承：在写一个类的时候，发现这个类中的部分属性和方法另一个类都拥有，这个时候就不用去声明这些属性和方法，直接从另外一个类中继承下来就可以
        实例一：怎么继承
        class 子类(父类):
        	子类的内容
        class Person:
        	"""人"""
        	def __init__(self, name='aaa', age=0):
        		self.name = name
        		self.age = age
        class Student(Person):
        	pass
        stu1 = Student()
        print(stu1.name)
* 可以继承哪些东西？
  >a.公开属性可以继承
  >b.私有的属性不可以继承
  >c.公开的对象方法可以继承（私有的不行）
  >d.类字段可以继承
  >e.类的方法和静态方法可以
* 总结：属性和方法除了私有的都可以继承; __slots__不能继承的
        class Animal:
        	#1.对象的属性
        	__slots__ = ('name', '__age')
        	def __init__(self, name='bb'):
        		self.name = name
        		self.__age = 18
        	def run(self):
        		print(self.__age)
        	#2.对象方法
        	def eat(self):
        		print('吃东西')
        	# 私有的对象方法，只能类的内部调用
        	def __shout(self):
        		print('叫')
        	#3.类字段
        		count = 100
        	#4.类方法
        	@classmethod
        	def class_func(cls):
        		print('class_func')
        	#5.静态方法
        	@staticmethod
        	def static_func():
        		print('static_func')
         class Dog(Animal):
         	pass
         	# def eat_bone(self):
         	# print('吃骨头',self.__age)
         dog1 = Dog()
         print(dog1.name)
         dog1.eat()
         print(Dog.count)
         Dog.class_func()
         Dog.static_func()
         dog1.color = 'red'
         print(dog1.color)

##6、类的继承重写

* 声明一个类，如果不声明其父类，那么这个类默认继承自object这个类。
* object类是python中所有类直接或者间接的父类
* 示例一：什么是重写
  >重新实现从父类继承下来的方法 ---> 重写
        class Aniaml(object):
        	def __init__(self, name):
        		self.name = name
        	def shout(self):
        		print('%s:嗷嗷叫' % (self.name))
        	def be_beat(self):
        		print(self.name,'在跑')
        		print('跑的时候嗷嗷叫')
        class Dog(Aniaml):
        	# 重写父类的shout方法。然后通过Dog对象调用shout执行的是子类的方法
        	def shout(self):
        		print('%s:汪汪汪！'% (self.name))
        	# 重写父类的be_beat，保留了父类实现的功能，并且添加了新的功能
        	def be_beat(self):
        		# super()指的就是父类对象
        		super().be_beat()
        		print('奋起反抗')
* 示例2：init方法的继承和重写
  >重写init方法要注意：如果需要继承父类的对象属性，就需要通过super(). _ _ init _ _ ()去保留父类的对象属性。然后再添加新的属
        class Person:
        	"""人"""
         	def __init__(self, name='', age=0):
        		self.name = name
        		self.age = age
         class Student(Person):
         	"""学生类"""
         	def __init__(self, name='', age=0, study_id=''):
         		super().__init__(name, age)
         		self.study_id = study_id
         练习：设计两个类：
         一个正方形类，拥有方法：求面积、求周长  拥有的属性是边长
         一个长方形类，拥有方法：求面积、求周长  拥有的属性是长和宽
        class Rect:
         	def __init__(self, length=0, width=0):
         		self.length = length
         		self.width = width
        	def area(self):
         		return self.width * self.length
         	def perimeter(self):
        		return (self.width + self.length)*2
        class Square(Rect):
         	def __init__(self, length=0, width=0):
         		super().__init__(length, width)
         		self._side = 0
         	@property
         	def side(self):
        		return self._side
         	@side.setter
         	def side(self, side):
         		self.width = side
        		self.length = side
        		self._side = side

#三十五、类和对象

##1、类的多态

* 多态：就是一个事物有多种形态,继承就会产生多态
* 类的多态:通过继承，同一个方法可以有多种实现
        class Animal:
        	def shout(self):
            	print('嗷嗷叫')
        class Cat(Animal):
        	def shout(self):
        		print('喵喵叫')
        class Dog(Animal):
        	def shout(self):
        		print('汪汪叫')
        animal1 = Animal()
        animal1.shout()   # 嗷嗷叫
        cat1 = Cat()
        cat1.shout()   # 喵喵叫
        dog1 = Dog()
        dog1.shout()   # 汪汪叫

##2、运算符的重载

* 类中可以通过实现相应的魔法方法，来实现对象的比较运算（<、>）和加减运算（+、-）
* 实现后就可以通过运算符'>'和'<'来判断对象的大小。通过'+'和'-'来求两个对象的和和差
* 怎么重载：
        > --> __gt__
        < --> __lt__
        + --> __add__
        - --> __sub__
        
        class Student:
        	def __init__(self, name='', age=0, score=0):
        		self.name = name
        		self.age = age
        		self.score = score
        		# 重载'>'符号
        		# 对象1 > 对象2
        		# self ->对象1；other -> 对象2
         	def __gt__(self, other):
         		# 怎么实现就看怎么判断大于的
         		return self.age > other.age
        	# 重载'<'符号
        	def __lt__(self, other):
        		return self.score < other.score
         		# 说明：如果大于比较和小于比较的内容是一样的，只需要重载其中的一个符号就可以了
        		# 重载'+'
            def __add__(self, other):
        		return self.score + other.score
            	# 重载'-'
            def __sub__(self, other):
        		return self.score - other.score
        stu1 = Student('小明', 18, 90)
        stu2 = Student('小花', 20, 80)
        stu3 = Student('aa',23,67)
        print(stu1 > stu2)  # False
        print(stu1 - stu2)  # 10
        print(stu1 + stu2)  # 170

##3、多继承

* python支持多继承
        class Animal:
        	def __init__(self,age=0,name=''):
        		self.age = age
        		self.name = name
        
        class Fly:
        	def fly(self):
        		print('飞起来')
        		# Bird类同时继承Animal类和Fly类
        class Bird(Animal,Fly):
        		pass
        bird1 = Bird()
        print(bird1.age)
        bird1.fly()
* 注意：实际开发中，不到万不得已不建议使用多继承

##4、对象的内存管理

* 对象值是存在堆中的，python自动去回收的
* 掌握：对象到底什么时候才会被销毁（回收）
* 栈中的内存是系统自动创建自动销毁的，不需要管理。平时说的内存管理指的是对堆中的内存的管理。
* python中能够存到堆里面的数据，全是对象
* python中管理内存的机制：
  >python是通过引用计数来管理内存的：就看一个对象的引用计数的值是否为0，为0就销毁
  >让一个变量存储对象的地址，那么这个变量就是对象的一个引用；如果变量存别的值或者删除这个变量，都会让这个引用消失。
* 应用：如果想要对象提前被销毁，就删除其所有的引用
        class Person:
        	def __init__(self,name='', age=0, scores=[]):
        		self.name = name
        		self.age = age
        		self.scores = scores
        p1 = Person()
* p1是一个变量，变量存的是对象的地址；变量p1本身是在栈里面的
* Person()返回值才是对象

##6、包的应用

* 函数 --->对实现功能的代码的封装
* 类 --->对属性和方法进行封装
* 模块 --->对多个函数或者多个类进行封装
* 包 --->对多个模块进行封装
* 举例：对时间操作的相关功能
  >1.日期对应的时间（年月日 -> 获取当天的时间/获取指定哪一天对应的星期/计算哪一年是闰年）
  >2.时分秒（秒钟/计算小时数/分数/时间相加）
  >3.时间戳（时间转换、时间加密）
* 通过 from - import - 或 import - 导入包的内容

#三十六、pygame

    import pygame

## 1.初始化

    pygame.init()

## 2.创建窗口

* set_mode((宽，高)) --->单位是像素
        screen = pygame.display.set_mode((600, 400))

##3.设置填充颜色

* 颜色值（是由计算机的三原色组成-->红、绿、蓝），简称RGB。我们能使用的所有的颜色都可以通过RGB值来表示。
* RGB值的表示方式：
  >a.（red值，green值，blue值）值都是数字：0-255  (255,0,0)->红色 （255,255,255）->白色
  >b.十六进制的RGB值  #ff0000->红色   #000000->黑色  #00ff00->绿色
        screen.fill((233, 233, 233))

## 4.显示图片/文字/图形


###1、显示图片

>a.创建一个图片对象
    image = pygame.image.load('./files/1.jpg')

>b.获取图片的大小
* (width,height) = 图片对象.get_size()
        print(image.get_size())
>c.对图片进行缩放
* 将指定的图片，变成指定的大小，返回一个新的图片对象
* pygame.transform.scale(图片对象, (宽度, 高度)
        image1 = pygame.transform.scale(image, (300, 200))

>d.对图片进行旋转
* pygame.transform.rotate(图片对象,旋转角度)
* 角度：0-360的度数值
        image2 = pygame.transform.rotate(image1, 90)
>e.对图片进行旋转缩放
* pygame.transform.rotozoom(图片对象, 缩放角度, 缩放倍数)
        image3 = pygame.transform.rotozoom(image2, 270, 0.8)
>d.将对象添加到窗口对象中
* blit(需要添加到窗口的对象,坐标)
        screen.blit(image3, (150, 100))

###2、显示文字

>a.创建字体对象
* SysFont(系统字体大小，字体大小)
* pygame.font.Font(字体文件地址，字体大小)
        # font = pygame.font.SysFont('Times', 50)
        font = pygame.font.Font('./files/aa.ttf', 50)
>b.根据字体创建文字对象
* font.render(文字，是否平滑，颜色)
        text = font.render('hello python, 你好 世界！', True, (255, 0, 0))
>c.将文字对象添加到窗口上
    screen.blit(text, (80, 170))

###3、画图形

>a.画线
* line(外观对象，线的颜色，起始点，终点,线的宽度)
        pygame.draw.line(screen, (0, 0, 255), (100, 100), (300, 100), 5)
        pygame.draw.line(screen, (0, 0, 255), (100, 200), (300, 200), 5)
* lines(外观对象，线颜色，是否闭合，点的列表)
* 第三个参数：False-->不闭合 ； True-->闭合
        pygame.draw.lines(screen, (255, 0, 0), True, [(10,40),(60,40),(30,80)],3)
>b.画矩形
* pygame.draw.rect(外观对象, 颜色, 范围, 线宽 )
* 范围：告诉位置和大小-->(x,y,width,height)
* 线宽：线宽为0时就会填充矩形
        pygame.draw.rect(screen, (0, 255, 0),(300,200,100,80) ,0 )
>c.画弧线
* pygame.draw.arc(外观对象，颜色，范围，起始角度，终止角度，线宽)
        from math import pi
        pygame.draw.arc(screen, (255, 255, 0), (150, 100, 200, 200), pi/2, pi, 3)

## 4.显示在屏幕上

    pygame.display.flip()
    # pygame.display.update()

##5.让窗口停留

    while True:
    	for event in pygame.event.get():
    		# 关闭事件
        	if event.type == pygame.QUIT:
            	exit()
            # 鼠标按下事件
        	if event.type == pygame.MOUSEBUTTONDOWN:
            	# 获取鼠标按下的位置
            	print(event.pos)
            	print('鼠标按下')
        	# 鼠标弹起事件
        	if event.type == pygame.MOUSEBUTTONUP:
            	# 获取鼠标弹起的位置
            	print(event.pos)
            	print('鼠标弹起')
        	# 鼠标移动事件
        	if event.type == pygame.MOUSEMTTON:
            	print('鼠标移动')


#三十七、正则表达式

* 正则表达式主要用于字符串查找、匹配和分割

##1、正则符号

>不带任何正则符号的正则表达式
> .--> 匹配任意的字符
> \w-->匹配字母、数字、下划线
> \s-->匹配空白字符（包括空格(\r)、制表符(\t)和回车(\n)等）
> \d-->匹配数字
> \b-->匹配单词边界（字符串的开始和结束、空白、标点符号、括号、~等）
* 注意：\b是不能匹配出结果的，只是对需要出现的边界的要求(遇到\b的时候一定要注意\b后面的字符必须是单词的边界才会成功)
> ^ -->匹配开头
> $ -->匹配字符串结束
> \相应的大写字母-->\相应的小写字母的功能取反
> []-->匹配[]中任意的一个字符
* []中可以是任意的字符，也可以是正则符号.一个[]只能匹配出一位字符
> [^]-->匹配不在[]中的任意的一个字符
> ' * ''   -->匹配0次或者多次
> '+''   --> 匹配1次或者多次
> '?''   -->匹配0次或者1次
> {N}-->匹配N次
> {M,}-->匹配至少M次
> {M,N}-->匹配至少M次，最多N次
> | -->分之（相当于逻辑运算符中的or）
> '*?''  -->重复任意次，尽可能少的匹配
    print(re.match(r'a*?', 'aaabcd'))  # match=''
> +? --->重复一次或者多次，尽可能少的匹配
* 总结？:就是在重复多次的匹配总如果后面加？，匹配的时候以能匹配的最少次数去匹配
* 注意：正则表达式中如果需要使用有特殊功能的字符，需要使用'\'进行特殊说明
        . --> \.    * --> \*    + --> \+   [ --> \[   ] --> \]
* []字符集中的特殊字符不需要加'\'来说明其为一个普通字符功能

##2、正则函数

>a. compile:将正则表达式字符串编译成正则对象（就可以去调用相关的正则表达式对象方法）
    import re
    result = re.compile(r'\d\d[a-zA-Z]{2}')
    print(type(result))  # <class '_sre.SRE_Pattern'>
>b. match
>>1.  re.match(正则表达式字符串/对象，要匹配的字符串)
>>2.  正则表达式对象.match(要匹配的字符串)
* 用指定的正则表达式和指定的字符串进行匹配，如果匹配成功就返回匹配对象，否则返回None
        result = re.match(r'a\dd.', 'a2dlhuhh')
* 获取匹配结果在原字符串中的范围
        print(result.span())   # (0, 4)
* 获取匹配开始的位置和结束的位置
        print(result.start(), result.end())   # 0 4
* 获取匹配的结果
        print(result.group())   # a2dl
* 获取原字符串
        print(result.string)  # a2dlhuhh
>c. search
>>1.  re.search(正则表达式/对象，指定的字符串)
>>2.  对象.search(指定的字符串)
* 在指定的字符串中，去查找第一个指定正则表达式匹配的字符串.如果找到了就返回匹配对象，否则返回None
        result = re.search(r'a\dc', 'wfwfa3cdef')
        print(result)  # <_sre.SRE_Match object; span=(4, 7), match='a3c'>
>d. findall
>>re.findall(正则表达式/对象,指定的字符串)
* 获取指定字符串中，所有满足正则表达式的子串。返回值是一个列表。
        result = re.findall(r'a\dc', 'dwa3cfffwa7cdw')
        print(result)   # ['a3c', 'a7c']
        练习：获取一个字符串中所有以'ing'结束的单词
        result = re.findall(r'[a-zA-Z]*ing\b', 'I love singing and dangcing')
        print(result)
>e. split
>>1.  re.split(正则表达式/对象,指定的字符串,最大拆分数)
    最大拆分数：拆分数量，默认是0. 0-->代表全部拆分
>>2.  正则对象.split(指定的字符串)
    result = re.compile(r'[,\s]').split('abc,bcd,amm,ssff affefe erefef')
    print(result)
    result = re.compile(r'[，。]').split('床前明月光，疑是地上霜。举头望明月，低头思故乡。')
    del result[-1]
    print(result)  # ['床前明月光', '疑是地上霜', '举头望明月', '低头思故乡']
>f. sub
>>re.sub(正则表达式，替换字符串，原字符串)-->替换后原字符串不变，返回一个新的字符串
* 将指定字符串中的指定的子串替换成其它的字符串
        删除字符串'abdf nbdafwfwffwaalmlafkle'中的'a'和'b'
        result = re.sub(r'[ab]', '', 'abdf nbdafwfwffwaalmlafkle')
        print(result)
* 注意：正则表达式中有分组，findall的时候，只获取匹配结果中和分组内容相匹配的内容。


#三十八、获取网络数据

* python中使用第三方库requests来获取网络数据
        import requests

##1. 确定请求的地址(url)

* GET传参的两种方式：
  >a.直接拼接在url后面（?参数1=值&参数2=值2....）
  >b.给get函数中的第二个参数传参（{参数:值, 参数2:值2...}）
      # url = 'https://www.apiopen.top/satinApi?type=1&page=1'
      url = 'https://www.apiopen.top/satinApi'

##2.通过GET方式请求数据,请求结束后会返回响应

    response = requests.get(url,{'type': 1, 'page': 1})

##3.获取数据内容

>a.获取字符串形式的数据
    print(type(response.text), response.text)
>b.获取json格式的数据
    reslut = response.json()
    print(type(reslut), reslut)
>c.获取二进制形式的数据
    data = response.content
    print(type(data), data)

#三十九、socket _ sever

* socket又叫套接字，我们把进行网络通信的一段就叫一个套接字
* socket编程，就是通过程序实现通信的两端（服务器和客户端）
* python中支持socket有三种，分别是基于TCP、UDP和IP的，叫做TCP套接字、UDP套接字和原始套接字
        import socket
* 基于TCP的服务器端

##1.创建套接字对象，并且指定服务类型

* family:
        AF_INET-->ipv4
        AF_INET6-->ipv6
* type:
        SOCK_STREAM-->TCP

        server = socket.socket(family=socket.AF_INET,type=socket.SOCK_STREAM)

##2.绑定IP地址和端口

* 地址：(IP地址，端口)
* IP地址：服务器所在的硬件的IP地址
* 端口：不同的端口绑定不同的服务，同一个时间同一个端口只能绑定一个服务
* 端口的范围0-65535，但是小于等于1024的端口叫“著名端口”，用于绑定著名服务（比如http服务，邮件服务等），最好不要用
        server.bind(('10.7.154.101', 16345))

##3.监听访问

    server.listen()
    print('开始监听....')
    # 让服务器一直运行，等待访问
    while True:
        # 当有客户端访问当前服务器后就建立连接
    	connet, addr = server.accept()  # 当有一个客户端来连接当前服务器的时候才会执行
    	print('=========')
    	while True:
        	# 通过会话给客户端发送消息
        	# 发送的内容必须是二级制数
        	#字符串转二进制：字符串.encode('utf-8')
        	#二进制转字符串：二进制数据.decode('utf-8')
        	message = input('>>>')
        	connet.send(message.encode('utf-8'))
        	# 接收客户端发送给服务器的消息
        	data = connet.recv(1024)
        	print(data.decode('utf-8'))
        # 关闭连接
        # connet.close()

#四十、socket _ 客户端

    import socket

##1.创建套接字对象

    client = socket.socket(family=socket.AF_INET,type=socket.SOCK_STREAM)

##2.连接服务器

    client.connect(('10.7.154.62', 12346))
    while True:

##3.接收服务器返回的数据

* 1024是接收数据的大小
        data = client.recv(1024)
        print(data.decode('utf-8'))

##4.给服务器发送数据

    message = input('>>>')
    client.send(message.encode('utf-8'))

