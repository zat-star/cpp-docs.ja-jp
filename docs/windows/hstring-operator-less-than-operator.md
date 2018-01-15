---
title: "Hstring::operator&lt;演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs: C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4cbb21e34255d5350702d949792656bdf0a849a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringoperatorlt-operator"></a>Hstring::operator&lt;演算子
最初のパラメーターがあるか、2 番目のパラメーターより小さいことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初のパラメーター。 `lhs`HString への参照ができます。  
  
 `rhs`  
 比較する 2 番目のパラメーターです。 `rhs`HString への参照ができます。  
  
## <a name="return-value"></a>戻り値  
 `true`場合、`lhs`パラメーターより小さい`rhs`パラメーターです。 それ以外の場合、`false`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HString クラス](../windows/hstring-class.md)