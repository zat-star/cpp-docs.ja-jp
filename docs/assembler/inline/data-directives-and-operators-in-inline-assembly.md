---
title: "インライン アセンブリでのデータ ディレクティブと演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9875a6d4ee0b061db609f45d574a80a7ee5424ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 ただし、`__asm`ブロックは、C または C++ のデータ型およびオブジェクトを参照できる、MASM ディレクティブまたは演算子を持つデータ オブジェクトを定義できません。 具体的には、定義ディレクティブを使用することはできません**DB**、 `DW`、 **DD**、 `DQ`、 `DT`、および`DF`、か、または演算子`DUP`または**これは、**です。 MASM の構造とレコードもご利用いただけません。 インライン アセンブラーは、ディレクティブを受け取らない`STRUC`、 `RECORD`、**幅**、または**マスク**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)