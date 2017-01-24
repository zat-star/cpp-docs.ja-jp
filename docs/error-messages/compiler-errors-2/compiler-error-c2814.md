---
title: "コンパイラ エラー C2814 | Microsoft Docs"
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
  - "C2814"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2814"
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2814
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : ネイティブ型をマネージ型または WinRT 型の 'type' の中に入れ子にすることはできません  
  
## 使用例  
 ネイティブ型を CLR 型または WinRT 型の中に入れ子にすることはできません。  次の例では、C2814 を生成し、その修正方法を示しています。  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
  
## 使用例  
 C\+\+ マネージ拡張を使用する際は、キーワード [\_\_gc](../Topic/__gc.md)、[\_\_nogc](../../misc/nogc.md)、[\_\_value](../../misc/value.md) のいずれかを使用して、埋め込み型の "マネージ特性" を明示的に指定する必要があります。  
  
 次の例では、C2814 を生成し、その修正方法を示しています。  
  
```  
// C2814_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class A {  
   class B {};   // C2814  
   __gc class C {};   // OK  
};  
```