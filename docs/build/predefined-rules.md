---
title: "定義済み規則 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "規則、定義済み"
  - "NMAKE プログラム、定義済み規則"
  - "定義済みの規則 (NMAKE の)"
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 定義済み規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。  
  
|規則|コマンド|既定の<br /><br /> アクション|Batch<br /><br /> 規則|nmake が実行されるプラットフォーム|  
|--------|----------|-------------------|------------------|--------------------------|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml $\<|no|x86|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml \/c $\<|可|x86|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml64 $\<|no|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml64 \/c $\<|可|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|.c.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|no|all|  
|.c.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|可|all|  
|.cc.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|no|all|  
|.cc.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|可|all|  
|.cpp.exe|$\(CPP\) $\(CPPFLAGS\) $\<|cl $\<|no|all|  
|.cpp.obj|$\(CPP\) $\(CPPFLAGS\) \/c $\<|cl \/c $\<|可|all|  
|.cxx.exe|$\(CXX\) $\(CXXFLAGS\) $\<|cl $\<|no|all|  
|.cxx.obj|$\(CXX\) $\(CXXFLAGS\) \/c $\<|cl \/c $\<|可|all|  
|.rc.res|$\(RC\) $\(RFLAGS\) \/r $\<|rc \/r $\<|no|all|  
  
## 参照  
 [推論規則](../build/inference-rules.md)