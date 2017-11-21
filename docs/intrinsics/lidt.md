---
title: "_ _lidt |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs: C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 729df3d4dd415891a9e89ea373e0b4f740e13c1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__lidt`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `__lidt`関数と同じ、`LIDT`マシン語命令、およびカーネル モードでのみ使用できます。 詳細については、検索、ドキュメントの"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2: 命令セットの参照を"で、 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)サイトです。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)