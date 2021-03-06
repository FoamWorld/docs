# 指令信息
## 指令格式
基本格式：`指令名 参数1 参数2 ... 参数n`  
若参数中有空格，可以在最外套一层 **\`\`** ，其中可以使用转义：
* **\\\`** => **\`**
* **\\\\** => **\\**

## 指令参数类型
|名称|代号|说明|
|:-:|:-:|:-:|
|字符串|s|保留原字符串|
|整数|i|10进制整数|
|x整数坐标|px|若第一个字符为`~`，表示以发起者x坐标偏移，否则为绝对坐标，使用10进制整数|
|y整数坐标|py|若第一个字符为`~`，表示以发起者y坐标偏移，否则为绝对坐标，使用10进制整数|
|方块|blk|使用`fw`格式，不同的是2边不需要括号|
|物品|itm|使用`fw`格式，不同的是2边不需要括号、若检测到方块类型，自动嵌套`IFB`|

## 指令列表
|名称|参数类型|描述|
|:-:|:-:|:-:|
|clear/clear_info||清空信息框|
|eval|s|嵌入代码|
|fill/fill_override|blk,px,py,i,i|覆盖一块矩形区域的原有方块|
|give|itm,i:1|给予物品|
|say|s|在信息框发言|
|seed/show_seed||显示地图种子|

## 数据结构
* 以字典方式存于全局变量`commands`中
* `Tuple{Tuple,UInt8,Function}`
* 第一个元组是参数类型列表
* 第二个元组是默认参数（在末尾）个数
* 第三个函数用于执行
