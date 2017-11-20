---
title: "Hstringreference::operator&lt;演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs: C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46d839cd10144877ee4af561ce9e1ab52343de83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::operator&lt;演算子
最初のパラメーターがあるか、2 番目のパラメーターより小さいことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初のパラメーター。 `lhs`HStringReference への参照ができます。  
  
 `rhs`  
 比較する 2 番目のパラメーターです。  `rhs`HStringReference への参照ができます。  
  
## <a name="return-value"></a>戻り値  
 `true`場合、`lhs`パラメーターより小さい`rhs`パラメーターです。 それ以外の場合、`false`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)