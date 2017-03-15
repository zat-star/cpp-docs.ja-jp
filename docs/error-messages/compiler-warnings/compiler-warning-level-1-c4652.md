---
title: "コンパイラの警告 (レベル 1) C4652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4652"
ms.assetid: 2cf2c666-8cdd-4dd9-bda0-662921498b03
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラ オプション 'option' はプリコンパイル済みヘッダーのものと一致しません。現在のオプションを優先しプリコンパイルのオプションは無視されます。  
  
 指定されたコマンド ライン オプションは、プリコンパイル済みヘッダー \(.pch\) が作成されたときに指定されたオプションと異なります。  現在のコマンド ラインで指定されたオプションが使用されます。  
  
 この警告は、コマンド ラインで指定のオプションを使用して、プリコンパイル済みヘッダーを再生成することで回避できます。