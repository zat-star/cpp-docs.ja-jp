---
title: "_variant_t::Attach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 33e21d3bea71c80b8b60df222682fda560fbce9c
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
