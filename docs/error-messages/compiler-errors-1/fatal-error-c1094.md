---
title: "致命的なエラー C1094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1094"
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 致命的なエラー C1094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-Zmval1' : コマンド ライン オプションは、プリコンパイルされたヘッダー \('\-Zmval2'\) をビルドするために使用される値と矛盾します  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) に渡される値は、[\/Yu](../../build/reference/yu-use-precompiled-header-file.md) に渡される値と同じである必要があります \(**\/Zm** 値は、同じプリコンパイル済みヘッダー ファイルを使用または作成するすべてのコンパイル単位で同じである必要があります\)。  
  
 次の例では警告 C1094 が生成されます。  
  
```  
// C1094.h  
int func1();  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```