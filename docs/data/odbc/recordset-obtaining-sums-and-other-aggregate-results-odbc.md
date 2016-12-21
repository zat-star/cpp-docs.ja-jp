---
title: "レコードセット: 集計値の計算 (ODBC) | Microsoft Docs"
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
  - "ODBC レコードセット, 取得 (SQL 集計値を)"
  - "レコードセット, 取得 (SQL 集計値を)"
  - "取得 (レコードセットから SQL 集計値を)"
  - "SQL の集計値"
  - "SQL の集計値, 取得 (レコードセットから)"
  - "SQL Server プロジェクト, 取得 (レコードセットから集計値を)"
  - "SQL, 取得 (レコードセットから集計値を)"
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: 集計値の計算 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、以下の [SQL](../../data/odbc/sql.md) キーワードを使用して、各種の集計結果を求める方法について説明します。  
  
-   **SUM** 数値データ型列の値の合計を求めます。  
  
-   **MIN** 数値データ型列の最小値を求めます。  
  
-   **MAX** 数値データ型列の最大値を求めます。  
  
-   **AVG** 数値データ型列の平均値を求めます。  
  
-   **COUNT** 任意のデータ型の列のレコード数を求めます。  
  
 これらの SQL 関数は、データ ソースからレコードを抽出せずに、データ ソースの統計情報を調べます。  通常は、1 つの値を持つ 1 つのレコード \(すべての列が集計値を持つ場合\) から成るレコードセットが作成されます。**GROUP BY** 句を使った場合は、レコードが複数になることもあります。レコードには、SQL 関数によって計算または抽出された値が格納されます。  
  
> [!TIP]
>  SQL の **GROUP BY** 句 \(および場合によっては **HAVING** 句\) を SQL ステートメントに追加する場合は、**m\_strFilter** の後に追加します。  たとえば、次のようになります。  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 列をフィルター処理するかまたは並べ替えると、集計対象のレコードの範囲を限定できます。  
  
> [!CAUTION]
>  集計によって得られる値の型は、その列本来の型とは異なる場合があります。  
  
-   **SUM** と **AVG** は、サイズが一段上のデータ型を返すことがあります。たとえば、`int` 型を渡して呼び出すと、**LONG** 型または **double** 型が返されます。  
  
-   **COUNT** は、通常、列本来の型に関係なく **LONG** 型を返します。  
  
-   **MAX** と **MIN** は、計算対象の列と同じ型の値を返します。  
  
     たとえば、クラスの追加ウィザードは Sales 列の値を格納するために `long` `m_lSales` を作成しますが、集計値を格納するには `double m_dblSumSales` データ メンバーと置き換える必要があります。  次の例を参照してください。  
  
#### レコードセットの集計値を求めるには  
  
1.  「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」の説明に従って、集計の対象となる \(複数の\) 列を持つレコードセットを作成します。  
  
2.  メンバー関数 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) を変更します。  列名を表す文字列 \([RFX](../../data/odbc/record-field-exchange-using-rfx.md) 関数呼び出しの 2 番目の引数\) を列の集計関数を表す文字列に置き換えます。  たとえば、次の RFX 関数呼び出しは、  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     この部分を次のように変更します。  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  レコードセットを開きます。  集計値は、`m_dblSumSales` に格納されます。  
  
> [!NOTE]
>  ウィザードが使用するデータ メンバー名では、一部のプレフィックスが省略されます。  たとえば、列 Sales に対するメンバー名として、`m_lSales` ではなく `m_Sales` が使用されます。  
  
 [CRecordView](../../mfc/reference/crecordview-class.md) クラスを使用してデータを表示する場合、DDX 関数呼び出しを変更して、新しいデータ メンバーの値を表示できるようにする必要があります。この場合は、次の関数呼び出しを変更します。  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 To:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)