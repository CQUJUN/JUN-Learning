# JUN‘s Python learning

## 1. python简介

### 1.1 编辑器

​	**编译型语言(如C/C++)**：程序在执行之前需要一个专门的编译过程，把程序编译成机器语言的文件，运行时不需要重新翻译，直接使用编译的结果就行。程序执行效率高，依赖编译器，跨平台性能差些。

​	**解释性语言(如Python)**：解释型语言编写的程序不进行预先编译，以文本方式存储程序代码，会将代码一句一句直接运行。在发布程序时，看起来节省了编译工序，但是在运行程序的时候，必须先解释再运行。

### 1.2 Python特点

- Python是**完全面向对象**的语言
  - **函数、模块、数字、字符串**都是对象，在**Python中一切皆对象**
  - 完全支持继承、重载、多重继承
  - 支持重载运算符，也支持泛型设计
- Python**拥有一个强大的标准库**，Python语言的核心只包含 **数字、字符串、列表、字典、文件** 等常见类型和函数，而由Python标准库提供了 **系统管理、网络通信、文本处理、数据库接口、图形系统、XML处理** 等额外的功能
- Python社区提供了**大量第三方模块**，使用方式与标准库类似。它们的功能覆盖 **科学计算、人工智能、机器学习、Web开发、数据库接口、图形系统** 多个领域

### 1.3 面向对象的思维方式

- **面向对象** 是一种 **思维方式**，也是一门 **程序设计技术**

- 要解决一个问题前，首先考虑**由谁**来做，怎么做事情是 谁 的职责，最好把事情做好就行！

  **对象** 就是 **谁**

- 要解决复杂的问题，就可以找**多个不同的对象，各司其职**，共同实现，最终完成需求

### 1.4 程序执行原理

```markdown
CPU <-------> 内存 <-------> 硬盘
		|Python解释器|    |Python程序|
```

1. 操作系统会首先让CPU把 **Python解释器** 的程序复制到 **内存** 中
2. **Python解释器** 根据语法规则，**从上向下** 让**CPU**翻译**Python程序中的代码**
3. **CPU** 负责执行翻译完成的代码

## 2. python基础知识

### 2.1 第一个python程序

```python
def print_hi(name):
    # 在下面的代码行中使用断点来调试脚本。
    print(f'Hi, {name}')  # 按 Ctrl+F8 切换断点。

# 按装订区域中的绿色按钮以运行脚本。
if __name__ == '__main__':
    print_hi('PyCharm')
```

### 2.2 注释

1.  **单行注释**

   ```python
   # 描述信息
   ```

   - 以`#`开头，`#`右边的所有东西都被当作说明文字，而不是真正要执行的程序，只起到辅助说明作用

2. **多行注释**

   ```python
   """
   描述信息
   """
   ```

   - 要在Python程序中使用多行注释，可以用 一对 连续的 三个 引号(单引号和双引号都可以)

### 2.3 print基本用法

1. print可输出多个内容，用逗号隔开

   ```python
   JUN = 30
   print("JUN还有：", JUN, "元\n")
   ```

2. `print`函数用于输出内容到控制台。基本语法是`print(value1, value2, ..., sep=' ', end='\n')`。可以输出字符串、数字等，也可以通过`sep`参数自定义分隔符，通过`end`参数控制行尾符号。例如：`print("Hello", "World", sep="-")`会输出`Hello-World`。

   ```python
   print("apple", "banana", "cherry", sep=", ")
   ```

   > 取消换行：end=''，tab键：\t

3. **f-string：**字符串格式化快速写法（注意不限数据类型，即输出为字符串）`f:format`

   使用`f`前缀，然后在字符串中使用大括号`{}`包围变量或表达式

   ```python
   print(f"我是{name}, 今天是{month}月")
   ```

   > 变量和表达式的计算是在运行时进行的。

   > 如果需要在字符串中插入大括号本身，可以使用双大括号`{{`和`}}`

4. 字符串格式化，`%d %s %f %%`：占位，s：表示把变量变成字符串放入占位的地方

   ```python
   month = 7
   day = 13.0
   print("我是：%s今天是%d月%f日" % (name, month, day))
   ```

### 2.4 常用函数

1. `len()`：返回对象的长度。

   ```python
   my_list = [1, 2, 3, 4]
   print(len(my_list))  # 输出：4
   ```

2. `type()`：返回对象的类型。

   ```python
   my_var = 42
   print(type(my_var))  # 输出：<class 'int'>
   ```

3. `range()`：生成一个整数序列。

   ```python
   range(num1): range(3): [0,1,2]
   range(num1, num2):range(1, 3):[1,2]
   range(num1, num2, step): range(5, 10, 2):[5,7,9](step为数字间步长)
   ```

   ```python
   for i in range(2,5):
       print(i)  # 输出： 1 2 3 4
   ```

   >  for从1循环到4循环五次，continue：暂时调过本次循环进行下一次，break：直接结束

4. `sum()`：返回可迭代对象的总和。

   ```python
   my_numbers = [1, 2, 3, 4]
   print(sum(my_numbers))  # 输出：10
   ```

5. `max()` 和 `min()`：返回最大值和最小值。

   ```python
   my_numbers = [3, 1, 4, 1, 5]
   print(max(my_numbers))  # 输出：5
   print(min(my_numbers))  # 输出：1
   ```

6. `sorted()`：返回排序后的**列表**。

   ```python
   my_numbers = [3, 1, 4, 1, 5]
   print(sorted(my_numbers))  # 输出：[1, 1, 3, 4, 5]
   ```

7. `input()`：用于从用户获取输入，可选地传入一个提示字符串。返回的输入是字符串类型。

   ```python
   name = input("提示信息：\n")
   ```

### 2.5 算数运算符

- 算数运算符是运算符的一种
- 是完成基本的算数运算使用的符号，用来处理四则运算

| 运算符 | 描述   | 实例                            |
| ------ | ------ | ------------------------------- |
| `+`    | 加     | `10+20=30`                      |
| `-`    | 减     | `10-20=-10`                     |
| `*`    | 乘     | `10*20=200`                     |
| `/`    | 除     | `10/20=0.5`                     |
| `//`   | 取整除 | 返回除法的整数部分(商) `9//2=4` |
| `%`    | 取余数 | 返回除法的余数 `9%2=1`          |
| `**`   | 幂     | 又称为次方、乘方`2**3=8`        |

- 在Python中`*`运算符还可以用于字符串，计算结果就是字符串重复指定次数的结果

### 2.6 变量的基本使用

1. **变量定义**

   - **变量名 只有在第一次出现 才是 定义变量**

   - **变量名 再次出现，不是定义变量，而是直接使用之前定义过的变量**

2. **变量的类型**

   - 在内存中创建一个变量，会包括

     1. 变量的名称
     2. 变量保存的数据
     3. 变量存储数据的类型
     4. 变量的地址(标示)

   - 数据类型
     1. `str`--字符串
     2. `bool`--布尔型(真假)
     3. `int`--整数
     4. `float`--浮点数(小数)

3. **强制类型转换**

   | 函数       | 说明                      |
   | ---------- | ------------------------- |
   | `int(x)`   | 将 x 转换为一个整数       |
   | `float(x)` | 将 x 转换到一个浮点数     |
   | `str(x)`   | 将 x 转换到一个字符串类型 |


### 2.7 判断(if)语句

**if基本语法：**

```python
if 要判断的条件:
	条件成立时，要做的事情
	...
```

**elif基本语法：**

```python
if 条件1:
	条件1满足执行的代码
	...
elif 条件2:
	条件2满足执行的代码
	...
elif 条件3:
	条件3满足执行的代码
	...
else:
	以上条件都不满足时，执行代码
	...
```

### 2.8 随机数的处理

在 `Python` 中，要使用随机数，首先需要导入 随机数 的 模块“工具包”

```python
import random
```

随机返回 `[a, b]` 之间的整数，包含 `a` 和 `b`

```python
raddom.randint(a, b)
```

### 2.9 逻辑运算符

1. **与/并且**

   两个条件同时满足，返回`True`

   只要有一个不满足，就返回`False`

   ```python
   条件1 and 条件2
   ```

2. **或/或者**

   两个条件只要有一个满足，返回 `True`

   两个都不满足，返回 `False`

   ```python
   条件1 or 条件2
   ```

3. **非/不是**

   将条件取反，如果条件为假，则返回 `True`

   ```python
   not 条件
   ```

### 2.10 循环

1. **while 语句基本语法**

   ```python
   count = 0
   while count < 5:
       print(count)
       count += 1
   ```

2. **for语句基本语法**

   ```python
   """
   for 临时变量 in 待处理数据集：
      循环满足条件时执行的代码
   """
   for i in range(5):
       print(i)  # 输出：0 1 2 3 4
   ```

   > `for`循环会遍历可迭代对象中的每个元素，并在每次迭代时将元素赋值给指定的变量

3. **break 和 continue**

   > `break` 和 `continue` 是专门在循环中使用的关键字

   - `break` 直接结束
   - `continue` 暂时调过本次循环进行下一次

### 2.11 字符串中的转义字符

| 转义字符 | 描述       |
| -------- | ---------- |
| `\\`     | 反斜杠符号 |
| `\'`     | 单引号     |
| `\"`     | 双引号     |
| `\t`     | 横向制表符 |
| `\r`     | 回车       |
| `\n`     | 换行       |

> **制表符** 的功能是在不适用表格的情况下在 **垂直方向** 按列对齐文本

## 3. 函数

### 3.1 函数的定义

`def` 是英文 `define` 的缩写

```python
# 创建函数并进行文档说明
def my_len(data):
    """
    my_len可接受一个参数，进行字符串长度读取功能
    :param data: 形参data表示输入字符串
    :return: 返回值为字符串长度
    """
    count = 0
    for _ in data:
        count += 1
    print(f"字符串{data}的长度是{count}")
    return count


# 函数的调用
my_len(name)
```

> 总结：
>
> - 在开发中，如果希望给函数添加注释，应该在 **定义函数** 的下方，使用 **连续的三对引号**
> - 在 **连续的三对引号** 之间缩写对函数的说明文字
> - 在 **函数调用** 位置，使用快捷键 `Ctrl + Q` 可以查看函数的说明信息
> - 因为 **函数体相对比较独立，函数定义的上方**，应该和 **其他代码(包括注释)保留两个空行**
> - `_`：可用作临时变量或者一些定义了参数但不需要使用的情况
>
> 如上格式`""" """`可为函数进行文档说明，`:param data:`形参含义，`:return:`返回值含义，当调用时右键会显示该函数说明
>

### 3.2 函数内部

1. **形参和实参**

   - **形参** **定义** 函数时，小括号中的参数，是用来**接受参数**用的，在函数内部 **作为变量使用**

   - **实参**：**调用** 函数时，小括号中的参数，是用来把数据传递到 **函数内部** 用的

2. **变量**

   - **局部变量：**函数内部定义的变量均为局部变量

   - **全局变量：**global 关键字声明局部变量可以转变为全局变量

     ```python
     def test():
         # global 关键字声明a是全局变量,在函数内定义的均为局部变量，需要声明
         global num
         num = 200
         print(num)
     ```

3. **函数的返回值**

   > `return` 表示返回，后续代码都不会被执行

### 3.3 函数的多返回值

在Python中，函数可以返回多个值，通常通过**元组**实现

当函数返回多个值时，Python会将这些值打包成一个**元组**，并且可以在调用函数时直接解包这些值

```python
def calculate(a, b):
    sum_result = a + b
    product_result = a * b
    return sum_result, product_result

# 调用函数并解包返回值，接收顺序和return顺序一样
sum_val, product_val = calculate(5, 3)

print("Sum:", sum_val)        # 输出: Sum: 8
print("Product:", product_val) # 输出: Product: 15
```

### 3.4 函数的多种参数使用形式

1. **位置参数**

   这是最基本的参数形式，按照位置传递参数

   ```python
   def add(a, b):
       return a + b
   
   result = add(3, 5)  # 位置参数
   ```

2. **关键字参数**

   可以通过指定参数名来传递值，这样可以不按照位置顺序传递参数，使函数更清晰更容易使用

   ```python
   def greet(name, age):
       return f"Hello, {name}. You are {age} years old."
   
   message = greet(age=30, name="Alice")  # 关键字参数
   ```

3. **缺省参数(默认参数)**

   可以为参数指定默认值，如果在调用时未提供这些参数，则使用默认值

   ```python
   def user_info(name, age=17, gender='M'):
       print(f"姓名{name}, 年龄{age}, 性别{gender}")
       
   user_info(name='JUN')
   ```

   > 注意：但只能放在最后，中间不能间隔一个非缺省参数

4. **不定长参数**

   使用`*args`和`**kwargs`来处理可变数量的参数。

   - `*args`位置不定长-用于接收可变数量的位置参数(传进的参数会根据传入位置合并为一个元祖)。

     ```python
     def sum_all(*args):
         return sum(args)
     
     result = sum_all(1, 2, 3, 4)  # 结果是10
     ```

   - `**kwargs`关键字不定长-用于接收可变数量的关键字参数(传进的参数会根据传入位置合并为一个字典)

     ```python
     def print_info(**kwargs):
         for key, value in kwargs.items():
             print(f"{key}: {value}")
     
     print_info(name="Alice", age=30, city="New York")
     ```

### 3.5 函数作为参数传递

1. **函数可以作为参数传递给其他函数**

   定义一个函数，然后将其作为参数传递给另一个函数

   ```python
   def add(x, y):
       return x + y
   
   def operate(func, a, b):
       return func(a, b)
   
   result = operate(add, 3, 5)  # 传递函数和参数
   print(result)  # 输出: 8
   ```

2. **匿名函数 (Lambda 函数)**

   **语法：**

   `lambda arguments: expression`

   - `arguments`：输入参数，可以是多个，用逗号分隔

   - `expression`：返回的计算结果，必须是单一的表达式

   **示例：**

   ```python
   def operate(func, a, b):
       return func(a, b)			# 确定了func是函数
   
   result = operate(lambda x, y: x * y, 4, 6)  # 使用匿名函数
   print(result)  # 输出: 24
   ```

### 3.6 使用模块中的函数

> 模块是 Python 程序架构的一个核心概念

- **模块** 就好比 **工具包**，要想使用这个工具，就需要导入 **import** 这个模块
- 每一个以扩展名 `.py` 结尾的 `Python` 源代码文件都是一个 **模块**
- 在模块中定义的 **全局变量、函数** 都是模块能够提供给外界直接使用的工具

> Python包的功能，是一个文件夹，可存放一堆模块，额外带有`_init_.py`文件：**有该文件才是包**，不然就是普通文件夹
>
> 导入包：import 包名.模块名

#### **3.6.1 导入工具包中函数方式**

**核心语法：**`[from 模块名] import [模块| 类| 变量| 函数| *] [as 别名]`

1. **导入整个模块**

   ```python
   import math
   
   result = math.sqrt(16)  # 调用 math 模块中的 sqrt 函数
   print(result)  # 输出: 4.0
   ```

2. **导入特定函数**

   ```python
   from math import factorial
   
   result = factorial(5)  # 直接调用 factorial 函数
   print(result)  # 输出: 120
   ```

3. **导入多个函数**

   ```python
   from math import sin, cos, pi
   
   print(sin(pi / 2))  # 输出: 1.0
   print(cos(0))      # 输出: 1.0
   ```

4. **使用别名**

   ```python
   import pandas as pd  # 使用 as 将 pandas 模块设置为别名 pd
   
   data = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})
   print(data)
   ```

5. **导入所有函数**

   - 如果需要导入模块中的所有函数，可以使用 `*`，但这通常**不推荐**，因为可能会导致**命名冲突**：

     ```python
     from math import *
     
     print(sqrt(16))  # 直接使用 sqrt 函数
     ```

   - 导入软件包中的所有函数

     ```python
     from JUN_PACK import *
     ```

     `JUN_PACK`为软件包名称

   - `__all__`变量：作用在`*`上，**在模块中**使用时实现只导入指定函数，其他函数导入不了

     **在软件包中**，通过在`_init_.py`里的`__all__`变量，控制`import *`只导入指定的模块

     ```python
     # init.py中
     __all__ = ['my_mod1']
     ```

     如上当使用`from JUN_PACK import *`时，将只导入`my_mod1.py`

#### **3.6.2 编写可重用的模块**

在Python中，`__main__` 是一个特殊的变量，主要编写 **可重用且可测试** 的代码

```py
# example.py
def main():
    print("Main function is running.")

if __name__ == "__main__":
    main()
```

在直接运行 `example.py` 时，会调用 `main()` 函数；如果导入这个模块，则不会执行 `main()`

#### **3.6.3 模块函数例子**

- 新建`JUN_PACK`软件包

- 在软件包内新建 `my_mod.py`工具包文件，并输入：

  ```python
  def info_print1():
      print("mod1 hello world")
      
  if __name__ == "__main__":
  	info_print1()
  ```

- 新建 `fun_test.py` 主函数文件，并且编写以下代码：

  ```python
  import JUN_PACK.my_mod1
  
  JUN_PACK.my_mod1.info_print1()
  ```

  或者：

  ```python
  from JUN_PACK import my_mod1
  
  my_mod1.info_print1()
  ```

- 可以 **在一个 Python 文件** 中 **定义 变量 或者 函数**
- 然后在 另外一个文件中 使用 `import` 导入这个模块
- 导入之后，就可以使用 `模块名.变量` / `模块名.函数` 的方式，使用这个模块中定义的变量或者函数

## 4. 数据容器

在 `Python` 中，数据容器指的是：**列表(`list`)、元祖(`tuple`)、字符串(`str`)、集合(`set`)、字典(`dict`)**

数据容器是用于存储和管理多个数据项的结构

### 4.1 列表

#### 4.1.1 列表的定义

- `List` (列表) 是 `Python` 中使用 **最频繁** 的数据类型，在其他语言中通常叫作 **数组**
- 专门用于存储 **一串信息**
- 列表用 `[]` 定义，**数据**之间使用 `,` 分隔
- 列表的 **索引** 从 `0` 开始
  - **索引** 就是数据在 **列表** 中的位置编号，索引 又可以被称为 **下标**
  - 从头到尾顺序为`0,1,2,...`
  - 从尾到头顺序为`-1,-2,-3,...`

> 注意：从列表中取值时，如果 **超出索引范围**，程序会报错

1. **定义空列表**

   ```python
   my_list_empty = list()
   ```

2. **定义列表**

   ```python
   list1 = ['JUN', 'LU', 'ZI']
   
   list2 = [[1, 2, 3], list1[0], 666, True]
   ```

#### 4.1.2 列表常用操作

1. **访问元素**：使用索引访问元素，索引从0开始，从头到尾顺序为`0,1,2,...`，从尾到头顺序为`-1,-2,-3,...`

   ```python
   print(list2[0][1])
   ```

2. **查找某元素在列表内的下标索引(第一个匹配项)**

   ```python
   index = list2.index([1, 2, 3])
   
   print(f"下标索引值是{index}")
   ```

3. **指定下标位置插入指定元素**

   语法：`list.insert(索引,数据)`

   ```python
   list2.insert(1, "best")
   
   print(f"插入元素后结果是{list2}")
   ```

4. **在列表尾部追加单个新元素**

   ```python
   list2.append(666)
   
   print(f"追加元素后结果是{list2}")
   ```

5. **在列表尾部追加一批元素**

   ```python
   new_list = [3, 2, 1]
   
   list2.extend(new_list)
   
   print(f"追加新列表后结果是{list2}")
   ```

6. **删除元素：**

   - **删除元素 del 列表[下标]**

     `del` 关键字本质上是用来 **将一个变量从内存中删除的**

     ```python
     del list2[0]
     
     print(f"删除元素后结果是{list2}")
     ```

   - **删除元素 列表.pop(下标)-将指定元素取出来并返回出去**

     ```python
     back = list2.pop(0)
     
     print(f"删除元素后结果是{list2}，取出的元素是{back}")
     ```

7. **删除某元素在列表中的第一个匹配项**

   ```python
   list2.remove(666)
   
   print(f"删除指定元素后结果是{list2}")
   ```

8. **清空列表**

   ```python
   list2.clear()
   
   print(f"清空列表后结果是{list2}")
   ```

9. **统计某元素数量**

   ```python
   list2 = [[1, 2, 3], list1[0], 666, True]
   
   count = list2.count(666)
   
   print(f"指定元素数量是{count}")
   ```

10. **统计列表多少元素**

    ```python
    length = len(list2)
    
    print(f"元素数量共{length}")
    ```

#### 4.1.3 列表的循环遍历

- **遍历**就是**从头到尾**依次从**列表**中获取数据
  - 在**循环内部**针对**每一个元素**，执行相同的操作
- 在 `Python` 中为了提高列表的遍历效率，专门提供的 **迭代 iteration 遍历**
- 使用 `for` 就能够实现迭代遍历

```python
list1 = ['JUN', 'LU', 'ZI']

list2 = [[1, 2, 3], list1[0], 666, True]

# 使用迭代遍历列表
"""
顺序从列表中依次获取数据，每一次循环过程中，数据都会保存在my_name 这个变量中，
在循环体内部可以访问当前这一次获取到的数据，直到列表地址访问结束
"""
for my_list in list2:
    print("列表内容是 %s" % my_list)
```

- 列表中**可以存储不同类型的数据**
- 在开发中，更多的应用场景是
  1. **列表**存储相同类型的数据
  2. 通过**迭代遍历**，在循环体内部，针对列表中的每一项元素，执行相同的操作

#### 4.1.4 列表推导式

基本语法：`new_list = [expression for item in iterable]`

- **expression**：每个元素在新列表中的表示形式，可以是对 `item` 的操作。
- **item**：用于从可迭代对象中提取元素的部分。
- **iterable**：可以是列表、元组、字符串、范围等可迭代对象。

1. **从一个数字列表生成其平方值的新列表：**

   ```python
   numbers = [1, 2, 3, 4, 5]
   
   squared_numbers = [x**2 for x in numbers]
   
   print(squared_numbers)  # 输出: [1, 4, 9, 16, 25]
   ```

2. **列表推导式可以包含条件，允许你筛选元素**

   ```python
   # 只生成偶数的平方
   even_squared = [x**2 for x in numbers if x % 2 == 0]
   
   print(even_squared)  # 输出: [4, 16]
   ```


### 4.2 元组

#### 4.2.1 元祖的定义

只读的列表，一旦定义完成就不可修改(但**可修改元祖内的列表**)

- 元组(`tuple`) 与列表类似，不同之处在于元组的**元素不能修改**
  - 元组表示多个元素组成的序列
  - 元组在 `Python` 开发中，有特定的应用场景
- 用于存储一串信息，**数据之间使用 `,` 分隔**
- 元组用 `()` 定义
- 元组的**索引**从 `0` 开始
  - 索引就是数据在元素中的位置编号

1. **定义空元祖**

   ```python
   my_tuple_empty = tuple()
   ```

2. **定义元祖**

   ```python
   tuple1 = ((1, 2, 3), 1, 2, 3, 2)
   ```

3. **定义单个元素后必须加个逗号**

   ```python
   tuple2 = ('JUN', )
   ```

#### 4.2.2 元组常用操作

1. 下标索引取出内容

   ```python
   print(tuple1[0][1])
   ```

2. 查找某元素在元祖内的下标索引

   ```python
   print(f"2的下标索引值是{tuple1.index(2)}")
   ```

3. 统计某元素数量

   ```python
   print(f"指定元素’2‘数量是{tuple1.count(2)}")
   ```

4. 统计元组中包含元素的个数

   ```python
   print(len(tuple1))
   ```

#### 4.2.3 元祖的循环遍历

- **取值**就是从元组中获取存储在指定位置的数据
- **遍历**就是从头到尾依次从元组中获取数据

```python
tuple1 = ((1, 2, 3), 1, 2, 3, 2)

# 使用迭代遍历元组
for my_info in tuple1:
    # 使用格式化字符串拼接 my_info 这个变量不方便！
    # 因为元组中通常保存的数据类型是不同的！
    print(my_info)
```

>- 在 `Python` 中，可以使用 `for` 循环遍历所有非数字类型的变量：**列表、元组、字典以及字符串**
>- 提示：在实际开发中，除非能**够确认元组中的数据类型**，否则针对元组的循环遍历需求并不是很多

#### 4.2.4 应用场景

- 在开发中，更多的应用场景是：
  - **函数的参数和返回值**，一个函数可以**接受任意多个参数**，或者一次**返回多个数据**
  - **格式化字符串**，后面的 `()` **本质上就是一个元组**
  - **让列表不可以被修改**，以保护数据安全

```python
info = ("zhangsan", 18)
print("%s 的年龄是 %d" % info)
```

**元组和列表之间的转换**

- 使用 `list` 函数可以把元组转换成列表

```python
list(元组)
```

- 使用 `tuple` 函数可以把列表转换成元组

```python
tuple(列表)
```

### 4.3 字符串

#### 4.3.1 字符串的定义

- 存放字符,并且也是一个**无法修改**的数据容器

- 字符串就是一串字符，是变成语言中表示文本的数据类型
- 在 Python 中可以使用**一对双引号** `""` 或者**一对单引号** `''` 定义一个字符串
  - 如果字符串内部需要使用双引号 `"` ，可以使用单引号 `''` 定义字符串
  - 如果字符串内部需要使用单引号 `'` ，可以使用双引号 `"` 定义字符串
- 可以使用**索引**获取一个字符串中指定位置的字符，索引计数从0开始
- 也可以使用 `for` **循环遍历**字符串中每一个字符

>大多数语言使用双引号 `""` 定义字符串

1. **定义空字符串**

   ```python
   my_str_empty = ""
   ```

2. **定义字符串**

   ```python
   my_str = "JUN"
   ```

#### 4.3.2 字符串常用操作

1. **通过下标索引取值**

   - 从头到尾顺序为`0,1,2,...`
   - 从尾到头顺序为`-1,-2,-3,...`

   ```python
   print(f"值是{my_str[-1]}")
   ```

2. **`index`方法**

   ```python
   print(f"'U'下标索引值是{my_str.index('U')}")
   ```

3. **`replace`方法：**将字符串1全部替换为字符串2,得到一个新字符串

   ```python
   new_my_str = my_str.replace("JU", "LU")
   
   print(f"旧字符串{my_str}，新字符串{new_my_str}")
   ```

4. **`split`字符串的分割：**将字符串划分多个字符串，并存入列表对象中，如下将空格作为分隔符

   ```python
   my_str = "LU ZI JUN"
   
   my_str_list = my_str.split(" ")
   
   print(f"旧字符串{my_str}，分割后得到列表{my_str_list}")
   ```

5. **`strip`字符串的规整操作(去除前后内容)**

   ```python
   my_str = "12LU ZI JUN21"
   
   new_my_str = my_str.strip("12")
   
   print(f"旧字符串{my_str}，新字符串{new_my_str}")
   ```

6. **统计某字符串数量**

   ```python
   print(f"指定字符串数量是{my_str.count('U')}")
   ```

#### 4.3.3 字符串的循环遍历

```python
s = "hello"
for char in s:
    print(char)
```

### 4.4 序列

#### 4.4.1 序列的定义

内容**连续、有序**，可使用下标索引的数据容器，如列表(`list`)、元祖(`tuple`)、字符串(`str`)

#### 4.4.2 序列的切片

从一个序列中，取出一个子序列

- 切片使用索引值来限定范围，从一个大的字符串中切出小的字符串
- **列表**和**元组**都是有序的集合，都能够**通过索引值**获取到对应的数据

语法：`序列[ 起始下标 : 结束下标 : 步长 ]`

- 起始下标：表示从何处开始，可以留空表示从头开始，开始索引数字可以省略，冒号不能省略
- 结束下标：(不含本元素)，留空表示截取到结尾，结束索引数字可以省略，冒号不能省略
- 步长：表示依次取元素的间隔,默认为1，如果连续切片，数字和冒号都可以省略

1. **对list进行切片，从1开始，4结束，步长1**

   ```python
   my_list = [0, 1, 2, 3, 4, 5, 6]
   
   result1 = my_list[1:4]
   
   print(f"结果1：{result1}")
   ```

2. **对tuple进行切片，从头开始，到最后结束，步长1**

   ```python
   my_tuple = (0, 1, 2, 3, 4, 5, 6)
   
   result2 = my_tuple[:]
   
   print(f"结果2：{result2}")
   ```

3. **对str进行切片，从头开始，到最后结束，步长2**

   ```python
   my_str = "0123456"
   
   result3 = my_str[::2]
   
   print(f"结果3：{result3}")
   ```

4. **对`str`进行切片，从头开始，到最后结束，步长-1(表示从后往前取，等同于将序列反转)**

   ```python
   my_str = "0123456"
   
   result4 = my_str[::-1]
   
   print(f"结果4：{result4}")
   ```

5. **对list进行切片，从3开始，1结束，步长-1**

   ```python
   my_list = [0, 1, 2, 3, 4, 5, 6]
   
   result5 = my_list[3:1:-1]
   
   print(f"结果5：{result5}")
   ```

6. **对序列进行反转(如反转图像)**

   ```python
   # 水平反转图像
   flipped_image = image_array[:, ::-1]  # 反转列
   ```

#### 4.4.3 序列的应用场景

序列切片的主要应用场景包括：

1. **数据处理**：在数据分析中，切片可用于提取特定数据段，如提取时间序列中的某些日期。
2. **字符串处理**：在文本处理中，切片可以用于提取子字符串，如从用户输入中获取特定部分。
3. **图像处理**：在处理图像数据时，切片可以提取图像的特定区域进行分析或修改。
4. **算法实现**：许多算法（如排序、查找）可以利用切片操作来简化代码逻辑。
5. **列表操作**：切片可用于批量更新列表中的元素，例如替换或删除一组元素

#### 4.4.4 序列切片图像处理示例

 **使用 `NumPy` 处理图像**

在 Python 中，图像通常以数组的形式存储，可以使用 NumPy 库进行切片。以下是一些常见操作

1. **读取图像**

   使用 `PIL`（Python Imaging Library）读取图像并将其转换为 NumPy 数组：

   ```python
   from PIL import Image
   import numpy as np
   
   # 读取图像
   image = Image.open('example.jpg')
   image_array = np.array(image)
   ```

2. **提取子图像**

   可以通过切片提取图像的某一部分：

   ```python
   # 提取图像的中心部分
   height, width, _ = image_array.shape
   center_image = image_array[height//4:3*height//4, width//4:3*width//4]
   ```

   `image_array`是一个二维数组对象，故虚采用两次切片分别对图片的高和宽进行裁剪

### 4.5 集合

#### 4.5.1 集合的定义

集合(`set`)：不支持内容的重复(会自动**去除重复的内容**，无序)，并且内容**无序(不支持下标访问)**

**特性**

- **无序**：集合中的元素没有固定顺序。
- **唯一性**：集合不允许重复元素。
- **可变性**：集合是可变的，可以添加或删除元素。
- **支持集合运算**：可以进行并集、交集、差集等操作。

1. **定义空集合**

   ```python
   my_set_empty = set()
   ```

2. **定义集合**

   ```python
   my_set = {"JUN", "LU", "ZI"}
   ```

#### 4.5.2 集合常用操作

1. **添加新元素**

   ```python
   my_set.add("Python")
   print(f"my_set添加结果是{my_set}")
   ```

2. **移除元素**

   ```python
   my_set.remove("JUN")
   print(f"my_set移除结果是{my_set}")
   ```

3. **随机取出一个元素**

   ```python
   element = my_set.pop()
   print(f"my_set取出{element}结果是{my_set}")
   ```

4. **清空集合**

   ```python
   my_set.clear()
   print(f"清空结果是{my_set}")
   ```

5. **取出两个集合的差集(集合1有而集合2没有的)**

   ```python
   set1 = {1, 2, 3}
   set2 = {1, 5, 6}
   set3 = set1.difference(set2)
   print(f"取出差集的结果是{set3}")
   ```

6. **消除两个集合的差集(在集合1内删除与集合2相同的元素)**

   ```python
   set1.difference_update(set2)
   print(f"消除差集的结果是{set1}")
   ```

7. **两个集合合并为一个**

   ```python
   set1 = {1, 2, 3}
   set2 = {1, 5, 6}
   set3 = set1.union(set2)
   print(f"合并的结果是{set3}")
   ```

#### 4.5.3 集合应用场景

- **去重**：快速去除列表中的重复元素。
- **成员测试**：快速判断某个元素是否在集合中。
- **集合运算**：进行数学集合的运算，如找出共同元素或不同元素。

### 4.6 字典

字典(`dict`)：通过字典可实现用`key`取出`Value`的操作，存储的元素是键值对,和集合一样`key`不能重复

#### 4.6.1 字典的定义

- `dictionary` (字典)是除**列表以外** `Python` 之中**最灵活**的数据类型
- 字典同样可以用来**存储多个数据**
  - 通常用来存储 **描述一个 `物体` 的相关信息**
- 和列表的区别
  - **列表是有序的对象集合**
  - **字典是无序的对象集合**
- 字典用 `{}` 定义
- 字典使用**键值对**存储数据，键值对之间使用 `,` 分隔
  - **键** `key` 是索引
  - **值** `value` 是数据
  - **键**和**值**之间使用 `:` 分隔
  - **键必须是唯一的**
  - **值**可以取任**何数据类型**，但**键**只能使用**字符串、数字或元组**

1. **定义空字典**

   ```python
   my_dict_empty = dict()
   ```

2. **定义字典**

   ```python
   my_dict = {'name': 'Alice', 'age': 30}
   
   xiaoming = {
       "name":"宋江",
       "绰号":"及时雨",
       "地位":"梁山统领三代目",
       "星宿":"天魁星"
   }
   ```

   ![1](./JUN‘s_Python_learning.assets/1.png)

3. **字典中基于`key`获取`Value`**

   ```python
   name = my_dict['name']  # 获取 'Alice'
   ```

4. **字典的嵌套**

   ```python
   my_dict = {
       "JUN": {
           "good": 1,
           "bad": 2
       }, "LU": {
           "good": 1,
           "bad": 2
       }, "ZI": {
           "good": 1,
           "bad": 2
       }
   }
   
   # 字典中基于key获取Value
   print(f"JUN的good是{my_dict["JUN"]["good"]}")
   ```

#### 4.6.2 字典常用操作

1. **新增元素**

   ```python
   my_dict = {"JUN": 3, "LU": 2, "ZI": 1}
   my_dict["jun"] = 4
   print(f"字典经过新增元素后，结果：{my_dict}")
   ```

2. **更新元素**

   ```python
   my_dict["JUN"] = 10
   print(f"字典经过更新后，结果：{my_dict}")
   ```

3. **删除元素**

   ```python
   my_dict.pop("jun")
   print(f"字典经过删除后，结果：{my_dict}")
   ```

4. **清空字典**

   ```python
   my_dict.clear()
   print(f"字典经过清空后，结果：{my_dict}")
   ```

5. **获取全部`key`**

   ```python
   my_dict = {"JUN": 3, "LU": 2, "ZI": 1}
   keys = my_dict.keys()
   print(f"字典的全部keys是{keys}")
   ```

#### 4.6.3 字典的循环遍历

> 遍历就是依次从字典中获取所有键值对
>

```python
xiaoming_dict = {"name":"小明",
                "qq":"123456",
                "phone":"10086"}

# 迭代遍历字典
# 变量k是每一次循环中，获取到的键值对的key
for k in xiaoming_dict:
    print("%s - %s" % (k, xiaoming_dict[k]))
```

#### 4.6.4 字典的应用场景

- 使用多个键值对，存储描述一个 `物体` 的相关信息--描述更复杂的数据信息
- **将多个字典放在一个列表中，再进行遍历，在循环体内部针对每一个字典进行相同的处理**

### 4.7 数据容器的通用功能

#### **4.7.1 内置函数**

| 函数                | 描述                 | 备注                        |
| ------------------- | -------------------- | --------------------------- |
| `len(item)`         | 计算容器中元素个数   |                             |
| `del(item)`         | 删除变量             | del 有两种方式-关键字或函数 |
| `max(item)`         | 返回容器中元素最大值 | 如果是字典，只针对 key 比较 |
| `min(item)`         | 返回容器中元素最小值 | 如果是字典，只针对 key 比较 |
| `cmp(item1, item2)` | 比较两个值           | python3.x中取消             |

> 注意：字符串的比较符合以下规则 `"0"<"A"<"a"`

#### **4.7.2 数据容器类型转换**

- 容器转列表：`list(item)`
- 容器转字符串：`str(item)`
- 容器转元祖：`tuple(item)`
- 容器转集合：`set(item)`

#### **4.7.3 sorted排序**

- 排序结果变成**列表对象**
- 从小到大：`sorted(item)`
- 从大到小：`sorted(item, [reverse=True])`

```python
print(f"列表对象的排序结果：{sorted(my_list)}")
print(f"元祖对象的排序结果：{sorted(my_tuple)}")
print(f"字符串对象的排序结果：{sorted(my_str)}")
print(f"集合对象的排序结果：{sorted(my_set)}")
print(f"字典对象的排序结果：{sorted(my_dict)}")
```

#### **4.7.4 运算符(in、not in)**

| 运算符         | Python表达式       | 结果               | 描述           | 支持的数据类型           |
| -------------- | ------------------ | ------------------ | -------------- | ------------------------ |
| `+`            | `[1,2]+[3,4]`      | `[1,2,3,4]`        | 合并           | 字符串、列表、元组       |
| `*`            | `["Hi"]*3`         | `["Hi","Hi","Hi"]` | 重复           | 字符串、列表、元组       |
| `in`           | `3 in (1,2,3)`     | `True`             | 元素是否存在   | 字符串、列表、元组、字典 |
| `not in`       | `4 not in (1,2,3)` | `True`             | 元素是否不存在 | 字符串、列表、元组、字典 |
| `> >= == < <=` | `(1,2,3)<(2,2,3)`  | `True`             | 元素比较       | 字符串、列表、元组       |

- `in` 在对**字典**操作时，判断的是**字典的键**
- `in` 和 `not in` 被称为**成员运算符**

- **成员运算符**用于**测试**序列中是否包含指定的成员

| 运算符   | 描述                                                | 实例                          |
| -------- | --------------------------------------------------- | ----------------------------- |
| `in`     | 如果在指定的序列中找到值返回 True，否则返回 False   | `3 in (1,2,3)` 返回 True      |
| `not in` | 如果在指定的序列中没有找到值返回True，否则返回False | `3 not in (1,2,3)` 返回 False |

>注意：在对字典操作时，判断的是**字典的键**

## 5. 文件操作

### 5.1 文件的概念

计算机的文件，就是存储在某种长期存储设备上的一段数据

### 5.2 文件的基本操作

#### 5.2.1 操作文件的套路

在计算机中要操作的文件的套路非常固定，一共包含三个步骤：

1. 打开文件
2. 读、写文件
   - **读** 将文件内容读入内存
   - **写** 将内存内容写入文件
3. 关闭文件

#### 5.2.2 操作文件的函数/方法

- 在 Python 中要操作文件需要记住 **1个函数 和 3个方法**

| 序号 | 函数/方法 | 说明                           |
| ---- | --------- | ------------------------------ |
| 01   | `open`    | 打开文件，并且返回文件操作对象 |
| 02   | `read`    | 将文件内容读取到内存           |
| 03   | `write`   | 将指定内容写入文件             |
| 04   | `close`   | 关闭文件                       |

- `open` 函数默认以**只读模式**打开文件，并且返回文件对象
- `read/write/close` 三个方法都需要通过**文件对象**来调用

#### **5.2.3 打开函数**

1. **语法：**`open(name, mode, encoding)`

2. **参数含义：**

   `name`：要打开目标文件名的字符串(可以包含文件所在的具体路径)

   `mode`：

   **设置打开文件的模式(访问模式)**：

   `r`：以只读方式打开文件

   `w`：打开一个文件只用于写入，文件存在则从头开始编辑，原有内容会被删除。文件不存在则创建新文件

   `a`：打开一个文件用于追加，文件存在则新的内容会写入到已有内容之后，文件不存在则创建新文件进行写入
   只读、写入、追加

   `encoding`：编码格式(推荐使用`UTF-8`)

3. **注意事项：**

   由于使用时`encoding`的顺序不是第三位所以要用关键字参数直接指定

   如：`f = open('python.txt', 'r', encoding='utf-8')`

   此时`'f'`是`'open'`函数的文件对象，对象拥有属性和方法，可以使用`对象.属性`或`对象.方法`对其访问

#### 5.2.4 读操作相关方法

1. **语法**：`文件对象.read(num)`

   使用`read`后光标会停留在这次读的地方，下次会从这个地方开始读

2. **参数含义：**

   `num`：表示从文件中读取的数据长度，没传入`num`默认读取全部数据,返回内容是字符串

3. **相关方法：**

   `readlines()`：可以按照行的方式把整个文件的内容进行一次性读取，返回的是一个列表，其中每一行数据为一个元素

   `readline()`：使用一次读取一行

4. **示例：**

   ```python
   # 打开文件
   f = open("D:\\Application\\pycharm\\python_learn\\pythonProject\\test.txt", 'r', encoding='utf-8')
   print(type(f))
   
   # 读取文件 - read():使用read后光标会停留在这次读的地方，下次会从这个地方开始读
   print(f"读取10个字节的结果{f.read(10)}")
   print(f"读取全部内容的结果{f.read()}")
   # 读取文件 - readlines()
   lines = f.readlines()
   print(f"lines对象类型：{type(lines)},内容是：{lines}")
   # for循环读取文件行
   for line in f:
       print(f"每一行数据是{line}")
   # 文件的关闭(不关闭导致该文件一直被Python占用)
   f.close()
   # with open as f语法操作文件(打开文件执行完函数体后会自动关闭该文件)
   with open('test.txt', 'r', encoding='utf-8') as f:
       for line in f:
           print(f"每一行数据是{line}")
   ```

#### 5.2.5 写操作相关方法

1. **写入操作：**

   `'w'`

   `write()`

   直接调用`write`，内容并未真正写入文件，而是写入到程序的内存中(缓冲区)

   当调用`flush`时才会真正写入文件

2. **示例：**

   ```python
   # 打开文件
   f = open('test2.txt', 'w', encoding='utf-8')
   # write写入
   f.write("hello world")
   # flush刷新
   f.flush()
   # close关闭(其中也包含了flush的功能)
   f.close()
   ```

#### 5.2.6 文件追加相关方法

1. **文件追加操作：**

   `'a'`

   `write()`

   直接调用`write`，内容并未真正写入文件，而是写入到程序的内存中(缓冲区)

   当调用`flush`时才会真正写入文件

   文件若已经存在则追加写入文件

2. **示例：**

   ```python
   # 打开文件
   f = open('test2.txt', 'a', encoding='utf-8')
   # write写入
   f.write("\nhello world")
   # flush刷新
   f.flush()
   # close关闭(其中也包含了flush的功能,所以有close可以不需要flush)
   f.close()
   ```

### 5.3 文本文件的编码方式

- 文本文件存储的内容是基于**字符编码**的文件，常见的编码有 `ASCII`  编码，`UNICODE` 编码等

>Python 2.x 默认使用 `ASCII` 编码
>Python 3.x 默认使用 `UTF-8` 编码

UTF-8是目前全球通用的编码格式，一般使用UTF-8(将内容转换为计算机能识别的二进制语言)

## 6.  异常

### 6.1 异常的概念

- 程序在运行时，如果 `Python 解释器` 遇到一个错误，**会停止程序的执行，并且提示一些错误信息**，这就是**异常**
- 程序停止执行并且提示错误信息这个动作，我们通常称之为：**抛出(raise)异常**

>程序开发时，很难将所有的特殊情况都处理的面面俱到，通过**异常捕获**可以针对突发事件做集中的处理，从而保证程序的稳定性和健壮性

### 6.2 捕获异常

#### 6.2.1 简单的捕获异常语法

1. **语法：**

   ```python
   try:
   	尝试执行的代码
   except:
   	出现错误的处理
   ```

   - `try` 尝试，下方编写要尝试的代码，不确定是否能够正常执行的代码
   - `except` 如果不是，下方编写尝试失败的代码

2. **示例：**

   ```python
   try:
       f = open("ABC.txt", "r", encoding="utf-8")
   except:
       print("出现异常了，因为文件不存在，所以改变open的模式")
       f = open("ABC.txt", "w", encoding="utf-8")
       f.close()
   ```

#### 6.2.2 错误类型的捕获

- 在程序执行时，可能会遇到不同类型的异常，并且需要**针对不同类型的异常，做出不同的响应，这个时候，就需要捕获错误类型**

1. **语法：**

   ```python
   try:
   	# 尝试执行的代码
   	pass
   except 错误类型1:
   	# 针对错误类型1，对应的代码处理
   	pass
   except (错误类型2, 错误类型3):
   	# 针对错误类型2 和 3，对应的代码处理
   	pass
   except Exception as result:
   	print("未知错误 %s " % result)
   ```

   > 当 `Python` **解释器抛出异常时，最后一行错误信息的第一个单词，就是错误类型**

2. **示例：**

   ```python
   try:
       # 1. 提示用户输入一个整数
       num = int(input("输入一个整数："))
   
       # 2. 使用 `8` 除以用户输入的整数并且输出
       res = 8 / num
   
       print(res)
   except ZeroDivisionError:
       print("除0错误")
   except ValueError:
       print("请输入正确的整数")
   except Exception as result:
   	print("未知错误 %s" % result)
   ```

   - 在开发时，要预判到所有可能出现的错误，还是有一定难度的
   - 如果希望程序无论出现任何错误，都不会因为 `Python` 解释器抛出异常而被终止，可以再增加一个 `except Exception as result`
   - `Exception` 是捕获的异常类型，这里是一个通用的异常类型，意味着它会捕获所有继承自 `Exception` 的异常。
   - `as result` 表示将捕获到的异常对象赋值给变量 `result`，这样你就可以在 `except` 块中使用这个变量来访问异常的详细信息。

#### 6.2.3 异常捕获完整语法

在实际开发中，为了能够处理复杂的异常情况，实际的**异常语法如下**：

> 使用 `pass` 可以让代码保持结构完整，即该段落什么都不做，未来会填写

```python
try:
	# 尝试执行的代码
	pass
except 错误类型1:
	# 针对错误类型1，对应的代码处理
	pass
except 错误类型2:
	# 针对错误类型2，对应的代码处理
	pass
except (错误类型3, 错误类型4):
	# 针对错误类型3 和 4，对应的d代码处理
	pass
except Exception as result:
	# 打印错误信息
	print(result)
else:
	# 没有异常才会执行的代码
	pass
finally:
	# 无论是否有异常，都会执行的代码
	print("无论是否有异常，都会执行的代码")
```

> - `else` 只有在没有异常时才会执行的代码
> - `finally` 无论是否有异常，都会执行的代码

### 6.3 异常的传递

- 异常的传递 -- 当函数/方法执行出现异常，会将异常传递给函数/方法的**调用**一方
- 而在主函数中调用的其他函数，只要出现异常，都会传递到主函数的异常捕获中
- 这样就不需要在代码中，增加大量的异常捕获，能够保证代码的整洁

```python
def demo1():
    return int(input("请输入整数："))

def demo2():
    return demo1()

# 利用异常的传递性，在主程序捕获异常
try:
    print(demo2())
except Exception as result:
    print("未知错误 %s" % result)
```

### 6.4 抛出 raise 异常

> 在开发中，还可以**根据应用程序特有的业务需求主动抛出异常**

- 在 Python 中提供了一个 `Exception` 异常类
- 在开发时，如果满足特定业务需求时，希望抛出异常，可以：
  1. **创建一个 `Exception` 的对象**
  2. **使用 `raise` 关键字抛出异常对象**

```python
def input_password():

    # 1.提示用户输入密码
    pwd = input("请输入密码：")
    # 2.判断密码长度 >= 8，返回用户输入的密码
    if len(pwd) >= 8:
        return pwd
    # 3.如果 < 8，主动抛出异常
    print("主动抛出异常")
    # 1>创建异常对象 - 可以使用错误信息字符串作为参数
    ex = Exception("密码长度不够")
    # 2>主动抛出异常
    raise ex

# 提示用户输入密码
try:
    print(input_password())
except Exception as result:
    print(result)
```

## 7. Pyecharts实例分析

### 7.1 JSON数据

#### 7.1.1 JSON数据概念

JSON数据格式：轻量级的数据交互格式，可以按照JSON指定的格式去**组织和封装数据**

JSON本质上是一个带有**特定格式的字符串**

主要功能：`json`就是一种在各个编程语言中流通的数据格式，负责不同编程语言中的**数据传递和交互**

JSON就是把字典转变为字符串，或者说是一个元素都是字典的列表转变为字符串

如{"name":"admin,"age":18}

#### 7.1.2 JSON数据转换

```python
# 导入json模块
import json

# 准备列表，列表内每一个元素都是字典，将其转换为JSON
data = [{"name": "卢", "age": 11}, {"name": "zi", "age": 18}, {"name": "jun", "age": 22}]

# 通过json.dumps(data)方法把python数据转化为json数据(ensure_ascii=False即可输出中文字符)
json_str = json.dumps(data, ensure_ascii=False)
print(f"类型是{type(json_str)},内容是{json_str}")

# 通过json.loads(data)方法把json数据转化为python数据(字典)
json.loads(json_str)
print(f"类型是{type(json.loads(json_str))},内容是{json.loads(json_str)}")
```

### 7.2 Pyecharts基础使用

#### 7.2.1 Pyecharts概念

Pyecharts 是一个用于生成图表的 Python 库，基于 ECharts。它提供了简单易用的接口，可以快速创建各种交互式图表，如折线图、柱状图、饼图等

#### 7.2.2 基础实例

1. 实例：绘制折线图

   ```python
   from pyecharts.charts import Line
   from pyecharts.options import TitleOpts, LegendOpts, ToolboxOpts, VisualMapOpts
   
   # 创建一个折线图对象
   line = Line()
   # 对该对象调用其方法，给折线图添加x轴数据
   line.add_xaxis(["中国", "美国", "英国"])
   # 对该对象调用其方法，给折线图添加y轴数据
   line.add_yaxis("GDP", [30, 20, 10])
   
   # 全局配置(针对通用配置，如标题，工具箱)采用set_global_opts方法
   line.set_global_opts(
       title_opts=TitleOpts(title="GDP展示", pos_left="center", pos_bottom="1%"),
       legend_opts=LegendOpts(is_show=True),
       toolbox_opts=ToolboxOpts(is_show=True),
       visualmap_opts=VisualMapOpts(is_show=True),
   )
   # 通过render方法，将代码生成为图像(html文件)
   line.render()
   ```

2. 实例二：绘制柱状图

   ```python
   """
   演示带有时间线的柱状图开发
   """
   # 添加Bar(柱状图)、Timeline(时间线)功能包
   from pyecharts.charts import Bar, Timeline
   # 添加LabelOpts(图例)功能包
   from pyecharts.options import LabelOpts
   # 添加ThemeType(主题设置)功能包
   from pyecharts.globals import ThemeType
   
   bar1 = Bar()
   bar1.add_xaxis(["中国", "美国", "英国"])
   # label_opts=LabelOpts(position="right"):修改图例数据位置
   bar1.add_yaxis("GDP", [30, 30, 20], label_opts=LabelOpts(position="right"))
   # 反转x和y轴
   bar1.reversal_axis()
   
   bar2 = Bar()
   bar2.add_xaxis(["中国", "美国", "英国"])
   # label_opts=LabelOpts(position="right"):修改图例数据位置
   bar2.add_yaxis("GDP", [50, 50, 50], label_opts=LabelOpts(position="right"))
   # 反转x和y轴
   bar2.reversal_axis()
   
   bar3 = Bar()
   bar3.add_xaxis(["中国", "美国", "英国"])
   # label_opts=LabelOpts(position="right"):修改图例数据位置
   bar3.add_yaxis("GDP", [70, 60, 60], label_opts=LabelOpts(position="right"))
   # 反转x和y轴
   bar3.reversal_axis()
   
   # 构建时间线对象,传入字典("theme": ThemeType.LIGHT-主题设置)
   timeline = Timeline({"theme": ThemeType.LIGHT})
   # 在时间线内添加柱状图对象
   timeline.add(bar1, "点1")
   timeline.add(bar2, "点2")
   timeline.add(bar3, "点3")
   # 绘图是用时间线对象绘图，而不是bar对象了
   """
   自动播放设置
   play_interval:自动播放的时间间隔，单位毫秒
   is_timeline_show:是否在播放的时候显示时间线
   is_auto_play:是否自动播放
   is_loop_play:是否循环自动播放
   """
   timeline.add_schema(
       play_interval=1000,
       is_timeline_show=True,
       is_auto_play=True,
       is_loop_play=True
   )
   
   # 绘图是用时间线对象绘图，而不是bar对象了
   timeline.render("基础时间线柱状图.html")
   
   ```

## 8. 类和对象

### 8.1 面向对象(OOP)基本概念

> 面向对象编程 -- `Object Oriented Propragramming` 简称 `OOP`
>

**面向过程：**

1. 把完成某一个需求时 `所有步骤` `从头到尾` 逐步实现
2. 根据开发需求，将某些功能独立地代码封装成一个又一个函数
3. 最后完成地代码，就是顺序地调用不同的函数

![2](./JUN‘s_Python_learning.assets/2.png)

**面向对象：**

> 相比较函数，**面向对象是更大的封装，根据职责在一个对象中封装多个方法**

1. 在完成某一个需求前，首先确定职责--要做的事情(方法)
2. 根据职责确定不同的需求变化，**是专门应对复杂项目开发，提供的固定套路**
3. 最后完成的代码，就是顺序地让不同地对象调用不同的方法

> 可以理解为设计表格-打印生产表格-填写表格

### 8.2 类和对象的概念

类和对象是面向对象编程的两个核心概念

#### 8.2.1 类

- 类是对一群**具有相同特征或者行为的事物的一个统称**，是抽象的，**不能直接使用**
  - **特征**被称为**属性**
  - **行为**被称为**方法**
- 类就相当于制作填写表格的模板，**是一个模板，是负责创建对象的**

#### 8.2.2 对象

- 对象是由类创建出来的一个具体存在，可以直接使用
- 由哪一个类创建出来的对象，就拥有在哪一个类中定义的：
  - 属性
  - 方法
- 对象就相当于根据自己信息填写表格上的内容

>在程序开发中，应该现有类，再有对象

#### 8.3 类和对象的关系

- 类是模板，对象是根据类这个模板创建出来的，应该**先有类，再有对象**
- 类只有一个，而对象可以有很多个
  - 不同的对象之间属性可能会各不相同
- 类中定义了什么属性和方法，对象中就有什么属性和方法，不可能多，也不可能少

> 在程序中使用对象组织数据就是：**设计类(class)-创建对象-对象属性赋值**
>
> 可理解为三个步骤：**设计表格-打印生产表格-填写表格**

#### 8.4 类的设计

在使用面向对象开发前，应该首先分析需求，确定一下程序中需要包含哪些类

![3](./JUN‘s_Python_learning.assets/3.png)

在程序开发中，要设计一个类，通常需要满足以下三个要素：

1. **类名** 这类事物的名字，满足大驼峰命名法
2. **属性** 这类食物具有什么样的特征
3. **方法** 这类食物具有什么样的行为

### 8.3 类和对象基础语法

#### 8.3.1 `dir`内置函数

在 Python 中可以使用以下两个方法查看对象的属性和方法：

1. 在**标识符/数据**后输入一个 `.` ，然后按下 `Tab` 键，`iPython` 会提示改对象能够调用的**方法列表**
2. 使用内置函数 `dir` 传入标识符/数据，可以查看对象内的**所有属性及方法**

> 提示：`__方法名__` 格式的方法是 `Python` 提供的内置方法/属性

| 序号 | 方法名     | 类型 | 作用                                       |
| ---- | ---------- | ---- | ------------------------------------------ |
| 01   | `__new__`  | 方法 | **创建对象**时，会被自动调用               |
| 02   | `__init__` | 方法 | **对象被初始化**时，会被自动调用           |
| 03   | `__del__`  | 方法 | **对象被从内存中销毁**前，会被自动调用     |
| 04   | `__str__`  | 方法 | 返回**对象的描述信息**，print 函数输出使用 |

1. **构造方法**

   `__init__()`,称之为构造方法

   在创建类对象(构造类)的时候，会自动执行,如下`print`自动执行

   在创建类对象(构造类)的时候，将传入参数自动传递给`__init__()`方法使用

   ```python
   class Student:
       # 可以省略，因为在下面方法里面已经完成了对成员变量的定义了
       name = None
       age = None
       tel = None
   
       def __init__(self, name, age, tel):
           self.name = name
           self.age = age
           self.tel = tel
           print("student类创建了一个类对象")
   
   
   std = Student("JUN", 18, "555555")
   print(std.name)
   print(std.age)
   print(std.tel)
   ```

2. 字符串方法

   `__str__`:字符串方法，控制类转换为字符串的方法

   ```python
   class Student:
       def __init__(self, name, age):
           self.name = name
           self.age = age
   
       # __str__魔术方法
       def __str__(self):
           return f"Student:类对象name: {self.name}, age: {self.age}"
   
   
   stu = Student("JUN", 18)
   # 正常情况打印stu将得到类的内存地址，但使用__str__后将会按照规定的返回值进行输出
   print(stu)
   print(str(stu))
   ```

#### 8.3.2 定义简单的类和对象

1. **类的定义和使用：**

   `class` 类名称:     class是关键字

   ​	类的属性      类的属性，即定义在类中的变量(成员变量)

   ​	类的行为      类的行为，即定义在类中的函数(成员方法)

   所有定义在类中的函数将其称之为方法

2. **成员方法的定义语法：**

   `def` 方法名(`self`, 形参1, 形参2)

   ​	方法体

   在成员方法定义的时候必须填写self关键字

   用来表示类自身的意思

   并且在方法内部，想要访问类的成员变量必须使用`self`

   在调用具体方法时不需要理会`self`

3. **创建类对象的语法：**

   对象 = 类名称()

4. **示例**：

   > 面向对象编程思想：类是一种程序内的“设计图纸”，需要基于图纸生产实体(对象)，才能正常工作
   >
   > 面向对象编程就是设计类，基于类创建对象，由对象做具体的工作，即使用对象进行编程

   ```python
   # 设计一个闹钟类
   class Clock:
       # 成员属性
       id = None
       price = None
       
   	# 成员方法
       def ring(self, id, price):
           import winsound
           self.id = id
           self.price = price
           winsound.Beep(2000, 3000)
   
   # 构建两个闹钟对象并让其工作
   clock1 = Clock()
   clock1.ring("id1", 100)
   print(f"id是{clock1.id}价格{clock1.price}")
   
   clock2 = Clock()
   clock1.ring("id2", 10)
   print(f"id是{clock2.id}价格{clock2.price}")
   ```

   















