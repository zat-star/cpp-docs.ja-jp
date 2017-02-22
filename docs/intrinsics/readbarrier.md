---
title: "_ReadBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadBarrier 組み込み"
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _ReadBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。  
  
> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨となっているため、使用しないでください。  スレッド間通信には、[C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)で定義されている [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) や [std::atomic\<T\>](../standard-library/atomic.md) などの機構を使用します。  ハードウェア アクセスには、[volatile](../cpp/volatile-cpp.md) "キーワードと共に [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラ オプションを使用します。  
  
## 構文  
  
```  
void _ReadBarrier(void);  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_ReadBarrier`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 `_ReadBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)