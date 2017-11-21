---
title: "Comptr::asweak メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::AsWeak
dev_langs: C++
helpviewer_keywords: AsWeak method
ms.assetid: 23e29dcd-39cb-423f-abe6-6df4428213bf
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d4bdf9e6f2e3a484af825cea7facc78830b0cc48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrasweak-method"></a>ComPtr::AsWeak メソッド
現在のオブジェクトへの弱い参照を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT AsWeak(  
   _Out_ WeakRef* pWeakRef  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pWeakRef`  
 この操作の完了時、弱い参照オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)