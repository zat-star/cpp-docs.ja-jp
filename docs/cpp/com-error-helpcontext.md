---
title: "_com_error::HelpContext |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2dbdd52b311a35d390a61a0601a63c1b680f79b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft 固有の仕様**  
  
 呼び出し**ierrorinfo::gethelpcontext**関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 結果を返します**ierrorinfo::gethelpcontext**の**IErrorInfo**内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は**IErrorInfo**オブジェクトが記録されますが、ゼロが返されます。  
  
## <a name="remarks"></a>コメント  
 呼び出すときの失敗、 **ierrorinfo::gethelpcontext**メソッドは無視されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_error クラス](../cpp/com-error-class.md)