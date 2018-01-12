---
title: "_com_error::Description |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Description
dev_langs: C++
helpviewer_keywords: Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3ed306a8eba4e76c2eefc738b617117188e85c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::getdescription**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::getdescription**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は**IErrorInfo**は空白を返しますが、記録`_bstr_t`です。  
  
## <a name="remarks"></a>コメント  
 呼び出し、 **ierrorinfo::getdescription**関数と取得**IErrorInfo**内に記録された、`_com_error`オブジェクト。 呼び出すときの失敗、 **ierrorinfo::getdescription**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_error クラス](../cpp/com-error-class.md)