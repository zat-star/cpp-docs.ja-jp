---
title: "Comptr::detach メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feb76819ce032608fdc717b3176f0242149eb8a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrdetach-method"></a>ComPtr::Detach メソッド
この関連付けを解除`ComPtr`オブジェクトが表すインターフェイスからです。  
  
## <a name="syntax"></a>構文  
  
```  
T* Detach();  
```  
  
## <a name="return-value"></a>戻り値  
 これによって表されるインターフェイスへのポインター`ComPtr`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)