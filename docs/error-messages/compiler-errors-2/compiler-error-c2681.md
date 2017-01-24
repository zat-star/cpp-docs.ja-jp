---
title: "コンパイラ エラー C2681 | Microsoft Docs"
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
  - "C2681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2681"
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2681
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : name の式の型が無効です。  
  
 キャスト演算子を使用して無効な型からの変換を試みています。  たとえば、[dynamic\_cast](../../cpp/dynamic-cast-operator.md) 演算子を使用して式をポインター型に変換する場合は、元の式がポインターである必要があります。  
  
 次の例では警告 C2681 が生成されます。  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```