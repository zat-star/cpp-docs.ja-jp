---
title: "リンカー ツールの警告 LNK4022 | Microsoft Docs"
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
  - "LNK4022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4022"
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シンボル 'symbol' に対する一意の対応が見つかりません。  
  
 LINK または LIB は、装飾されていないシンボルに一致するものを複数検出しました。一意的に解決できません。  出力ファイル \(.exe、.dll、.exp、または .lib\) は作成されませんでした。  この警告の後、重複する各シンボルについて警告 [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) が出力され、最後に致命的なエラー [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md) が発生します。  
  
 この警告を回避するには、装飾された形式でシンボルを指定してください。  装飾名を見るには、オブジェクトに対して [DUMPBIN](../../build/reference/dumpbin-options.md) を実行してください。