---
title: "NMAKE の致命的なエラー U1073 | Microsoft Docs"
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
  - "U1073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1073"
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'targetname' のビルド方法が指定されていません。  
  
 指定されたターゲットは存在せず、このターゲットの生成のために実行するコマンドや適用する推論規則もありません。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  ターゲット名が正しいかどうかを確認してください。  
  
2.  *targetname* が疑似ターゲットの場合、別の記述ブロックのターゲットとして指定してください。  
  
3.  *targetname* がマクロの呼び出しの場合、そのマクロが null 文字列に展開しないかどうかを確認してください。