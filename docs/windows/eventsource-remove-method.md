---
title: "Eventsource::remove メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::Remove
dev_langs: C++
helpviewer_keywords: Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1879c939237275c279e1dd4bd1861ab3b02b468
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourceremove-method"></a>EventSource::Remove メソッド
現在の EventSource オブジェクトに関連付けられているイベント ハンドラーのセットから指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `token`  
 イベント ハンドラーを表すためのハンドル。 イベント ハンドラーがによって登録されたときにこのトークンが返された、 [Add()](../windows/eventsource-add-method.md)メソッドです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 EventRegistrationToken 構造体の詳細については、Windows ランタイムのリファレンス ドキュメントで Windows::Foundation::EventRegistrationToken 構造体を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [EventSource クラス](../windows/eventsource-class.md)