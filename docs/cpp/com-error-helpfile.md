---
title: "_com_error::HelpFile |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
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
ms.openlocfilehash: 7e1e9ec8c7d6684bb7b244fd9ba6773b6f1460e1
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::gethelpfile**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::gethelpfile**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は**IErrorInfo**は空白を返しますが、記録`_bstr_t`です。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::gethelpfile**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)
