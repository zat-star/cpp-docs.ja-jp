---
title: "プロパティ マップ マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fbbed22766f9029456f15c4a554ae91322e6a275
ms.lasthandoff: 02/24/2017

---
# <a name="property-map-macros"></a>プロパティ マップ マクロ
これらのマクロは、プロパティ マップとエントリを定義します。  
  
|||  
|-|-|  
|[あり、その場合](#begin_prop_map)|ATL プロパティ マップの先頭をマークします。|  
|[するため](#prop_data_entry)|範囲、または ActiveX コントロールのサイズを示します。|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|プロパティ マップには、プロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|プロパティの DISPID、プロパティ ページの CLSID、プロパティの説明を入力し、`IDispatch`プロパティ マップに IID です。|  
|[PROP_PAGE](#prop_page)|プロパティ マップには、プロパティ ページの CLSID を入力します。|  
|[マクロと](#end_prop_map)|ATL プロパティ マップの最後をマークします。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="a-namebeginpropmapa--beginpropmap"></a><a name="begin_prop_map"></a>あり、その場合  
 オブジェクトのプロパティ マップの先頭をマークします。  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]プロパティ マップを含むクラスを指定します。  
  
### <a name="remarks"></a>コメント  
 プロパティ マップがプロパティ Dispid、Clsid、 プロパティ ページのプロパティの説明を格納し、`IDispatch`の Iid です。 クラス[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)、 [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)、 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、および[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)プロパティ マップを使用して取得し、この情報を設定します。  
  
 指定して、空のプロパティ マップが作成されます ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに`BEGIN_PROP_MAP`続けて[マクロと](#end_prop_map)です。  
  
 `BEGIN_PROP_MAP`エクステントはありませんので、プロパティ マップを使用してオブジェクトは、ユーザー インターフェイスがない可能性が、プロパティ マップの範囲 (大きさ) を保存しません。 オブジェクトがユーザー インターフェイスを持つ ActiveX コントロールの場合は、エクステントができます。 この場合は、指定する必要があります[するため](#prop_data_entry)範囲を指定するプロパティ マップします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&103;](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="a-namepropdataentrya--propdataentry"></a><a name="prop_data_entry"></a>するため  
 範囲、または ActiveX コントロールのサイズを示します。  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `member`  
 [in]エクステント; を含んでいるデータ メンバーたとえば、`m_sizeExtent`です。  
  
 *vt*  
 [in]プロパティのバリアント型を指定します。  
  
### <a name="remarks"></a>コメント  
 このマクロでは、永続化する指定したデータ メンバーが発生します。  
  
 ActiveX コントロールを作成するときに、このマクロはプロパティ マップ マクロの後に挿入された[あり、その場合](#begin_prop_map)とプロパティのマップ マクロの前に[マクロと](#end_prop_map)です。  
  
### <a name="example"></a>例  
 次の例では、オブジェクトの範囲 ( `m_sizeExtent`) 永続化します。  
  
 [!code-cpp[NVC_ATL_Windowing #&131;](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing #&132;](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="a-namepropentrytypea--propentrytype"></a><a name="prop_entry_type"></a>PROP_ENTRY_TYPE  
 このマクロを使用すると、オブジェクトのプロパティ マップ プロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `dispid`  
 [in]プロパティのように DISPID します。  
  
 `clsid`  
 [in]関連付けられたプロパティ ページの CLSID。 特殊な値を使用して`CLSID_NULL`プロパティが関連付けられたプロパティ ページの場合。  
  
 `vt`  
 [in]プロパティの型。  
  
### <a name="remarks"></a>コメント  
 `PROP_ENTRY`マクロが安全ではなく、非推奨です。 置き換えられました`PROP_ENTRY_TYPE`します。  
  
 [あり、その場合](#begin_prop_map)マクロには、プロパティ マップの始まり、[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 例を参照してください[あり、その場合](#begin_prop_map)します。  
  
##  <a name="a-namepropentrytypeexa--propentrytypeex"></a><a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX  
 ような[PROP_ENTRY_TYPE](#prop_entry_type)は、オブジェクトは、複数のデュアル インターフェイスをサポートしている場合、特定の IID を指定するようにします。  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `dispid`  
 [in]プロパティのように DISPID します。  
  
 `clsid`  
 [in]関連付けられたプロパティ ページの CLSID。 特殊な値を使用して`CLSID_NULL`プロパティが関連付けられたプロパティ ページの場合。  
  
 `iidDispatch`  
 [in]プロパティを定義するデュアル インターフェイスの IID です。  
  
 `vt`  
 [in]プロパティの型。  
  
### <a name="remarks"></a>コメント  
 `PROP_ENTRY_EX`マクロが安全ではなく、非推奨です。 置き換えられました`PROP_ENTRY_TYPE_EX`します。  
  
 [あり、その場合](#begin_prop_map)マクロには、プロパティ マップの始まり、[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 次の例のエントリをグループ化`IMyDual1`のエントリを続けて`IMyDual2`します。 デュアル インターフェイスでグループ化には、パフォーマンスが向上します。  
  
 [!code-cpp[NVC_ATL_Windowing #&133;](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="a-nameproppagea--proppage"></a><a name="prop_page"></a>PROP_PAGE  
 このマクロを使用すると、オブジェクトのプロパティ マップにプロパティ ページの CLSID を入力します。  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]プロパティ ページの CLSID。  
  
### <a name="remarks"></a>コメント  
 `PROP_PAGE`ような[PROP_ENTRY_TYPE](#prop_entry_type)プロパティの説明または DISPID は必要ありません。  
  
> [!NOTE]
>  持つ CLSID を入力した場合`PROP_ENTRY_TYPE`または[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)に追加エントリを作成する必要はありません`PROP_PAGE`します。  
  
 [あり、その場合](#begin_prop_map)マクロには、プロパティ マップの始まり、[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&134;](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="a-nameendpropmapa--endpropmap"></a><a name="end_prop_map"></a>マクロと  
 オブジェクトのプロパティ マップの最後をマークします。  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>コメント  
 指定して、空のプロパティ マップが作成されます ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに[あり、その場合](#begin_prop_map)続けて`END_PROP_MAP`します。  
  
### <a name="example"></a>例  
 例を参照してください[あり、その場合](#begin_prop_map)します。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

