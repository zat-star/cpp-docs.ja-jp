---
title: "イメージ形式 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# イメージ形式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実行可能イメージの形式は、PE32\+ です。  実行可能イメージ \(DLL、EXE の両方\) は、最大 2 GB までに制限されるため、静的イメージ データをアドレス指定するには 32 ビットの変位による相対アドレス指定を使用できます。  このデータには、インポート アドレス テーブル、文字列定数、静的なグローバル データなどが含まれます。  
  
## 参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)