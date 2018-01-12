---
title: "コンパイラ エラー C2903 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2903
dev_langs: C++
helpviewer_keywords: C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9632a481227cfe428a84c1c0366f88a44f7f27dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2903"></a>コンパイラ エラー C2903
'identifier' : シンボルがクラス テンプレートでも関数テンプレートでもありません  
  
 コードで、テンプレートではないものを明示的にインスタンス化しようとしています。  
  
 次の例では C2903 が生成されます。  
  
```  
// C2903.cpp  
// compile with: /c  
namespace N {  
   template<class T> class X {};  
   class Y {};  
}  
void g() {  
   N::template Y y;   // C2903  
   N::X<N::Y> y;   // OK  
}  
```  
  
 C2903 は、ジェネリックを使用しているときにも発生します。  
  
```  
// C2903b.cpp  
// compile with: /clr /c  
namespace N {  
   class Y {};  
   generic<class T> ref class Z {};  
}  
  
void f() {  
   N::generic Y y;   // C2903  
   N:: generic Z<int>^ z;   // OK  
}  
```