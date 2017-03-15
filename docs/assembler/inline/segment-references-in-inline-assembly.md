---
title: "インライン アセンブリでのセグメント参照 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "インライン アセンブラー, レジスタ"
  - "インライン アセンブラー, セグメント参照"
  - "参照, インライン アセンブラー"
  - "レジスタ"
  - "レジスタ, インライン アセンブラー"
  - "インライン アセンブラー内のセグメント参照"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# インライン アセンブリでのセグメント参照
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 名前ではなく登録によってセグメントを参照する必要があります \(たとえば `_TEXT` セグメント名は無効です。  セグメント オーバーライドはにレジスタが明示的に使用する必要があります : \[入力\] BX。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)