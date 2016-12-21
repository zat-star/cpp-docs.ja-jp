---
title: "_InterlockedCompareExchangePointer の組み込み関数 | Microsoft Docs"
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
  - "_InterlockedCompareExchangePointer_HLERelease"
  - "_InterlockedCompareExchangePointer_rel"
  - "_InterlockedCompareExchangePointer_acq_cpp"
  - "_InterlockedCompareExchangePointer"
  - "_InterlockedCompareExchangePointer_cpp"
  - "_InterlockedCompareExchangePointer_np"
  - "_InterlockedCompareExchangePointer_rel_cpp"
  - "_InterlockedCompareExchangePointer_HLEAcquire"
  - "_InterlockedCompareExchangePointer_acq"
  - "_InterlockedCompareExchangePointer_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedCompareExchangePointer 組み込み"
  - "_InterlockedCompareExchangePointer_acq 組み込み"
  - "_InterlockedCompareExchangePointer_HLEAcquire 組み込み"
  - "_InterlockedCompareExchangePointer_HLERelease 組み込み"
  - "_InterlockedCompareExchangePointer_nf 組み込み"
  - "_InterlockedCompareExchangePointer_np 組み込み"
  - "_InterlockedCompareExchangePointer_rel 組み込み"
  - "InterlockedCompareExchangePointer 組み込み"
  - "InterlockedCompareExchangePointer_acq 組み込み"
  - "InterlockedCompareExchangePointer_rel 組み込み"
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedCompareExchangePointer の組み込み関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `Comparand` と `Destination` アドレスが等しい場合、`Destination` アドレスに `Exchange` アドレスを格納するアトミックな演算を実行します。  
  
## 構文  
  
```  
void * _InterlockedCompareExchangePointer (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_acq (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLEAcquire (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLERelease (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_nf (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_np (    void * volatile * Destination,    void * Exchange,    void * Comparand ); long _InterlockedCompareExchangePointer_rel (    void * volatile * Destination,    void * Exchange,    void * Comparand );  
```  
  
#### パラメーター  
 \[入力、出力\] `Destination`  
 対象値へのポインターへのポインター。  符号は無視されます。  
  
 \[入力\] `Exchange`  
 Exchange へのポインター。  符号は無視されます。  
  
 \[入力\] `Comparand`  
 対象と比較するポインター。  符号は無視されます。  
  
## 戻り値  
 戻り値は、対象の初期値です。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|Header|  
|----------|-------------|------------|  
|`_InterlockedCompareExchangePointer`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h\>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 解説  
 `_InterlockedCompareExchangePointer` は `Destination` アドレスと `Comparand` アドレスのアトミックな比較を実行します。  `Destination` のアドレスが `Comparand` のアドレスと等しい場合、`Exchange` のアドレスは `Destination` で指定したアドレスに格納されます。  それ以外の場合は演算が実行されません。  
  
 `_InterlockedCompareExchangePointer` は、Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx) 関数のコンパイラ組み込みサポートを提供します。  
  
 `_InterlockedCompareExchangePointer` の使用例については、「[\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)」を参照してください。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。  `_nf` \("フェンスなし"\) サフィックスの付いた ARM 組み込みはメモリ バリアとしては機能しません。  
  
 組み込みに `_np` \("プリフェッチなし"\) サフィックスが付いていると、コンパイラによってプリフェッチ操作が挿入される可能性がなくなります。  
  
 Hardware Lock Elision \(HLE\) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。  HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)