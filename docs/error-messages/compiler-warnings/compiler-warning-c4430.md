---
title: "コンパイラの警告 C4430 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4430
dev_langs:
- C++
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4455419ab6ce8a98dfb26bdb6575cc229d364c0f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4430"></a>コンパイラの警告 C4430
型指定子がありません - int と仮定しました。 注: C++ は int を既定値をサポートしていません  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができますすべての宣言から型を明示的に指定する必要があります。int は不要になったと見なされます。  
  
 C4430 は常に、エラーとして発行されます。  この警告をオフにすることができます、`#pragma warning`または**/wd**; を参照してください[警告](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C4430 を生成します。  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```
