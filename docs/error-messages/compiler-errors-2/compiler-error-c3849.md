---
title: "コンパイラ エラー C3849 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3849"
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型 'type' の式における関数スタイルの呼び出しは、使用できる number 個すべての演算子オーバーロードの const または volatile 修飾子を失う可能性があります。  
  
 const\-volatile 型の変数で呼び出すことができるのは、同等以上の const\-volatile 修飾で定義されているメンバー関数だけです。  
  
 このエラーを解決するには、適切なメンバー関数を指定します。  変換により修飾が失われる場合、const または volatile で修飾されたオブジェクトでの変換は実行できません。  修飾子を取得する変換は実行できますが、修飾子を失う変換は実行できません。  
  
 次の例では C3849 エラーが生成されます。  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```