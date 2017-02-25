---
title: "コンパイラ エラー C3815 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3815"
ms.assetid: c5a3b404-6341-4fd3-92af-152b404c4dde
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メソッド 'get\_accessor' の戻り値の型は、setter の最後のパラメーターの型と一致しなければなりません  
  
 [プロパティ](../../misc/property.md)の宣言時に、`get_accessor` メソッドの戻り値が set アクセサー メソッドの宣言内の最後のパラメーターと一致する必要があります。  
  
 C3815 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では警告 C3815 が生成されます。  
  
```  
// C3815.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc class X  
{  
public:  
   __property char get_N()  
   // try the following line instead  
   // __property int get_N()  
   {  
      return m_val;  
   }  
  
   __property void set_N( int val)  
   {  
      m_val = val;  
   }  
  
private:  
   int m_val;  
};   // C3815  
```  
  
 次の例では、プロパティをオーバーロードして、getter の戻り値の型が setter の最後のパラメーターと一致しないようにする方法を示します。  
  
```  
// C3815b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
public __gc class MyClass {  
public:  
// 1st property:  
   __property System::Int32 get_p1();  
   __property void set_p1(System::Int32 i);  
  
// 2nd property (only setter):  
   __property void set_p1(System::Int32* i);  
  
};  
```