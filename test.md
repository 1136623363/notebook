

1. 空列表只能从第一个元素list[0]开始赋值
2. 列表转换成字符串
   使用 join 函数
   
   ```
   list1 = ['a', '1', 'b', '2']
   list1_str = ', '.join(list1)
   list1_str = ' '.join(list1)
   ```
3. 可以使用下划线_作为数字（包括整数和小数）的分隔符，不会对数值造成影响
4. 0.1转化成二进制是无限循环的
5. 三个单引号或者双引号可以对多行内容进行注释，这其实是 Python 长字符串的写法
6. 使用切片访问列表元素的格式为：   
   ```listname[start : end : step]```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMjc5MzkwNTJdfQ==
-->