---
title: "コンパイラ エラー C2910 | Microsoft Docs"
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
  - "C2910"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2910"
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 明示的な特殊化にすることはできません。  
  
 関数の明示的な特化が 2 回試行されています。  
  
 次の例では警告 C2910 が生成されます。  
  
```  
// C2910.cpp  
// compile with: /c  
template <class T>  
struct S;  
  
template <> struct S<int> { void f() {} };  
template <> void S<int>::f() {}   // C2910 delete this specialization  
```  
  
 C2910 エラーは、非テンプレート メンバーの明示的な特化を試みた場合にも生成されることがあります。  つまり、明示的な特化を行うことができるのは、関数テンプレートだけです。  
  
 次の例では警告 C2910 が生成されます。  
  
```  
// C2910b.cpp  
// compile with: /c  
template <class T> struct A {  
   A(T* p);  
};  
  
template <> struct A<void> {  
   A(void* p);  
};  
  
template <class T>  
inline A<T>::A(T* p) {}  
  
template <> A<void>::A(void* p){}   // C2910  
// try the following line instead  
// A<void>::A(void* p){}  
```  
  
 このエラーは、Visual Studio .NET 2003 で行った、コンパイラ準拠作業の結果として生成されることもあります。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ でコードを有効にするには、`template <>` を削除します。  
  
 次の例では警告 C2910 が生成されます。  
  
```  
// C2910c.cpp  
// compile with: /c  
template <class T> class A {  
   void f();  
};  
  
template <> class A<int> {  
   void f();  
};  
  
template <> void A<int>::f() {}   // C2910  
// try the following line instead  
// void A<int>::f(){}   // OK  
```