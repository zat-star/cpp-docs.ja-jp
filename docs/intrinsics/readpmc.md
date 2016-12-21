---
title: "__readpmc | Microsoft Docs"
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
  - "__readpmc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "パフォーマンス監視カウンターの読み取り命令"
  - "__readpmc 組み込み"
  - "rdpmc 命令"
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readpmc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `counter` で指定されているパフォーマンス カウンターを監視 `rdpmc` 読み取り命令を生成します。  
  
## 構文  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### パラメーター  
 \[入力\] `counter`  
 読み取るパフォーマンス カウンター。  
  
## 戻り値  
 指定のパフォーマンス カウンター値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__readpmc`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みではカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)