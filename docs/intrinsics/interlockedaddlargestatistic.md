---
title: "_InterlockedAddLargeStatistic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAddLargeStatistic"
  - "_InterlockedAddLargeStatistic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAddLargeStatistic 組み込み"
  - "InterlockedAddLargeStatistic 組み込み"
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _InterlockedAddLargeStatistic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 1 番目のオペランドが 64 ビット値である Interlocked 加算を実行します。  
  
## 構文  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### パラメーター  
 \[入力、出力\] `Addend`  
 追加の操作の 1 番目のオペランドへのポインター。  が指す値を加算した結果に置き換えられます。  
  
 \[入力\] `Value`  
 2 番目のオペランド ; 1 番目のオペランドに追加する値。  
  
## 戻り値  
 2 番目のオペランドの値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みでは2 種類の別個のロックされた命令として実行されるため分割不可能ではありません。  読み取りこの組み込みの実行中に別のスレッドで発生するアトミック 64 ビットは競合する値になります。  
  
 この関数は読み取り \/ 書き込みバリアとして機能します。  詳細については[\_ReadWriteBarrier](../intrinsics/readwritebarrier.md) を参照してください。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)