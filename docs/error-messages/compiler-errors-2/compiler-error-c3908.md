---
title: "コンパイラ エラー C3908 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 05b4f772c5c1acf8da9247f27fa92a947a0ffc5b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908
'construct' より少ない制限の厳しいアクセス レベル  
  
 プロパティ アクセサー メソッド (get または set) は、プロパティ自体に指定されたアクセスよりも制限の緩いアクセスにはできません。  同様に、イベントのアクセサー メソッドの  
  
 詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3908 が生成されます。  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```
