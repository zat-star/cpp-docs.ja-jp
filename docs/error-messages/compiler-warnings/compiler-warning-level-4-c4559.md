---
title: "コンパイラの警告 (レベル 4) C4559 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4559"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4559"
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 4) C4559
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 再定義; 関数は \_\_declspec\(modifier\) を取得します  
  
 関数が再定義されたか再宣言され、2 番目の定義または宣言で \_\_**declspec** 修飾子 \(***modifier***\) が追加されました。  この警告は、情報を提供するためだけのものです。  この警告を解決するには、いずれかの定義を削除します。  
  
 次の例では警告 C4559 が生成されます。  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```