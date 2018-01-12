---
title: "_InterlockedAddLargeStatistic |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs: C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d9e61abc6ac531fe489465b1d81e167bdde5242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft 固有の仕様**  
  
 最初のオペランドの 64 ビット値、インタロックされた加算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Addend`  
 追加操作の最初のオペランドへのポインター。 示される値は、加算の結果によって置き換えられます。  
  
 [入力] `Value`  
 2 番目のオペランドです。最初のオペランドを加算する値。  
  
## <a name="return-value"></a>戻り値  
 2 番目のオペランドの値。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みはアトミック 2 つの別々 のロックされた手順としては実装されているためです。 組み込みの実行中に別のスレッドで発生するアトミックの 64 ビット読み取り、一貫性のない値が読み取られている可能性があります。  
  
 この関数は、読み取り/書き込みのバリアとしては動作します。 詳細については、次を参照してください。 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)