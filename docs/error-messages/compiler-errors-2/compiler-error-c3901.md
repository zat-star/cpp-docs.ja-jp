---
title: "コンパイラ エラー C3901 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3901
dev_langs:
- C++
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 778bb3336d33c52ce0efcefe96d4da304c1502cf
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3901"></a>コンパイラ エラー C3901
'accessor_function': 戻り値の型 'type' があります。  
  
 少なくとも 1 つの get メソッドの戻り値の型は、プロパティの型と一致する必要があります。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 次の例では、C3901 が生成されます。  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```
