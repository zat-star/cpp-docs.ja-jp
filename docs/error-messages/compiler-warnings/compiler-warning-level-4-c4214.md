---
title: "コンパイラの警告 (レベル 4) C4214 | Microsoft Docs"
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
  - "C4214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4214"
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 整数型以外のビット フィールドです。  
  
 既定の Microsoft 拡張機能 \(\/Ze\) では、ビット フィールドの構造体のメンバーに、任意の整数型を使用できます。  
  
## 使用例  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 このようなビット フィールドは ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。