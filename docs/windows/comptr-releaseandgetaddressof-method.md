---
title: "Comptr::releaseandgetaddressof メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6711cc93071c1e260a5d216a6ad21add9c00540
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf メソッド
この ComPtr に関連付けられたインターフェイスを解放してから、 [ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>戻り値  
 アドレス、 [ptr _](../windows/comptr-ptr-data-member.md)この ComPtr のデータ メンバーです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)