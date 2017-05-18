---
title: "コネクション ポイントに関するマクロ |Microsoft ドキュメント"
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
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: c16b6f2f889745270a51a32a1449add86dec6ecb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-macros"></a>コネクション ポイントに関するマクロ
これらのマクロは、コネクション ポイントのマップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|コネクション ポイントのマップのエントリの先頭をマークします。|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|マップへの接続ポイントを入力します。|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017)CONNECTION_POINT_ENTRY と同様には、iid へのポインターがかかります。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|コネクション ポイントのマップのエントリの終了を示します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h 
   
##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP  
 コネクション ポイントのマップのエントリの先頭をマークします。  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]コネクション ポイントを含むクラスの名前。  
  
### <a name="remarks"></a>コメント  
 コネクション ポイントのマップを開始、`BEGIN_CONNECTION_POINT_MAP`マクロ、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを使用して、地図を完了、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&101;](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY と CONNECTION_POINT_ENTRY_P  
 アクセスできるように、接続ポイント コネクション ポイントのマップに指定したインターフェイスを入力します。  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コネクション ポイントのマップに追加されているインターフェイスの GUID です。 
 
 `piid`  
 [in]他追加されていますがされているインターフェイスの GUID へのポインター。   
  
### <a name="remarks"></a>コメント  
 マップ内の接続ポイント エントリで使用される[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)します。 コネクション ポイントのマップを含むクラスを継承する必要がある`IConnectionPointContainerImpl`です。  
  
 コネクション ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロ、各接続ポイントのエントリを追加、`CONNECTION_POINT_ENTRY`マクロを使用して、地図を完了、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&120;](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP  
 コネクション ポイントのマップのエントリの終了を示します。  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>コメント  
 コネクション ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロ、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロを使用して、地図を完了、`END_CONNECTION_POINT_MAP`マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&128;](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [コネクション ポイント グローバル関数](../../atl/reference/connection-point-global-functions.md)

