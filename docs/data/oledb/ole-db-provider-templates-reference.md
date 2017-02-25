---
title: "OLE DB プロバイダー テンプレート リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー テンプレート"
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OLE DB プロバイダー テンプレート リファレンス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB プロバイダー テンプレートのクラスおよびインターフェイスには、次のカテゴリに分類できます。  リファレンスでは、[OLE DB プロバイダー テンプレートののマクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)に関する情報が含まれます。  
  
 クラスは、次の名前付け規則を使用して: パターン **IWidgetImpl** というクラスは **IWidget**インターフェイスの実装を提供します。  
  
## セッション クラス  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 データ ソース オブジェクトから新しいセッションが作成され、新規作成されたセッションの要求されたインターフェイスを返します。  データ ソース オブジェクトの必須インターフェイス。  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 静的関数は、プロパティ セット マップによって定義された呼び出してセッション プロパティを実装します。  プロパティ セット マップには、セッション クラスで指定する必要があります。  セッションの必須インターフェイス。  
  
## 行セット クラス  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 多くのインターフェイス実装の多重継承を必要とせずに標準 OLE DB の行セットの実装を提供します。  、実装を提供する必要があるのは **実行**メソッドです。  
  
 [CSimpleRow](../Topic/CSimpleRow%20Class.md)  
 `IRowsetImpl` クラスで使用される行ハンドルの既定の実装を提供します。  行ハンドルは論理的に結果行の一意のタグです。  `IRowsetImpl` は `IRowsetImpl::GetNextRows`で要求されるすべての行の新しい `CSimpleRow` を作成します。  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB は、プロバイダーが **HACCESSOR**を実装するように必要があります。**DBBINDING** 構造体の配列にタグです。  **HACCESSOR**s を提供します **BindType** 構造体のアドレスです。  行セット オブジェクトとコマンドで必須。  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 プロバイダーの列マップによって定義された静的関数へのデリゲート。  行セット オブジェクトとコマンドの必須インターフェイス。  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 コマンドと行セットの型変換の可用性の情報を提供します。  コマンドと行セットとインデックスの行セットで必須。  OLE DB に用意されている変換オブジェクトへのデリゲートによって **IConvertType** インターフェイスを実装します。  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 **IDBSchemaRowset** インターフェイスとテンプレート化されます作成関数 `CreateSchemaRowset`を実装します。  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 単一のベース テーブルまたはインデックスのすべての行を含む行セットを開き、返します。  セッション オブジェクトの必須インターフェイス。  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 既存の行内の列の値を更新し、行を削除し、新しい行の挿入を有効にする [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) の OLE DB インターフェイスを実装します。  
  
 [IRowsetCreatorImpl](../Topic/IRowsetCreatorImpl%20Class.md)  
 このクラスは [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) から継承し、[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)をオーバーライドします。  `IRowsetCreatorImpl` は `IObjectWithSite` と同じ機能を実行しますが、OLE DB のプロパティ **DBPROPCANSCROLLBACKWARDS** と **DBPROPCANFETCHBACKWARDS**を有効にします。  
  
 [IRowsetIdentityImpl](../Topic/IRowsetIdentityImpl%20Class.md)  
 2 行のデータが同一かどうかを比較する **IRowsetIdentity** インターフェイスを実装します。  
  
 [IRowsetImpl](../Topic/IRowsetImpl%20Class.md)  
 基本行セット インターフェイスである `IRowset` インターフェイスの実装を提供します。  
  
 [IRowsetInfoImpl](../Topic/IRowsetInfoImpl%20Class.md)  
 定義されたコマンド クラスのプロパティ セット マップを使用して行セット プロパティを実装します。  行セットの必須インターフェイス。  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 行セットの任意の行をフェッチする OLE DB の [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) インターフェイスを実装します。  行セットの OLE DB のブックマークをサポートするには、このクラスから行セットを継承させます。  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 実装は、行セットの内容変更のコネクション ポイント **IID\_IRowsetNotify** のリスナーに指示する関数をブロードキャストしました。  通知を処理するコンシューマーは [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) を実装し、そのコネクション ポイントに登録します。  
  
 [IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md)  
 コンシューマーが [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) に行われたデータ ソースへの変更の送信を遅らせ、送信する前に変更を元に戻すことができる OLE DB の [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) インターフェイスを実装します。  
  
## コマンド クラス  
 [ICommandImpl](../Topic/ICommandImpl%20Class.md)  
 `ICommand` インターフェイスの実装を提供します。  このインターフェイスは表示されませんが、**ICommandTextImpl**によって処理されます。  コマンド オブジェクトの必須インターフェイス。  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 この **ICommandProperties** インターフェイスの実装は `BEGIN_PROPSET_MAP` マクロによって定義された静的関数によって提供されます。  コマンドでは、必ず指定します。  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 設定、コマンド テキスト ストアを返します。  コマンドでは、必ず指定します。  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 セッション オブジェクトから新しいコマンドを作成して、新しく作成されたコマンドの要求されたインターフェイスを返します。  セッション オブジェクトの省略可能なインターフェイス。  
  
 他のコマンド クラスは、前の行セット クラス"で説明されている `IColumnsInfoImpl` と `IAccessorImpl`です。  
  
## データ ソース クラス  
 [IDBInitializeImpl](../Topic/IDBInitializeImpl%20Class.md)  
 コンシューマーと接続を作成および削除する。  データ ソース オブジェクトの列挙子の必須インターフェイスと省略可能なインターフェイス。  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` を列挙子データ ソース オブジェクトと省略可能なインターフェイスの必須インターフェイスです。  ただし、列挙子が **IDBInitialize**を公開する場合は、`IDBProperties` \(データ ソースのプロパティ\) を公開する必要があります。  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 データ ソース オブジェクトへのインターフェイス ポインターを取得します。  セッションの必須インターフェイス。  
  
## そのほかのクラス  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 さまざまな OLE DB インターフェイスのプロパティのプロパティを実装します \(たとえば、`IDBProperties`、**ISessionProperties**と `IRowsetInfo`\)。  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 レコードを追加し、データ メンバーのレコードを取得する OLE DB の [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) インターフェイスを実装します。  
  
## 参照  
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB テンプレート](../Topic/OLE%20DB%20Templates.md)