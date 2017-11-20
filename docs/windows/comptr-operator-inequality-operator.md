---
title: "Comptr::operator! = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator!=
dev_langs: C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce13c5dabf267be5d7c8a77a51d1450f182d226d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= 演算子
2 つの ComPtr オブジェクトが等しくないかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `a`  
 ComPtr オブジェクトへの参照。  
  
 `b`  
 もう 1 つの ComPtr オブジェクトへの参照。  
  
## <a name="return-value"></a>戻り値  
 最初の演算子によって生成`true`場合オブジェクト`a`がオブジェクトと等しくない`b`、それ以外の`false`します。  
  
 2 番目と 3 番目の演算子の yield`true`場合オブジェクト`a`は等しくありません`nullptr`、それ以外の`false`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr クラス](../windows/comptr-class.md)