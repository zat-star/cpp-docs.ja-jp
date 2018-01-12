---
title: "_variant_t::Attach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs: C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: effeaaaf3f8df9eb100d5e92e760eb439a865552
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft 固有の仕様**  
  
 アタッチ、**バリアント**オブジェクトに、`_variant_t`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**オブジェクトにアタッチされる`_variant_t`オブジェクト。  
  
## <a name="remarks"></a>コメント  
 所有権を取得、**バリアント**によってカプセル化しています。 このメンバー関数は、既存のカプセル化を解放**バリアント**、指定されたコピー**バリアント**、設定とその**VARTYPE**に`VT_EMPTY`を確認する、リソースを解放することができますのみ、`_variant_t`デストラクターです。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_variant_t クラス](../cpp/variant-t-class.md)