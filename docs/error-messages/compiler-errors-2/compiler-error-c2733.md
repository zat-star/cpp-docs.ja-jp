---
title: "コンパイラ エラー C2733 | Microsoft Docs"
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
  - "C2733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2733"
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オーバーロードされた関数 'function' の C リンケージの 2 回以上の宣言は許されません。  
  
 複数のオーバーロードされた関数が、C のリンケージで宣言されています。  C のリンケージを使用するときは、その関数のうちの 1 つの形式だけを外部リンケージにしてください。  オーバーロードされた関数どうしは同じ非装飾名を持つため、これらを C のプログラムでは使用できません。  
  
 次の例では警告 C2733 が生成されます。  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```