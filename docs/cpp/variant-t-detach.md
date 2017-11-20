---
title: "_variant_t::Detach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs: C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 014de597ffbc9a7004f821393902ffe05ac1f278
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたデタッチ**バリアント**オブジェクトからこの`_variant_t`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 カプセル化された**バリアント**です。  
  
## <a name="remarks"></a>コメント  
 抽出して戻し、カプセル化された**バリアント**、これをクリア`_variant_t`破棄せずオブジェクト。 このメンバー関数を削除、**バリアント**カプセル化し、セットから、 **VARTYPE**この`_variant_t`オブジェクトを`VT_EMPTY`です。 返されたを解放するかどうかは**バリアント**を呼び出して、 [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835)関数。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)