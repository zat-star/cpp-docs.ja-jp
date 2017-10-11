---
title: "コンパイラ エラー C3612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3612
dev_langs:
- C++
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dd430c7dbdfae88d80e073fa9e624f123c41f366
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3612"></a>コンパイラ エラー C3612
'type': シールされたクラスを抽象にすることはできません  
  
使用して定義されている型`value`は既定では、封印されていると、クラスが抽象クラス ベースのすべてのメソッドを実装しない限り、します。 シールされた抽象クラスは基底クラスにもできます。 また、インスタンス化できます。  
  
詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
次の例では、C3612 が生成されます。  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```
