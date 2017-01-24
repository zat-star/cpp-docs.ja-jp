---
title: "レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC) | Microsoft Docs"
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
  - "ODBC レコードセット, クエリ"
  - "定義済みクエリとレコードセット"
  - "レコードセット, 定義済みクエリ"
  - "レコードセット, ストアド プロシージャ"
  - "ストアド プロシージャ, およびレコードセット"
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、定義済みクエリ \(Microsoft SQL Server ではストアド プロシージャ\) 用のレコードセット クラスを作成する方法について説明します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを実装しているレコードセットでも、方法は基本的に同じです。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 データベース管理システム \(DBMS: Database Management System\) によっては、定義済みクエリを作成し、そのクエリをプログラムから関数のように呼び出すことができます。  クエリは名前が付いており、パラメーターを取得したり、レコードを返したりできます。  ここでは、レコードを返す \(およびパラメーターを取得する\) 定義済みクエリを呼び出す手順について説明します。  
  
 データベース クラスでは、定義済みクエリを更新できません。  スナップショットの定義済みクエリとダイナセットの定義済みクエリの違いは、更新可能かどうかではなく、ほかのユーザー \(またはほかのレコードセット\) による更新が反映されるかどうかです。  
  
> [!TIP]
>  レコードを返さない定義済みクエリを呼び出す場合は、レコードセットは不要です。  次に説明する SQL ステートメントを用意し、`CDatabase` のメンバー関数 [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) を呼び出して実行します。  
  
 定義済みクエリを呼び出すために独立したレコードセット クラスを作成することもできますが、プログラマによる作業が必要です。  ウィザードでは、この目的のためのクラス作成がサポートされていません。  
  
#### 定義済みクエリ \(ストアド プロシージャ\) を呼び出すクラスを作成するには  
  
1.  クラスの追加の [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md) を使って、クエリによって大部分の列の値が指定されるテーブル用のレコードセット クラスを作成します。  これをベースにして目的のクラスを構築します。  
  
2.  ソース コードを直接編集して、クエリが返す列に対応するフィールド データ メンバーのうち、ウィザードで生成されなかったフィールド データ メンバーを追加します。  
  
     たとえば、選択しなかった 2 つのテーブルに対してクエリがそれぞれ 3 つの列を返すときは、該当する型のフィールド データ メンバーを 6 つクラスに追加します。  
  
3.  ソース コードを直接編集して、追加したフィールド データ メンバーに該当する型の [RFX](../../data/odbc/record-field-exchange-rfx.md) 関数呼び出しをメンバー関数 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) に追加します。  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  結果セットで返されるデータ型と列の順序を知っている必要があります。  `DoFieldExchange` における RFX 関数呼び出しの順序は、結果セット列の順序に一致させます。  
  
4.  新しく加えたフィールド データ メンバーの初期化コードをレコードセット クラスのコンストラクターに付加します。  
  
     また、データ メンバー [m\_nFields](../Topic/CRecordset::m_nFields.md) の値を初期化処理の中の一環としてインクリメントする必要があります。  ウィザードは m\_nFields の値を初期化しますが、ウィザードが作成したフィールド データ メンバーだけが対象です。  たとえば、次のようになります。  
  
    ```  
    m_nFields += 6;  
    ```  
  
     `CLongBinary` やバイト配列など、データ型によってはここで初期化できないこともあります。  
  
5.  パラメーターを持つクエリの場合は、各パラメーターに対応するパラメーター データ メンバー、RFX 関数呼び出し、初期化コードを追加します。  
  
6.  また、この手順の手順 4. でフィールドを追加するために `m_nFields` をインクリメントしたように、追加したパラメーターごとに `m_nParams` をインクリメントします。  詳細については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
7.  次のような SQL ステートメントの文字列を直接書きます。  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     **CALL** は ODBC キーワード、**proc\-name** はデータ ソースが認識できるクエリの名前、"?" 項目は実行時に \(パラメーターを使う場合\) パラメーター値に置き換えられるプレースホルダーです。  次に、パラメーターを 1 つ使う例を示します。  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  レコードセットを開くためのコードを編集します。まず、レコードセットのパラメーター データ メンバーの値を設定し、次に、上で作成した SQL 文字列をパラメーター **lpszSQL** に渡して **Open** メンバー関数を呼び出します。  または、メンバー関数 `GetDefaultSQL` の戻り値をこの SQL 文字列に置き換えます。  
  
 定義済みクエリを呼び出す手順の例を次に示します。ここでは、`Delinquent_Accts` という名前のクエリを呼び出しています。  このクエリは、セールス地域番号を表す 1 つのパラメーターを取り、`Acct_No`、`L_Name`、および `Phone` の 3 つの列を返します。  これらの列は、すべてテーブル Customers の列です。  
  
 次のレコードセットでは、クエリが返す列に対応するフィールド データ メンバーと、セールス地域番号を表すパラメーター \(実行時に値が決定されます\) を指定します。  
  
```  
class CDelinquents : public CRecordset  
{  
// Field/Param Data  
    LONG m_lAcct_No;  
    CString m_strL_Name;  
    CString m_strPhone;  
    LONG m_lDistParam;  
    // ...  
};  
```  
  
 このクラス宣言のうち、直接記述した `m_lDistParam` 以外の部分はウィザードによって生成されています。  ここでは、他のメンバーは示されていません。  
  
 `CDelinquents` コンストラクターのデータ メンバー初期化コードを次に示します。  
  
```  
CDelinquents::CDelinquents(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
    // Wizard-generated params:  
    m_lAcct_No = 0;  
    m_strL_Name = "";  
    m_strPhone = "";  
    m_nFields = 3;  
    // User-defined params:  
    m_nParams = 1;  
    m_lDistParam = 0;  
}  
```  
  
 [m\_nFields](../Topic/CRecordset::m_nFields.md) と [m\_nParams](../Topic/CRecordset::m_nParams.md) の初期化コードに注目してください。  ウィザードは `m_nFields` を初期化します。`m_nParams` の初期化コードは追加します。  
  
 `CDelinquents::DoFieldExchange` の RFX 呼び出しの部分を次に示します。  
  
```  
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Long(pFX, "Acct_No", m_lAcct_No);  
    RFX_Text(pFX, "L_Name", m_strL_Name);  
    RFX_Text(pFX, "Phone", m_strPhone);  
    pFX->SetFieldType(CFieldExchange::param);  
    RFX_Long(pFX, "Dist_No", m_lDistParam);  
}  
```  
  
 このコードでは、戻り値として返される 3 つの列に対して RFX 関数が呼び出され、実行時に得られる値がパラメーターとして渡されます。  パラメーターは、`Dist_No` \(district Number 地域番号\) 列のキーとして渡されます。  
  
 次に、SQL 文字列を設定し、この文字列でレコードセットを開く例を示します。  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 このコードは、スナップショットを構築し、ユーザーから得たパラメーターを渡し、定義済みクエリを呼び出します。  クエリが終了すると、指定した販売地域のレコードが返ります。  各レコードには、顧客番号、顧客名、および顧客電話番号の列が格納されます。  
  
> [!TIP]
>  ストアド プロシージャの戻り値 \(出力パラメーター\) を処理する場合もあります。  詳細および例については、「[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: クエリの再実行 \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [レコードセット: テーブルにアクセスするレコードセット クラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [レコードセット: 結合 \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)