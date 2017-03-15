---
title: "コンパイラ エラー C2990 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2990"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2990"
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# コンパイラ エラー C2990
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : 非クラス '型' は、既にクラス '型' として宣言されていました  
  
 非ジェネリック クラスまたは非テンプレート クラスは、ジェネリック クラスまたはテンプレート クラスを再定義します。  ヘッダー ファイルに矛盾がないかどうかを調べてください。  
  
 次の例では警告 C2990 が生成されます。  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 は、Visual C\+\+ 2005 の Visual C\+\+ コンパイラの互換性に影響する変更点が原因で発生することもあります。1 つの型に対する複数の宣言がテンプレートの仕様に関して一致することがコンパイラで要求されるようになりました。  
  
 次の例では警告 C2990 が生成されます。  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```