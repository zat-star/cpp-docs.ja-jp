---
title: "接続ポイント マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs: C++
helpviewer_keywords: connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f98b5abd00f1d7ac3e3d69b0e22b549fdea35a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="connection-point-macros"></a>接続ポイント マクロ
これらのマクロは、接続ポイントのマップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|接続ポイントのマップ エントリの先頭を示します。|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|マップには、接続ポイントを入力します。|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017)CONNECTION_POINT_ENTRY と同様には、iid へのポインターがかかります。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|コネクション ポイントのマップ エントリの末尾をマークします。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h 
   
##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP  
 接続ポイントのマップ エントリの先頭を示します。  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]接続ポイントを含むクラスの名前。  
  
### <a name="remarks"></a>コメント  
 接続ポイントのマップを開始、`BEGIN_CONNECTION_POINT_MAP`マクロ、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロでマップを完了し、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY と CONNECTION_POINT_ENTRY_P  
 アクセスできるようにに接続ポイントのマップに指定されたインターフェイスの接続ポイントを入力します。  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コネクション ポイントのマップに追加されているインターフェイスの GUID です。 
 
 `piid`  
 [in]Adde をされているインターフェイスの GUID へのポインター。   
  
### <a name="remarks"></a>コメント  
 マップ内の接続ポイントのエントリがによって使用される[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)です。 接続ポイントのマップを含むクラスを継承する必要があります`IConnectionPointContainerImpl`です。  
  
 接続ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロ、各接続ポイントのエントリを追加、`CONNECTION_POINT_ENTRY`マクロでマップを完了し、 [END_CONNECTION_POINT_MAP](#end_connection_point_map)マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP  
 コネクション ポイントのマップ エントリの末尾をマークします。  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>コメント  
 接続ポイントのマップを開始、 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)マクロ、各接続ポイントのエントリを追加、 [CONNECTION_POINT_ENTRY](#connection_point_entry)マクロ、し、でマップを完了`END_CONNECTION_POINT_MAP`マクロです。  
  
 ATL のコネクション ポイントの詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>参照  
 [マクロ](../../atl/reference/atl-macros.md)   
 [コネクション ポイントに関するグローバル関数](../../atl/reference/connection-point-global-functions.md)
