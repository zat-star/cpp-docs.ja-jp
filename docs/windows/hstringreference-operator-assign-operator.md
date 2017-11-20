---
title: "Hstringreference::operator = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs: C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b6a9938308f0cbd8339c24d1876c09ae49df349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 演算子
別の HStringReference オブジェクトの値を現在の HStringReference オブジェクトに移動します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 既存の HStringReference オブジェクト。  
  
## <a name="remarks"></a>コメント  
 既存の値`other`オブジェクトが現在の HStringReference オブジェクトにコピーし、`other`オブジェクトは破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)