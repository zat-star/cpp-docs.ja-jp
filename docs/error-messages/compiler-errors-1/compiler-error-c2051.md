---
title: "コンパイラ エラー C2051 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2051
dev_langs: C++
helpviewer_keywords: C2051
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6814d3d8bd7e11214e3ab33d14f2dad67c74b152
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2051"></a>コンパイラ エラー C2051
case 式の定数ではありません。  
  
 Case 式は、整数定数である必要があります。  
  
 次の例では、C2051 が生成されます。  
  
```  
// C2051.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case x:   // C2051 use constant expression to resolve error  
         break;  
      default:  
         break;  
   }  
}  
```  
  
 考えられる解決策:  
  
```  
// C2051b.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```