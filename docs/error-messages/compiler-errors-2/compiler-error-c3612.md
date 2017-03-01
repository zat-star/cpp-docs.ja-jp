---
title: "コンパイラ エラー C3612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: fa36c033cf311538e1d77ce37b2d3e4a3936b7d7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3612"></a>コンパイラ エラー C3612
'type': シール クラスは抽象にすることはできません  
  
使用して定義されている型`value`は既定では、封印されてクラスは、その基本のすべてのメソッドを実装する場合を除き、抽象とします。 シールされた抽象クラスは、基本クラスにもなることができます。 また、インスタンス化できます。  
  
詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
次の例では、c3612 エラーが生成されます。  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```
