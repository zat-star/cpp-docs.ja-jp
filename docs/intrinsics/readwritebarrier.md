---
title: "_ReadWriteBarrier |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadWriteBarrier
dev_langs: C++
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2235c2089dd23a0572e960b995958c9e1740e108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier
**Microsoft 固有の仕様**  
  
 呼び出し場所全体にわたってメモリ アクセスの順序を変更できるコンパイラの最適化を制限します。  
  
> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨となっているため、使用しないでください。 スレッド間通信の場合などのメカニズムを使用して[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)と[std::atomic\<T >](../standard-library/atomic.md)で定義されている、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md). ハードウェアへのアクセスを使用して、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションと共に、[揮発性](../cpp/volatile-cpp.md)キーワード。  
  
## <a name="syntax"></a>構文  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_ReadWriteBarrier`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `_ReadWriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセスを削除または順序変更できるコンパイラの最適化を制限します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [_WriteBarrier](../intrinsics/writebarrier.md)   
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)