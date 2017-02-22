---
title: "ガイド付き最適化のプロファイルのエラー PG0165 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# ガイド付き最適化のプロファイルのエラー PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Filename.pgd' の読み込み中 : 'PGD バージョンがサポートされていません \(バージョンの不一致\)'。  
  
 PGD ファイルは、特定のコンパイラ ツールセットに固有のものです。  このエラーは *Filename*.pgd で使用したものとは異なるコンパイラを使用している場合に生成されます。  このエラーは、現在のプログラムを最適化するためにこのコンパイラ ツールセットが *Filename*.pgd からデータを使用できないことを示します。  
  
 この問題は、再生 *Filename*.pgd 現在のコンパイラ ツールセットを使用して解決できます。