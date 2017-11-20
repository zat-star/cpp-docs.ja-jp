---
title: "_ReadBarrier |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadBarrier
dev_langs: C++
helpviewer_keywords: _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 654d68ddf16dd0e162e0e50bbfb85f15fe9b5a86
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="readbarrier"></a>_ReadBarrier  
  
**Microsoft 固有の仕様**  
  
 呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。  
  
> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨となっているため、使用しないでください。 スレッド間通信の場合などのメカニズムを使用して[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)と[std::atomic\<T >](../standard-library/atomic.md)で定義されている、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md). ハードウェアへのアクセスを使用して、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションと共に、[揮発性](../cpp/volatile-cpp.md)キーワード。  
  
## <a name="syntax"></a>構文  
  
```  
void _ReadBarrier(void);  
```  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_ReadBarrier`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `_ReadBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)