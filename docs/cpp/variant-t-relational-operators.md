---
title: "_variant_t 関係演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d8bcf9550e3e3f8af1836aa3f6e8747089837142
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-relational-operators"></a>_variant_t 関係演算子
**Microsoft 固有の仕様**  
  
 2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**と比較する、`_variant_t`オブジェクト。  
  
 `pSrc`  
 ポインター、**バリアント**と比較する、`_variant_t`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 返します**true**比較が保持している場合**false**しない場合。  
  
## <a name="remarks"></a>コメント  
 比較、`_variant_t`オブジェクトを**バリアント**等しいかどうかをテストします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
