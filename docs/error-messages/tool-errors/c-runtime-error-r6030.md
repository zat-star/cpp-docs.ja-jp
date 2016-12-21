---
title: "C ランタイム エラー R6030 | Microsoft Docs"
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
  - "R6030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6030"
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: 9
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT が初期化されていません  
  
 このエラーは、CRT を使用していて、CRT スタートアップ コードが実行されなかった場合に発生します。  [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) リンカー スイッチを使用して既定の開始アドレスをオーバーライドすると、このエラーが発生する可能性があります。既定の開始アドレスは、通常は **mainCRTStartup**、コンソール EXE の場合は **wmainCRTStartup**、Windows EXE の場合は **WinMainCRTStartup** または **wWinMainCRTStartup**、DLL の場合は **\_DllMainCRTStartup** になります。  起動時に上記の関数のいずれかが呼び出されないと、C ランタイムは初期化されません。