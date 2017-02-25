---
title: "コンパイラ エラー C3637 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3637"
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : friend 関数の定義を関数 '型' の特殊化にすることはできません。  
  
 フレンド関数が、テンプレートまたはジェネリックに対して正しく定義されていません。  
  
 次の例では警告 C3637 が生成されます。  
  
```  
// C3637.cpp  
template <class T>  
void f();  
  
struct S {  
   friend void f<int>() {}   // C3637  
};  
```  
  
 解決方法 :  
  
```  
// C3637b.cpp  
// compile with: /c  
template <class T>  
void f();  
  
struct S {  
   friend void f() {}  
};  
```  
  
 C3637 は、ジェネリックを使用しているときも発生します。  
  
```  
// C3637c.cpp  
// compile with: /clr  
  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf<int>() {}   // C3637  
};  
```  
  
 解決方法 :  
  
```  
// C3637d.cpp  
// compile with: /clr /c  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf() {}  
};  
```