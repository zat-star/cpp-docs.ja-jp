---
title: "レコードセット (ODBC) | Microsoft Docs"
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
  - "動的レコードセット"
  - "ダイナセット"
  - "前方スクロール専用レコードセット"
  - "ODBC レコードセット"
  - "ODBC レコードセット, CRecordset オブジェクト"
  - "レコードセット, レコードセットの概要"
  - "レコードセット, 作成"
  - "レコードセット, ダイナセット"
  - "レコードセット, スナップショット"
  - "スナップショット, ODBC レコードセット"
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 [CRecordset](../Topic/CRecordset%20Class.md) オブジェクトは、データ ソースから選択したレコードの集合を表します。  レコードは以下のいずれかで作成されます。  
  
-   テーブル  
  
-   クエリ  
  
-   1 つ以上のテーブルにアクセスするストアド プロシージャ  
  
 たとえば、データ ソースとして顧客一覧表があるとき、これに対するテーブル タイプのレコードセットの例としては、すべてのレコードから構成される "全顧客" レコードセットが考えられます。  クエリ型レコードセットの例としては、"Joe Smith 氏宛て全請求書" レコードから構成されるレコードセットが考えられます。ストアド プロシージャ \(定義済みクエリとも呼ばれます\) レコードセットの例としては、"未払いの全顧客" という条件に該当するレコードから構成されるレコードセットが考えられます。このレコードセットは、バックエンド データベースのストアド プロシージャを起動します。  1 つのレコードセットでは、同一のデータ ソースからの複数のテーブルを結合できますが、複数の異なるデータ ソースからのテーブルは結合できません。  
  
> [!NOTE]
>  ウィザードを使用してレコードセット クラスを派生させる方法については、「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」および「[&#91;データベース サポート&#93; \(MFC アプリケーション ウィザード\)](../../mfc/reference/database-support-mfc-application-wizard.md)」を参照してください。  
  
> [!NOTE]
>  一部の ODBC ドライバーは、データベースのビューをサポートしています。  この場合のビューとは、SQL の `CREATE VIEW` ステートメントによって作成されたクエリのことです。  ウィザードは現在のところビューをサポートしていませんが、自作コードでビューをサポートできます。  
  
##  <a name="_core_recordset_capabilities"></a> レコードセットの機能  
 どのレコードセット オブジェクトにも以下の機能が備わっています。  
  
-   データ ソースが読み取り専用でないときは、レコードセットに対して[更新可能](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、[追加可能](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、読み取り専用のいずれかを設定できます。  レコードセットが更新可能のときは、排他または共有の[ロック](../../data/odbc/recordset-locking-records-odbc.md) メソッドを選択できます。ただし、ドライバーがそのロックをサポートする場合に限ります。  データ ソースが読み取り専用のときは、レコードセットも読み取り専用になります。  
  
-   メンバー関数を呼び出して、選択されたレコード間を[スクロール](../Topic/Recordset:%20Scrolling%20\(ODBC\).md) \(移動\) できます。  
  
-   レコードを[フィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)すると、選択するレコードをさらに限定できます。  
  
-   1 つ以上の列を基準にしてレコードを[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md) \(昇順または降順\) できます。  
  
-   レコードセットを[パラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)し、実行時にレコードセットの選択を限定できます。  
  
##  <a name="_core_snapshots_and_dynasets"></a> スナップショットとダイナセット  
 レコードセットは、基本的に、[スナップショット](../Topic/Snapshot.md)と[ダイナセット](../../data/odbc/dynaset.md)の 2 種類に分類されます。  どちらのレコードセットも、基本クラスは `CRecordset` クラスです。  スナップショットとダイナセットは、レコードセットとしての基本特性は同一ですが、拡張部分が異なっています。  スナップショットは、データを静的に表示するので、レポートなど、ある瞬間のデータの状態が必要なときに使うことができます。  ダイナセットでは、レコードセットに対して "クエリの再実行" つまり "最新表示" を行わずに、ほかのユーザーによる更新をレコードセット内に表示できます。  スナップショットもダイナセットも、更新可能または読み取り専用に設定できます。  ほかのユーザーによって追加または削除されたレコードを反映するには、[CRecordset::Requery](../Topic/CRecordset::Requery.md) を呼び出します。  
  
 また、`CRecordset` では、他にも動的レコードセットと前方スクロール専用レコードセットという 2 種類のレコードセットも使用できます。  動的レコードセットは、ダイナセットに似ています。ただし、動的レコードセットでは、`CRecordset::Requery` を呼び出さずに、追加または削除されたレコードを反映できます。  このため、動的レコードセットは、DBMS での処理時間が一般的に長く、多くの ODBC ドライバーでもサポートされていません。  それに対して、前方スクロール専用レコードセットは、更新および後方スクロールを必要としないレコードセットに対して最も効率的なデータ アクセスを提供します。  たとえば、あるデータ ソースから別のデータ ソースにデータ転送を行うプログラムでは、逆方向へのスクロールが不要なため、このレコードセットを使用できます。  前方スクロール専用レコードセットを使うには、以下の両方の操作を行います。  
  
-   [Open](../Topic/CRecordset::Open.md) メンバー関数の `nOpenType` パラメーターとして、**CRecordset::forwardOnly** オプションを渡します。  
  
-   **Open** の `dwOptions` パラメーターとして **CRecordset::readOnly** を渡します。  
  
    > [!NOTE]
    >  ダイナセット用の ODBC ドライバーの必要条件については、「[ODBC の基礎](../../data/odbc/odbc-basics.md)」を参照してください。  Visual C\+\+ のこのバージョンに含まれている ODBC ドライバー一覧、および他のドライバーを取得する方法については、「[ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)」を参照してください。  
  
##  <a name="_core_your_recordsets"></a> レコードセットの作成  
 通常は、アクセスするテーブル、ビュー、またはストアド プロシージャごとに、`CRecordset` から派生したクラスを定義します。ただし、データベースが結合されている場合、つまり、1 つのレコードセットが複数のテーブルの列を表している場合は例外です。レコードセット クラスを派生させる場合には、ダイアログ データ エクスチェンジ \(DDX: Dialog Data Exchange\) 機構に似たレコード フィールド エクスチェンジ \(RFX: Record Field Exchange\) 機構またはバルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) 機構を使用します。  RFX や Bulk RFX を使用すると、データを簡単にデータ ソースからレコードセットに転送できます。RFX では、逆にレコードセットからデータ ソースにもデータを転送できます。  詳細については、「[レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)」と「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 レコードセット オブジェクトでは、選択されているすべてのレコードにアクセスできます。  `CRecordset` のメンバー関数 `MoveNext` や `MovePrev` などを使うと、選択されたレコードの間を移動できます。  ただし、レコードセット オブジェクトでは、選択されたレコードの 1 つである現在のレコードしか表示されません。  このレコードを現在のレコードと呼びます。テーブルの列、またはデータベース クエリによって得られたレコードの列に対応するレコードセット クラスのメンバー変数を宣言すると、現在のレコードの各フィールドにアクセスできます。  レコードセット データ メンバーについては、「[レコードセット : レコードセットの構造 \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)」を参照してください。  
  
 レコードセット オブジェクトの使い方の詳細については、次のトピックを参照してください。  各トピックは、機能別に分類されており、順番に参照できるようになっています。  
  
### レコードセットのオープン、読み込み、およびクローズの各機構に関するトピック  
  
-   [レコードセット : レコードセットの構造 \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [レコードセット : テーブルにアクセスするレコードセット クラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [レコードセット : レコードセットの生成と破棄 \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [レコードセット : スクロール \(ODBC\)](../Topic/Recordset:%20Scrolling%20\(ODBC\).md)  
  
-   [レコードセット : ブックマークと絶対位置 \(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [レコードセット : レコードのフィルター処理 \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [レコードセット : レコードの並べ替え \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### レコードセットの変更機構に関するトピック  
  
-   [レコードセット : レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [レコードセット : レコードのロック \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [レコードセット : クエリの再実行 \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### レコードセットの高度な利用法に関するトピック  
  
-   [レコードセット : 結合 \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)  
  
-   [レコードセット : 定義済みクエリを利用したクラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [レコードセット : データ列を動的に結び付ける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)  
  
-   [レコードセット : 大量のデータの処理 \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [レコードセット : 集計値の計算 \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### レコードセットの動作に関するトピック  
  
-   [レコードセット : レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)  
  
-   [レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)   
 [MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)