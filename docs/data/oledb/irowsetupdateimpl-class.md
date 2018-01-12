---
title: "IRowsetUpdateImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
dev_langs: C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 206f3d25069eaa12efce8150e82c4f54fc96f4fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl クラス
OLE DB テンプレートの実装、 [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  
class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass  
>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`IRowsetUpdateImpl`です。  
  
 `Storage`  
 ユーザー レコードです。  
  
 `UpdateArray`  
 行セットを更新するためのキャッシュされたデータを格納する配列。  
  
 `RowClass`  
 記憶域ユニットを**HROW**です。  
  
 `MapClass`  
 すべての行ハンドルの記憶域ユニットでは、プロバイダーによって保持されています。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスのメソッド (IRowsetChange で使用)  
  
|||  
|-|-|  
|[Setdata メソッド](../../data/oledb/irowsetupdateimpl-setdata.md)|1 つまたは複数の列のデータ値を設定します。|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>インターフェイスのメソッド (IRowsetUpdate と共に使用)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|最後に送信または保留中の変更を無視して、データ ソースから取得したデータを取得します。|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|保留中の変更を持つ行の一覧を返します。|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|指定された行の状態を返します。|  
|[元に戻す](../../data/oledb/irowsetupdateimpl-undo.md)|最後のフェッチまたは更新以降、行への変更を元に戻します。|  
|[更新](../../data/oledb/irowsetupdateimpl-update.md)|最後のフェッチまたは更新以降、行に加えられた変更を送信します。|  
  
### <a name="implementation-methods-callback"></a>実装メソッド (コールバック)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|チェックするセキュリティ、整合性などの更新を許可する前に使用されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|遅延された操作の元のデータが含まれています。|  
  
## <a name="remarks"></a>コメント  
 必要がありますまず読んで理解してドキュメントを[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)が説明されているすべてのものも適用されるため、ここで、します。 第 6 章を参照することも必要があります、 *OLE DB プログラマーズ リファレンス*データを設定します。  
  
 `IRowsetUpdateImpl`OLE DB を実装する`IRowsetUpdate`インターフェイスで行われた変更の送信を遅延するコンシューマー`IRowsetChange`をデータ ソースし、データ伝送する前に変更を元に戻します。  
  
> [!IMPORTANT]
>  プロバイダーを実装する前に、次のドキュメントを読むことを強くお勧めします。  
  
-   [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)  
  
-   第 6 章、 *OLE DB プログラマーズ リファレンス*  
  
-   参照してください、 `RUpdateRowset` UpdatePV サンプルで使用されます  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)