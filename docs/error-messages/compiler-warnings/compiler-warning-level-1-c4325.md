---
title: "コンパイラの警告 (レベル 1) C4325 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4325
dev_langs: C++
helpviewer_keywords: C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b5ce2e90705a1f3a899ef31313d1a402d2ecc04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4325"></a>コンパイラの警告 (レベル 1) C4325
**標準のセクションの属性 '**   
 ***セクション*' は無視されます**  
  
 標準のセクションの属性は変更できません。 例:  
  
```  
#pragma section(".sdata", long)  
```  
  
 これは、上書き、`.sdata`標準のセクションを使用して、**短い**データ型、**長い**データ型。  
  
 変更することがありますいない属性を含めるには、標準のセクション  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 その他のセクションでは、後で追加可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [section](../../preprocessor/section.md)