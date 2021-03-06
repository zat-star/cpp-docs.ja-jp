---
title: "Comptr::getaddressof メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d62a1bca258e0903ddd4e71b161d87d926588248
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrgetaddressof-method"></a>ComPtr::GetAddressOf メソッド
[ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。これには、この ComPtr によって表されるインターフェイスへのポインターが含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## <a name="return-value"></a>戻り値  
 変数のアドレス。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)