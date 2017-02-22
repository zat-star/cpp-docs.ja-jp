---
title: "コンパイラ エラー C2480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2480"
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'thread' は静的なデータ項目に対してのみ有効です。  
  
 `thread` 属性は、自動変数、非静的なデータ メンバー、関数パラメーター、関数宣言または関数定義と共に使用できません。  
  
 `thread` 属性は、グローバル関数、静的データ メンバー、およびローカル静的変数に対してだけ使用してください。  
  
 次の例では警告 C2480 が生成されます。  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```