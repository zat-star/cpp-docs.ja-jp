---
title: "__super | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__super_cpp"
  - "__super"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__super キーワード [C++]"
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __super
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 オーバーライドする関数について、基底クラス実装を呼び出すことを明示できます。  
  
## 構文  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## 解説  
 オーバーロード解決フェーズ時にすべてのアクセス可能な基底クラス メソッドが考慮され、最優先の一致を示す関数が呼び出されます。  
  
 `__super` は、メンバー関数の本体でのみ表示できます。  
  
 `__super` は、using 宣言と共に使用することはできません。  詳細については、「[using 宣言](../cpp/using-declaration.md)」を参照してください。  
  
 コードを挿入する[属性](../windows/cpp-attributes-reference.md)を導入すると、呼び出す必要があるメソッドを含む 1 つ以上の名前がわからない基底クラスがコードに含まれる可能性があります。  
  
## 使用例  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)