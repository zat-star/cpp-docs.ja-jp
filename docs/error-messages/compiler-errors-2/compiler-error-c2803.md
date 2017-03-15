---
title: "コンパイラ エラー C2803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2803"
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' の宣言で、クラス型のパラメーターが 1 つも指定されていません。  
  
 オーバーロードされた演算子に、クラス型のパラメーターが指定されていません。  
  
 「b」を作成、参照 \(ポインターではなく参照を使用\) または値を 1 個以上のパラメーターを \< 渡す必要があります \(型クラス A\) である a および b。  
  
 どちらのパラメーターもポインターの場合は、ポインター アドレスの純粋な比較が行われるため、ユーザー定義の変換は使用されません。  
  
 次の例では警告 C2803 が生成されます。  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```