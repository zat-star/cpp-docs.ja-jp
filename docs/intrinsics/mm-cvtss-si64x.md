---
title: "_mm_cvtss_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvtss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtss2si 組み込み"
  - "_mm_cvtss_si64x 組み込み"
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_cvtss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 64 ビット整数 \(`cvtss2si`\) 命令に変換のスカラー単精度の浮動小数点数の [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] によって拡張されたバージョンを生成します。  
  
## 構文  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### パラメーター  
 \[入力\] `value`  
 Point 値をフローティング `__m128` を含む構造体。  
  
## 戻り値  
 64 ビットの整数整数への最初の浮動小数点値変換の結果。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 構造体の最初の要素の値を整数に変換されが返されます。  MXCSR の丸め制御が丸め動作を決定するために使用されます。  既定の丸めモードは小数部を 0.5 回場合は最も近い偶数に切り上げられます。  `__m128` の構造は XMM レジスタを表すためこの組み込みでは XMM レジスタから値を受け取りシステム メモリに書き込みます。  
  
 このルーチンは組み込みとしてのみ使用できます。  
  
## 使用例  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_m128d](../cpp/m128d.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)