---
title: "SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC) | Microsoft Docs"
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
  - "カスタマイズ (SQL ステートメントを)"
  - "ODBC レコードセット, SQL ステートメント"
  - "オーバーライド, SQL ステートメント"
  - "レコードセット, SQL ステートメント"
  - "SQL ステートメント, カスタマイズ"
  - "SQL ステートメント, レコードセット"
  - "SQL, 開く (レコードセットを)"
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、次の内容について説明します。  
  
-   SQL ステートメントの作成  
  
-   SQL ステートメントのオーバーライド  
  
> [!NOTE]
>  この内容は、MFC ODBC クラスに該当します。  MFC DAO クラスを使用している場合は、DAO ヘルプの「Comparison of Microsoft Jet Database Engine SQL and ANSI SQL」を参照してください。  
  
## SQL ステートメントの作成  
 レコードセットがレコードを選択するときは、まず SQL ステートメント **SELECT** が作成されます。  ウィザードを使ってレコードセット クラスを宣言すると、ウィザードはメンバー関数 `GetDefaultSQL` をオーバーライドします。次に、この関数の例を示します \(この例ではレコードセット クラス名は `CAuthors` です\)。  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 既定では、この関数は、ウィザードで指定したテーブルの名前を返します。  この例では、テーブル名は "AUTHORS" です。次に、レコードセットのメンバー関数 **Open** を呼び出すと、次のような **SELECT** ステートメントが作成されます。  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 `table-name` は、`GetDefaultSQL` を呼び出して取得します。`rfx-field-list` は、`DoFieldExchange` で RFX 関数を呼び出して取得します。  実行時に動的にステートメントをオーバーライドしない限り、**SELECT** ステートメントはこのように作成されます。パラメーターやフィルターを設定すると、このステートメントの既定の動作を変更できます。  
  
> [!NOTE]
>  列名が空白文字を含む \(またはその可能性がある\) 場合は、列名を角かっこ \(\[ \]\) で囲む必要があります。  たとえば、列名 "First Name" は "\[First Name\]" のように指定します。  
  
 **SELECT** ステートメントの既定の動作をオーバーライドするには、**Open** を呼び出すときに完全な **SELECT** ステートメントを表す文字列を渡します。  レコードセットは、既定のステートメントの代わりに、この文字列を使用します。  ステートメントに **WHERE** 句があるときは、**m\_strFilter** でフィルターを指定しないでください \(フィルター ステートメントの重複防止\)。  また、**ORDER BY** 句があるときは、`m_strSort` で並べ替えを指定しないでください \(並べ替えステートメントの重複防止\)。  
  
> [!NOTE]
>  SQL ステートメント内のフィルターなどでリテラル文字列を使用する場合は、文字列全体を引用符で囲むことが必要な場合があります。引用符とは、DBMS 固有のリテラル プリフィックスおよびリテラル サフィックスとして指定されている区切り記号のことです。  
  
 DBMS の種類によっては、外部結合などの操作を行うときに専用の構文が使われます。  この情報は、ODBC 関数を使って DBMS ドライバーから取得できます。  たとえば、特定のデータ型 \(**SQL\_VARCHAR** など\) に対して **::SQLGetTypeInfo** を呼び出すと、**LITERAL\_PREFIX** および **LITERAL\_SUFFIX** 用の文字を取得できます。  データベースに依存しないコードを作成する場合は、MSDN ライブラリ CD の『ODBC Programmer's Reference』の「Appendix C: SQL Grammar」を参照してください。構文についての詳細な情報が記載されています。  
  
 カスタム SQL ステートメントを指定しない限り、レコード選択用の SQL ステートメントはレコードセット オブジェクトによって構築されます。  ステートメントの内容は、メンバー関数 **Open** のパラメーター `lpszSQL` の値によって異なります。  
  
 次に、SQL **SELECT** ステートメントの一般形式を示します。  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 レコードセットが生成する SQL ステートメントに **DISTINCT** キーワードを加える方法として、`DoFieldExchange` で最初に呼び出す RFX 関数に **DISTINCT** キーワードを埋め込む方法もあります。  たとえば、次のようになります。  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  この手法は、読み取り専用レコードセットを開くときだけ使用できます。  
  
## SQL ステートメントのオーバーライド  
 次の表に、**Open** のパラメーター `lpszSQL` として指定できる値を示します。  各ケースについては、表の後で説明します。  
  
 **lpszSQL パラメーターと作成される SQL 文字列**  
  
|Case|lpszSQL に渡す値|作成される SELECT ステートメント|  
|----------|------------------|--------------------------|  
|1|**NULL**|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> `CRecordset::Open` は、`GetDefaultSQL` を呼び出してテーブル名 \(table\-name\) を取得します。  作成される文字列は、`GetDefaultSQL` が返す値に応じてケース 2 からケース 5 のいずれかになります。|  
|2|テーブル名|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> *rfx\-field\-list* は、`DoFieldExchange` の RFX ステートメントによります。  **m\_strFilter** と `m_strSort` が空でない場合は、**WHERE** 句および **ORDER BY** 句が加えられます。|  
|3 \*|完全な **SELECT** ステートメント \(**WHERE** 句と **ORDER BY** 句は含まない\)|そのまま渡されます。  **m\_strFilter** と `m_strSort` が空でない場合は、**WHERE** 句および **ORDER BY** 句が加えられます。|  
|4 \*|完全な **SELECT** ステートメント \(**WHERE** 句と **ORDER BY** 句を含む\)|そのまま渡されます。  **m\_strFilter** と `m_strSort` の両方またはいずれかを空にしておく必要があります \(空にしないと、フィルターおよび並べ替えが重複して生成されます\)。|  
|5 \*|ストアド プロシージャの呼び出し|そのまま渡されます。|  
  
 \* `m_nFields` の値は、**SELECT** ステートメントで指定する列数以下にする必要があります。  **SELECT** ステートメントで指定する各列のデータ型は、対応する RFX 出力列の型に一致させてください。  
  
### ケース 1   lpszSQL \= NULL  
 選択されるレコードは、`CRecordset::Open` が呼び出した `GetDefaultSQL` が返す文字列によって異なります。  この文字列は、ケース 2 からケース 5 に分類できます。  
  
### ケース 2   lpszSQL \= \(テーブル名\)  
 レコードセットは、レコード フィールド エクスチェンジ \(RFX: Record Field Exchange\) を使って列名のリストを構築します。列名は、レコードセット クラスのオーバーライド関数 `DoFieldExchange` から RFX 関数を呼び出して取得します。  ウィザードでレコードセット クラスを宣言した場合は、ケース 1 と同じ結果になります \(ウィザードで指定したテーブル名と同じテーブル名を指定した場合\)。  ウィザードを使用せずにレコードセット クラスを作成した場合は、ケース 2 が最も簡単に SQL ステートメントを作成できます。  
  
 次の例は、MFC データベース アプリケーションからレコードを抽出する SQL ステートメントを作成します。  フレームワークがメンバー関数 `GetDefaultSQL` を呼び出すと、この関数はテーブルの名前 \(`SECTION`\) を返します。  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 フレームワークは、メンバー関数 `DoFieldExchange` を呼び出して、SQL **SELECT** ステートメントで使用する列名を取得します。  
  
```  
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Text(pFX, "CourseID", m_strCourseID);  
    RFX_Text(pFX, "InstructorID", m_strInstructorID);  
    RFX_Text(pFX, "RoomNo", m_strRoomNo);  
    RFX_Text(pFX, "Schedule", m_strSchedule);  
    RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 この処理が終了すると、SQL ステートメントは次のようになります。  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### ケース 3   lpszSQL \= SELECT\/FROM ステートメント  
 RFX を呼び出さずに、列のリストを手作業で直接指定します。  この方法は、以下の場合に使用します。  
  
-   **SELECT** の後に **DISTINCT** キーワードを指定する場合。  
  
     列のリストは、`DoFieldExchange` で指定する列名と型の順序に一致させる必要があります。  
  
-   ODBC 関数 **::SQLGetData** を使って列の値を直接取得する場合。つまり、RFX に列の連結と取得を任せられない場合。  
  
     たとえば、アプリケーションの配布後にアプリケーション ユーザーがデータベース テーブルに列を追加した場合です。  このような場合には、ウィザードでクラスを宣言したときに予測できなかった新しい列に対応するフィールド データ メンバーを追加する必要があります。  
  
     列のリストの先頭部分 \(動的に追加しない部分\) は、`DoFieldExchange` で指定する列名と型の順序に一致させる必要があります。リストの末尾に新しく作成された列を追加します。  詳細については、「[レコードセット: データ列を動的に結びつける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。  
  
-   **FROM** 句を使って複数のテーブルを結合する場合。  
  
     使用例および詳細については、「[レコードセット: 結合 \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)」を参照してください。  
  
### ケース 4   lpszSQL \= WHERE\/ORDER BY 句を含む SELECT\/FROM ステートメント  
 ステートメントのすべての要素を指定します。つまり、列のリスト \(関数 `DoFieldExchange` からの RFX 呼び出しで取得\)、テーブルのリスト、**WHERE** 句および **ORDER BY** 句の内容を指定します。  このケースで **WHERE** 句および **ORDER BY** 句を指定する場合は、**m\_strFilter** および `m_strSort` を使用しないでください。  
  
### ケース 5   lpszSQL \= ストアド プロシージャ呼び出し  
 定義済みクエリ \(Microsoft SQL Server データベースのストアド プロシージャなど\) を呼び出すときは、パラメーター `lpszSQL` で **CALL** ステートメントを渡します。  ウィザードは、定義済みクエリを呼び出すレコードセット クラスをサポートしていません。  レコードを返さない定義済みクエリもあります。  
  
 定義済みクエリがレコードを返さない場合は、`CDatabase` の `ExecuteSQL` メンバー関数を直接呼び出すことができます。  レコードを返す定義済みクエリの場合は、返される列に対応して `DoFieldExchange` に RFX 呼び出しを記述する必要があります。  RFX 関数を呼び出す順序と関数が返す型は、定義済みクエリと同じにしてください。  詳細については、「[レコードセット: 定義済みクエリを利用したクラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)」を参照してください。  
  
## 参照  
 [SQL: SQL と C\+\+ のデータ型 \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: SQL の直接呼び出し \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)