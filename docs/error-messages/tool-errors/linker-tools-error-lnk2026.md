---
title: "リンカ ツール エラー LNK2026 | Microsoft Docs"
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
  - "LNK2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2026"
ms.assetid: 9955bf7c-59b5-4fa1-8481-147db0d7df45
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

モジュールは SAFESEH イメージには安全ではありません。  
  
 [\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md) が指定されていますが、モジュールに安全な例外処理機能との互換性がありませんでした。  このモジュールを **\/SAFESEH** で使用する場合は、Visual C\+\+ .NET 2003 以降のコンパイラでモジュールを再コンパイルする必要があります。