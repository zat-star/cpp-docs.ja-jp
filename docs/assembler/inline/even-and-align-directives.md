---
title: "EVEN および ALIGN ディレクティブ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "align"
  - "EVEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIGN ディレクティブ"
  - "ディレクティブ, MASM"
  - "EVEN ディレクティブ"
  - "MASM (Microsoft Macro Assembler), ディレクティブ"
  - "NOP (操作なし命令)"
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EVEN および ALIGN ディレクティブ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブラーはほとんどの MASM ディレクティブをサポートしていませんが`EVEN` と  **整列**  をサポートします。  特定の境界にラベルを配置できます。これらのディレクティブはアセンブリ コードに必要に **NOP** 操作 \(なし\) 命令を追加します。  これは取出し命令を操作するプロセッサ用に効率的になります。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)