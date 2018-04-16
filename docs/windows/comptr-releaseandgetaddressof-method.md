---
title: "Comptr::releaseandgetaddressof メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be56e7afb23295e9b03d801943af25c652d18758
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf メソッド
この ComPtr に関連付けられたインターフェイスを解放してから、 [ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>戻り値  
 アドレス、 [ptr _](../windows/comptr-ptr-data-member.md)この ComPtr のデータ メンバーです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)