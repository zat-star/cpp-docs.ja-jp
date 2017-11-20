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
ms.openlocfilehash: 6541dc5dc262f5d00325c594d64637b5e87a45d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="predefined-rules"></a>定義済み規則
組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。  
  
|ルール|コマンド|既定<br /><br /> アクション|Batch<br /><br /> ルール|nmake が実行されるプラットフォーム|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|no|x86|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|可|x86|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Ｘ|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|可|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|no|all|  
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|all|  
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|no|all|  
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|all|  
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|no|all|  
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|可|all|  
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|no|all|  
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|可|all|  
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|no|すべて|  
  
## <a name="see-also"></a>関連項目  
 [推論規則](../build/inference-rules.md)