---
title: "_com_error::operator = |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= _com_error objects
- = operator [C++], with specific Visual C++ objects
- operator = _com_error objects
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ddbd09e7783818cb5d2bc72941c8f9e0472e7a3c
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerroroperator-"></a>_com_error::operator =
**Microsoft 固有の仕様**  
  
 既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _com_error& operator = (  
   const _com_error& that   
) throw ( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `that`  
 `_com_error` オブジェクト。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)
