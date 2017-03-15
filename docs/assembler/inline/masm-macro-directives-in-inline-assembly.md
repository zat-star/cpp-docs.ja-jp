---
title: "インライン アセンブリでの MASM マクロ ディレクティブ | Microsoft Docs"
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
  - "ディレクティブ, マクロ"
  - "インライン アセンブラー, macro ディレクティブ"
  - "マクロ, ディレクティブ"
  - "MASM (Microsoft Macro Assembler), インライン アセンブラー マクロ ディレクティブ"
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# インライン アセンブリでの MASM マクロ ディレクティブ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブラーはマクロアセンブラーではありません。  MASM ディレクティブ \(マクロ  **マクロ** `REPT`**IRC**`IRP` と `ENDM`\) またはマクロ **\<\>\!** 演算子 \(および `%``.TYPE`\) は使用できません。  ただし`__asm` ブロックは C プリプロセッサ ディレクティブを使用できます。  詳細については[\_\_asm ブロックの C または C\+\+ を使用する](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) を参照してください。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)