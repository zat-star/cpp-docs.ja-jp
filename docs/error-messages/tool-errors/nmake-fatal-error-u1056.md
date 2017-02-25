---
title: "NMAKE の致命的なエラー U1056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1056"
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE の致命的なエラー U1056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド プロセッサが見つかりません。  
  
 コマンド プロセッサが環境変数 **COMSPEC** や **PATH** に設定されているパスに存在しません。  
  
 NMAKE は、コマンドを実行するときにコマンド プロセッサとして COMMAND.COM または CMD.EXE を使用します。  NMAKE は、まず **COMSPEC** で設定されているパスでコマンド プロセッサを検索します。  **COMSPEC** で見つからない場合は、**PATH** で設定されているフォルダーを検索します。