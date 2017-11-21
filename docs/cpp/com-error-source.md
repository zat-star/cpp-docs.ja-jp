---
title: "_com_error::Source |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Source
dev_langs: C++
helpviewer_keywords: Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01f63158f2406505e833ab58dcb53e099c3348f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorsource"></a>_com_error::Source
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::getsource**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::getsource**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は**IErrorInfo**は空白を返しますが、記録`_bstr_t`です。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::getsource**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)