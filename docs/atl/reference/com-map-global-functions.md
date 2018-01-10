---
title: "グローバル関数の COM マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs: C++
helpviewer_keywords: COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7a0a02e46906ae8d3b6c62b8cc1b9147d396966
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-global-functions"></a>COM マップ グローバル関数
これらの関数では、COM マップのサポート**IUnknown**実装します。  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|デリゲート、 **IUnknown**の非集約オブジェクト。|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|に対するインターフェイスを比較するための効率的なコードを生成**IUnknown**です。|  

  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pThis`  
 [in]公開されるインターフェイスの COM マップを含んでいるオブジェクトへのポインター`QueryInterface`です。  
  
 `pEntries`  
 [in]配列**_ATL_INTMAP_ENTRY**使用可能なインターフェイスのマップにアクセスする構造体。  
  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 `AtlInternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトを集約すると場合、`AtlInternalQueryInterface`外部への委任しません。 インターフェイスを入力するには、COM マップ テーブルにマクロを持つ[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリエーションの 1 つです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 この関数の呼び出しのためのテストの特殊なケースの**IUnknown**です。  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>パラメーター  
 *rguid1*  
 [in]比較する GUID **IID_IUnknown**です。  
  
## <a name="see-also"></a>参照  
 [関数](../../atl/reference/atl-functions.md)   
 [COM マップに関するマクロ](../../atl/reference/com-map-macros.md)
