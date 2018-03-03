---
title: "COM マップ マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e97db324dc8e130418419ef435e2665c84eb0b64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-macros"></a>COM マップ マクロ
これらのマクロは、COM インターフェイス マップを定義します。  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイス マップのエントリの先頭をマークします。|  
|[END_COM_MAP](#end_com_map)|COM インターフェイス マップのエントリの末尾をマークします。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 COM マップを介してクライアントにオブジェクト上のインターフェイスを公開するメカニズムは、`QueryInterface`です。  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイスを公開するのには、クラスのオブジェクトの名前です。  
  
### <a name="remarks"></a>コメント  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)のみ COM マップ内のインターフェイス ポインターを返します。 インターフェイス マップを開始、`BEGIN_COM_MAP`マクロをインターフェイスの各エントリを追加、 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)マクロ、またはそのバリエーションの 1 つでマップを完了し、 [END_COM_MAP](#end_com_map)マクロです。  

  
### <a name="example"></a>例  
 ATL から[ポケットベル](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 COM インターフェイス マップの定義を終了します。  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>参照  
 [マクロ](../../atl/reference/atl-macros.md)   
 [COM マップに関するグローバル関数](../../atl/reference/com-map-global-functions.md)
