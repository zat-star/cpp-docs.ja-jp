---
title: "/STACK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STACK editbin オプション"
  - "STACK editbin オプション"
  - "-STACK editbin オプション"
  - "スタック, 設定 (サイズの)"
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## 解説  
 このオプションは、スタックのサイズをバイト単位で設定します。10 進表記または C 言語表記の引数を使用します。  \/STACK オプションの対象は、実行可能ファイルだけです。  
  
 引数 *reserve* には、仮想メモリ内のスタックの割り当ての総サイズを指定します。  指定した値は、4 バイト単位に切り上げられます。  
  
 引数 `commit` \(省略可能\) は、オペレーティング システムによって解釈が異なります。  Windows NT、Windows 95、および Windows 98 では、`commit` は一度に確保する物理メモリ量を指定します。  仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。  `commit` の値を大きく設定すると、アプリケーションに必要なスタック領域が増えたときに処理時間を節約できます。ただし、必要なメモリ量と起動時間が増えます。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)