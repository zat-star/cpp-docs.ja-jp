---
title: "Comptrref::operator = = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs: C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea2fd557c9ae7da6c696ab8f8174ad8610a9174b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator== 演算子
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `a`  
 ComPtrRef オブジェクトへの参照。  
  
 `b`  
 別の ComPtrRef オブジェクト、または匿名型へのポインターへの参照を (`void*`)。  
  
## <a name="return-value"></a>戻り値  
 最初の演算子によって生成`true`場合オブジェクト`a`がオブジェクトと等しい`b`、それ以外の`false`します。  
  
 2 番目と 3 番目の演算子の yield`true`場合オブジェクト`a`と等しい`nullptr`、それ以外の`false`します。  
  
 4 番目と 5 番目の演算子の yield`true`場合オブジェクト`a`がオブジェクトと等しい`b`、それ以外の`false`します。  
  
## <a name="remarks"></a>コメント  
 2 つの ComPtrRef オブジェクトが等しいかどうかを示します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef クラス](../windows/comptrref-class.md)