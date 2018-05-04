---
title: _bstr_t::operator = = |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5537f4ad3abbac9686272e15d06bfa5df0bfca6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft 固有の仕様**  
  
 既存の `_bstr_t` オブジェクトに新しい値を代入します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *S1*  
 既存の `_bstr_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。  
  
 *S2*  
 既存の `_bstr_t` オブジェクトに割り当てられるマルチバイト文字列。  
  
 `s3`  
 既存の `_bstr_t` オブジェクトに割り当てられる Unicode 文字列。  
  
 `var`  
 既存の `_variant_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)の使用例については`operator=`します。  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)