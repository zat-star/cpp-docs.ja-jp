---
title: "_ _invlpg |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs: C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 919e1ff5d01dca587eff255f5a7164c41d2f04b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="invlpg"></a>__invlpg
**Microsoft 固有の仕様**  
  
 X86 が生成されます`invlpg`が指すメモリに関連付けられているページの変換のルック アサイド バッファー (TLB) を無効になります命令`Address`です。  
  
## <a name="syntax"></a>構文  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [in]`Address`  
 64 ビットのアドレス。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__invlpg`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 組み込み`__invlpg`特権命令を生成し、0 の特権レベル (CPL) でのカーネル モードでのみ使用します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)