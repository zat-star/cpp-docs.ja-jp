---
title: "_disable |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _disable_cpp
- _disable
dev_langs: C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85b4b454b84767290f6c95255e4b2d3fc341dda9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="disable"></a>_disable
**Microsoft 固有の仕様**  
  
 割り込みを無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
void _disable(void);  
```  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_disable`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `_disable` は、プロセッサに対して割り込みフラグをクリアするように指示します。 x86 システムでは、この関数は割り込みフラグのクリア (`cli`) 命令を生成します。  
  
 この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、実行時に特権命令例外がスローされます。  
  
 ARM プラットフォームでは、このルーチンは組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)