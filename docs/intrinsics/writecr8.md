---
title: __writecr8 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _writecr8
dev_langs:
- C++
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 467e1662af3bf1b0e43a03d7196bb5a1131e8967
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="writecr8"></a>__writecr8
**Microsoft 固有の仕様**  
  
 値を書き込む`Data`CR8 レジスタにします。  
  
## <a name="syntax"></a>構文  
  
```  
void writecr8(   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Data`  
 CR8 レジスタに書き込む値。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__writecr8`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)