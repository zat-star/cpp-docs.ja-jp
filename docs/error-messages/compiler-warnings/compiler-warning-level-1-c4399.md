---
title: "コンパイラの警告 (レベル 1) C4399 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4399"
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'シンボル' : プロセスごとのシンボルは、\/clr:pure と共にコンパイルされるときに、\_\_ \_\_declspec\(dllimport\) と共に設定することはできません  
  
 ネイティブ イメージのデータ、またはネイティブな構成要素および CLR 構成要素を持つイメージのデータを純粋なイメージにインポートすることはできません。  この警告を解決するには、**\/clr:pure** ではなく **\/clr** を指定してコンパイルするか、`__declspec(dllimport)` を削除します。  
  
## 使用例  
 次の例では C4399 エラーが生成されます。  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```