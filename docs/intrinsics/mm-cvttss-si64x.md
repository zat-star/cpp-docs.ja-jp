---
title: "_mm_cvttss_si64x |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_cvttss_si64x
dev_langs: C++
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b93426c814378ea3b52dfadd1617b641a7564f16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x
**Microsoft 固有の仕様**  
  
 出力拡張 x64 バージョンの 64 ビットの整数に切り捨て単精度浮動小数点数に変換 (`cvttss2si`) 命令します。  
  
## <a name="syntax"></a>構文  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `value`  
 `__m128`単精度浮動小数点値を含む構造体。  
  
## <a name="return-value"></a>戻り値  
 最初の浮動小数点値の 64 ビット整数への変換の結果。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 組み込みとは異なります`_mm_cvtss_si64x`ことだけ不正確な変換がゼロに向かって切り捨てられます。 `__m128`構造は XMM レジスタを表す、生成された命令は、システム メモリに XMM レジスタからデータを移動します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_ _m128](../cpp/m128.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)