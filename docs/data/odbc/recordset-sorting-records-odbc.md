---
title: "レコードセット: レコードの並べ替え (ODBC) | Microsoft Docs"
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
  - "ODBC レコードセット, 並べ替え"
  - "レコードセット, 並べ替え"
  - "並べ替え (データの), レコードセットのデータ"
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: レコードの並べ替え (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコードセットを並べ替える方法について説明します。  並べ替えを行うときは、基準にする列と、昇順 \(`ASC`\) または降順 \(**DESC**\) を指定できます。`ASC` が既定値です。  たとえば、2 つの列を指定した場合は、最初に指定した列を基準にして並べ替えが行われ、次に 2 番目に指定した列を基準にして並べ替えが行われます。  並べ替えの内容は、SQL **ORDER BY** 句で定義します。  レコードセットの SQL クエリに **ORDER BY** 句を追加すると、選択されたレコードの並べ替えが行われます。  
  
 レコードセットの並べ替え順序は、レコードセット オブジェクトの構築後、メンバー関数 **Open** を呼び出す前に \(既に開かれているレコードセット オブジェクトを再利用する場合はメンバー関数 **Requery** を呼び出す前に\) 指定します。  
  
#### レコードセット オブジェクトの並べ替え順序を指定するには、  
  
1.  新しいレコードセット オブジェクトを構築します。既存のオブジェクトを利用する場合は、**Requery** を呼び出せる状態にします。  
  
2.  レコードセット オブジェクトの [m\_strSort](../Topic/CRecordset::m_strSort.md) データ メンバーの値を設定します。  
  
     並べ替えは、NULL で終わる文字列で指定します。  この文字列は、SQL **ORDER BY** 句から **ORDER BY** キーワードを除いた部分です。  次のように設定します。  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  必要に応じて、その他のオプション \(フィルター、ロック方法、パラメーターなど\) を設定します。  
  
4.  新規オブジェクトでは **Open** を呼び出します。既存のオブジェクトを利用するときは **Requery** を呼び出します。  
  
 選択されたレコードは指定された順に並べ替えられます。  たとえば、学生レコードをまず姓に基づいて、次に名前に基づいて、それぞれ降順で並べ替えるには、次のように設定します。  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 このレコードセットには、全学生のレコードが姓名に基づいて降順で \(Z から A へ\) 並べ替えられて格納されています。  
  
> [!NOTE]
>  **Open** に新しい SQL 文字列を渡すと、レコードセットの既定の SQL 文字列がオーバーライドされます。この場合、カスタム文字列に **ORDER BY** 句が含まれているときは、並べ替えを設定しないでください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [レコードセット: レコードのフィルター処理 \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)