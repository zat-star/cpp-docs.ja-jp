---
title: "テクニカル ノート 45: MFC/データベースの Long Varchar/Varbinary 型のサポート | Microsoft Docs"
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
  - "vc.mfc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN045"
  - "Varbinary データ型"
  - "Varchar データ型"
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 45: MFC/データベースの Long Varchar/Varbinary 型のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、MFC データベース クラスを使用して ODBC **SQL\_LONGVARCHAR** と **SQL\_LONGVARBINARY** のデータ型を取得し送信する方法について説明します。  
  
## Long Varchar\/Varbinary サポートの概要  
 ODBC **SQL\_LONG\_VARCHAR** と **SQL\_LONGBINARY** のデータ型 \(長データ列と呼ばれます\) に次莫大な量のデータを保持できます。  このデータを処理する方法は 3 つあります。:  
  
-   `CString`\/`CByteArray`にバインドしてください。  
  
-   `CLongBinary`にバインドしてください。  
  
-   これはバインドしない、long データ値を、データベース クラスに関係なく、手動で取得しない、および送信しないでください。  
  
 3 種類のメソッドには、それぞれの長所と短所があります。  
  
 長データ列はクエリへのパラメーターではサポートされません。  これらは outputColumns でのみサポートされます。  
  
## CString\/CByteArray へ長データ列をバインドする。  
 利点:  
  
 この方法は理解しやすく使い慣れたクラスを使用します。  フレームワークは `DDX_Text`を `CString` に `CFormView` サポートします。  `CString` と `CByteArray` クラスの一般的な文字列またはコレクションの多くの機能があり、データ値を格納するために割り当てるメモリの量をローカルで制御できます。  フレームワークは **編集** または `AddNew` 関数呼び出しの間にデータ フィールドの古いコピーを保持し、フレームワークは自動的に、のデータへの変更を検出できます。  
  
> [!NOTE]
>  `CString` の文字データの動作、およびバイナリ データで動作の `CByteArray` 用に設計されているため、`CString`に文字データ \(**SQL\_LONGVARCHAR**\) を送信した、バイナリ データ \(**SQL\_LONGVARBINARY**\) ことが `CByteArray`にお勧めします。  
  
 `CString` と `CByteArray` の RFX 関数にデータ列の取得した値を格納するために割り当てるメモリの既定のサイズをオーバーライドする追加の引数があります。  次の関数宣言の nMaxLength 引数を確認する:  
  
```  
void AFXAPI RFX_Text(CFieldExchange* pFX, const char *szName,  
    CString& value, int nMaxLength = 255, int nColumnType =  
    SQL_VARCHAR);  
  
void AFXAPI RFX_Binary(CFieldExchange* pFX, const char *szName,   
    CByteArray& value,int nMaxLength = 255);  
```  
  
 `CString` または `CByteArray`に長データ列を取得すれば、返されたデータの最大サイズは、既定では 255 バイトです。  新機能には何も無視されます。  この場合、フレームワークは **AFX\_SQL\_ERROR\_DATA\_TRUNCATED**例外をスローします。  しかし、**MAXINT**まで大きな価値に明示的に nMaxLength、を向上させることができます。  
  
> [!NOTE]
>  MFC によって nMaxLength の値が **SQLBindColumn** 関数のローカル バッファーを設定するために使用されます。  これは、データのストレージのローカル バッファーでは、使用する ODBC ドライバーによって実際に返されるデータの量に影響しません。  `RFX_Text` と `RFX_Binary` は **SQLFetch** のみを使用してバックエンド データベースからデータを取得するための 1 種類の呼び出しを行います。  各 ODBC ドライバーの内容を単一のフェッチで返すことができるデータの量の別の制限があります。  この制限は **AFX\_SQL\_ERROR\_DATA\_TRUNCATED** 例外がスローされれば nMaxLength の設定値がよりも小さい場合があります。  この場合、すべてのデータを取得するために、に切り替えま `RFX_LongBinary` を `RFX_Text` または `RFX_Binary` の代わりに使用します。  
  
 ClassWizard は `CString`に **SQL\_LONGVARCHAR** か、の `CByteArray` に **SQL\_LONGVARBINARY** をバインドします。  ユーザーが長データ列を取得する 255 バイト以上割り当てる場合は、nMaxLength を明示的に値を提供できます。  
  
 SQL\_**VARCHAR** または SQL\_**VARBINARY**にバインドされる場合長データ列フィールドが作業を更新する `CString` または `CByteArray`に同じにバインドされる場合。  **編集**中は、データ値はデータ値への変更を検出し、列のダーティ、null 値を適切に設定するに **更新** が呼び出されると、キャッシュと比較されます。  
  
## CLongBinary に長データ列をバインドする。  
 長データ列がデータの **MAXINT** 超えるバイト数が含まれる可能性がある場合は、`CLongBinary`に取得することを検討してください。  
  
 利点:  
  
 これは、使用できるメモリの容量まで全体の長データ列、を取得します。  
  
 欠点:  
  
 データをメモリに保持されます。  この方法は、大量のデータにとって、非常に高くなっています。  フィールドが **更新** 操作に含まれていることを確認するにバインドされたデータのメンバーの `SetFieldDirty` を呼び出す必要があります。  
  
 `CLongBinary`に長データ列を取得すれば、データベース クラスは長データ列の合計サイズを確認し、それを保持するのに十分な大きさ `HGLOBAL` のメモリ セグメントを全体の値を割り当てます。  データベース クラスは、割り当てられた `HGLOBAL`に、全体のデータ値を取得します。  
  
 データ ソースが長データ列の予想サイズを返すことができない場合、フレームワークは **AFX\_SQL\_ERROR\_SQL\_NO\_TOTAL**例外をスローします。  `HGLOBAL` の割り当てに失敗すると、標準メモリ不足の例外がスローされます。  
  
 ClassWizard が自動的に `CLongBinary` に **SQL\_LONGVARCHAR** または **SQL\_LONGVARBINARY** をバインドします。  メンバー変数の追加ダイアログ変数の型として `CLongBinary` を選択します。  ClassWizard は `DoFieldExchange` の呼び出しと `RFX_LongBinary` の呼び出しを追加し、バインドされたフィールドの総数をインクリメントします。  
  
 `CLongBinary`の `m_hData` のメンバーの **::GlobalSize** を呼び出して、新しいデータを保持するには、割り当てられた `HGLOBAL` が十分に大きいことを長データ列値を更新するには、最初に確認します。  これが非常に小さかったら、`HGLOBAL` を解放し、適切なサイズ 1 を割り当てます。  新しいサイズを反映する設定された `m_dwDataLength`。  
  
 それ以外の場合は `m_dwDataLength` が、置換するデータのサイズを超えると、いずれかの自由 `HGLOBAL`を再割り当てすることも、それを割り当てられたままにします。  実際に `m_dwDataLength`で使用されているバイト数を示すことを確認します。  
  
## CLongBinary を更新することがどのように動作するかを示します。  
 3 番目のメソッドを選択すると `CLongBinary` を更新することがどのように動作すると、次のデータ ソースに長いデータ値を送信する方法の一例として利用する方法を理解する必要はありません。  
  
> [!NOTE]
>  更新に含める `CLongBinary` フィールドに対して明示的にフィールドの `SetFieldDirty` を呼び出す必要があります。  これを null に設定すると、フィールドに変更を加える場合は、`SetFieldDirty`を呼び出す必要があります。  また **FALSE**で 2 番目のパラメーターは、呼び出す必要が `SetFieldNull`値を持つとしてフィールドを設定する。  
  
 `CLongBinary` フィールドを更新した場合、データベース クラスは、ODBC を使っての **DATA\_AT\_EXEC** 機構 \(**SQLSetPos** の rgbValue 引数の ODBC のドキュメントを参照してください。  フレームワークが挿入を準備することも含む `HGLOBAL` を指すように更新ステートメント、データ列の *値* は、**SQL\_DATA\_AT\_EXEC**に設定した長さのインジケーターとして、`CLongBinary`*アドレス* の代わりに設定されます。  更新ステートメントをデータ ソースに送信すると、**SQLExecDirect** は **SQL\_NEED\_DATA**を返します。  この列のパラメーターの値が実際に `CLongBinary`のアドレスは、フレームワークに警告します。  フレームワークは、データの実際の長さを返すとドライバーが要求する小さいバッファーの **SQLGetData** を一度呼び出されます。  ドライバーがバイナリ ラージ オブジェクト \(BLOB\) の実際の長さを返した場合、MFC は BLOB をフェッチするために、必要に応じて任意の数の領域を再割り当てします。  データ ソースが返す場合、**SQL\_NO\_TOTAL**BLOB のサイズを決定できない場合は MFC を小さなブロックを作成します。  既定の初期のサイズは KB で、その後にブロックは二重サイズ\) ; たとえば、2 番目は、128K 番目です 256K などです。  初期サイズを設定できます。  
  
## バインドしません: \/SQLGetData の ODBC から直接データを取得する  
 このメソッドによって完全に長データ列によってデータベース クラスおよび処理を独自にバイパスします。  
  
 利点:  
  
 ディスクにデータを必要に応じてキャッシュしたり、取得するかデータの量を動的に決定します。  
  
 欠点:  
  
 フレームワークの **編集** または `AddNew` サポートを取得し、独自の基本機能を実行するコードを記述する必要があります \(**削除** は、列レベル操作ではないため、使用できます。  
  
 この場合、長データ列はレコードセットの選択リストにあるかつフレームワークによってにバインドされることはありません。  これを行うには、1 とおりの方法、独自の SQL ステートメントを `GetDefaultSQL`、または lpszSQL に引数として `CRecordset`**開く** 関数に指定し、RFX\_ の関数呼び出しと追加の列をバインドしないことです。  ODBC は自由なフィールドがバインドされたフィールドの右側に表示されるため、追加する非バインド列または列を必要とする選択リストの末尾に。  
  
> [!NOTE]
>  長データ列がフレームワークによってバインドされないので、への変更は `CRecordset::Update` の呼び出しと処理されません。  独自の SQL **INSERT** と **更新** のステートメントを作成し、送信する必要があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)