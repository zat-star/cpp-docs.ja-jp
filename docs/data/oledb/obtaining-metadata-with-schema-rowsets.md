---
title: "スキーマ行セットを使用したメタデータの取得 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メタデータ, 取得 (OLE DB テンプレートを)"
  - "OLE DB コンシューマー テンプレート, 取得 (プロバイダーのメタデータを)"
  - "スキーマ行セット, 取得 (OLE DB プロバイダーのメタデータを)"
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スキーマ行セットを使用したメタデータの取得
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダー、行セット、テーブル、列、またはその他のデータベース情報に関する情報を行セットを開かずに取得することが必要な場合があります。  データベース構造に関するデータはメタデータと呼ばれます。メタデータはさまざまな方法で取得できます。  1 つは、スキーマ行セットを使用する方法です。  
  
 OLE DB テンプレートは、スキーマ情報を取得するためのクラスのセットを提供します。これらのクラスは、定義済みのスキーマ行セットを作成します。「[スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)」にクラスの一覧を示しています。  
  
> [!NOTE]
>  OLAP を使用していて、行セットの一部がスキーマ行セット クラスでサポートされていない場合 \(列数が変数の場合など\) は、`CManualAccessor` または `CDynamicAccessor` の使用を検討する必要があります。  列をスクロールし、case ステートメントを使用して、各列で可能なデータ型を処理できます。  
  
## カタログ\/スキーマ モデル  
 ANSI SQL はデータ ストアのカタログ\/スキーマ モデルを定義しています。OLE DB はこのモデルを使用します。  このモデルでは、カタログ \(データベース\) にスキーマが含まれ、スキーマにテーブルが含まれます。  
  
-   **カタログ** カタログは、データベースの別の名前です。  これは、関連するスキーマのコレクションです。  特定のデータ ソースに属するカタログ \(データベース\) の一覧を表示するには、[CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md) を使用します。  多くのデータベースにはカタログが 1 つしかないため、メタデータは、単純にスキーマ情報と呼ばれることがあります。  
  
-   **スキーマ** スキーマは、特定のユーザーが所有している、または作成したデータベース オブジェクトのコレクションです。  特定のユーザーが所有しているスキーマの一覧を表示するには、[CSchemata](../../data/oledb/cschemata-cschematainfo.md) を使用します。  
  
     Microsoft SQL Server と ODBC 2.x の用語では、スキーマは所有者です。たとえば、dbo は一般的なスキーマ名です。  また、SQL Server では、テーブルのセットにメタデータを格納します。あるテーブルにはすべてのテーブルの一覧が含まれ、別のテーブルにはすべての列の一覧が含まれます。  Microsoft Access データベースにはスキーマに相当するものはありません。  
  
-   **テーブル** テーブルは、特定の順序で並べられた列のコレクションです。  特定のカタログ \(データベース\) で定義されているテーブルの一覧や、それらのテーブルに関する情報を表示するには、[CTables](../../data/oledb/ctables-ctableinfo.md) を使用します。  
  
## 制約  
 スキーマ情報を照会するときに、制約を使用して、目的の情報の種類を指定できます。  制約は、クエリのフィルターまたは修飾子として考えることができます。  たとえば、次のクエリについて考えます。  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 このクエリでは、`l_name` が制約です。  これは制約が 1 つしかない単純な例です。スキーマ行セット クラスは複数の制約をサポートします。  
  
 [スキーマ行セットの typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)は、すべての OLE DB スキーマ行セットをカプセル化するため、スキーマ行セットは他の行セットと同様に初期化して開くことでアクセスできます。  たとえば、typedef クラス [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) は次のように定義されます。  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../Topic/CRestrictions%20Class.md) クラスでは制約がサポートされています。  スキーマ行セットのインスタンスを作成した後で、[CRestrictions::Open](../../data/oledb/crestrictions-open.md) を呼び出します。  このメソッドは、指定された制約に基づいて結果セットを返します。  
  
 制約を指定するには、「[付録 B スキーマ行セット](http://go.microsoft.com/fwlink/?LinkId=64681)」を参照し、使用する行セットを検索してください。  たとえば、**CColumns** は [COLUMNS Rowset](http://go.microsoft.com/fwlink/?LinkId=64682) に対応します。COLUMNS Rowset のトピックでは、COLUMNS 行セットの制約列の一覧 \(TABLE\_CATALOG、TABLE\_SCHEMA、TABLE\_NAME、COLUMN\_NAME\) を示しています。  制約を指定するときは、この順序に従う必要があります。  
  
 このため、たとえばテーブル名で制約する場合は、TABLE\_NAME が 3 番目の制約列であることを確認し、**Open** を呼び出して、3 番目の制約パラメーターとして目的のテーブル名を指定します。これを次の例に示します。  
  
#### スキーマ行セットを使用するには  
  
1.  Atldbsch.h ヘッダー ファイルをインクルードする必要があります \(コンシューマー サポートでも Atldbcli.h が必要です\)。  
  
2.  コンシューマーまたはドキュメントのヘッダー ファイル内のスキーマ行セット オブジェクトをインスタンス化します。  テーブル情報が必要な場合は **CTables** オブジェクトを宣言します。列情報が必要な場合は **CColumns** オブジェクトを宣言します。  authors テーブルの列を取得する方法の例を次に示します。  
  
    ```  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  情報をフェッチするには、スキーマ行セット オブジェクトの適切なデータ メンバーにアクセスします。たとえば、`ColumnSchemaRowset.m_szColumnName` にアクセスします。  これは COLUMN\_NAME に対応します。  各データ メンバーが OLE DB のどの列に対応するかについては、「[CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)」を参照してください。  
  
 OLE DB テンプレートに用意されているスキーマ行セット typedef クラスのリファレンスについては、「[スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)」を参照してください。  
  
 OLE DB スキーマ行セット \(制限列を含む\) の詳細については、『OLE DB プログラマーズ リファレンス』の「[付録 B スキーマ行セット](http://go.microsoft.com/fwlink/?LinkId=64681)」を参照してください。  
  
 スキーマ行セット クラスを使用する方法の複雑な例については、[CatDB](http://msdn.microsoft.com/ja-jp/003d516b-2bf6-444e-8be5-4ebaa0b66046) と [DBViewer](http://msdn.microsoft.com/ja-jp/07620f99-c347-4d09-9ebc-2459e8049832) のサンプルを参照してください。  
  
 プロバイダーでのスキーマ行セットのサポートについては、「[スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)