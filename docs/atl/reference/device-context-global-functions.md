---
title: "デバイス コンテキストのグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlwin/ATL::AtlCreateTargetDC
dev_langs: C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2560043bc97c384846696b76d8e38b459ae4a34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="device-context-global-functions"></a>デバイス コンテキストのグローバル関数
この関数は、特定のデバイスのデバイス コンテキストを作成します。  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイス コンテキストを作成します。|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 指定されたデバイスのデバイス コンテキストを作成、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)構造体。  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>パラメーター  
 *hdc*  
 [in]デバイス コンテキストの既存のハンドルまたは**NULL**です。  
  
 `ptd`  
 [in]ポインター、 **DVTARGETDEVICE**ターゲット デバイスに関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 ハンドルで指定されたデバイスのデバイス コンテキストを返します、 **DVTARGETDEVICE**です。 デバイスが指定されていない場合は、既定のディスプレイ デバイスにハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 構造が場合**NULL**と*hdc*は**NULL**既定のディスプレイ デバイスのデバイス コンテキストを作成します。  
  
 場合*hdc*は**NULL**と`ptd`は**NULL**、既存の関数を返します*hdc*です。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
