---
title: "致命的なエラー C1352 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1352"
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 致命的なエラー C1352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数 'function' \(元モジュール 'file'\) の無効な、または壊れた MSIL です。  
  
 .netmodule がコンパイラに渡されましたが、コンパイラでファイルの破損が検出されました。  調査するために .netmodule の作成者に問い合わせてください。  
  
 コンパイラは、.netmodule ファイルのすべての種類の破損をチェックしません。  ただし、return ステートメントを含む関数内のすべてのコントロール パスのすべての種類の破損をチェックします。  
  
 詳細については、「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」を参照してください。