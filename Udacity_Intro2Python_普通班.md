# Udacity Intro2Python 课程知识点回顾与拓展
作者：陈啟超     修订：刘淑雯

# 暖场

1. 回顾本周学习的内容

2. 助教自我介绍

   此部分助教大大们可自由发挥，与学生建立信任感，可参考：

   Ø   介绍个人

   Ø   你的学习/工作背景、擅长领域

   Ø   工作之外的你

   Ø   聊聊自己是如何学习编程的，突出刻意练习的重要性

3. 邀请学员分享

   让每一个学员列出3条自己在本周内最有收获的知识点，发送在聊天框中，并对其中的几个做出简单点评。

   参考的内容：

   Ø   在学习中，掌握到的debug技巧；

   Ø   掌握的Python某一个语法知识；

   Ø   或者说一说学习过程中对Uda印象最深刻的部分。 

# 猜一猜之Python小趣闻

主要目的：两真一假游戏化介绍Python的历史与趣闻，吸引学生兴趣

以下3个问题有2个为真、1个为假，请同学们猜猜哪些是真的，哪些是假的。

1. **Python是根据卢浮宫的一个作品命名的（错）**

解释：Python是Guido van Rossum创立的，1989年，为了打发圣诞节假期，Guido开始写Python语言的编译/解释器。van Rossum希望选择一个“简短、独特而且略带神秘色彩”的字眼。他从著名英国喜剧团体Monty Python（巨蟒）身上得到了灵感，他本人也是该剧团的铁杆粉丝。而不是直接根据卢浮宫的《阿波罗战胜了巨蛇》命名。

2. **Python最有生命力的地方在于丰富的库（对）**

解释：Python 语言号称自带电池(Battery Included)，寓意是 Python 语言的类库非常的全面，包含了解决各种问题的类库。无论实现什么功能，都有现成的类库可以使用。如果一个功能比较特殊，标准库没有提供相应的支持，那么，很大概率也会有相应的开源项目提供了类似的功能。合理使用 Python 的类库和开源项目，能够快速的实现功能，满足业务需求。

3. **输入’import this’后会出现《Python之禅》这首诗，指导我们使用Python编程的准则（对）**

```python
>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than right now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

Python之禅 by Tim Peters

优美胜于丑陋（Python 以编写优美的代码为目标）

明了胜于晦涩（优美的代码应当是明了的，命名规范，风格相似）

简洁胜于复杂（优美的代码应当是简洁的，不要有复杂的内部实现）

复杂胜于凌乱（如果复杂不可避免，那代码间也不能有难懂的关系，要保持接口简洁）

扁平胜于嵌套（优美的代码应当是扁平的，不能有太多的嵌套）

间隔胜于紧凑（优美的代码有适当的间隔，不要奢望一行代码解决问题）

可读性很重要（优美的代码是可读的）

即便假借特例的实用性之名，也不可违背这些规则（这些规则至高无上）

不要包容所有错误，除非你确定需要这样做（精准地捕获异常，不写 except:pass 风格的代码）

当存在多种可能，不要尝试去猜测

而是尽量找一种，最好是唯一一种明显的解决方案（如果不确定，就用穷举法）

虽然这并不容易，因为你不是 Python 之父（这里的 Dutch 是指 Guido ）

做也许好过不做，但不假思索就动手还不如不做（动手之前要细思量）

如果你无法向人描述你的方案，那肯定不是一个好方案；反之亦然（方案测评标准）

命名空间是一种绝妙的理念，我们应当多加利用（倡导与号召）

\--------------------- 

作者：赖勇浩 

来源：CSDN 

原文：https://blog.csdn.net/gzlaiyonghao/article/details/2151918 

版权声明：本文为博主原创文章，转载请附上博文链接！

# Part1 - 使用Python前的几个注意事项

## 基础知识回顾
在学习这门 Python 课程的过程中，需要注意几个事项：
### **1.Python 区分大小写。**
一些简单的大小写混淆错误有事很有可能就是怎么都找不出来的error，如：
```
pd.dataframe()    #错误
pd.DataFrame()    #正确
```
**分享：在编程的过程中，你还能举出什么因为大小写混淆而代码语句出错的例子吗？**
### **2.空格很重要。**
python不使用一些编程语言使用的符号作为语句块的划分（如 '()' 或 '{}' 等等），而是使用空格缩进来表示语句块，缩进空格使用不当会导致代码的无法运行，如：
```
#正确
for i in range(10):
    for j in range(10):
        x+=1
#错误
for i in range(10):
for j in range(10):
x+=1
```
### **3.通过报错 Error Message 了解错误信息。**
再高明的程序员也很难保证项目一次就能直接运行，所以当代码运行错误时，无须惊慌，仔细分析Error Message提供的信息，再找出bug做出代码修正。
## 知识拓展
### 1.Python3和Python2的关系与区别
Python的3​.0版本，常被称为Python 3000，或简称Py3k。相对于Python的早期版本，这是一个较大的升级。
为了不带入过多的累赘，Python 3.0在设计的时候**没有考虑向下相容**。
许多针对早期Python版本设计的程式都无法在Python 3.0上正常执行。
为了照顾现有程式，**Python 2.6**作为一个过渡版本，基本使用了Python 2.x的语法和库，同时考虑了向Python 3.0的迁移，允许使用部分Python 3.0的语法与函数。
新的Python程式建议使用Python 3.0版本的语法。
大多数第三方库都正在努力地相容Python 3.0版本。即使无法立即使用Python 3.0，也建议编写相容Python 3.0版本的程式，然后使用Python 2.6, Python 2.7来执行。
[Python 3.0的变化主要在这几个方面](http://www.runoob.com/python/python-2x-3x.html)

### 2.Python是脚本语言，那么什么是脚本语言呢
脚本语言的脚本这一说法缘于Unix操作系统，目的是让其**批量的，按照既定的方式去做一些事情**，就想照着剧本做事一样。英文中的script就是剧本的意思，中文对应的词就是剧本，脚本。脚本就是剧本意思。
脚本语言的“优势”，其实只在于它**不需要事先“编译”**。开发**快**，调试、测试都更加**便捷**。
# Part2 - 数据类型和运算符
在本章节，主要对Python基本数据类型、运算符、内置函数、复合数据结构等方面进行介绍。
## 基础知识回顾
### **1.算术运算**
* + 加
* - 减
* * 乘
* / 除
* % 取模（相除后的余数）
* ** 取幂**（注意 ****^**** (XOR)并不执行该运算，你可能在其他语言中见过这种情形）**
* // 相除后向下取整到最接近的整数
```
#练习：
#现有面积为8的地砖，用多少块才能铺满长为10，宽为5的长方形的地面？     
print( (10*5) / 8 )
```

### **2.变量**
变量是一段有名字的连续存储空间。在源代码中通过定义变量来申请并命名这样的存储空间，并通过变量的名字来使用这段存储空间。
python使用** “变量名 = 值”**  或  **“变量名1,变量名2,...,变量名n = 值1,值2,...,值n”**的等式形式为变量存储值，但不能左右对调，如：
```
#正确
x = 3
y,z = 4,5

#错误
3 = x
```
除了要设定具有描述性的变量名称之外，在 Python 中命名变量时，还需要注意以下几个事项：
* 只能在变量名称中使用常规字母、数字和下划线。不能包含空格，并且需要以字母或下划线开头。
* **不能使用保留字或内置标识符**，它们在 Python 中具有重要含义。
* 在 python 中，变量名称的命名方式是全部使用小写字母，并用下划线区分单词。
```
#练习：
#下面哪些变量的赋值正确

my pen = 2
MYPEN = 2
my_pen = 2
myPen = 2
```

### **3.赋值运算符**
赋值运算符是运算符操作的代码简写形式，当要对同一变量进行连续的操作时，使用赋值运算符将会较为简便。常用的赋值运算符有 += 、-=、*= 等。

### **4.整点数与浮点数**
数字值可以用到两种 python 数据类型：
* **int** - 表示整数值
* **float** - 表示小数或浮点数值

你可以通过以下语法创建具有某个数据类型的值：
```
x = int(4.7)   # x结果为4，注意：int()不等同于四舍五入，而是直接将小数点后舍去
y = float(4)   # y结果为4
```
你可以使用函数 type 检查数据类型：
```
print(type(x))
#int
print(type(y))
#float
```
因为 0.1 的浮点数（或近似值）实际上比 0.1 稍微大些，当我们将好几个这样的值相加时，可以看出在数学上正确的答案与 Python 生成的答案之间有区别。
```
print(.1 + .1 + .1 == .3)
#False
```

```
#练习：
#以下实际问题中的数字分别为什么类型

#1.Mike高1.75m    (float)
#2.今天进行1KM跑步测试   (int)
```

### **5.****布尔型运算符、比较运算符和逻辑运算符**
布尔数据类型存储的是值 True 或 False，通常分别表示为 1 或 0。
通常有 6 个比较运算符会获得布尔值：
| **符号使用情况**   | **布尔型**   | **运算符**   |
|:----|:----|:----|
| 5 < 3   | False   | 小于   |
| 5 > 3   | True   | 大于   |
| 3 <= 3   | True   | 小于或等于   |
| 3 >= 5   | False   | 大于或等于   |
| 3 == 5   | False   | 等于   |
| 3 != 5   | True   | 不等于   |

**思考：为何使用 '==' 进行逻辑判断而不是 '='**

你需要熟悉三个逻辑运算符：
| **逻辑使用情况**   | **布尔型**   | **运算符**   |
|:----|:----|:----|
| 5 < 3 and 5 == 5   | False   | and - 检查提供的所有语句是否都为 True   |
| 5 < 3 or 5 == 5   | True   | or - 检查是否至少有一个语句为 True   |
| not 5 < 3   | True   | not - 翻转布尔值   |

### **6.字符串**
使用双引号 " 或单引号 ' 定义字符串。
```
student_name = 'Mike'
professor_name = "Blake"
```
可以在字符串中使用 \，以包含其中一种引号：
```
notice = 'Mike\'s book m**i**ssed.'
```
还可以对字符串执行其他多种操作。
```
first_word = 'Hello'
second_word = 'World'
print(first_word + second_word)

#HelloThere 字符串的连接

print(first_word + ' ' + second_word)

#Hello There

print(first_word * 5)

#HelloHelloHelloHelloHello 字符串的重复

print(len(first_word))

#5  使用len()获取字符串长度

print(first_word[0])

#H  字符串的索引
```

```
#练习：
#以下代码运行结果是什么

student_name = 'Mike'
professor_name = "Blake"
print((student_name+professor_name)*2)
#MikeBlakeMikeBlake
```

### **7.类型和类型转换**
不同的变量数据类型能执行的运算操作也不一样，因此在数据操作前应该先检查数据类型，在必要时进行类型转换。
* 使用type()来检查你所处理的任何变量的数据类型。
* 使用int()、float()、str()等方法进行类型转换
```
type(age) 
#int
type(ticket_price)
#float
message = "Somebody who is " + str(age) + "years old will pay $" + str(ticket_price) + "to ride the bus."
print(message) #将变量统一成str字符串形式，完成输出
```

```
#练习：
print(2 + '2')
#结果为什么
#TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

### **8.字符串方法**
### ![图片](https://s3.cn-north-1.amazonaws.com.cn/u-img/0f8956e4-5f32-4710-ae99-24b5afd01c06)
每个方法都接受字符串本身作为该方法的第一个参数。但是，它们还可以接收其他参数。以下是一些示例：
* captialize()和title() 
```
>>> a = "this is a test string"
>>> a.title()
'This Is A Test String'
>>> a.capitalize()
'This is a test string'
```
* a.islower()     判断字符串a是否全为小写       
* a.istitle()        判断字符串a是否首字母为大写
* a.count("b")   在a中查询b出现的次数     如 "aasddwdc".count("d") = 3
* a.find("d")    在a中查询第一个d出现的索引  如 "aasddwdc".find("w") = 5

任何专业人士都无法记住所有方法，因此知道如何通过文档查询答案非常重要。掌握扎实的编程基础使你能够利用这些基础知识查询文档，并且构建的程序比死记硬背所有 python 可用函数的人士构建的程序强大得多。

### **9.列表**
使用方括号创建列表。列表可以包含我们到目前为止所学的任何数据类型并且可以混合到一起。
```
lst_of_random_things = [1, 3.4, 'a string', True]
```
这是一个包含 4 个元素的类别。在 python 中，所有有序容器（例如列表）的起始索引都是 0。我们可以编写以下代码获取列表中的值：
```
lst_of_random_things[0] #显示 1 lst_of_random_things[len(lst_of_random_things)] #报错

lst_of_random_things[len(lst_of_random_things) - 1] #显示 true

lst_of_random_things[-1] #True

lst_of_random_things[-2] #a string
```

**列表切片**：切片功能从列表中提取多个值。在使用切片功能时，务必注意，下限索引包含在内，上限索引排除在外。
```
lst_of_random_things[1:2]   #[3.4]

#如果你要从列表的开头开始，也可以省略起始值。 
lst_of_random_things[:2]  #[1, 3.4]

#或者你要返回到列表结尾的所有值，可以忽略最后一个元素。
lst_of_random_things[1:]  #[3.4, 'a string', True]

#切片可以使用负索引 eclipse_dates[-3:] 代表列表后三个元素

#in 和 not in 返回一个布尔值，表示某个元素是否存在于列表中，或者某个字符串是否为另一个字符串的子字符串。 

'this' in 'this is a string'   #True 
5 not in [1, 2, 3, 4, 6]  #True
```

**可变性**是指对象创建完毕后，我们是否可以更改该对象。如果对象（例如列表或字符串）可以更改，则是**可变的**。但是，如果无法更改对象以创建全新的对象（例如字符串），则该对象是**不可变的**。
```
my_lst = [1, 2, 3, 4, 5]
my_lst[0] = 'one'
print(my_lst)
#['one', 2, 3, 4, 5]

greeting = "Hello there" 
greeting[0] = 'M' #报错
```

### **10.一些列表方法**
1. max() 返回列表中的最大元素。最大元素的判断依据是列表中的对象类型。数字列表中的最大元素是最大的数字。字符串列表中的最大元素是按照字母顺序**(首字母)**排序时排在最后一位的元素。因为 max() 函数的定义依据是大于比较运算符。如果列表包含不同的无法比较类型的元素，则 max() 的结果是 undefined。 
2. min() 返回列表中的最小元素。它是 max() 函数的对立面，返回列表中的最小元素。 
3. sorted() 返回一个从最小到最大**(字母按首字母)**排序的列表副本，并使原始列表保持不变。
4. sum()计算列表内元素之和
5. 列表重新赋值后原变量可变，字符串不变

![图片](https://images-cdn.shimo.im/08zdYVRWSBInRC5q/image.png!thumbnail)![图片](https://images-cdn.shimo.im/hpxC7MvD6foyxQoF/image.png!thumbnail)
1. "连接符".join()用于连接列表元素       
```
name = "-".join(["García", "O'Kelly"]) 
print(name) #输出: García-O'Kelly
```
2. 列表.append("a") 会将元素a添加到列表末尾

### **11.元组**
元组是另一个实用容器。它是一种**不可变有序**元素数据类型。通常用来存储相关的信息。
元组()：tuple = (a,b,c)  也可不用()直接  tuple = a,b,c    
不可变有序 ，无法直接排序 ，可通过索引查询
```
location = (13.4125, 103.866667) 
print("Latitude:", location[0])
print("Longitude:", location[1])
```
元组还可以用来以紧凑的方式为多个变量赋值。
```
dimensions = 52, 40, 100
length, width, height = dimensions
print("The dimensions are {} x {} x {}".format(length, width, height))
```
如果我们不需要直接使用 dimensions，可以将这两行代码简写为一行，一次性为三个变量赋值。
```
length, width, height = 52, 40, 100
print("The dimensions are {} x {} x {}".format(length, width, height))
```

```
#练习：
#以下代码的输出是什么？
tuple_a = 1, 2
a, b = tuple_a
tuple_b = (1, 2)

print(tuple_a == tuple_b)  #True
print(a == tuple_a[0])  #True
```

### **12.集合**
集合形如set(列表)，无序(**不支持索引与切片**)，可添加，**内部元素不重复**  
集合是一个包含唯一元素的可变无序集合数据类型。集合的一个用途是快速删除列表中的重复项。(由于集合不支持元素重复)
```
numbers = [1, 2, 6, 3, 1, 1, 6]
unique_nums = set(numbers)
print(unique_nums)
#{1, 2, 3, 6}
```
支持in来检测元素是否存在   
可使用.add(元素)来无序添加元素(不一定添加到尾部)，.pop()**随机**删除一个元素
```
#练习
#判断运行下列代码后新添加元素的位置是否可定？

a = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]
b = set(a)
b.add(5)
```

**思考：使用代码 a = (1,2,3) 和  b = set(1,2,3) 和 c  = set([1,2,3])分别对a,b,c定义后，a,b,c各自的type是什么？****（a元组,b出错,c集合）**

### **13.字典**
字典{}(形似json)是可变数据类型，其中存储的是唯一键到值的映射。下面是存储元素和相应原子序数的字典。
```
elements = {"hydrogen": 1, "helium": 2, "carbon": 6}
```
可使用键查询添加删除
```
print(elements["helium"]) 
elements["lithium"] = 3 
```
使用关键字 in 检查值是否在字典中。字典有一个也很有用的相关方法，叫做 get。get 会在字典中查询值，但是和方括号不同，如果没有找到键，get 会返回 None（或者你所选的默认值）。
```
print("carbon" in elements)  #True
print(elements.get("dilithium"))  #None
```
如果你预计查询有时候会失败，get 可能比普通的方括号查询更合适，因为错误可能会使程序崩溃。
**字典的键必须是不可变的**，即所属的类型必须不可变。键可以是字符串、元组，不能是列表。

### **14.复合数据结构**
我们可以在其他容器中包含容器，以创建复合数据结构。例如，下面的字典将键映射到也是字典的值！
```
elements = {"hydrogen": {"number": 1,
                         "weight": 1.00794,
                         "symbol": "H"},
              "helium": {"number": 2,
                         "weight": 4.002602,
                         "symbol": "He"}}
```
我们可以如下所示地访问这个嵌套字典中的元素。
```
helium = elements["helium"]  # get the helium dictionary
hydrogen_weight = elements["hydrogen"]["weight"]  # get hydrogen's weight
```

### **15.各种数据结构的区别**
|    | 列表   | 元组   | 集合   | 字典   |
|:----|:----|:----|:----|:----|
| 是否有序   | 是   | 是   | 否   | 否   |
| 是否可直接排序   | 是  sorted()   | 否   | 否   | 是  sorted()   |
| 是否可重复   | 是   | 是   | 否   | 是   |
| 是否可变   | 是   | 否   | 是   | 是   |
| 添加   | .append()   | 不可变   | .add()   | 方括号['键名']=值   |

**分享：你是否有一些方法对无法直接使用内置方法( sort()/sorted() )进行排序的数据结构进行人工排序？**
## 知识拓展
### 1.列表切片进阶
分片操作还可以接受第三个参数，其代表的是步长，默认情况下该值为1，来试试将其改成2会有什么效果？
```
list1 = [1,2,3,4,5,6,7,8,9]
list1[0:9:2]
#[1,3,5,7,9]
```
如果将步长改成2，那么**每前进两个元素**才取一个出来。其实还可以直接写成**list1[: : 2]**。如果步长的值是负数，例如-1，结果会怎样？
```
list1[::-1]
#[9,8,7,6,5,4,3,2,1]
```
### 2.列表与操作符
此前学过的大多数操作符都可以运用到列表上：
```
list1 = [123]
list2 = [234]
list1>list2
#False

list3 = ['abc']
list4 = ['bcd']
list3<list4
#True
```
单个元素的列表可直接正常进行大小比较，那如果列表中不止一个元素呢？
```
list1 = [123,456]
list2 = [234,123]
list1>list2
#False
```
list1列表中元素之和123+456=579，大于list2中元素之和234+123=357，然而最后结果却显示list1并不大于list2，所以并不能这样进行比较。
注：当列表包含多个元素的时候，默认是**从第一个元素开始比较**，只要有一个PK获胜，就算整个列表获胜。如本例中，两个list各自的第一个元素123<234，所以算list2更大。所以在多元素列表的比较时，**直接使用操作符需谨慎**。
我们知道字符串可以用加号(+)来进行拼接，用乘号(*)来复制自身若干次。它们在列表身上也是可以实现的：
```
list1 = [123,456]
list2 = [234,123]
list3 = list1 + list2
#[123,456,234,123]

list4 = list1 * 2
#[123,456,123,456]
```
### 3.Python的转义字符及含义
| **符号**   | **说明**   | **符号**   | **说明**   |
|:----:|:----|:----:|:----|
| \'   | 单引号   | \r   | 回车符   |
| \''   | 双引号   | \f   | 换页符   |
| \a   | 发出系统响铃声   | \o   | 八进制数代表的字符   |
| \b   | 退格符   | \x   | 十六进制数代表的字符   |
| \n   | 换行符   | \0   | 表示一个空字符   |
| \t   | 横向制表符(TAB)   | \\   | 反斜杠   |
| \v   | 纵向制表符   |    |    |

### 4.字典的一些内置方法
* fromkeys()

用于创建并返回一个新的字典，它有两个参数：第一个参数是字典的键，第二个参数可选，是传入键对应的值，如果不提供默认为None。
```
dict1 = {}
dict1.fromkeys((1,2,3))
#{1: None, 2: None, 3: None}

dict2 = {}
dict2.fromkeys((1,2,3), 'Number')
#{1: Number, 2: Number,3 :Number}

dict3 = {}
dict3.fromkeys((1,2,3),('one','two','three'))
#{1: ('one','two','three'), 2: ('one','two','three'), 3: ('one','two','three')}
```
可见，fromkeys()**不会分别赋值**，但是将字典**初始化**或为每一个key**赋同样的值**十分方便。

* clear()

用于清空一个字典
```
dict3
#{1: ('one','two','three'), 2: ('one','two','three'), 3: ('one','two','three')}
dict3.clear()
dict3
#{}
```

* update()

用于字典的更新
```
fruit = {'apple': 10, 'banana': 15}
fruit.update(apple = 16)
#{'apple': 16, 'banana': 15}
```
### 5.不可变集合
有时候我们希望集合中的数据更具稳定性，像元组一样不能被随意增加或删除其中的元素。那么我们可以定义不可变集合，使用**frozenset()函数**。
```
set1 = frozenset({1,2,3,4,5})
set1.add(6)
#AttributeError: 'frozenset' object has no attribute 'add'
```
# Part3 - 控制流
## 基础知识回顾
### **1.条件语句**
if 语句是是一种条件语句，根据条件为 true 还是 false 运行或执行相关代码。下面是一个简单的示例：
```
if phone_balance < 5:
    phone_balance += 10
    bank_balance -= 10
```
条件用布尔表达式指定，结果为 True 或 False。条件为 True 时将执行缩进代码块。如果条件为False，这个 if 块中的代码将被跳过。
除了 if 条件之外，if 语句经常还会使用另外两个可选条件：elif(**注意不是else if**)和else。
elif 条件用来检查其他条件（前提是 if 语句中之前的条件结果为 False）,可以使用多个 elif 块处理不同的情形。 
else 条件，它必须位于 if 语句的末尾。该条件语句不需要条件。如果 if 语句中所有前面的语句结果都为 False 时，将运行 else 块中的代码。
条件语句以及符合条件运行的语句块完全使用缩进进行控制，例如，if 语句使用缩进告诉 Python 哪些代码位于不同条件语句里面，哪些代码位于外面。在 Python 中，缩进通常是四个空格一组。请严格遵守该惯例，因为更改缩进会完全更改代码的含义。

```
#练习
#请使用if-elif-else语句将学生的成绩按0~60、60~70、70~90、90~100分为D、C、B、A四个档次 

if 0< score <= 60:
  result = 'D'
elif 60 < score <= 70:
  result = 'C'
elif 70 < score <= 90:
  result = 'B'
elif 90 < points <= 100:
  result = 'A'
else:
  result = 'Wrong score
```
If 语句有时候会使用更加复杂的条件布尔表达式。可能包括多个比较运算符、逻辑运算符，甚至包括算式。对于非常复杂的条件，你可能需要结合使用** ****and****、****or**** 和 ****not**。使用括号可以使运算符组合更清晰。
**请勿使用真价值恒定的True和False进行条件的判断**，会导致判断结果的恒定，如（if False/if True）

### **2.条件布尔表达式**
如果我们在if 语句中使用**非布尔对象**代替布尔表达式，Python 将检查其真假值，判断是否运行缩进代码。默认情况下，Python 中对象的真假值被视为 True，除非在文档中被指定为 False。
以下是在 Python 中被视为 False 的大多数内置对象：
* 定义为 false 的常量：None 和 False
* 任何数字类型的零：0、0.0、0j、Decimal(0)、Fraction(0, 1)
* 空序列和空集合：””、()、[]、{}、set()、range(0)
```
#练习
#一下代码块结果为

if range(0):
  print('a')
elif 1:
  print('b')

#b
```

### **3.For 循环**
```
# iterable of cities
cities = ['new york city', 'mountain view', 'chicago', 'los angeles']

# for loop that iterates over the cities list
for city in cities:
    print(city.title())
```
* 循环的第一行以关键字 for 开始，表示这是一个 for 循环
* 然后是 iteration_variable in iterable，表示正在被遍历的是可迭代的对象，并且用迭代变量表示当前正在被处理的可迭代对象的元素。在此示例中，迭代变量 city 在第一次迭代时将是“new york city”，在第二次迭代时将是“mountain view。
* for 循环头部始终以英文冒号 : 结束。
* for 循环头部之后的是在此 for 循环的每次迭代时运行的缩进代码块。在此块中，我们可以使用迭代变量访问当前正在被处理的元素的值。

你可以随意命名迭代变量。常见模式是为迭代变量和可迭代对象指定相同的名称，但是分别使用**单复数形式**（例如 'city' 和 'cities）

### **4.重要方法range()**
**range(start=0, stop, step=1)**        从start到stop-1       range(4) = [1,2,3,4]       **默认自然数    **
* 如果你在 range() 的括号里指定一个参数，它将用作 'stop' 的值，另外两个参数使用默认值。 

E.g. list(range(4)) 返回 [0, 1, 2, 3] 
* 如果你在 range() 的括号里指定两个参数，它们将用作 'start' 和 'stop' 的值，'step' 将使用默认值。 

E.g. list(range(2, 6)) 返回 [2, 3, 4, 5] 
* 或者你可以为三个参数 'start、stop' 和 'step' 均指定一个值。 

E.g. list(range(1, 10, 2)) 返回 [1, 3, 5, 7, 9]

**注意**，在这些示例中，我们将 range **封装在列表中**。因为 range 本身的输出是一个 range 对象(**print(range(6))输出range(6)**)。我们可以通过将其转换为列表或在 for 循环中遍历它，查看 range 对象中的值集合。
```
#练习
#使用range()来改变列表自身
for i in range(len(usernames)): 
  usernames[i]=usernames[i].lower().replace(' ','_')
#而不直接进行修改
for name in usernames: 
  name = username.lower().replace(" ", "_")            
#name只是一个变量，在这里给name赋了新的值，并不会改变列表的值
```

### **5.While循环**
无限迭代循环是指循环重复未知次数，并在满足某个条件时结束，while 循环正是这种情况。
因此请注意，**给While循环设定合理的循环条件以及跳出循环的方式**，避免程序进入**死循环**耗费资源。

```
card_deck = [4, 11, 8, 5, 13, 2, 8, 10]
hand = []
while sum(hand)  <= 17:
    hand.append(card_deck.pop())
```
这个示例包含两个函数。sum 返回列表中的元素之和，pop 是一个列表方法，它会从列表中删除最后一个元素并返回该元素。
**While**** 循环的组成部分**
* 第一行以关键字 while 开始，表示这是一个 while 循环。
* 然后是要检查的条件。在此示例中是 sum(hand) <= 17。
* while 循环头部始终以冒号 : 结束。
* 该头部之后的缩进部分是 while 循环的主体。如果 while 循环的条件为 true，该循环的主体将被执行。每次运行循环主体时，条件将被重新评估。这个检查条件然后运行循环的流程将重复，直到该表达式变成 false。

**分享：在你编码过程中，是否碰到过死循环的情况，最后你是怎么发现并且解决的呢。**

### **6.Break和Continue**
* break 使循环终止
* continue 跳过循环的一次迭代
```
#练习：
#歌单里有['安静','恰似你的温柔','火锅底料','青藏高原']四首歌，你可以使用方法play()播放音乐，并可以发出指令'下一首'和'停止播放'，请使用适当的方法编写一个简单的播放器。

song_list = ['安静','恰似你的温柔','火锅底料','青藏高原']
command = 'playing'
for i in range(song_list):
    print('开始播放',song_list(i))
    play(song_list(i))
    if command = '下一首':
        print('播放下一首')
        continue
    elif command = '停止播放':
        print('停止播放')
        break  
```

### **7.zip**** 和 ****enumerate**
* zip()可用于合并或拆分列表

list(zip(['a', 'b', 'c'], [1, 2, 3])) 将输出 [('a', 1), ('b', 2), ('c', 3)].
可以如下所示地用 for 循环拆封每个元组。 
```
letters = ['a', 'b', 'c'] 
nums = [1, 2, 3] 
for letter, num in zip(letters, nums): 
    print("{}: {}".format(letter, num)) 
```
除了可以将两个列表组合到一起之外，还可以使用星号拆封列表。 
```
some_list = [('a', 1), ('b', 2), ('c', 3)]
letters, nums = zip(*some_list)
```
* enumerate 是一个会返回元组迭代器的内置函数，这些元组包含列表的索引和值。当你需要在循环中获取可迭代对象的每个元素及其索引时，将经常用到该函数。 
```
letters = ['a', 'b', 'c', 'd', 'e'] 
for i, letter in enumerate(letters): 
    print(i, letter) 
  这段代码将输出： 
  0 a 
  1 b 
  2 c 
  3 d 
  4 e
```
* zip实例：
    * 组装列表并拆分成要求格式的字符串，再保存在新列表中
```
x_coord = [23, 53, 2, -12, 95, 103, 14, -5]
y_coord = [677, 233, 405, 433, 905, 376, 432, 445]
z_coord = [4, 16, -6, -42, 3, -6, 23, -1]
labels = ["F", "J", "A", "Q", "Y", "B", "W", "X"]
points = []
# write your for loop here
for point in zip(labels,x_coord,y_coord,z_coord):
    points.append("{}: {}, {}, {}".format(*point))
for point in points:
    print(point)
```
    * 将列表组装成字典
```
cast_names = ["Barney", "Robin", "Ted", "Lily", "Marshall"]
cast_heights = [72, 68, 72, 66, 76]
cast =dict(zip(cast_names,cast_heights))
print(cast)
```
    * 使用zip进行矩阵的转置
```
data = ((0, 1, 2), (3, 4, 5), (6, 7, 8), (9, 10, 11))
data_transpose =tuple(zip(*data)) # 根据索引将相同索引的值放在一组，如索引为1时拆分为（0，3，6，9）
print(data_transpose)
输出：((0, 3, 6, 9), (1, 4, 7, 10), (2, 5, 8, 11))
```

### **8.列表推导式**
* 列表推倒式：**[操作   for循环]  **

用于对旧列表的元素值进行更改并将每一项添加至新列表
```
capitalized_cities = [] 
for city in cities: 
    capitalized_cities.append(city.title()) 
#可以简写为： 
capitalized_cities = [city.title() for city in cities] 
#将cities中每一项title()后逐项保存至capitalized_cities中
```
    * 使用关键字 if 检查每次迭代中的条件。 
```
squares = [x**2 for x in range(9) if x % 2 == 0]          
#只有if，if必须写在for条件后
```
    * 要添加 else，则需要将条件语句移到列表推导式的开头，直接放在表达式后面 
```
squares = [x**2 if x % 2 == 0 else x + 3 for x in range(9)]     
#有if还有else，if和else放在for条件前
```
* 列表推导式实例：
    * 使用列表推导式创建新的列表 first_names，其中仅包含 names 中的名字（小写形式）。
```
names = ["Rick Sanchez", "Morty Smith", "Summer Smith", "Jerry Smith", "Beth Smith"] 
first_names =[name.split()[0].lower() for name in names]
print(first_names)
```
注：a.split()会将默认根据空字符将字符串分为多个字符串并保存在新的列表中，如"Rick Sanchez".split() = ["Rick","Sanchez"]，其中split()[0] = "Rick"，只有字符串才能调用lower()方法，列表不能直接调用 [http://www.runoob.com/python/att-#string-split.html](http://www.runoob.com/python/att-#string-split.html)

    * 字典的遍历与列表推导
```
scores = {
             "Rick Sanchez": 70,
             "Morty Smith": 35,
             "Summer Smith": 82,
             "Jerry Smith": 23,
             "Beth Smith": 98
          }
passed =[name for name,letters in scores.items() if letters>=65]
#列表使用index , value in dir.items()来遍历列表中的索引与值
print(passed)
```
## 知识拓展
### 1.三元操作符
```
a = x if 条件 else y
```
三元操作符拥有三个操作数，使用三元操作符可以**使用一条语句**完成以下的条件判断和赋值操作：
```
if x < y:
    small = x
else:
    small = y
```
表示当条件为True的时候，a的赋值为x，否则为y，可以改进为：
```
small = x if x < y else y
```

### 2.断言(assert)
asert这个关键字称为“断言"，当这个关键字后边的条件为假的时候，程序自动崩溃并抛出AssertionError的异常。
什么情况下需要这样的代码呢？当我们在测试程序的时候就很好用，因为与其在错误的条件继续运行下去，不如在错误条件出现的时候自我崩溃。
```
assert 3<4
assert 3>4
#AssertionError
```
# Part4 - 函数
## 基础知识回顾
### **1.定义函数**
```
def cylinder_volume(height, radius):
    pi = 3.14159
    return height * pi * radius ** 2
```
定义 cylinder_volume 函数后，我们可以如下所示地**调用**该函数。
```
cylinder_volume(10, 3)
```

def 函数名(参数):
函数体

**思考：你是否还记得函数中实参和形参的**[区别与关系](https://blog.csdn.net/haojiahj/article/details/11155249)**？**

函数名称遵守和变量一样的命名规范。
* 仅在函数名称中使用普通字母、数字和下划线。不能有空格，需要以字母或下划线开头。
* **不能使用在 Python 中具有重要作用的保留字或内置标识符**，我们将在这门课程中学习这方面的知识。要了解 python 保留字列表，请参阅[此处](https://pentangle.net/python/handbook/node52.html)。
* 尝试使用可以帮助读者了解函数作用的描述性名称。

我们可以向函数中添加**默认参数**，以便为在函数调用中未指定的参数提供默认值。
```
def cylinder_volume(height, radius=5):
    pi = 3.14159
    return height * pi * radius ** 2
```
在上述示例中，如果在函数调用中忽略了 radius，则将该参数设为 5。如果我们调用 cylinder_volume(10)，该函数将使用 10 作为高度，使用 5 作为半径。但是，如果调用 cylinder_volume(10, 7)，7 将覆盖默认的值 5。
此外注意，我们按照位置向参数传递值。可以通过两种方式传递值：**按照位置和按照名称。**下面两个函数的效果是一样的。
```
cylinder_volume(10, 7)
cylinder_volume(height=10, radius=7)
```

```
#练习：
#还记得之前编写播放器的练习吗，请将它写在一个新的函数player(song_list,commond)中，并且commond默认为playing，以便传递不同的歌单进行调用。

def player(song_list,commond = 'playing'):
    for i in range(song_list):
      print('开始播放',song_list(i))
      play(song_list(i))
      if command = '下一首':
          print('播放下一首')
          continue
      elif command = '停止播放':
          print('停止播放')
          break  
```

### **2.变量作用域**
在函数中使用变量时，务必要考虑作用域。如果变量是在函数内创建的，则只能在该函数内使用该变量。你无法从该函数外面访问该变量。
这意味着你可以为在不同函数内使用的不同变量使用相同的名称。

```
#练习：
#下列代码的输出结果？

money = 100
money_modify = 15

def win(money, money_modify = 10):
	  money+=money_modify
	  return money
    
def loss(money,money_modify):
	  money-=money_modify
	  return money

print(win(money))
print(win(money,money_modify))
print(win(money,50))
money_modify = 20
print(loss(money,money_modify))
```

### **3.文档**
文档使代码更容易理解和使用。函数尤其容易理解，因为它们通常使用文档字符串，简称 docstrings。文档字符串是一种注释，用于解释函数的作用以及使用方式。下面是一个包含文档字符串的人口密度函数。
```
def population_density(population, land_area):
    """Calculate the population density of an area. """
    return population / land_area
```
文档字符串用三个引号引起来，第一行简要解释了函数的作用。如果你觉得信息已经足够了，可以在文档字符串中只提供这么多的信息；一行文档字符串完全可接受，如上述示例所示。

### **4.lambda表达式**
你可以使用 Lambda 表达式创建匿名函数，即没有名称的函数。lambda 表达式非常适合快速创建在代码中以后不会用到的函数。尤其对高阶函数或将其他函数作为参数的函数来说，非常实用。
我们可以使用 lambda 表达式将以下函数
```
def multiply(x, y):
    return x * y
```
简写为：
```
double = lambda x, y: x * y
```

Lambda 函数的组成部分
* 关键字 lambda 表示这是一个 lambda 表达式。
* lambda 之后是该匿名函数的一个或多个参数（用英文逗号分隔），然后是一个英文冒号 :。和函数相似，lambda 表达式中的参数名称是随意的。
* 最后一部分是被评估并在该函数中返回的表达式，和你可能会在函数中看到的 return 语句很像。

鉴于这种结构，lambda 表达式**不太适合复杂的函数，但是非常适合简短的函数**。

```
#练习：
#使用lambda表达式简写下列函数

r = [3,4,5]
def get_square(r):
	  s=r
	  for i in range(len(r)):
		    s[i] = 3.14*r[i]**2
	  return s
print(get_square(r))


s = list(map(lambda x: 3.14*x**2, r))
```

## 知识拓展
### 1.map(函数,序列, ...)   
map() 会根据提供的函数对指定序列做映射。 第一个参数 function 以参数序列中的每一个元素调用 function 函数，返回包含每次 function 函数返回值的新列表。
```
numbers = [ 
[34, 63, 88, 71, 29], 
[90, 78, 51, 27, 45], 
[63, 37, 85, 46, 22], 
[51, 22, 34, 11, 18] 
]
averages = list(map(lambda x : sum(x) / len(x) , numbers))           
#使用map()将numbers中每一个元素做lambda匿名函数处理，再将结果保存为list（不使用list()会返回一个map object）
print(averages)
```
### 2.filter(函数,序列)    
函数用于**过滤序列，过滤掉不符合条件的元素**，返回由符合条件元素组成的新列表。 该接收两个参数，第一个为函数，第二个为序列，序列的**每个元素**作为参数传递给函数进行判，然后返回 True 或 False，**最后将返回 True 的元素放到新列表中**。
```
cities = ["New York City", "Los Angeles", "Chicago", "Mountain View", "Denver", "Boston"] 
short_cities = list(filter(lambda name:len(name)<10,cities))         
#使用list()将cities中每一个元素做lambda匿名函数处理，判断条件为长度小于10，再将符合条件的元素过滤出来保存在list
print(short_cities)
```
下面是一个叫做 my_range 的生成器函数，它会生成一个从 0 到 (x - 1) 的数字流。
```
def my_range(x):
    i = 0
    while i < x:
        yield i
        i += 1
```
注意，该函数使用了 yield 而不是关键字 return。这样使函数能够一次返回一个值，并且每次被调用时都从停下的位置继续。**关键字 yield 是将生成器与普通函数区分开来的依据。**
注意，因为这段代码会返回一个迭代器，因此我们可以将其转换为列表或用 for 循环遍历它，以查看其内容。例如，下面的代码：
```
for x in my_range(5):
    print(x)
```
输出：
```
0
1
2
3
4
```
### 3.为何使用生成器
由于使用生成器是一次处理一个数据，在内存和存储的需求上会比使用list方式直接全部生成再存储**节省很多资源**。
由此区别，在处理大量数据时，经常使用生成器初步处理数据后，再进行长期存储，而不是使用 list。因为无论使用生成器还是 list，都是使用过就要丢弃的临时数据。既然功能和结果一样，那就不如用生成器。
但是生成器也有自己的局限，它**产生的数据不能回溯**，不像list可以任意选择。

### 4.进阶函数参数收集
Python还有另一种收集参数的方式，就是用两个星号(**)表示。两个星号的收集参数表示为将参数们打包成字典的形式。
* 以元组的形式打包
```
def test(**params):
    print('有%d个参数' % len(params))
    print('他们分别是:',params)

test(a = 1, b = 2, c = 3)
#有5个参数
#他们分别是：{'a': 1, 'b': 2, 'c': 3}
```
* 以字典的形式打包
```
a = {'a': 1, 'b': 2, 'c': 3}
test(**a)
#有3个参数
#他们分别是: {'a': 1, 'b': 2, 'c': 3}
```
# Part5 - 脚本编写
## 基础知识回顾
### 1.安装Python
* 安装 [Anaconda](https://www.continuum.io/downloads)

 对于数据分析学员，强烈建议采用这种 Python 安装方式。
### 2.运行 Python 脚本
* 打开终端并使用 cd 命令转到包含脚本文件的目录。
* 现在你已经位于该文件所在的目录，可以运行该文件了，方法是输入‘脚本名’.py，然后按下 Enter 键。
### 3.在脚本中接受原始输入
我们可以使用内置函数 input 获取用户的原始输入，该函数接受一个可选字符串参数，用于指定在要求用户输入时向用户显示的消息。
```
name = input("Enter your name: ")
print("Hello there, {}!".format(name.title()))
```
这段代码提示用户输入姓名，然后在问候语中使用该输入。input 函数获取用户输入的任何内容并将其存储为字符串。如果你想将输入解析为字符串之外的其他类型，例如整数（如以下示例所示），需要用新的类型封装结果并从字符串转换为该类型。
```
num = int(input("Enter an integer"))
print("hello" * num)
```
我们还可以使用**内置函数 ****eval**** 将用户输入解析为 Python 表达式**。该函数会将字符串评估为**一行 Python 代码**。
```
result = eval(input("Enter an expression: "))
print(result)
```
如果用户输入 2 * 3，输出为 6。

### 4.错误和异常
* 当 Python 无法解析代码时，就会发生**语法错误**，因为我们没有遵守正确的 Python 语法。当你出现拼写错误或第一次开始学习 Python 时，可能会遇到这些错误。
* 当在程序执行期间出现意外情况时，就会发生**异常**，即使代码在语法上正确无误。Python 有不同类型的内置异常，你可以在错误消息中查看系统抛出了什么异常。

常见错误：
* ValueError

向内置操作或函数中传入类型正确但是值不合适的对象作为输入。
* AssertionError

断言语句失败了。
* IndexError

序列下标超出了范围。
* KeyError

在字典中找不到某个键。
* TypeError

向操作或函数中传入类型不受支持的对象作为输入。

**分享：你还见过什么异常，并且怎么处理的？**

### 5.处理异常
Try 语句
我们可以使用 try 语句处理异常（ 4 个子句）
* try：这是 try 语句中的唯一**必需子句**。该块中的代码是 Python 在 try 语句中首先运行的代码。
* except：如果 Python 在运行 try 块时遇到异常，它将跳到**处理**该异常的 except 块。
    * 可以指定要在 except 块中处理哪个错误，如
```
try:
    # some code
except ValueError:
    # some code
```
    * 在处理异常时，依然可以访问其错误消息
```
try:
    # some code
except Exception as e:
   # some code
   print("Exception occurred: {}".format(e))
```
* else：如果 Python 在运行 try 块时没**有遇到异常**，它将在运行 try 块后运行该块中的代码。
* finally：在 Python 离开此 try 语句之前，在**任何情形下它都将运行**此 finally 块中的代码，即使要结束程序，例如：如果 Python 在运行 except 或 else 块中的代码时遇到错误，在停止程序之前，依然会执行此finally 块。

### **6.读写文件**
* 读取文件
```
f = open('my_path/my_file.txt', 'r')
file_data = f.read()
f.close()
```
1. 首先使用内置函数 open 打开文件。需要文件路径字符串。open 函数会返回文件对象，它是一个 Python 对象，Python 通过该对象与文件本身交互。在此示例中，我们将此对象赋值给变量 f。
2. 你可以在 open 函数中指定可选参数。参数之一是打开文件时采用的模式。在此示例中，我们使用 r，即只读模式。这实际上是模式参数的默认值。
3. 使用 read 访问文件对象的内容。该 read 方法会接受文件中包含的文本并放入字符串中。在此示例中，我们将该方法返回的字符串赋值给变量 file_data。
4. 当我们处理完文件后，使用 close 方法释放该文件占用的系统资源。

**如果向 ****.read()**** 传入整型参数，它将读取长度是这么多字符的内容**
**用语法 ****for line in file**** 循环访问文件中的各行内容，使用 ****.strip()****删掉换行符。**

* 写入文件
```
f = open('my_path/my_file.txt', 'w')
f.write("Hello there!")
f.close()
```
1. 以写入 ('w') 模式打开文件。如果文件不存在，Python 将为你创建一个文件。如果以写入模式打开现有文件，该文件中之前包含的所有内容将被删除。如果你打算向现有文件添加内容，但是不删除其中的内容，可以使用**附加 ('a') 模式**，而不是写入模式。
2. 使用 write 方法向文件中添加文本。
3. 操作完毕后，关闭文件。

* Python 提供了一个特殊的语法，该语法会在你使用完文件后自动关闭该文件。
```
with open('my_path/my_file.txt', 'r') as f:
    file_data = f.read()
```
该 with 关键字使你能够打开文件，对文件执行操作，并在缩进代码（在此示例中是读取文件）执行之后自动关闭文件。现在，我们不需要调用 f.close() 了！你只能在此缩进块中访问文件对象 f。

```
#练习：
#说明下列代码的作用
with open('uda.txt', 'r') as f:
    str = f.read(15)

with open('uda15.txt', 'a') as f:
	f.write(str)

#读取uda.txt中的前15个字符再将它们以附加模式保存在uda15.txt中，如果该文件不存在则新建
```

### 7.导入本地脚本
我们实际上可以导入其他脚本中的 Python，如果你处理的是大型项目，需要将代码整理成多个文件并重复利用这些文件中的代码，则导入脚本很有用。如果你要导入的 Python 脚本与当前脚本位于同一个目录下，**只需输入 ****import**，然后是文件名，**无需扩展名 .py**。

**使用 ****if main**** 块**
为了避免运行从其他脚本中作为模块导入的脚本中的可执行语句，将这些行包含在 if __name__ == "__main__" 块中。或者，将它们包含在函数 main() 中并在 if main 块中调用该函数。
每当我们运行此类脚本时，Python 实际上会为所有模块设置一个特殊的内置变量 __name__。当我们运行脚本时，Python 会将此模块识别为主程序，并将此模块的 __name__ 变量设为字符串 "__main__"。对于该脚本中导入的任何模块，这个内置 __name__ 变量会设为该模块的名称。因此，条件 if __name__ == "__main__"会检查该模块是否为主程序。
```
# demo.py

import useful_functions as uf

scores = [88, 92, 79, 93, 85]

mean = uf.mean(scores)
curved = uf.add_five(scores)

mean_c = uf.mean(curved)

print("Scores:", scores)
print("Original Mean:", mean, " New Mean:", mean_c)

print(__name__)
print(uf.__name__)

```

```
# useful_functions.py
def mean(num_list):
    return sum(num_list) / len(num_list)

def add_five(num_list):
    return [n + 5 for n in num_list]

def main():
    print("Testing mean function")
    n_list = [34, 44, 23, 46, 12, 24]
    correct_mean = 30.5
    assert(mean(n_list) == correct_mean)

    print("Testing add_five function")
    correct_list = [39, 49, 28, 51, 17, 29]
    assert(add_five(n_list) == correct_list)

    print("All tests passed!")

if __name__ == '__main__':
    main()    #只有在本模块作为主模块时才调用main()
```

## 知识拓展
### 1.文件的打开模式
| **打开模式**   | **执行操作**   |
|:----:|:----|
| 'r'   | 以只读模式打开文件   |
| 'w'   | 以只写模式打开文件，且先把文件内容清空   |
| 'x'   | 如果文件已经存在，使用此模式打开将引发异常   |
| 'a'   | 以添加模式打开文件，写文件的时候总是写到文件末尾   |
| 'b'   | 以二进制模式打开文件   |
| 't'   | 以文本模式打开（默认）   |
| 'U'   | 通用换行符支持   |
| '+'   | 可读写模式（可添加到其他模式中使用）   |

### 2.使用pickle模块进行多种数据对象持久化
如果要从文件中读取字符串十分简单，然而要**保存或读取**数据像列表、字典甚至是类的实例这些**复杂的数据类型**时，普通的文件操作便不可用了。
Python提供了一个标准模块**pickle**，使用这个模块就可以较为容易的将列表、字典这类复杂数据类型存储为文件了。它几乎可以把所有Python的对象都转化为二进制的形式存放，这个过程称为pickling，那么从二进制形式转换回对象的过程称为unpickling。
```
import pickle
my_list = [123,3.14,'a',['another list']]
pickle_file = open('my_list.pkl', 'wb')
pickle.dump(my_list,pickle_file)
pickle_file.close()
```
这些代码运行后，将my_list列表永久保存成文件，打开的文件一定要以**二进制形式打开('b')**，后缀名随意，使用pickle保存便使用.pkl。使用dump()来保存数据。my_list.pkl使用记事本打开后**显示为乱码**，因为是以**二进制保存**的，无需担心。
使用load()加载本地pickle文件：
```
import pickle
pickle_file = open('my_list.pkl', 'rb')
my_list = pickle_load(pickle_file)
print(my_list)
#[123,3.14,'a',['another list']]
```
