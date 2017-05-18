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
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 1c8e73fc4d6cab2e9052e74d68bddbb5796ebfa8
ms.contentlocale: ja-jp
ms.lasthandoff: 03/31/2017

---
# <a name="com-map-macros"></a>COM マップ マクロ
これらのマクロは、COM インターフェイス マップを定義します。  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイス マップのエントリの先頭をマークします。|  
|[END_COM_MAP](#end_com_map)|COM インターフェイス マップのエントリの末尾をマークします。|  

## <a name="requirements"></a>要件  
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
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)のみ COM マップ内のインターフェイス ポインターを返します。 インターフェイス マップを開始、`BEGIN_COM_MAP`マクロでインターフェイスの各エントリを追加、 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)マクロ、またはそのバリエーションの 1 つのマップを完了し、 [END_COM_MAP](#end_com_map)マクロです。  

  
### <a name="example"></a>例  
 ATL から[ポケットベル](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_ATL_COM 1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 COM インターフェイス マップの定義を終了します。  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [COM マップに関するグローバル関数](../../atl/reference/com-map-global-functions.md)

