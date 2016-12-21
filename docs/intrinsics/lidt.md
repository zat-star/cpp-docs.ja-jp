---
title: "__lidt | Microsoft Docs"
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
  - "__lidt"
  - "__lidt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIDT 命令"
  - "__lidt 組み込み"
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定したメモリ位置の値 \(IDTR\) で割り込み記述子の表の登録を読み込みます。  
  
## 構文  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `Source`|IDTR にコピーされる値へのポインター。|  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__lidt`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 `__lidt` の関数は `LIDT` のマシン語命令とカーネル モードでのみ使用できます。  詳細については文書の検索「 Intel アーキテクチャのソフトウェア開発者の手動Volume 2: サイトの命令セットの参照です [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 」。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_sidt](../Topic/__sidt.md)