---
title: "グローバル関数の WinModule |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
dev_langs: C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 290566c27fa5698c4a00a323a8c2431681b69d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="winmodule-global-functions"></a>WinModule グローバル関数
これらの関数のサポートを提供する`_AtlCreateWndData`操作を構成します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|`_AtlCreateWndData` 構造体を初期化して追加します。|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|既存の `_AtlCreateWndData` 構造体を抽出します。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  `            
##  <a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
 `_AtlCreateWndData` 構造体を初期化して追加します。  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWinModule`  
 モジュールへのポインター [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体。  
  
 `pData`  
 ポインター、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体を初期化し、現在のモジュールに追加します。  
  
 `pObject`  
 オブジェクトへのポインター**この**ポインター。  
  
### <a name="remarks"></a>コメント  
 初期化、`_AtlCreateWndData`の格納に使用する構造体、**この**ポインターのクラスのインスタンスを参照するために使用し、モジュールによって参照されているリストに追加します`_ATL_WIN_MODULE70`構造体。 によって呼び出されます[CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)です。  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 既存の `_AtlCreateWndData` 構造体を抽出します。  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWinModule`  
 モジュールへのポインター [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、既存の抽出`_AtlCreateWndData`構造体、モジュールによって参照されている一覧から`_ATL_WIN_MODULE70`構造体。  
  
## <a name="see-also"></a>参照  
 [関数](../../atl/reference/atl-functions.md)
