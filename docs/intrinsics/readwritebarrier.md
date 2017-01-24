---
title: "_ReadWriteBarrier | Microsoft Docs"
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
  - "_ReadWriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadWriteBarrier 組み込み"
  - "ReadWriteBarrier 組み込み"
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ReadWriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 呼び出し場所全体にわたってメモリ アクセスの順序を変更できるコンパイラの最適化を制限します。  
  
> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨となっているため、使用しないでください。  スレッド間通信には、[C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)で定義されている [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) や [std::atomic\<T\>](../standard-library/atomic.md) などの機構を使用します。  ハードウェア アクセスには、[volatile](../cpp/volatile-cpp.md) "キーワードと共に [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラ オプションを使用します。  
  
## 構文  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_ReadWriteBarrier`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 `_ReadWriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセスを削除または順序変更できるコンパイラの最適化を制限します。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_WriteBarrier](../intrinsics/writebarrier.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)