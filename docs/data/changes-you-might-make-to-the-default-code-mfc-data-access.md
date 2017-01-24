---
title: "既定の処理の変更 (MFC データ アクセス) | Microsoft Docs"
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
  - "レコード ビュー [C++], カスタマイズ (既定のコードを)"
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 既定の処理の変更 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)で生成したレコードセット クラスでは、1 つのテーブル内のすべてのレコードが選択されます。  この動作は多くの場合、次の 1 つ以上の方法で変更する必要があります。  
  
-   レコードセットのフィルターまたは並べ替え順序の設定。  フィルターと並べ替え順序は、レコードセット オブジェクトの構築後、**Open** メンバー関数が呼び出される前に `OnInitialUpdate` で設定します。  詳細については、「[レコードセット: レコードのフィルター処理 \(ODBC\)](../data/odbc/recordset-filtering-records-odbc.md)」および「[レコードセット: レコードの並べ替え \(ODBC\)](../data/odbc/recordset-sorting-records-odbc.md)」を参照してください。  
  
-   レコードセットのパラメーター化。  実際のランタイム パラメーター値はフィルターの後に指定します。  詳細については、「[レコードセット: パラメーターを利用したレコードセット \(ODBC\)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
-   カスタマイズした SQL 文字列を [Open](../Topic/CRecordset::Open.md) メンバー関数に渡す方法。  この方法で実行できる内容については、「[SQL: レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)」を参照してください。  
  
## 参照  
 [レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)