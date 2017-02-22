---
title: "レコード フィールド エクスチェンジ: RFX の動作のしくみ | Microsoft Docs"
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
  - "データ バインディング [C++], DFX"
  - "ODBC [C++], RFX"
  - "レコード編集 [C++], 使用 (RFX を)"
  - "RFX (ODBC) [C++], バインド (フィールドとパラメーターを)"
  - "RFX (ODBC) [C++], 更新 (レコードセットのレコードを)"
  - "スクロール [C++]"
  - "スクロール [C++], RFX"
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード フィールド エクスチェンジ: RFX の動作のしくみ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、RFX 処理について説明します。  このトピックは上級者向けのトピックです。以下の内容について説明します。  
  
-   [RFX とレコードセット](#_core_rfx_and_the_recordset)  
  
-   [RFX 処理の内容](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生クラスを対象にしています。  バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) が実装されています。  Bulk RFX と RFX は似ています。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX とレコードセット  
 レコードセット オブジェクトのフィールド データ メンバーは、全体で 1 つの編集バッファーを設け、そこに 1 つのレコードの選択されている列を格納します。  レコードセットを初めて開き、先頭のレコードを読み込むときに、選択された各列が該当するフィールド データ メンバーのアドレスに結び付けられます。  レコードセットによってレコードが更新されると、RFX は、ODBC API 関数を呼び出して、SQL の **UPDATE** ステートメントまたは **INSERT** ステートメントをドライバーに送出します。  RFX は、フィールド データ メンバーの情報に基づき、書き込む列を決定します。  
  
 フレームワークは、特定のタイミングでエディット バッファーをバックアップして、必要に応じて内容を復元できるように保存します。  RFX は、新しいレコードを追加する前および既存のレコードを編集する前に、エディット バッファーをバックアップします。  エディット バッファーにバックアップした内容を復元するのは、`AddNew` の後に **Update** を呼び出すときなどです。  更新したエディット バッファーを捨てたくないときに、**Update** を呼び出す前に他のレコードに移動するなどして、エディット バッファーの変更内容を破棄した場合は、エディット バッファーは復元されません。  
  
 データ ソースとレコードセット フィールド データ メンバー間のデータ交換のほか、RFX はパラメーターの管理も行います。  レコードセットを開くと、すべてのパラメーター データ メンバーは、`CRecordset::Open` で構築される SQL ステートメントの "?" プレースホルダーの順に結び付けられます。  詳細については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
 レコードセット クラスのオーバーライド関数 `DoFieldExchange` は、データの双方向転送におけるあらゆる処理を行います。  RFX は、ダイアログ データ エクスチェンジ \(DDX: Dialog Data Exchange\) と同じように、レコードセット クラスのデータ メンバーに関する情報を必要とします。  ウィザードは、指定されたフィールド データ メンバー名とデータ型に基づいて、`DoFieldExchange` のレコードセット固有の実装を作成して、必要な情報を提供します。  
  
##  <a name="_core_the_record_field_exchange_process"></a> レコード フィールド エクスチェンジの処理  
 ここでは、レコードセット オブジェクトを開くとき、およびレコードを作成、更新、削除するときに発生する RFX イベントの流れについて説明します。  レコードセットの **Move** コマンドを処理する場合および更新処理を行う場合の RFX の動作については、表「[レコードセットを開くときの RFX 処理の流れ](#_core_sequence_of_rfx_operations_during_recordset_open)」および「[スクロールを行うときの RFX 処理の流れ](#_core_sequence_of_rfx_operations_during_scrolling)」を参照してください。  これらの処理では、さまざまな操作を行うために [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) が呼び出されます。  必要な操作は、[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) オブジェクトのデータ メンバー **m\_nOperation** によって指定されます。  以下の説明を読む前に、基礎知識として、「[レコードセット : レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)」と「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX : 列とパラメーターの初期設定  
 プログラムからレコードセット オブジェクトのメンバー関数 [Open](../Topic/CRecordset::Open.md) を呼び出すと、以下の RFX の処理がこの順に行われます。  
  
-   パラメーター データ メンバーを持つレコードセットでは、フレームワークは、`DoFieldExchange` を呼び出して、パラメーターをレコードセットの SQL ステートメントの文字列パラメーター プレースホルダーに結び付けます。  データ型に応じたパラメーター値が、**SELECT** ステートメントのプレースホルダーごとに書き込まれます。  この処理は、SQL ステートメントの "作成" 後、実際に実行される前に行われます。  SQL ステートメントの作成については、『ODBC Programmer's Reference』の **::SQLPrepare** 関数に関するトピックを参照してください。  
  
-   フレームワークは、`DoFieldExchange` をもう 1 回呼び出して、選択された列の値を該当するレコードセットのフィールド データ メンバーに結び付けます。  これにより、レコードセット オブジェクトが、最初のレコードの列を格納したエディット バッファーとして設定されます。  
  
-   レコードセットが SQL ステートメントを実行し、データ ソースが最初のレコードを選択します。  レコードの列がレコードセットのフィールド データ メンバーに読み込まれます。  
  
 次の表に、レコードセットを開くときの RFX 処理の流れを示します。  
  
### レコードセットを開くときの RFX 処理の流れ  
  
|プログラマの操作|DoFieldExchange の処理|Database\/SQL の動作|  
|--------------|-------------------------|-----------------------|  
|1.  レコードセットを開きます。|||  
||2.  SQL ステートメントを作成します。||  
|||3.  SQL を送出します。|  
||4.  パラメーター データ メンバーをバインドします。||  
||5.  フィールド データ メンバーを列にバインドします。||  
|||6.  ODBC によって移動、データ転送が行われます。|  
||7.  データを C\+\+ で扱える形式に変換します。||  
  
 レコードセットは、ODBC のプリペアド エクゼキューションを使用して、同一の SQL ステートメントによるクエリの再実行を高速化します。  プリペアド エクゼキューションの詳細については、MSDN ライブラリの『ODBC Programmer's Reference』を参照してください。  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX : スクロール  
 レコードをスクロールすると、フレームワークは、`DoFieldExchange` を呼び出して、フィールド データ メンバーの値を新しいレコードの内容に置き換えます。  
  
 次の表に、レコードをスクロールするときの RFX の処理の流れを示します。  
  
### スクロールを行うときの RFX 処理の流れ  
  
|プログラマの操作|DoFieldExchange の処理|Database\/SQL の動作|  
|--------------|-------------------------|-----------------------|  
|1.  `MoveNext` または他の Move 関数を呼び出します。|||  
|||2.  ODBC によって移動、データ転送が行われます。|  
||3.  データを C\+\+ で扱える形式に変換します。||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX : 新規レコードの作成と既存レコードの編集  
 新しいレコードを追加すると、レコードセットがエディット バッファーとして動作して、新しいレコードの内容を構築します。  レコードの追加時と同じように、レコードの編集時にも、レコードセットのフィールド データ メンバーの値が変更されます。  RFX から見ると、これらの処理は次のような流れになります。  
  
1.  プログラムからレコードセットのメンバー関数 [AddNew](../Topic/CRecordset::AddNew.md) または [Edit](../Topic/CRecordset::Edit.md) を呼び出すと、RFX は、現在のエディット バッファーの内容を後で復元できるように格納します。  
  
2.  `AddNew` や **Edit** は、エディット バッファーのフィールドを操作して、RFX がフィールド データ メンバーの変更を検出できるようにします。  
  
     新規作成したレコードには比較対象となる以前の値がないので、`AddNew` は、各フィールド データ メンバーの値を **PSEUDO\_NULL** 値に設定します。  後で **Update** が呼び出されると、RFX は、各データ メンバーの値を **PSEUDO\_NULL** と比較します。  異なる場合は、そのデータ メンバーに値が代入されています。**PSEUDO\_NULL** は、実際に Null 値を格納しているレコード列の値や C\+\+ の **NULL** 値とは異なります。  
  
     `AddNew` の **Update** 呼び出しとは異なり、**Edit** の **Update** 呼び出しは、更新後の値を **PSEUDO\_NULL** ではなく、以前保存した値と比較します。  Edit と `AddNew` の違いは、AddNew には比較対象になる過去の値が保存されていないという点です。  
  
3.  編集するフィールド データ メンバー、または新しいレコード用に値を設定するフィールド データ メンバーの値は、直接設定します。  この場合、`SetFieldNull` を呼び出すことができます。  
  
4.  [Update](../Topic/CRecordset::Update.md) を呼び出すと、フィールド データ メンバーが変更されているかどうかが確認されます \(手順 2 を参照\)。詳細については、表「[スクロールを行うときの RFX 処理の流れ](#_core_sequence_of_rfx_operations_during_scrolling)」を参照してください。  変更がないときは、**Update** は 0 を返します。  フィールド データ メンバーが変更されているときは、**Update** は、変更されたすべてのフィールドの値を更新する SQL **INSERT** ステートメントを作成し、実行します。  
  
5.  `AddNew` の場合、**Update** は、`AddNew` を呼び出す前に現在のレコードに保存されていた値を復元することによって処理を完了させます。  **Edit** の場合は、新しく編集した結果が残ります。  
  
 次の表に、レコードを新規作成または既存レコードを編集したときの RFX 処理の流れを示します。  
  
### AddNew および Edit を実行したときの RFX 処理の流れ  
  
|プログラマの操作|DoFieldExchange の処理|Database\/SQL の動作|  
|--------------|-------------------------|-----------------------|  
|1.  `AddNew` または **Edit** を呼び出します。|||  
||2.  エディット バッファーをバックアップします。||  
||3.  `AddNew` の場合は、フィールド データ メンバーを "変更なし \(クリーン\)" で Null としてマークします。||  
|4.  レコードセットのフィールド データ メンバーに値を代入します。|||  
|5.  **Update** を呼び出します。|||  
||6.  フィールドが変更されているかどうかをチェックします。||  
||7.  SQL **INSERT** ステートメント \(`AddNew` の場合\) または **UPDATE** ステートメント \(**Edit** の場合\) を作成します。||  
|||8.  SQL を送出します。|  
||9.  `AddNew` では、エディット バッファーの内容をバックアップしておいた値に戻します。  **Edit** では、バックアップを消去します。||  
  
### RFX : レコードの削除  
 レコードを削除すると、RFX は、すべてのフィールドに **NULL** を代入して、削除されたことを記録します。実際の削除処理は、プログラム中で行う必要があります。  削除については、これ以外の RFX 処理は必要ありません。  
  
## 参照  
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [マクロ、グローバル関数、およびグローバル変数](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)