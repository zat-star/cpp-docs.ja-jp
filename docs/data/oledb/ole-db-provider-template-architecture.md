---
title: "OLE DB プロバイダー テンプレートのアーキテクチャ |Microsoft ドキュメント"
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
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 122da4031eff1cacfaf3242000cbd36eb7b75356
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB プロバイダー テンプレートのアーキテクチャ
## <a name="data-sources-and-sessions"></a>データ ソースとセッション  
 OLE DB プロバイダーのアーキテクチャには、データ ソース オブジェクトと 1 つまたは複数のセッションが含まれています。 データ ソース オブジェクトは、すべてのプロバイダーのインスタンスを作成する必要があります最初のオブジェクトです。 コンシューマー アプリケーション、データを必要とは併置プロバイダーを起動するデータ ソース オブジェクトを作成します。 データ ソース オブジェクトは、セッション オブジェクトを作成 (を使用して、 **IDBCreateSession**インターフェイス) を介して、コンシューマーのデータ ソース オブジェクトに接続します。 ODBC プログラマは、データ ソース オブジェクトと等価と考えることができます、 **HENV**と同等として、セッション オブジェクト、 **HDBC**です。  
  
 ![プロバイダーのアーキテクチャ](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 OLE DB プロバイダー ウィザードによって作成されたソース ファイル、と共には、OLE DB テンプレートは、データ ソース オブジェクトを実装します。 OLE DB に対応するオブジェクトは、セッションは**TSession**です。  
  
## <a name="mandatory-and-optional-interfaces"></a>必須およびオプションのインターフェイス  
 OLE DB プロバイダー テンプレートを提供するすべての必要なインターフェイスの実装をパッケージ化されました。 必須およびオプションのインターフェイスは、OLE DB のいくつかの種類のオブジェクトによって定義されます。  
  
-   [データ ソース](../../data/oledb/data-source-object-interfaces.md)  
  
-   [セッション](../../data/oledb/session-object-interfaces.md)  
  
-   [Rowset](../../data/oledb/rowset-object-interfaces.md)  
  
-   [コマンド](../../data/oledb/command-object-interfaces.md)  
  
-   [トランザクション](../../data/oledb/transaction-object-interfaces.md)  
  
 OLE DB プロバイダー テンプレートは、行と記憶域オブジェクトを実装しないことに注意してください。  
  
 次の表は、上記のオブジェクトの必須およびオプションのインターフェイスによると、 [OLE DB 2.6 SDK ドキュメント](https://msdn.microsoft.com/en-us/library/ms722784.aspx)です。  
  
|コンポーネント|Interface|コメント|  
|---------------|---------------|-------------|  
|[データ ソース](../../data/oledb/data-source-object-interfaces.md)([CDataSource](../../data/oledb/cdatasource-class.md))|[mandatory] **IDBCreateSession**<br /><br /> [mandatory] **IDBInitialize**<br /><br /> [mandatory] `IDBProperties`<br /><br /> [mandatory] `IPersist`<br /><br /> [optional] **IConnectionPointContainer**<br /><br /> [オプション]**IDBAsynchStatus**<br /><br /> [optional] **IDBDataSourceAdmin**<br /><br /> [オプション]**IDBInfo**<br /><br /> [オプション] `IPersistFile`<br /><br /> [optional] **ISupportErrorInfo**|コンシューマーからプロバイダーへの接続。 オブジェクトはユーザー ID、パスワード、およびデータ ソース名などの接続のプロパティを指定するために使用します。 オブジェクトは、データ ソースの管理にも使用できます (作成、更新、削除、テーブル、およびなど)。|  
|[セッション](../../data/oledb/session-object-interfaces.md)([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[mandatory] **IGetDataSource**<br /><br /> [mandatory] `IOpenRowset`<br /><br /> [必須]**ISessionProperties**<br /><br /> [optional] **IAlterIndex**<br /><br /> [オプション]**IAlterTable**<br /><br /> [optional] **IBindResource**<br /><br /> [optional] **ICreateRow**<br /><br /> [optional] **IDBCreateCommand**<br /><br /> [optional] **IDBSchemaRowset**<br /><br /> [optional] **IIndexDefinition**<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [optional] **ITableCreation**<br /><br /> [オプション]**ITableDefinition**<br /><br /> [オプション]**ITableDefinitionWithConstraints**<br /><br /> [オプション]**ITransaction**<br /><br /> [オプション]**ITransactionJoin**<br /><br /> [オプション]**ITransactionLocal**<br /><br /> [オプション]**ITransactionObject**|セッション オブジェクトは、コンシューマーとプロバイダー間の 1 つのメッセージ交換を表します。 ODBC に似た**HSTMT**がアクティブにできる同時セッションの数にします。<br /><br /> セッション オブジェクトは、OLE DB 機能を取得するプライマリ リンクです。 コマンド、トランザクション、または行セット オブジェクトを取得は、セッション オブジェクトを移動します。|  
|[行セット](../../data/oledb/rowset-object-interfaces.md)([CRowset](../../data/oledb/crowset-class.md))|[mandatory] `IAccessor`<br /><br /> [mandatory] `IColumnsInfo`<br /><br /> [mandatory] **IConvertType**<br /><br /> [mandatory] `IRowset`<br /><br /> [mandatory] `IRowsetInfo`<br /><br /> [オプション]**IChapteredRowset**<br /><br /> [optional] **IColumnsInfo2**<br /><br /> [optional] **IColumnsRowset**<br /><br /> [optional] **IConnectionPointContainer**<br /><br /> [オプション]**IDBAsynchStatus**<br /><br /> [optional] **IGetRow**<br /><br /> [オプション] `IRowsetChange`<br /><br /> [オプション]**IRowsetChapterMember**<br /><br /> [optional] **IRowsetCurrentIndex**<br /><br /> [optional] **IRowsetFind**<br /><br /> [optional] **IRowsetIdentity**<br /><br /> [optional] **IRowsetIndex**<br /><br /> [オプション] `IRowsetLocate`<br /><br /> [optional] **IRowsetRefresh**<br /><br /> [オプション] `IRowsetScroll`<br /><br /> [オプション] `IRowsetUpdate`<br /><br /> [オプション]**IRowsetView**<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [オプション]**IRowsetBookmark**|行セット オブジェクトは、データ ソースからデータを表します。 オブジェクトは、そのデータと任意の基本的な操作 (更新、fetch、移動、および他のユーザー) のデータのバインドを担当します。 常に、行セット オブジェクトを格納およびデータの操作があります。|  
|[コマンド](../../data/oledb/command-object-interfaces.md)([CCommand](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[mandatory] `IAccessor`<br /><br /> [mandatory] `IColumnsInfo`<br /><br /> [mandatory] `ICommand`<br /><br /> [必須]**ICommandProperties**<br /><br /> [mandatory] `ICommandText`<br /><br /> [mandatory] **IConvertType**<br /><br /> [optional] **IColumnsRowset**<br /><br /> [オプション]**ICommandPersist**<br /><br /> [オプション]**ICommandPrepare**<br /><br /> [オプション] `ICommandWithParameters`<br /><br /> [optional] **ISupportErrorInfo**<br /><br /> [オプション]**ICommandStream**|コマンド オブジェクトでは、クエリなどのデータの操作を処理します。 パラメーター化または非パラメーター化ステートメントに対応できます。<br /><br /> コマンド オブジェクトは、パラメーターと出力列のバインドを処理するもできます。 バインディングは、行セット内の列を取得する方法に関する情報を含む構造です。 序数、データ型、長さ、およびステータスなどの情報が含まれています。|  
|[トランザクション](../../data/oledb/transaction-object-interfaces.md)(省略可能)|[mandatory] **IConnectionPointContainer**<br /><br /> [必須]**ITransaction**<br /><br /> [optional] **ISupportErrorInfo**|トランザクション オブジェクトは、データ ソース内の作業のアトミック単位を定義し、それらの作業単位が相互に関連付ける方法を決定します。 OLE DB プロバイダー テンプレートはこのオブジェクトを直接サポートされません (つまり、作成する、独自のオブジェクト)。|  
  
 詳細については、次のトピックを参照してください。  
  
-   [プロパティ マップ](../../data/oledb/property-maps.md)  
  
-   [ユーザー レコード](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB インターフェイス](https://msdn.microsoft.com/en-us/library/ms709709.aspx)