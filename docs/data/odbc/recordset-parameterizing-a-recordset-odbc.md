---
title: "レコードセット: パラメーターを利用したレコードセット (ODBC) | Microsoft Docs"
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
  - "ODBC レコードセット, パラメーター化"
  - "パラメーターを利用したレコードセット"
  - "渡す (パラメーターを), クエリへの実行時の"
  - "レコードセット, パラメーター化"
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# レコードセット: パラメーターを利用したレコードセット (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 場合によっては、ユーザー入力または計算結果に応じて実行時にレコードを選択できるようにする必要があります。  このような場合は、レコードセット パラメーターを使います。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコードセットをパラメーター化する目的](#_core_parameterized_recordsets)  
  
-   [レコードセットをパラメーター化するタイミングと理由](#_core_when_to_use_parameters)  
  
-   [レコードセット クラスでパラメーター データ メンバーを宣言する方法](#_core_parameterizing_your_recordset_class)  
  
-   [パラメーターの情報を実行時にレコードセット オブジェクトに渡す方法](#_core_passing_parameter_values_at_run_time)  
  
##  <a name="_core_parameterized_recordsets"></a> パラメーターを利用したレコードセット  
 パラメーター化したレコードセットでは、実行時にパラメーター値を渡すことができます。  これには、次の 2 つの利点があります。  
  
-   実行速度を向上できます。  
  
-   デザイン時に得られない情報 \(実行時のユーザー入力や計算結果など\) に基づき、実行時にクエリを構成できます。  
  
 **Open** を呼び出してクエリを実行すると、パラメーターの値を使って **SQL SELECT** ステートメントが作成されます。  どのレコードセットでもパラメーターを使用できます。  
  
##  <a name="_core_when_to_use_parameters"></a> パラメーターを使用する状況  
 通常、パラメーターは以下の場合に使います。  
  
-   定義済みのクエリに実行時の引数を渡す場合  
  
     ストアド プロシージャにパラメーターを渡すには、完全なカスタム ODBC **CALL** ステートメントを渡します。つまり、**Open** を呼び出すときに、パラメーター プレースホルダー付きの完全なカスタム ODBC CALL ステートメントを指定して、レコードセットの既定の SQL ステートメントをオーバーライドします。  詳細については、『MFC リファレンス』の「[CRecordset::Open](../Topic/CRecordset::Open.md)」、および「[SQL : レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)」と「[レコードセット : 定義済みクエリを利用したクラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)」を参照してください。  
  
-   そのつどパラメーター情報を変更して、クエリを繰り返し実行する場合  
  
     たとえば、学生の登録情報データベースを検索して特定の学生の情報を検索するたびに、学生の氏名または ID パラメーターに、ユーザーが値を入力できるようにします。  レコードセットのメンバー関数 **Requery** を呼び出すと、指定された学生のレコードだけが選択されます。  
  
     **m\_StrFilter** に保持するレコードセット フィルター文字列は、次のように設定します。  
  
    ```  
    "StudentID = ?"  
    ```  
  
     学生の ID を変数 `strInputID` に格納するとします。  `strInputID` に学生 ID の値として 100 を代入すると、この変数の値は、フィルター文字列内の "?" で示されるパラメーター プレースホルダーに結び付けられます。  
  
     パラメーター値を次のように代入します。  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     フィルター文字列は、次のように設定しないでください。  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     フィルター文字列の引用符の使い方については、「[レコードセット : レコードのフィルター処理 \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)」を参照してください。  
  
     クエリを再実行するたびに、パラメーターの値を新しい ID 値に設定します。  
  
    > [!TIP]
    >  パラメーターを使用すると、単にフィルターを使用するより効率的です。  パラメーターを使ったレコードセットでは、SQL **SELECT** ステートメントを作成するのは 1 回で済みます。  パラメーター化されていないフィルターを使ったレコードセットでは、新しいフィルター値を設定して **Requery** を呼び出すたびに、**SELECT** ステートメントを作成する必要があります。  
  
 フィルターの詳細については、「[レコードセット : レコードのフィルター処理 \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)」を参照してください。  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> パラメーターを利用したレコードセット クラスの作成  
  
> [!NOTE]
>  ここで説明する内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを使用するレコードセットでも、パラメーターを実装する方法は基本的に同じです。  詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 レコードセット クラスを作成する前に、どのパラメーターが必要か、パラメーターのデータ型を何にするか、パラメーターをどのように利用するかを決める必要があります。  
  
#### パラメーターを利用したレコードセット クラスを作成するには  
  
1.  クラスの追加の [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md) を実行して、クラスを作成します。  
  
2.  レコードセットの列に対応するフィールド データ メンバーを指定します。  
  
3.  ウィザードがプロジェクト内のファイルにクラスを出力したら、その .h ファイルを編集してクラス宣言に 1 つ以上のパラメーター データ メンバーを直接書き込みます。  このようにしてパラメーターを追加したスナップショット クラスの例を次に示します。この例では、"上級生を選択せよ" というクエリを作成します。  
  
    ```  
    class CStudentSet : public CRecordset  
    {  
    // Field/Param Data  
        CString m_strFirstName;  
        CString m_strLastName;  
        CString m_strStudentID;  
        CString m_strGradYear;  
  
        CString m_strGradYrParam;  
    };  
    ```  
  
     ウィザードによって生成されるフィールド データ メンバーの後にパラメーター データ メンバーを追加します。  命名規約として、ユーザー定義のパラメーター名の末尾には "Param" を付けます。  
  
4.  .cpp ファイル内の [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) メンバー関数定義に変更を加えます。  追加したパラメーター データ メンバーごとに RFX 関数呼び出しを追加します。  RFX 関数の記述方法については、「[レコード フィールド エクスチェンジ : RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。  すべてのパラメーターに対する RFX 呼び出しの前に、次の関数呼び出しを 1 回だけ行います。  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  レコードセット クラスのコンストラクターで、`m_nParams` のパラメーター数をインクリメントします。  
  
     詳細については、「[レコード フィールド エクスチェンジ : ウィザード コードの操作](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)」を参照してください。  
  
6.  このクラスのレコードセット オブジェクトを作成するコードを記述する場合は、SQL ステートメントの文字列の、パラメーター値に置き換える箇所に、プレースホルダーとして "?" \(疑問符\) を配置します。  
  
     プレースホルダーは、実行時に、パラメーター値に順番に置き換えられます。  [SetFieldType](../Topic/CFieldExchange::SetFieldType.md) 呼び出しの後で設定した最初のパラメーター データ メンバーは、SQL 文字列の最初の "?" プレースホルダーと置き換わります。以降のパラメーターと "?" プレースホルダーも同じように置き換わります。  
  
> [!NOTE]
>  パラメーターの順序は重要です。`DoFieldExchange` 関数のパラメーターに対する RFX 呼び出しの順序は、SQL 文字列のパラメーター プレースホルダーの順序に一致させる必要があります。  
  
> [!TIP]
>  最も多く使用される文字列は、クラスの [m\_strFilter](../Topic/CRecordset::m_strFilter.md) データ メンバーに指定した文字列ですが、ODBC ドライバーによっては、他の SQL 句のパラメーターも使用できます。  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> 実行時にパラメーター値を渡す方法  
 パラメーター値は、メンバー関数 **Open** \(新規作成したレコード オブジェクトの場合\) またはメンバー関数 **Requery** \(既存のオブジェクトを再利用する場合\) を呼び出す前に設定します。  
  
#### パラメーターの値を実行時にレコードセット オブジェクトに渡すには  
  
1.  レコードセット オブジェクトを構築します。  
  
2.  **m\_strFilter** など、SQL ステートメント \(またはその一部\) を含む文字列を 1 つ以上用意します。  後でパラメーター値を代入するプレースホルダーには "?" を書いておきます。  
  
3.  実行時にパラメーター データ メンバーに値を代入します。  
  
4.  メンバー関数 **Open** を呼び出します。既存のレコードセットを再利用する場合は **Requery** を呼び出します。  
  
 たとえば、実行時に得られたデータに基づきフィルター文字列を作成する場合を考えてみます。  `CStudentSet` クラスのレコードセット `rsStudent` が既に生成されている場合は、次のクエリを再実行して特定の情報を取得できます。  
  
```  
// Set up a filter string with   
// parameter placeholders  
rsStudents.m_strFilter = "GradYear <= ?";  
  
// Obtain or calculate parameter values   
// to pass--simply assigned here   
CString strGradYear = GetCurrentAcademicYear( );  
  
// Assign the values to parameter data members  
rsStudents.m_strGradYrParam = strGradYear;  
  
// Run the query  
if( !rsStudents.Requery( ) )  
    return FALSE;  
```  
  
 これにより、レコードセットには、実行時にパラメーターによって指定されたフィルター条件に合致するレコードだけが格納されます。  この場合、レコードセットには上級生のレコードだけが格納されます。  
  
> [!NOTE]
>  必要に応じて、[SetParamNull](../Topic/CRecordset::SetParamNull.md) を使用して、パラメーター データ メンバーの値を Null に設定することもできます。  パラメーター データ メンバーの値が NULL かどうかを調べるには [IsFieldNull](../Topic/CRecordset::IsFieldNull.md) を使います。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [レコードセット: レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)