---
title: "_ _readdr |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readdr
dev_langs: C++
helpviewer_keywords: __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba898d71895b74c43ad5de737355606a1d2b69ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="readdr"></a>__readdr
指定されたデバッグ レジスタの値を読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned         __readdr(unsigned int DebugRegister);  
unsigned __int64 __readdr(unsigned int DebugRegister);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `DebugRegister`  
 デバッグを識別する 0 ~ 7 の定数を登録します。  
  
## <a name="return-value"></a>戻り値  
 指定されたデバッグ レジスタの値です。  
  
## <a name="remarks"></a>コメント  
 これらの組み込みはカーネル モードでのみ使用し、ルーチンは組み込みとしてのみ使用できます。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__readdr`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)