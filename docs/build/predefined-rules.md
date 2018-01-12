---
title: "定義済み規則 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3be1c8eea7b11f60e9ce9a7cbf5ebc0c2b99b698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-rules"></a>定義済み規則
組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。  
  
|ルール|コマンド|既定値<br /><br /> アクション|Batch<br /><br /> ルール|nmake が実行されるプラットフォーム|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|Ｘ|x86|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|可|x86|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Ｘ|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|可|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|no|すべて|  
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|すべて|  
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|no|すべて|  
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|すべて|  
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|no|すべて|  
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|可|すべて|  
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|no|すべて|  
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|可|すべて|  
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|Ｘ|すべて|  
  
## <a name="see-also"></a>参照  
 [推論規則](../build/inference-rules.md)