# 物品信息
## 通用接口
|函数名|参数类型（第一个参数为Item类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|id||String:类型名|唯一辨识符|若在物品形态辨识符会丢失信息，堆叠数应设置为1|
|text||String|在当前语言中的显示信息||
|stack||UInt8:16|最大堆叠数≤16|
|c_use||Bool:false|能否使用||
|one_use||Bool:true|是否只能单次使用|在`c_use`为`true`后调用，不应调用`e_use`|
|use||Target,Target|开始使用|第一个参数为使用者，第二个参数为目标|
|e_use|||结束使用||
|updg|||更新GUI||
|i_show|*Canvas*||显示||
|i_show_l|*Canvas*||辅助显示|不应被`i_show`以外函数调用|
|t_blk||Union{Missing,Block}|转化为方块|非引用（调用`deepcopy`），默认missing|

* 允许在函数第二参数栏（`;`后）增加参数，但必须提供默认值
* `w`开头不会被占用

## 指定的field
|名称|类型|描述|
|:-:|:-:|:-:|
|wr||包裹|
|mat|Material|材料|
|t|UInt8|表示一类物品中一个的编号|

## 列表
+ EI (Empty Item) 占位，表示空物品
+ IFB (Item From Block) 对方块类型的一层包裹
+ NI (Named Item) 对物品类型的一层包裹，表示被命名的物体
+ DI (Detailed Item) 对物品类型的一层包裹，表示物品存在额外信息（可能包括但不限于`name`）
+ 书
+ 桶 用于装液体，数据在`装液体table`中
+ 模具 用于制造零件
* **零件**
	+ 薄板
	+ 锭
	+ 棍

# IB（Item Board，物品管理器）信息
## 原型
```jl
mutable struct IB
	l::Int
	n::Vector{UInt8}
	i::Vector{Item}
end
```

## 通用接口
|函数名|参数类型（第一个参数为IB类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|get_n|Int|UInt8|获得数量|`0x0-0xf`对应`1-16`|
|set_n!|Int,UInt8||设置数量|`0x0-0xf`对应`1-16`|
|get|Int|Pair{Item,UInt8}|获得数据|`0x0-0xf`对应`1-16`|
|set!|Int,Pair{Item,UInt8}||设置数据|`0x0-0xf`对应`1-16`|
|remove!|Int||移除||
|clear!|||清空||
|reduce!|Int,Int||减少一定数量||
|give!|Item,Int||给予一定数量的物品||
