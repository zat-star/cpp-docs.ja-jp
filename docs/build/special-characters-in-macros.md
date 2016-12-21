---
title: "マクロの特殊文字 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "特殊文字, NMAKE マクロで"
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マクロの特殊文字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

定義の後のシャープ記号 \(\#\) はコメントを示します。  マクロでリテラルのシャープ記号を指定するには、^\# のようにカレット \(^\) を使用します。  
  
 ドル記号 \($\) は、マクロの呼び出しを示します。  リテラルの $ を指定するには、$$ を使用します。  
  
 定義を次の行まで拡張するには、行を円記号 \(\\\) で終わらせます。  マクロが呼び出されると、円記号と改行文字の組み合わせが空白で置換されます。  行末でリテラルの円記号を指定するには、その前にカレット \(^\) を配置するか、その後にコメント指定子 \(\#\) を配置します。  
  
 リテラルの改行文字を指定するには、次のように行をカレット \(^\) で終わらせます。  
  
```  
CMDS = cls^  
dir  
```  
  
## 参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)