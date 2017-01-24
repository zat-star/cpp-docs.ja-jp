---
title: "コンパイラの警告 (レベル 4) C4221 | Microsoft Docs"
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
  - "C4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4221"
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 'identifier' : 自動変数のアドレスを使った初期化はできません。  
  
 既定の Microsoft 拡張機能 \(\/Ze\) では、集約型 \(配列、構造体、または共用体\) をローカル \(自動\) 変数のアドレスで初期化できます。  
  
## 使用例  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 このような初期化は、ANSI 互換のオプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。