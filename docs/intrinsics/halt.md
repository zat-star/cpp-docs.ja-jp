---
title: "__halt | Microsoft Docs"
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
  - "__halt"
  - "__halt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__halt 組み込み"
  - "HLT 命令"
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __halt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 有効な中断しマスクできないまたはリセット割り込みが \(NMI\) 発生するまでマイクロプロセッサを停止します。  
  
## 構文  
  
```  
void __halt( void );  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__halt`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 `__halt` の関数は `HLT` のマシン語命令とカーネル モードでのみ使用できます。  詳細については文書の検索「 Intel アーキテクチャのソフトウェア開発者の手動Volume 2: サイトの命令セットの参照です [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 」。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)