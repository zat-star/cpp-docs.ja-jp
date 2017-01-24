---
title: "リンカー ツールの警告 LNK4010 | Microsoft Docs"
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
  - "LNK4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4010"
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

サブシステムのバージョン番号 '数値' が無効です。既定サブシステムの設定にします。  
  
 イメージのサブシステム \([\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)\) のバージョンを指定できます。  各サブシステムには、最低限のバージョン要件があります。  指定されたバージョンが最低要件より低い場合はこの警告が発生し、リンカーは既定のサブシステムを使用します。