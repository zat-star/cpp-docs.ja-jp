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
ms.workload: cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [section](../../preprocessor/section.md)