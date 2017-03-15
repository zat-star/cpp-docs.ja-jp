---
title: "コンパイラの警告 (レベル 4) C4211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4211"
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : extern が static に再定義されました。  
  
 既定の Microsoft 拡張機能 \(\/Ze\) では、`extern` 識別子を **static** として再定義できます。  
  
## 使用例  
  
```  
// C4211.c  
// compile with: /W4  
extern int i;  
static int i;   // C4211  
  
int main()  
{  
}  
```  
  
 このような再定義は ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。  
  
## 参照  
 [\(NOTINBUILD\)Static Storage\-Class Specifiers](http://msdn.microsoft.com/ja-jp/3ba9289a-a412-4a17-b319-ceb2c087df48)