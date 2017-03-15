---
title: "レコードセット: レコードのフィルター処理 (ODBC) | Microsoft Docs"
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
  - "データ [MFC], フィルター処理"
  - "フィルター処理 (レコードセットを)"
  - "フィルター [C++], レコードセット オブジェクト"
  - "ODBC レコードセット [C++], フィルター処理 (レコードを)"
  - "レコードセット [C++], フィルター処理"
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコードセット: レコードのフィルター処理 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコードセットをフィルター処理して、特定のレコードだけを抽出する方法について説明します。  たとえば、MATH101 など、特定の課程に含まれる講義だけを抽出することもできます。  フィルターは、SQL **WHERE** 句で定義する検索条件です。  **WHERE** 句は、レコードセットの SQL ステートメントに付加されて、選択内容を限定します。  
  
 レコードセット オブジェクトのフィルターは、レコードセットの生成後、メンバー関数 **Open** を呼び出す前に \(既に開かれているレコードセット オブジェクトを再利用する場合は、メンバー関数 **Requery** を呼び出す前に\) 作成します。  
  
#### レコードセット オブジェクトのフィルターを設定するには  
  
1.  新しいレコードセット オブジェクトを構築します。既存のオブジェクトを利用する場合は、**Requery** を呼び出せる状態にします。  
  
2.  オブジェクトの [m\_strFilter](../Topic/CRecordset::m_strFilter.md) データ メンバーの値を設定します。  
  
     フィルターは、null で終わる文字列で、SQL **WHERE** 句の内容は含まれていますが、**WHERE** キーワードは含まれていません。  次のように設定します。  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  上記の例では、リテラル文字列 "MATH101" は単一引用符で囲まれています。  ODBC の仕様では、リテラル文字列を囲む記号として単一引用符を使います。  リテラル文字列を囲む記号については、使用する DBMS の ODBC ドライバーのドキュメントを参照してください。  この構文については、このトピックの最後でも詳しく説明します。  
  
3.  必要に応じて、その他のオプション \(並べ替え、ロック方法、パラメーターなど\) を設定します。  パラメーターは特に便利です。  フィルターのパラメーター化については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
4.  新規オブジェクトでは **Open** を呼び出します。既存のオブジェクトの場合は **Requery** を呼び出します。  
  
> [!TIP]
>  フィルターでパラメーターを使用すると、レコードの検索効率が向上する場合があります。  
  
> [!TIP]
>  レコードセット フィルターを使うと、テーブルを[結合](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)することも、実行時に入力または計算された値に基づいた[パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を使用することもできます。  
  
 レコードセットは、指定された選択条件に合致するレコードだけを選び出します。  たとえば、上の条件に合致する講義だけを指定するには \(`strCourseID` の値として、"MATH101" が設定されている場合\)、次のようにします。  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 このレコードセットには、MATH101 の全講義目録が格納されます。  
  
 上の例のフィルター文字列は、文字列変数を使って設定されています。  これは一般的な使い方です。  course ID にリテラル値 100 を指定するには、  次のコードのように、フィルター文字列を設定します。  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 単一引用符を必ず使います。次のようにすると、文字列は直接指定できません。  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 上記の引用符は ODBC 仕様に従っていますが、DBMS によっては他の引用符を使用する必要がある場合もあります。  詳細については、「[SQL : レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)」を参照してください。  
  
> [!NOTE]
>  **Open** に独自の SQL 文字列を渡すと、レコードセットの既定の SQL 文字列がオーバーライドされます。この場合、カスタム文字列に **WHERE** 句が含まれているときは、フィルターを設定しないでください。  既定の SQL をオーバーライドする方法の詳細については、「[SQL : レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコードの並べ替え \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [レコードセット: レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)   
 [レコードセット: レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [レコードセット: レコードのロック \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)