---
title: "コンパイラ エラー C2658 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80e7644e949c3d3c605568d820296bbe8310deed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2658"></a>コンパイラ エラー C2658
'member': 匿名構造体/共用体での再定義  
  
 2 つの匿名構造体または共用体には、さまざまな種類が、同じ識別子を持つメンバーの宣言が含まれています。 [/Za](../../build/reference/za-ze-disable-language-extensions.md)、同じ識別子と型を持つメンバーに対してもこのエラーが表示されます。  
  
 次の例では、C2658 が生成されます。  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```