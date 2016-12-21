---
title: "OLE DB コンシューマー テンプレート リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc.templates.ole"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB コンシューマー テンプレート, クラス"
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB コンシューマー テンプレート リファレンス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB コンシューマー テンプレートは次のクラスが含まれています。  リファレンスでは、[OLE DB コンシューマー テンプレート用マクロ](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)のトピックが含まれています。  
  
## セッション クラス  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 データ ソースの接続を管理します。  これは、必要なオブジェクト \(データ ソースとセッション\)、それをする必要がある作業をカプセル化するので、クライアントを作成するための便利なクラスは、データ ソースに接続できます。  
  
 [CDataSource](../Topic/CDataSource%20Class.md)  
 、データ ソースへの接続を表すことはプロバイダーを通じて OLE DB のデータ ソース オブジェクトに対応します。  一つ以上のデータベース セッションは、`CSession` オブジェクトによって表される一つの接続で個別にホストできます。  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 使用できるデータ ソースについての行セットの情報を取得する OLE DB 列挙子オブジェクトに対応します。  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 列挙子の行セットからデータにアクセスするために `CEnumerator` に使用されます。  この行セットは現在の列挙子で表示されるデータ ソースと列挙子で構成されます。  
  
 [CSession](../../data/oledb/csession-class.md)  
 一つのデータベース アクセス セッションを表します。  一つ以上のセッションを `CDataSource` の各オブジェクトと関連付けることができます。  
  
## アクセサー クラス  
 [CAccessor](../Topic/CAccessor%20Class.md)  
 データ ソースに静的にバインドされるレコードに使用されます。  データ ソースの構造を理解していると、このアクセサー クラスを使用します。  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 すべてのアクセサー クラスの基本クラスです。  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 実行時に作成できる行セットの列情報に基づいてアクセサーです。  データ ソースの構造がわからない場合、データを取得するには、このクラスを使用します。  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 コマンドの種類が不明な場合に使用できるアクセサーです。  `ICommandWithParameters` インターフェイスを呼び出すことでパラメーター情報を取得するプロバイダーがインターフェイスをサポートします。  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 データベースの基になる構造が不明な場合にデータ ソースにアクセスできます。  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 データを要求します。ANSI 文字列データとしてデータ ストアからアクセスする `CDynamicStringAccessor` が、このクラスに似ています。  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 データを要求します。UNICODE の文字列データとしてデータ ストアからアクセスする `CDynamicStringAccessor` が、このクラスに似ています。  
  
 [CManualAccessor](../Topic/CManualAccessor%20Class.md)  
 列とコマンド パラメーターの両方を処理するメソッドのアクセサーです。  このクラスを使用すると、プロバイダーが型を変換できる限りデータ型を使用できます。  
  
 [CNoAccessor](../Topic/CNoAccessor%20Class.md)  
 クラスのパラメーターまたは出力列をサポートできないようにするには、テンプレート引数として使用できます。  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 すべてのデータを変換します。XML 形式 \(番号付き\) データとしてデータ ストアからアクセスする `CDynamicStringAccessor` が、このクラスに似ています。  
  
## 行セット クラス  
 [CAccessorRowset](../Topic/CAccessorRowset%20Class.md)  
 行セットと関連のアクセサーをカプセル化します。  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 配列の構文を使用して、行セットの要素にアクセスするために使用します。  
  
 [CBulkRowset](../Topic/CBulkRowset%20Class.md)  
 一つの呼び出しで複数の行ハンドルの取得によって大量の行をフェッチし、処理するために使用します。  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 コマンドと行セットを返すテンプレート引数として使用できます。  
  
 [CRestrictions](../Topic/CRestrictions%20Class.md)  
 スキーマ行セットに制限を指定するために使用します。  
  
 [CRowset](../Topic/CRowset%20Class.md)  
 行セット データを処理し、設定および取得するために使用します。  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 行セットではなく `ISequentialStream` ;オブジェクトを返します。その後、XML 形式のデータを取得するために **読み取り** のメソッドを使用します。\(SQL Server 2000 は書式設定を行う; この機能は、SQL Server 2000 のみを使用することに注意してください\)。  
  
 [IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md)  
 `IRowsetNotify` のメソッド `OnFieldChange`、`OnRowChange`と `OnRowsetChange`の空の関数を `IRowsetNotify`にダミーの実装を提供します。  
  
 [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)  
  
 OLE DB テンプレートは、OLE DB スキーマ行セットに対応する一連のクラスが用意されています。  
  
## コマンド クラス  
 [CCommand](../../data/oledb/ccommand-class.md)  
 パラメーター ベースの OLE DB コマンドを設定し、実行するために使用します。  だけ単純な行セットを開くには、`CTable` を代わりに使用します。  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 複数の結果セットを処理するコマンドが必要なときに `CCommand` のテンプレートのテンプレート引数として使用されます。  
  
 [CNoAccessor](../Topic/CNoAccessor%20Class.md)  
 `CCommand`、および `CTable`などのアクセサー クラスの引数を受け取るテンプレート クラスのテンプレート引数として使用されます。  クラスのパラメーターまたは出力列をサポートしない場合 `CNoAccessor` を使用します。  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 一つの行セットを処理するコマンドが必要なときに `CCommand` のテンプレートのテンプレート引数として使用されます。  `CNoMultipleResults` は、テンプレートの引数の既定値です。  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 コマンド クラスまたはテーブルは行セットを返す `CCommand` または `CTable` のテンプレート引数として使用されます。  
  
 [CTable](../../data/oledb/ctable-class.md)  
 パラメーターなしの単純な行セットにアクセスするために使用します。  
  
## プロパティ クラス  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 コンシューマーは、プロパティ情報を表示するプロパティの ID の配列を渡すために使用します。  プロパティは、1 種類のプロパティ セットに属しています。  
  
 [CDBPropSet](../Topic/CDBPropSet%20Class.md)  
 プロバイダーのプロパティの設定に使用します。  
  
## ブックマーク クラス  
 [CBookmark クラス](../../data/oledb/cbookmark-class.md)  
 行セットのデータへのアクセスのためのインデックスとして使用されます。  
  
## エラー クラス  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 OLE DB のエラー情報を取得するために使用します。  
  
## 参照  
 [OLE DB プロバイダー テンプレート リファレンス](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB テンプレート](../Topic/OLE%20DB%20Templates.md)