---
title: "コンパイラ エラー C2034 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2034
dev_langs: C++
helpviewer_keywords: C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9b1f80fcdd3fa8819fbd3d800aa4cfbd50e01c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2034"></a>コンパイラ エラー C2034
'identifier': 型のビット フィールドがビット数には小さすぎます  
  
 ビット フィールドの宣言内のビット数は、基本型のサイズを超えています。  
  
 次の例では、C2034 が生成されます。  
  
```  
// C2034.cpp  
struct A {  
   char test : 9;   // C2034, char has 8 bits  
};  
```  
  
 考えられる解決方法:  
  
```  
// C2034b.cpp  
// compile with: /c  
struct A {  
   char test : 8;  
};  
```