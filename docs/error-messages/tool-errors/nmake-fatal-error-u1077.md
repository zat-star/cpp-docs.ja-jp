---
title: "NMAKE の致命的なエラー U1077 | Microsoft Docs"
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
  - "U1077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1077"
ms.assetid: 70d989f8-ef34-4ad7-8fe0-5b800556b2a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'program' : リターン コード 'value'  
  
 指定されたコマンドあるいはプログラムは NMAKE から呼び出されましたが、失敗に終わり、終了コード 'value' が返されました。  
  
 このエラーを発生させずに NMAKE セッションを続行させるには、\/I オプション、ドット ディレクティブ **.IGNORE**、またはダッシュ コマンド修飾子 \(**\-**\) を使用します。  NMAKE セッションの依存関係ツリー中のこのプログラムと関係ない部分の実行だけを続行させるには、\/K オプションを使用します。