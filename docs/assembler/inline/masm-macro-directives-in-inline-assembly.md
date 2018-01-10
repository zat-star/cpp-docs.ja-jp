---
title: "インライン アセンブリでの MASM マクロ ディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0df9f8584b87e511c43430a5c0df7dac61805ede
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="masm-macro-directives-in-inline-assembly"></a>インライン アセンブリでの MASM マクロ ディレクティブ
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 インライン アセンブラーは、マクロ アセンブラーではありません。 MASM マクロ ディレクティブを使用することはできません (**マクロ**、 `REPT`、 **IRC**、 `IRP`、および`ENDM`) またはマクロ演算子 (**<>**、**!**、  **&** 、 `%`、および`.TYPE`)。 `__asm`ブロックがただし、C プリプロセッサ ディレクティブを使用できます。 参照してください[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)詳細についてはします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)