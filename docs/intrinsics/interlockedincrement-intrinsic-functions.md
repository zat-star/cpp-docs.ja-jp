---
title: "_InterlockedIncrement の組み込み関数 | Microsoft Docs"
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
  - "_InterlockedIncrement_acq"
  - "_InterlockedIncrement16_rel_cpp"
  - "_InterlockedIncrement16_cpp"
  - "_InterlockedIncrement64_rel"
  - "_InterlockedIncrement_rel"
  - "_InterlockedIncrement64_nf"
  - "_InterlockedIncrement16_acq_cpp"
  - "_InterlockedIncrement_rel_cpp"
  - "_InterlockedIncrement64"
  - "_InterlockedIncrement64_rel_cpp"
  - "_InterlockedIncrement16_nf"
  - "_InterlockedIncrement16_rel"
  - "_InterlockedIncrement16_acq"
  - "_InterlockedIncrement_nf"
  - "_InterlockedIncrement_acq_cpp"
  - "_InterlockedIncrement64_cpp"
  - "_InterlockedIncrement64_acq_cpp"
  - "_InterlockedIncrement"
  - "_InterlockedIncrement_cpp"
  - "_InterlockedIncrement64_acq"
  - "_InterlockedIncrement16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedIncrement 組み込み"
  - "_InterlockedIncrement_acq 組み込み"
  - "_InterlockedIncrement_nf 組み込み"
  - "_InterlockedIncrement_rel 組み込み"
  - "_InterlockedIncrement16 組み込み"
  - "_InterlockedIncrement16_acq 組み込み"
  - "_InterlockedIncrement16_nf 組み込み"
  - "_InterlockedIncrement16_rel 組み込み"
  - "_InterlockedIncrement64 組み込み"
  - "_InterlockedIncrement64_acq 組み込み"
  - "_InterlockedIncrement64_nf 組み込み"
  - "_InterlockedIncrement64_rel 組み込み"
  - "InterlockedIncrement 組み込み"
  - "InterlockedIncrement_acq 組み込み"
  - "InterlockedIncrement_rel 組み込み"
  - "InterlockedIncrement16 組み込み"
  - "InterlockedIncrement64 組み込み"
  - "InterlockedIncrement64_acq 組み込み"
  - "InterlockedIncrement64_rel 組み込み"
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedIncrement の組み込み関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx) 関数のコンパイラ組み込みサポートを提供します。  
  
## 構文  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### パラメーター  
 \[入力、出力\] `lpAddend`  
 インクリメントする変数へのポインター。  
  
## 戻り値  
 戻り値は、インクリメントして生成された値です。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|ヘッダー|  
|----------|-------------|----------|  
|`_InterlockedIncrement`、`_InterlockedIncrement16`、`_InterlockedIncrement64`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h\>|  
  
## 解説  
 `_InterlockedIncrement` には、格納するデータ型、およびプロセッサ固有の取得または解放のセマンティクスを使用するかどうかに基づき、異なるいくつかの種類があります。  
  
 `_InterlockedIncrement` 関数は 32 ビット整数値で動作しますが、`_InterlockedIncrement16` は 16 ビット整数値および `_InterlockedIncrement64` は 64 ビット整数値で動作します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。  `_nf` \("フェンスなし"\) サフィックスの付いた組み込みはメモリ バリアとしては機能しません。  
  
 `lpAddend` パラメーターが指す変数は 32 ビットの境界に合わせて調整する必要があります。そのようにしない場合、この関数はマルチプロセッサの x86 システムおよび x 86 システム以外のシステムで失敗します。  詳細については、「[align](../cpp/align-cpp.md)」を参照してください。  
  
 Win32 関数は `Wdm.h` または `Ntddk.h` で宣言されています。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
## 使用例  
 `_InterlockedIncrement` の使用例については、「[\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)