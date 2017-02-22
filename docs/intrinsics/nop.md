---
title: "__nop | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__nop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nop 命令"
  - "__nop 組み込み"
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __nop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 操作を実行しないプラットフォーム固有のマシン語コードを生成します。  
  
## 構文  
  
```  
void __nop();  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__nop`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 解説  
 `__nop` の関数は `NOP` のマシン語命令と同じです。  詳細については文書の検索「 Intel アーキテクチャのソフトウェア開発者の手動Volume 2: サイトの命令セットの参照です [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 」。  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_noop](../intrinsics/noop.md)