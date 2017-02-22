---
title: "NMAKE の警告 U4011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4011"
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# NMAKE の警告 U4011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target' : 依存ファイルの一部が使用できません。; ターゲットはビルドされません。  
  
 指定されたターゲットの依存ファイルが存在しないか、または最新ではなく、依存ファイルを更新するためのコマンドが 0 以外の終了コードを返しました。  \/K オプションが指定されているため、NMAKE はこのビルドとは関係ない部分の処理を続行し、セッション終了時に終了コードとして 1 を返します。  
  
 この警告が発生する場合は、その前に依存ファイルの生成か更新に失敗したことによる警告 [U4010](../Topic/NMAKE%20Warning%20U4010.md) が発生しています。