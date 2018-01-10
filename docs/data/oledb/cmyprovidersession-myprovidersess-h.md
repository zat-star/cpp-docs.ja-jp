---
title: "CMyProviderSession (MyProviderSess.H) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs: C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3cf8a75a416f03fed1ae7e0deb9118b3c40ea5fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H には、宣言と OLE DB セッション オブジェクトの実装が含まれています。 データ ソース オブジェクトは、セッション オブジェクトを作成し、コンシューマーとプロバイダー間のメッセージ交換を表します。 複数の同時セッションは、1 つのデータ ソースを開くことができます。 継承リストに`CMyProviderSession`に従います。  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 セッション オブジェクトから継承**IGetDataSource**、 `IOpenRowset`、 **ISessionProperties**、および**IDBCreateCommand**です。 **IGetDataSource**インターフェイスにより、セッションを作成するデータ ソースを取得します。 これは、作成したデータ ソースまたはデータ ソースを提供できるその他の情報のプロパティを取得する必要がある場合に便利です。 **ISessionProperties**インターフェイスは、セッションのすべてのプロパティを処理します。 `IOpenRowset`と**IDBCreateCommand**データベース作業を行うためのインターフェイスが使用されます。 実装するプロバイダーは、コマンドをサポートする場合、 **IDBCreateCommand**インターフェイスです。 コマンドを実行できるコマンド オブジェクトの作成に使用されます。 プロバイダーは常に実装して、`IOpenRowset`オブジェクト。 プロバイダーからの単純な行セットの生成に使用されます。 既定の行セット (たとえば、 `"select * from mytable"`) プロバイダーからです。  
  
 ウィザードでは、次の 3 つのセッション クラスも生成されます: `CMyProviderSessionColSchema`、 `CMyProviderSessionPTSchema`、および`CMyProviderSessionTRSchema`です。 スキーマ行セットでは、これらのセッションが使用されます。 スキーマ行セットでは、プロバイダー、コンシューマーがデータのクエリやフェッチを実行することがなく、コンシューマーにメタデータを返すことができるようにします。 メタデータのフェッチがプロバイダーの機能を検出するよりも高速に実行できます。  
  
 OLE DB 仕様では、する必要がありますを実装するプロバイダー、 **IDBSchemaRowset**インターフェイス サポート 3 つのスキーマ行セットの種類: **DBSCHEMA_COLUMNS**、 **DBSCHEMA_PROVIDER_TYPES**、および`DBSCHEMA_TABLES`です。 ウィザードでは、各スキーマ行セットの実装を生成します。 ウィザードによって生成された各クラスが含まれています、`Execute`メソッドです。 この`Execute`メソッドをサポートするどのテーブル、列、およびデータ型は、プロバイダーにデータを返すことができます。 通常、このデータは、コンパイル時に呼ばれます。  
  
## <a name="see-also"></a>参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)