---
title: "イベント処理のグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4bf2a8b0211361f5d5d2bf0f996e978638631116
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="event-handling-global-functions"></a>イベント処理のグローバル関数
この関数は、イベント ハンドラーを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に記載されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|その一方で、必要に応じてウィンドウ メッセージをディスパッチ オブジェクトをシグナルを待機します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 オブジェクトがシグナル状態になるまで待機します。その間、必要に応じてウィンドウ メッセージをディスパッチします。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `hEvent`  
 [in]待機対象のオブジェクトのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**オブジェクトがシグナル状態になった場合。  
  
### <a name="remarks"></a>コメント  
 これは、オブジェクトのイベントが発生して、発生していることを通知するまで待機するウィンドウ メッセージを待機中にディスパッチするようにした場合に便利です。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

