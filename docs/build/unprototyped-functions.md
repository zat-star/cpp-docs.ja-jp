---
title: "プロトタイプ宣言されていない関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 574c4564394e251dde9345d3658304019dae838d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unprototyped-functions"></a>プロトタイプ宣言されていない関数
ない完全なプロトタイプ関数では、呼び出し元は、整数値として整数と浮動小数点値として渡します倍精度。 浮動小数点値の場合にのみ、整数レジスタと浮動小数点レジスタの両方値が含まれます、float 場合に、呼び出し先は、整数レジスタに値が必要です。  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)