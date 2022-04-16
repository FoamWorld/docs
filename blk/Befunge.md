# 原型
```jl
mutable struct Befunge<:固体
	dire::UInt8
	coll::Bool
	error::Bool
	stack::Vector{Int}
	on::Union{Nothing,地毯}
	input::IO
	output::String
end
Befunge(dire::UInt8=0x1)=Befunge(dire,false,false,[-1],nothing,stdin,"")
```

# 域说明
dire	朝向(0~3)  
coll	是否处在字符收集(collecting)模式  
error	是否发生过错误  
stack	内部数据  
on		所处的地毯（若有）  
ext		扩展信息  

# upd
必须一直处在地毯上  
根据地毯的文字和[原生Befunge语言](https://esolangs.org/wiki/Befunge)运行
