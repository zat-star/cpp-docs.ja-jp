---
title: "_InterlockedExchangeAdd の組み込み関数 | Microsoft Docs"
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
  - "_InterlockedExchangeAdd64_nf"
  - "_InterlockedExchangeAdd64_rel"
  - "_InterlockedExchangeAdd16_rel"
  - "_InterlockedExchangeAdd_acq"
  - "_InterlockedExchangeAdd_nf"
  - "_InterlockedExchangeAdd_rel"
  - "_InterlockedExchangeAdd8_acq"
  - "_InterlockedExchangeAdd16_nf"
  - "_InterlockedExchangeAdd_acq_cpp"
  - "_InterlockedExchangeAdd64_acq_cpp"
  - "_InterlockedExchangeAdd16_acq"
  - "_InterlockedExchangeAdd_HLERelease"
  - "_InterlockedExchangeAdd64_cpp"
  - "_InterlockedExchangeAdd64_HLERelease"
  - "_InterlockedExchangeAdd64_acq"
  - "_InterlockedExchangeAdd8"
  - "_InterlockedExchangeAdd64"
  - "_InterlockedExchangeAdd8_nf"
  - "_InterlockedExchangeAdd16"
  - "_InterlockedExchangeAdd64_rel_cpp"
  - "_InterlockedExchangeAdd_cpp"
  - "_InterlockedExchangeAdd8_rel"
  - "_InterlockedExchangeAdd_HLEAcquire"
  - "_InterlockedExchangeAdd64_HLEAcquire"
  - "_InterlockedExchangeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchangeAdd 組み込み"
  - "_InterlockedExchangeAdd_acq 組み込み"
  - "_InterlockedExchangeAdd_HLEAcquire 組み込み"
  - "_InterlockedExchangeAdd_HLERelease 組み込み"
  - "_InterlockedExchangeAdd_nf 組み込み"
  - "_InterlockedExchangeAdd_rel 組み込み"
  - "_InterlockedExchangeAdd16 組み込み"
  - "_InterlockedExchangeAdd16_acq 組み込み"
  - "_InterlockedExchangeAdd16_nf 組み込み"
  - "_InterlockedExchangeAdd16_rel 組み込み"
  - "_InterlockedExchangeAdd64 組み込み"
  - "_InterlockedExchangeAdd64_acq 組み込み"
  - "_InterlockedExchangeAdd64_HLEAcquire 組み込み"
  - "_InterlockedExchangeAdd64_HLERelease 組み込み"
  - "_InterlockedExchangeAdd64_nf 組み込み"
  - "_InterlockedExchangeAdd64_rel 組み込み"
  - "_InterlockedExchangeAdd8 組み込み"
  - "_InterlockedExchangeAdd8_acq 組み込み"
  - "_InterlockedExchangeAdd8_nf 組み込み"
  - "_InterlockedExchangeAdd8_rel 組み込み"
  - "InterlockedExchangeAdd 組み込み"
  - "InterlockedExchangeAdd_acq 組み込み"
  - "InterlockedExchangeAdd_rel 組み込み"
  - "InterlockedExchangeAdd64 組み込み"
  - "InterlockedExchangeAdd64_acq 組み込み"
  - "InterlockedExchangeAdd64_rel 組み込み"
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedExchangeAdd の組み込み関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md) 関数のコンパイラ組み込みサポートを提供します。  
  
## 構文  
  
```  
long _InterlockedExchangeAdd(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_rel(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLEAcquire(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLERelease(    long volatile * Addend,    long Value ); char _InterlockedExchangeAdd8(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_acq(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_rel(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_nf(    char volatile * Addend,    char Value ); short _InterlockedExchangeAdd16(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_acq(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_rel(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_nf(    short volatile * Addend,    short Value ); __int64 _InterlockedExchangeAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_rel(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_nf(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLEAcquire(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLERelease(    __int64 volatile * Addend,    __int64 Value );   
```  
  
#### パラメーター  
 \[入力、出力\] `Addend`  
 加算される値。加算の結果によって置き換えられます。  
  
 \[入力\] `Value`  
 加算する値。  
  
## 戻り値  
 戻り値は `Addend` パラメーターが指す変数の初期値です。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|Header|  
|----------|-------------|------------|  
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 解説  
 `_InterlockedExchangeAdd` には、格納するデータ型、およびプロセッサ固有の取得または解放のセマンティクスを使用するかどうかに基づき、異なるいくつかの種類があります。  
  
 `_InterlockedExchangeAdd` 関数は 32 ビット整数値で動作しますが、`_InterlockedExchangeAdd8` は 8 ビット整数値、`_InterlockedExchangeAdd16` は 16 ビット整数値、および `_InterlockedExchangeAdd64` は 64 ビット整数値で動作します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。  `_nf` \("フェンスなし"\) サフィックスの付いた組み込みはメモリ バリアとしては機能しません。  
  
 Hardware Lock Elision \(HLE\) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。  HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  したがって、これらは [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) または [\#pragma intrinsic](../preprocessor/intrinsic.md) が使用されているかに関係なく組み込み型です。  これらの組み込みで [\#pragma function](../preprocessor/function-c-cpp.md) を使用することはできません。  
  
## 使用例  
 `_InterlockedExchangeAdd` の使用例については、「[\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)