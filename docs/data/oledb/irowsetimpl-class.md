---
title: "IRowsetImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetImpl class
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 524f796b3ba864fe4e1d63c04b1b90fada314965
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimpl-class"></a>IRowsetImpl クラス
`IRowset` インターフェイスの実装を提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*>>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IRowsetImpl`です。  
  
 `RowsetInterface`  
 派生したクラス`IRowsetImpl`です。  
  
 `RowClass`  
 記憶域ユニットを**HROW**です。  
  
 `MapClass`  
 記憶域ユニットをすべての行ハンドルは、プロバイダーによって保持されています。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|既存の行ハンドルに参照カウントを追加します。|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|によって呼び出されます[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)に割り当てる新しい**HROW**です。 ユーザーが直接呼び出されません。|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|行の行セットのコピーからデータを取得します。|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|指定したフィールドの状態を返します。|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|前の位置を記憶、順番に行をフェッチします。|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|コンストラクターです。 ユーザーが直接呼び出されません。|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|によって呼び出されます[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)と[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)です。 ユーザーが直接呼び出されません。|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|行を解放します。|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|次のフェッチ位置を最初の位置に再配置します。つまり、行セットが最初の位置が作成されます。|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|指定したフィールドのステータスのフラグを設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|プロバイダーが旧バージョンとフェッチをサポートするかどうかを示します。|  
|[m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|プロバイダーがそのカーソルのスクロールを旧バージョンとができるかどうかを示します。|  
|[m_bReset](../../data/oledb/irowsetimpl-m-breset.md)|プロバイダーがカーソル位置をリセットするかどうかを示します。 これは後方スクロールまたは下位のフェッチ時に特別な意味[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)です。|  
|[m_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|カーソルを表す行セットのインデックスです。|  
|[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|行ハンドルの一覧。|  
  
## <a name="remarks"></a>コメント  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)行セットの基本インターフェイスです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)