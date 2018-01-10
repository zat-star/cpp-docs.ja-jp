---
title: "Hstringreference::operator = = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs: C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4e9c9c9edcd5c53ee3e26f89ed467140d1509e13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator== 演算子
2 つのパラメーターが等しいかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初のパラメーター。 `lhs`HStringReference オブジェクトまたは HSTRING ハンドルを指定できます。  
  
 `rhs`  
 比較する 2 番目のパラメーターです。  `rhs`HStringReference オブジェクトまたは HSTRING ハンドルを指定できます。  
  
## <a name="return-value"></a>戻り値  
 `true`場合、`lhs`と`rhs`パラメーターが等しい。 それ以外の場合、`false`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HStringReference クラス](../windows/hstringreference-class.md)