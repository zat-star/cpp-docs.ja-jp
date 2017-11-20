---
title: "Ftmbase::disconnectobject メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs: C++
helpviewer_keywords: DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 618590f28dcb82be0bcb9c4407c9aa4eaa2432ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject メソッド
オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーでは、シャット ダウンする前にこのメソッドのオブジェクトの実装を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 今後使用するために予約されています。0 にする必要があります。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)