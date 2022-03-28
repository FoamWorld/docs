# 状态信息
## 通用接口
|函数名|参数类型（第一个参数为状态类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|id||String|唯一辨识符||
|exist|||诞生时执行||
|e_exist|||湮灭时执行||
|c_union||Bool|（该类型）能否合并|应为定值|
|union|状态（同类型）,UInt,UInt|Pair{UInt,状态}|合并||
|upd|Entity||起效||

## 列表
+ 自发移动
* **毒**

# 状态组信息
## 原型
```jl
mutable struct 状态组
	data::Dict{String,Union{Pair{UInt,状态},Vector{Pair{UInt,状态}}}}
end
```

## 通用接口
|函数名|参数类型（第一个参数为状态组类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|push!|UInt,状态||添加状态||
