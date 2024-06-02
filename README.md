# shell-
COMP9044 shell学习
学习链接：https://www.runoob.com/linux/linux-shell-variable.html 



------day1 5.30------
#! 是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行，即使用哪一种 Shell。
echo 命令用于向窗口输出文本。
chmod +x ./test.sh  #使脚本具有执行权限
./test.sh  #执行脚本
------day2 6.1------
string="abcd"----获取字符串长度
echo ${#string}   # 输出 4
echo ${string:1:2}  #获取1-2字符
#----shell数组
array_name(
value0
value1
...
)
echo ${array_name[0]}#读取数组0
----------9024 CPU笔记------------
wc（word counter）：
  option：用于计算行l 单词数w，字节大小c
    eg: wc -l filename.sh
cut：用于按列 切割文本
  option：d:指定分隔符： -d‘｜’
          f：选择字段：-f3（选择第三个字段）；-f1-3：选择1-3字段；-f3-：选择3字段以后的所有字
          eg: cut -d'|' -f4 file·name.sh
sort:对文件的行进行排列
  option:
    n:按数值排序；
    r：逆序排序；
    k：指定排序的列；(-k2,2,起始第2列开始，第2列结束)
    t：分割；
  eg：short -t'|' -k2,2 nr filename.sh
uniq:去重，配合sort使用
  option:
    c:显示每行重复次数
    d:仅显示重复的行
    u:仅显示不重复的行
    f:
