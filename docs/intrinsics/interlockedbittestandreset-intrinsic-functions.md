---
title: "_interlockedbittestandreset の組み込み関数 | Microsoft Docs"
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
  - "_interlockedbittestandreset_rel"
  - "_interlockedbittestandreset64"
  - "_interlockedbittestandreset64_HLERelease"
  - "_interlockedbittestandreset_HLERelease"
  - "_interlockedbittestandreset_HLEAcquire"
  - "_interlockedbittestandreset_acq"
  - "_interlockedbittestandreset_cpp"
  - "_interlockedbittestandreset_nf"
  - "_interlockedbittestandreset64_cpp"
  - "_interlockedbittestandreset64_HLEAcquire"
  - "_interlockedbittestandreset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_interlockedbittestandreset 組み込み"
  - "_interlockedbittestandreset64 組み込み"
  - "lock_btr 命令"
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _interlockedbittestandreset の組み込み関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 アドレス `a` のビット `b` を 0 に設定し、その元の値を返す命令を生成します。  
  
## 構文  
  
```  
unsigned char _interlockedbittestandreset(    long *a,    long b ); unsigned char _interlockedbittestandreset_acq(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLEAcquire(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLERelease(    long *a,    long b ); unsigned char _interlockedbittestandreset_nf(    long *a,    long b ); unsigned char _interlockedbittestandreset_rel(    long *a,    long b );  unsigned char _interlockedbittestandreset64(    __int64 *a,    __int64 b );  unsigned char _interlockedbittestandreset64_HLEAcquire(    __int64 *a,    __int64 b ); unsigned char _interlockedbittestandreset64_HLERelease(    __int64 *a,    __int64 b );  
```  
  
#### パラメーター  
 \[入力\] `a`  
 検査するメモリへのポインター。  
  
 \[入力\] `b`  
 テストするビット位置。  
  
## 戻り値  
 `b` で指定された位置にあるビットの元の値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|Header|  
|----------|-------------|------------|  
|`_interlockedbittestandreset`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<intrin.h\>|  
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
|`_interlockedbittestandreset64`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 解説  
 x86 および [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] プロセッサでは、これらの組み込みはアトミックな演算で指定されたビットを読み込み、その値を 0 に設定する `lock btr` 命令を使用します。  
  
 ARM プロセッサでは、クリティカル セクションの最初と最後などでの取得と解放のセマンティクスのために、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。  `_nf` \("フェンスなし"\) サフィックスの付いた ARM 組み込みはメモリ バリアとしては機能しません。  
  
 Hardware Lock Elision \(HLE\) 命令をサポートする Intel プロセッサでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。  HLE をサポートしていないプロセッサ上でこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)