---
title: "コンパイラ エラー C3168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3168"
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : マネージ enum の基になる型が正しくありません。  
  
 `enum` 型に指定された基になる型は無効です。  基になる型は、C\+\+ の整数型または対応する CLR 型であることが必要です。  
  
 次の例では警告 C3168 が生成されます。  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
  
 次の例では警告 C3168 が生成されます。  
  
```  
// C3168_2.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {};  
  
__value enum E : G {e};   // C3168  
__value enum F {f};   // OK  
```