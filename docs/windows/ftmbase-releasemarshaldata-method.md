---
title: "Ftmbase::releasemarshaldata メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
dev_langs: C++
helpviewer_keywords: ReleaseMarshalData method
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b225cccdd34302bf6e2fa0e72c01ed7c7a3cd53a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasereleasemarshaldata-method"></a>FtmBase::ReleaseMarshalData メソッド
マーシャ リング データ パケットを破棄します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP ReleaseMarshalData(  
   __in IStream *pStm  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStm`  
 破棄されるデータ パケットを含んでいるストリームへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)