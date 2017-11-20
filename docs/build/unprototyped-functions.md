---
title: "プロトタイプ宣言されていない関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbc9324753f6ec2c9a332af00a00dd85116e1943
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="unprototyped-functions"></a>プロトタイプ宣言されていない関数
ない完全なプロトタイプ関数では、呼び出し元は、整数値として整数と浮動小数点値として渡します倍精度。 浮動小数点値の場合にのみ、整数レジスタと浮動小数点レジスタの両方値が含まれます、float 場合に、呼び出し先は、整数レジスタに値が必要です。  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)