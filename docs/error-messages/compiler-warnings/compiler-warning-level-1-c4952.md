---
title: "コンパイラの警告 (レベル 1) C4952 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4952"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4952"
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4952
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': プログラム データベース 'pgd\_file' にプロファイル データが見つかりません。  
  
 コンパイラが、[\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md) の使用時に、`/LTCG:PGINSTRUMENT` の後で再コンパイルされ、新しい関数 \(***function***\) を持つ入力モジュールを検出しました。  
  
 これは、情報提供の警告です。 この警告を解決するには、`/LTCG:PGINSTRUMENT` を実行してすべてのテストを再実行し、`/LTCG:PGOPTIMIZE` を実行します。  
  
 `/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。