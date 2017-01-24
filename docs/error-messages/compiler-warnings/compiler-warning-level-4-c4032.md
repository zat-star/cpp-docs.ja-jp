---
title: "コンパイラの警告 (レベル 4) C4032 | Microsoft Docs"
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
  - "C4032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4032"
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'数値' 番目の引数の型は以前の宣言の型と一致しません。  
  
 パラメーターの型は、既定の上位変換を行っても以前の宣言にある型との互換性がありません。  
  
 これは、ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md) オプション指定\) ではエラーになり、Microsoft 拡張機能 \(\/Ze オプション\) を使用している場合は警告になります。  
  
## 使用例  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```