---
title: "_variant_t::ChangeType |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 535bc332a108cf50badca116c496661b7c257bf7
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft 固有の仕様**  
  
 型を変更、`_variant_t`オブジェクトを指定された**VARTYPE**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `vartype`  
 **VARTYPE**この`_variant_t`オブジェクト。  
  
 `pSrc`  
 変換する `_variant_t` オブジェクトへのポインター。 この値が場合**NULL**変換が適切に行われます。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数に変換する`_variant_t`を指定されたオブジェクト**VARTYPE**です。 場合`pSrc`は**NULL**、変換が行われる代わりに、それ以外の場合この`_variant_t`からオブジェクトをコピー`pSrc`され、換算します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
