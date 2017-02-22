---
title: "コンパイラ エラー C2062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2062"
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型 'type' は不要です。  
  
 コンパイラが予期していない型名が見つかりました。  
  
 次の例では警告 C2062 が生成されます。  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 エラーは、コンストラクターのパラメーター リストで定義されていない型の処理方法が原因で発生する場合もあります。  コンパイラは未定義 \(またはスペルミス\) の型を検出すると、コンストラクターを式と見なし、C2062 エラーを表示します。  これを解決するには、コンストラクターのパラメーター リストに定義されている型だけを使用します。