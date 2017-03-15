---
title: "レコードの選択と操作 | Microsoft Docs"
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
  - "ODBC レコードセット, 選択 (レコードを)"
  - "レコード選択, MFC ODBC クラス"
  - "レコード, 選択"
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# レコードの選択と操作
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

通常、SQL の **SELECT** ステートメントを使用してデータ ソースのレコードを選択すると、テーブルまたはクエリの一連のレコードが結果セットとして取得されます。  データベース クラスでは、レコードセット オブジェクトを使用し、結果セットの選択やアクセスを行います。  レコードセットは、アプリケーション固有のクラスのオブジェクトとして、[CRecordset](../Topic/CRecordset%20Class.md) から派生します。  レコードセット クラスを定義する場合は、アクセス先のデータ ソース、参照するテーブル、およびその列を指定します。  MFC アプリケーション ウィザードまたは \[クラスの追加\] \(「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照\) を使うと、特定のデータ ソースへの接続を持つクラスを作成できます。  各ウィザードは、テーブル名を返す `CRecordset` クラスのメンバー関数 [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) を作成します。  ウィザードを使用してレコードセット クラスを作成する方法の詳細については、「[&#91;データベース サポート&#93; \(MFC アプリケーション ウィザード\)](../../mfc/reference/database-support-mfc-application-wizard.md)」および「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照してください。  
  
 実行時に [CRecordset](../Topic/CRecordset%20Class.md) オブジェクトを使うと、次のことができます。  
  
-   現在のレコードのデータ フィールドを参照する。  
  
-   レコードセットのフィルター処理やソートを行う。  
  
-   既定の SQL **SELECT** ステートメントをカスタマイズする。  
  
-   選択したレコードの間をスクロールする。  
  
-   レコードの追加、変更、削除を行う \(データ ソースとレコードセットの両方が変更可能な場合\)。  
  
-   レコードセットがクエリを再実行できるかどうかをテストし、レコードセットの内容を更新する。  
  
 レコードセット オブジェクトを使い終わったら、閉じて破棄します。  レコードセットの詳細については、「[レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)」を参照してください。  
  
## 参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)