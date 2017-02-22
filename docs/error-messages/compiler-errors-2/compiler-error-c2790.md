---
title: "コンパイラ エラー C2790 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2790"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2790"
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2790
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super' : このキーワードはクラス メンバー関数の本体内でのみ使用できます。  
  
 このエラー メッセージが表示されるのは、ユーザーがメンバー関数のコンテキストの外側でキーワード [super](../../cpp/super.md) を使用した場合です。  
  
 次の例では警告 C2790 が生成されます。  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```