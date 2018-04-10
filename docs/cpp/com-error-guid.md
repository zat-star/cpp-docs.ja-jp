---
title: _com_error::GUID |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1165f53027c5b8a116f97cd2660c7ca12c9e7302
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::getguid**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::getguid**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は**IErrorInfo**返しますオブジェクトが記録されて、`GUID_NULL`です。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::getguid**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_error クラス](../cpp/com-error-class.md)