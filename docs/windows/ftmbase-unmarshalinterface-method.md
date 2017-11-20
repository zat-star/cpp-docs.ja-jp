---
title: "Ftmbase::unmarshalinterface メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs: C++
helpviewer_keywords: UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d4b4ba8230d9118c7de7624f957d8be47a24f81b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface メソッド
新しく作成されたプロキシを初期化し、そのプロキシにインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStm`  
 インターフェイス ポインターのマーシャ リングする元となるストリームへのポインター。  
  
 `riid`  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 `ppv`  
 この操作の完了時で要求されたインターフェイス ポインターを受け取るポインター変数のアドレス`riid`です。 この操作が成功した場合 *`ppv`のマーシャ リングするインターフェイスの要求されたインターフェイス ポインターを格納します。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_NOINTERFACE または E_FAIL します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)