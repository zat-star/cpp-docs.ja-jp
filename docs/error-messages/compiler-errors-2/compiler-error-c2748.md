---
title: "コンパイラ エラー C2748 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2748"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2748"
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C2748
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マネージ配列または WinRT 配列を作成するには、配列のサイズまたは配列の初期化子を指定する必要があります。  
  
 マネージ配列または WinRT 配列の形式が正しくありません。  詳細については、「[配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では C2748 を生成し、その修正方法を示しています。  
  
```  
// C2748.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>();   // C2748  
   // try the following line instead  
   array<int> ^p2 = new array<int>(2);  
}  
```