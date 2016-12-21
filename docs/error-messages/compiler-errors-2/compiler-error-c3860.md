---
title: "コンパイラ エラー C3860 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3860"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3860"
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3860
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型引数リスト \(クラス '型' 名の後\) は、'型' パラメーター リストで使用されている順序でパラメーターを一覧表示しなければなりません  
  
 ジェネリック引数またはテンプレート引数リストの形式が間違っています。  
  
 次の例では警告 C3860 が生成されます。  
  
```  
// C3860.cpp  
// compile with: /LD  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T1, T2>::f() {}   // C3860  
```  
  
 解決方法 :  
  
```  
// C3860b.cpp  
// compile with: /c  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T2, T1>::f() {}  
```  
  
 C3860 は、ジェネリックを使用しているときも発生します。  
  
```  
// C3860c.cpp  
// compile with: /clr  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,T>::f() {}   // C3860  
```  
  
 解決方法 :  
  
```  
// C3860d.cpp  
// compile with: /clr /c  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,U>::f() {}  
```