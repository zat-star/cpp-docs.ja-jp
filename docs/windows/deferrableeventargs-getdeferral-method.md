---
title: "Deferrableeventargs::getdeferral メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d43aa6d82f44965e8defda2af3e6455e86cba38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral メソッド
参照を取得、[遅延](http://go.microsoft.com/fwlink/?LinkId=526520)遅延イベントを表すオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `result`  
 参照するポインター、[遅延](http://go.microsoft.com/fwlink/?LinkId=526520)オブジェクト呼び出しが完了したとき。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 コード例は、次を参照してください。 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)