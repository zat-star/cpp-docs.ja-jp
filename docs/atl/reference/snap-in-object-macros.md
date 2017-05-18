---
title: "スナップイン オブジェクト マクロ |Microsoft ドキュメント"
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
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 13823feb06e7fecb2e81a01f3c88e3664de01d30
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="snap-in-object-macros"></a>スナップイン オブジェクト マクロ
これらのマクロでは、スナップインの拡張機能がサポートされます。  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|スナップインでオブジェクトのスナップイン拡張データ クラスのマップの先頭をマークします。|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|スナップインでオブジェクトのツールバーのマップの先頭をマークします。|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|スナップイン オブジェクトのスナップイン拡張データ クラスのマップの最後をマークします。|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|スナップインでオブジェクトのマップをツールバーの最後をマークします。|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|スナップイン拡張機能のデータ クラスのデータ メンバーを作成します。|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|スナップインでオブジェクトのスナップイン拡張データ クラスのマップにスナップイン拡張データ クラスを入力します。|  
|[SNAPINMENUID](#snapinmenuid)|スナップイン オブジェクトで使用されるコンテキスト メニューの ID を宣言します。|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|スナップインでオブジェクトのツールバーのマップにツールバーを入力します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 スナップイン拡張データ クラスのマップの先頭を示します。  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>パラメーター  
 *クラス名*  
 [in]スナップインの拡張機能のデータ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 拡張スナップインでマップを開始、`BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP`マクロ、スナップイン拡張データ型と型の各エントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを対応付けを行い、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP  
 スナップインでオブジェクトのツールバー ID マップの先頭を宣言します。  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]スナップイン オブジェクト クラスを指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&106;](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP  
 スナップイン拡張データ クラスのマップの最後をマークします。  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>コメント  
 拡張スナップインでマップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロと拡張スナップインで使用するデータ型の各エントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを対応付けを行い、`END_EXTENSION_SNAPIN_NODEINFO_MAP`マクロです。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)します。  
  
##  <a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP  
 スナップインでオブジェクトのツールバー ID マップの最後を宣言します。  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]スナップイン オブジェクト クラスを指定します。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)します。  
  
##  <a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS  
 スナップイン拡張データ クラスにデータ メンバーを追加、 **ISnapInItemImpl**-クラスを派生します。  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>パラメーター  
 `dataClass`  
 [in]スナップイン拡張機能のデータ クラス。  
  
### <a name="remarks"></a>コメント  
 このクラスは、スナップイン拡張データのクラスのマップにも入力する必要があります。 スナップイン拡張データ クラス マップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロ、スナップイン拡張データ型と型の各エントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを対応付けを行い、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY  
 スナップイン拡張データ クラスを拡張スナップインでデータ クラスのマップに追加します。  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>パラメーター  
 `dataClass`  
 [in]スナップイン拡張機能のデータ クラス。  
  
### <a name="remarks"></a>コメント  
 スナップイン拡張データ クラス マップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロ、スナップイン拡張データ型と型の各エントリを追加、`EXTENSION_SNAPIN_NODEINFO_ENTRY`マクロを対応付けを行い、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)します。  
  
##  <a name="snapinmenuid"></a>SNAPINMENUID  
 このマクロを使用すると、スナップイン オブジェクトのコンテキスト メニューのリソースを宣言できます。  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]スナップインでオブジェクトのコンテキスト メニューを識別します。  
  
##  <a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY  
 このマクロを使用すると、スナップイン オブジェクトのツールバーの ID のマップにツールバー ID を入力します。  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]ツール バー コントロールを識別します。  
  
### <a name="remarks"></a>コメント  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)マクロには、ツールバー ID マップの始まり、 [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)します。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

