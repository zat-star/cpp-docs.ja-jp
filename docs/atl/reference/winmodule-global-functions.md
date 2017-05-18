---
title: "WinModule グローバル関数 |Microsoft ドキュメント"
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
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: 19
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
ms.openlocfilehash: c477f4500bd4fe78f21f04c58b02d1b493f72c01
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="winmodule-global-functions"></a>WinModule グローバル関数
これらの関数のサポートを提供する`_AtlCreateWndData`操作を構成します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|`_AtlCreateWndData` 構造体を初期化して追加します。|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|既存の `_AtlCreateWndData` 構造体を抽出します。|  

## <a name="requirements"></a>要件  
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
 ポインター、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造が初期化され、現在のモジュールに追加します。  
  
 `pObject`  
 オブジェクトへのポインター**この**ポインター。  
  
### <a name="remarks"></a>コメント  
 初期化、`_AtlCreateWndData`の格納に使用する構造体、**これ**ポインターのクラスのインスタンスを参照するために使用し、モジュールによって参照されているリストに追加`_ATL_WIN_MODULE70`構造体。 によって呼び出される[CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)します。  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 既存の `_AtlCreateWndData` 構造体を抽出します。  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWinModule`  
 モジュールへのポインター [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、既存の抽出は`_AtlCreateWndData`構造体、モジュールによって参照されているリストから`_ATL_WIN_MODULE70`構造体。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

