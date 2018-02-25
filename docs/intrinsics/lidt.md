---
title: "_ _lidt |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs:
- C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6fce509bee1f68746f4453111b04c95f9a584a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="lidt"></a>__lidt
**Microsoft 固有の仕様**  
  
 指定されたメモリ位置の値と割り込みの記述子テーブル レジスタ (IDTR) を読み込みます。  
  
## <a name="syntax"></a>構文  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `Source`|IDTR にコピーされる値へのポインター。|  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__lidt`|x86、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `__lidt`関数と同じ、`LIDT`マシン語命令、およびカーネル モードでのみ使用できます。 詳細については、検索、ドキュメントの"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2: 命令セットの参照を"で、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)