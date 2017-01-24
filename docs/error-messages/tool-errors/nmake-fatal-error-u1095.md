---
title: "NMAKE の致命的なエラー U1095 | Microsoft Docs"
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
  - "U1095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1095"
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

展開されたコマンド ライン 'commandline' が長すぎます。  
  
 マクロの展開後、このコマンド ラインの長さが、オペレーティング システムで決められているコマンド ラインの長さの制限を超えました。  
  
 MS\-DOS では、コマンド ラインの最大長は 128 文字です。  
  
 このコマンドで実行するプログラムがファイルからのコマンド ライン入力を受け付ける場合は、コマンドを変更してディスクに保存したファイルまたはインライン ファイルから入力を行ってください。  たとえば、LINK と LIB は応答ファイルからの入力を受け付けます。