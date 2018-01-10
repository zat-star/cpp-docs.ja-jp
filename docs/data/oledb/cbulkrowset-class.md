---
title: "CBulkRowset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs: C++
helpviewer_keywords: CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26ed8c0a3f58ae046ad3e4766b7e009023759be0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowset-class"></a>CBulkRowset クラス
フェッチして、1 回の呼び出しで複数の行ハンドルを取得することによってデータの一括で作業する行を操作できます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|参照カウントをインクリメントします。|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|コンストラクターです。|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|必要に応じて新しい一括フェッチを実行して、データの最初の行を取得します。|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|最後の行に移動します。|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|次のデータ行を取得します。|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|前の行に移動します。|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|そのブックマークからのブックマークでマークされた行または指定されたオフセット位置の行をフェッチします。|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|行セット内の小数部の位置から始まる行がフェッチされます。|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|現在の行を設定 (**m_nCurrentRow**) 0 およびリリースにあるすべての行。|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|1 回の呼び出しで取得する行ハンドルの数を設定します。|  
  
## <a name="example"></a>例  
 次の例での使用、`CBulkRowset`クラスです。  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)