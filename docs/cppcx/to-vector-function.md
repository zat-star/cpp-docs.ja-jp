---
title: "to_vector 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Windows::Foundation::Collections::to_vector
dev_langs: C++
helpviewer_keywords: to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5aa6698306f06fb5d63a8e351054aa2c123749fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tovector-function"></a>to_vector 関数
値が、指定された IVector または IVectorView パラメーターの基になるコレクションと同じである `std::vector` を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T>  
inline ::std::vector<T> to_vector(IVector<T>^ v); 
 
template <typename T>  
inline ::std::vector<T> to_vector(IVectorView<T>^ v);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 基になる Vector または VectorView オブジェクトへのアクセスを提供する IVector または IVectorView インターフェイス。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>参照  
 [:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)