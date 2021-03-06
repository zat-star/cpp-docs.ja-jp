---
title: "コンパイラ エラー C3900 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3900
dev_langs:
- C++
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7d85041e90584822397302c39a1050fb59b2b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3900"></a>コンパイラ エラー C3900
'member': 現在のスコープで許可されていません  
  
 プロパティ ブロックには、関数の宣言とインライン関数の定義のみを含めることができます。 プロパティ ブロックでは、関数以外のメンバーは許可されません。 Typedef、演算子、または friend 関数は許可されません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 イベントの定義には、アクセス メソッドおよび関数のみを含めることができます。  
  
 次の例では、C3900 が生成されます。  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 次の例では、C3900 が生成されます。  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```