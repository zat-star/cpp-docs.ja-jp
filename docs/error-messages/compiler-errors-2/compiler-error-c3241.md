---
title: "コンパイラ エラー C3241 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3241
dev_langs: C++
helpviewer_keywords: C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f704b466edc30fe3960ef0e2cedebad692015531
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3241"></a>コンパイラ エラー C3241
'method': このメソッドが 'interface' によって導入されていません  
  
 関数を明示的にオーバーライドすると場合、関数のシグネチャはオーバーライドする関数の宣言を正確に一致する必要があります。  
  
 次の例では、C3241 が生成されます。  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```