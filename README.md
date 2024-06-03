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

filter:input---->wc/cut/sort/...----->output
并没有改变原文件，只是做数据筛选

pipeline管道'|' 对数据进行多重筛选
filter1|filter2|...


cut -f3 filename.sh >result(筛选后将输出结果保存到result文件)
wc（word counter）：
  option：用于计算
    option：
      行l 单词数w，字节大小c
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
tr：用于删除或替换字符
  eg：tr'e''y'(吧e替换成y)
  option：
    d:tr -d'' filename.sh 删除所有空格
    s:tr -s'' filename.sh 压缩一个或多个连续空格字符为一个空格
sed:流编辑器 文本内容替换
  option：
    s:替换文本字符串 sed's/old/new'
    d:删除匹配模式的某行 sed'2d'删除第二行 sed'2-4d'删除2-4行
    g:全局替换 sed'g/old/new'

-----正则表达式regex-------
regex同样也是filter，匹配文本工具，定义一种搜索模式。
regex basical special meaning:
  .:anything
  *:anytime
  .*:anything anytime
  +:>=1
  ?:0/1 eg:a{?}c匹配结果ac，aac
  {}:重复确定次数；{4}:出现重复4次 a{4}c匹配结果：aaaac；a{6-9}c:出现6-9次
  []:match列表中任何一个字母
    eg：[aeiouAEIOU]:match anyvowel
        [a-zA-Z0-9]:match every 字母和数字
  pattern1|pattern2: match pattern1或2
  （）表示group
    eg：(hi|hello|hey)9044 结果：hi 9044；hello9044；hey9044
    
  

