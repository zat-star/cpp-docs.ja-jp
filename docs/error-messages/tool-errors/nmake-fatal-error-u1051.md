---
title: "NMAKE の致命的なエラー U1051 | Microsoft Docs"
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
  - "U1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1051"
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリが不足しています。  
  
 メイクファイルが大きすぎたか複雑すぎたため、NMAKE は仮想メモリも含めすべてのメモリを使い果たしました。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  ディスクの空き領域を増やしてください。  
  
2.  Windows NT のページング ファイルか Windows のスワップ ファイルのサイズを大きくします。  
  
3.  メイクファイルの一部分しか使用しない場合は、そのメイクファイルを複数のファイルに分割するか、プリプロセス ディレクティブ **\!IF** を使用して NMAKE が行う処理量を制限してください。  **\!IF** ディレクティブには、**\!IF**、`!IFDEF`、**\!IFNDEF**、**\!ELSE IF**、**\!ELSE** `IFDEF`、**\!ELSE** `IFNDEF` が含まれます。