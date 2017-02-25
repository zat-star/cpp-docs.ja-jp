---
title: "リソース コンパイラの致命的なエラー RC1120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1120"
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# リソース コンパイラの致命的なエラー RC1120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

out of memory, needed number bytes  
  
 ヒープ領域に保存するアイテムのための記憶領域を使い果たしました。  このエラーは、通常、シンボルの数が多すぎることが原因で発生します。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  Windows のスワップ ファイルの容量を増やします。  スワップ ファイルの容量を増やす方法の詳細については、Windows ヘルプの仮想メモリに関するトピックを参照してください。  
  
2.  不要なインクルード ファイル、特に `#define` 文や関数プロトタイプは削除してください。  
  
3.  現在のファイルを 2 つ以上のファイルに分割し、それぞれをコンパイルします。  
  
4.  現在システムで実行中のプログラムやドライバーのうち、大量のメモリを消費していると思われるものをシステムから取り除きます。