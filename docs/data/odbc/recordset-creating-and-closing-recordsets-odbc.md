---
title: "レコードセット: レコードセットの生成と破棄 (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC レコードセット, 閉じる"
  - "ODBC レコードセット, 作成"
  - "ODBC レコードセット, 開く"
  - "レコードセット, 閉じる"
  - "レコードセット, 作成"
  - "レコードセット, 開く"
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコードセット: レコードセットの生成と破棄 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコードセットを使用するには、まずレコードセット オブジェクトを構築します。次に、その **Open** メンバー関数を呼び出し、レコードセットのクエリを実行してレコードを選択します。  使用済みのレコードセット オブジェクトは閉じて破棄します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコードセットの実行時生成](#_core_creating_recordsets_at_run_time)  
  
-   [レコードセット オプションの設定](#_core_setting_recordset_options)  
  
-   [レコードセットを閉じる](#_core_closing_a_recordset)  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> レコードセットの実行時生成  
 レコードセット オブジェクトを作成するには、通常アプリケーション固有のレコードセット クラスを事前に定義します。  この手順の詳細については、「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照してください。  
  
 データ ソースからレコードを選択するときは、ダイナセット オブジェクトまたはスナップショット オブジェクトを開きます。  ダイナセットとスナップショットのどちらを使うかは、アプリケーションでデータをどのように扱うか、および使っている ODBC ドライバーのサポートによって異なります。  詳細については、「[ダイナセット](../../data/odbc/dynaset.md)」および「[スナップショット](../Topic/Snapshot.md)」を参照してください。  
  
#### レコードセットを開くには  
  
1.  `CRecordset` の派生クラスのオブジェクトを構築します。  
  
     オブジェクトは、ヒープ上または関数スタック フレーム上に構築します。  
  
2.  必要に応じてレコードセットの既定の動作を変更します。  詳細については、「[レコードセット オプションの設定](#_core_setting_recordset_options)」を参照してください。  
  
3.  オブジェクトの [Open](../Topic/CRecordset::Open.md) メンバー関数を呼び出します。  
  
 コンストラクターでは、`CDatabase` オブジェクトへのポインターを渡すか、**NULL** を渡して一時データベース オブジェクトを使用します。このオブジェクトは、[GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md) メンバー関数が返した接続文字列に基づき、フレームワークによって構築され、開かれます。  `CDatabase` オブジェクトは、既にデータ ソースに接続されている場合があります。  
  
 **Open** が呼び出されると SQL が発行され、レコードがデータ ソースから選択されます。  レコードが選択されると、先頭のレコードが現在のレコードになります。  現在のレコードの各フィールドの値は、レコードセット オブジェクトのフィールド データ メンバーに格納されます。  レコードが選択されたときは、メンバー関数 `IsBOF` および `IsEOF` が 0 を返します。  
  
 [Open](../Topic/CRecordset::Open.md) を呼び出すときは、次の手順に従ってください。  
  
-   レコードセットがダイナセットとスナップショットのどちらであるかを指定します。  既定では、スナップショットとして開かれます。  前方スクロール専用レコードセットを指定することもできます。このレコードセットでは、レコードを 1 つずつ順方向にのみスクロールします。  
  
     既定では、レコードセットは `CRecordset` クラスのデータ メンバー **m\_nDefaultType** を使います。  ウィザードによって、**m\_nDefaultType** を初期化するコードが生成されます。**m\_nDefaultType** は、ウィザードで選択したレコードセットの型に初期化されます。  この既定の型を使わずに、開発者自身の定義によるレコードセットの型を使うこともできます。  
  
-   レコードセットが構築した既定の SQL **SELECT** ステートメントを置き換える文字列を指定します。  
  
-   レコードセットを読み取り専用または追加可能として指定します。  既定ではあらゆる更新が可能ですが、上書き禁止または追加のみ可能を指定できます。  
  
 次に、アプリケーションで定義されている `CStudentSet` クラスに対して、上書き禁止のスナップショット オブジェクトを開く例を示します。  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 **Open** を呼び出した後、オブジェクトのメンバー関数とデータ メンバーを使ってレコードを処理します。  場合によっては、クエリの再実行つまり更新を実行し、Open を呼び出した後にデータ ソースに加えられた変更を反映させる必要があります。  詳細については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)」を参照してください。  
  
> [!TIP]
>  プログラム開発時に使用した接続文字列は、ユーザーが実際に使用する接続文字列と異なることがあります。  この点に関してアプリケーションを汎用化する方法については、「[データ ソース : 接続 \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)」を参照してください。  
  
##  <a name="_core_setting_recordset_options"></a> レコードセット オプションの設定  
 レコードセット オブジェクトの構築後、**Open** を呼び出してレコードを選択する前に、レコードセットの動作を制御するオプションを設定できます。  以下のオプションを指定できます。  
  
-   レコード選択条件を指定する[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)の指定。  
  
-   レコードの[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)順序の指定。  
  
-   レコード選択用の[パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)の設定。実行時のユーザー入力または計算結果に応じてレコードを選択できます。  
  
 条件が満たされれば、次のオプションも指定できます。  
  
-   更新可能なレコードセットでロックをサポートしている場合は、更新用の[ロック](../../data/odbc/recordset-locking-records-odbc.md) メソッドを指定できます。  
  
> [!NOTE]
>  オプションの設定をレコード選択に反映させるには、**Open** メンバー関数を呼び出す前に設定する必要があります。  
  
##  <a name="_core_closing_a_recordset"></a> レコードセットを閉じる  
 使用済みのレコードセットは破棄し、メモリを解放する必要があります。  
  
#### レコードセットを閉じるには  
  
1.  レコードセットの [Close](../Topic/CRecordset::Close.md) メンバー関数を呼び出します。  
  
2.  レコードセット オブジェクトを破棄します。  
  
     関数のスタック フレーム上にオブジェクトを宣言したときは、スコープから出たときに自動的に破棄されます。  そうでない場合は **delete** 演算子を使います。  
  
 **Close** は、レコードセットの **HSTMT** ハンドルを解放します。  C\+\+ オブジェクトは破棄しません。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: スクロール \(ODBC\)](../Topic/Recordset:%20Scrolling%20\(ODBC\).md)   
 [レコードセット: レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)