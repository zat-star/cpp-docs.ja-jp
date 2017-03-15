---
title: "/HEAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ヒープ割り当て、設定 (ヒープ サイズを)"
  - "HEAP editbin オプション"
  - "-HEAP editbin オプション"
  - "/HEAP editbin オプション"
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /HEAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ サイズをバイト単位で設定します。  このオプションは、実行可能ファイルにのみ適用されます。  
  
```  
  
/HEAP:  
reserve[,commit]  
  
```  
  
## 解説  
 `reserve` の引数には、仮想メモリ内の最初の合計ヒープ割り当てを指定します。  既定では、ヒープのサイズが 1 MB です。  [EDITBIN リファレンス](../Topic/EDITBIN%20Reference.md) は 4 バイトの倍数に指定された値を丸めます。  
  
 引数 `commit` \(省略可能\) は、オペレーティング システムによって解釈が異なります。  Windows オペレーティング システムでは、代入する物理メモリの最初の量、およびヒープに展開するか追加割り当てるメモリの量を指定します。  仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。  `commit` より大きい値は、アプリケーションでさらにヒープ領域メモリ量が増えますとアプリケーションの起動時間が必要な場合、システムがメモリをより少なくなるに割り当てることができます。  `commit` 値は `reserve` 値以下である必要があります。  
  
 小数点の `reserve` と `commit` 値または C 言語の 16 進数または 8 進表記指定します。  たとえば、1 MB の値は、04000000 として 1048576、または 16 進数 8 で 0x100000 として小数点で指定できます。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)