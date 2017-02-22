---
title: "コンパイラ エラー C3772 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3772"
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# コンパイラ エラー C3772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"name" : 無効なフレンド テンプレートの宣言  
  
 クラス テンプレートの特殊化のフレンドを宣言することは無効です。 クラス テンプレートの明示的または部分的な特殊化を宣言し、同じステートメントでその特殊化のフレンドを宣言することはできません。*name* プレースホルダーは、無効な宣言を識別します。  
  
### このエラーを解決するには  
  
-   クラス テンプレートの特殊化のフレンドを宣言しません。  
  
-   アプリケーションに適切な場合は、クラス テンプレートのフレンドを宣言するか、特定の部分的または明示的な特殊化のフレンドを宣言します。  
  
## 使用例  
 次のコード例は、クラス テンプレートの部分的特殊化のフレンドを宣言しているため、失敗します。  
  
```  
// c3772.cpp // compile with: /c // A class template. template<class T> class A {}; // A partial specialization of the class template. template<class T> class A<T*> {}; // An explicit specialization. template<> class A<char>; class X { // Invalid declaration of a friend of a partial specialization. template<class T> friend class A<T*>; // C3772 // Instead, if it is appropriate for your application, declare a // friend of the class template. Consequently, all specializations // of the class template are friends: //    template<class T> friend class A; // Or declare a friend of a particular partial specialization: //    friend class A<int*>; // Or declare a friend of a particular explicit specialization: //    friend class A<char>; };  
```  
  
## 参照  
 [テンプレートの仕様](../Topic/Template%20Specifications.md)   
 [クラス テンプレートの部分的特殊化](../../cpp/template-specialization-cpp.md)   
 [クラス テンプレートの明示的特殊化](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)