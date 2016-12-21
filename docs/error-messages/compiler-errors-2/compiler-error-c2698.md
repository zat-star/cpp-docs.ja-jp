---
title: "コンパイラ エラー C2698 | Microsoft Docs"
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
  - "C2698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2698"
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration 1' の using 宣言は、現存する 'declaration 2' の using 宣言と共存することはできません。  
  
 データ メンバーに [using 宣言](../../cpp/using-declaration.md)がある場合、オーバーロードできるのは関数だけであるため、同じスコープ内で同じ名前を使用する using 宣言は許可されません。  
  
 次の例では警告 C2698 が生成されます。  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```