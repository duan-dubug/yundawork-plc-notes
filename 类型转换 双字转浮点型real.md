

---
created: 2025-11-20
status: #已解决
tags: [类型转换, {{modbus读取的数据进行数据转换}}]
related: [485]
---
# {{485}}

## 问题描述
读取到的485数据  需要组合成双字然后转化成浮点类型

## 环境与复现步骤
1. 485读取后的数据需要进行类型转化  但是dword_to_real  只是进行数值转化  并不会进行内存的转化
2. 

## 错误信息/日志/图片
1.


## 根本原因分析
使用内存的转化 而不是数值的转化。使用指针或者使用联合体



## 解决方案/步骤
1. mem.MemMove(pSource:=ADR(dwcombine) , pDestination:=ADR(RTU_REAL) , uiNumberOfBytes:=4 );
2.使用以上指令  调取指针上的内存 
3，或者使用联合体  ![[Pasted image 20251120094727.png]]

## 参考链接
-
