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
ms.workload: cplusplus
ms.openlocfilehash: 9aa685604580423262ab694d1285897cd29eef63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
   
## <a name="see-also"></a>参照  
 [関数](../../atl/reference/atl-functions.md)
