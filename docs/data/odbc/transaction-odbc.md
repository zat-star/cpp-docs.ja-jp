---
title: "トランザクション (ODBC) | Microsoft Docs"
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
  - "データベース [C++], トランザクション"
  - "ODBC [C++], トランザクション"
  - "ODBC レコードセット [C++], トランザクション"
  - "ODBC レコードセット [C++], 更新"
  - "レコードセット [C++], トランザクション"
  - "レコードセット [C++], 更新"
  - "トランザクション [C++], MFC ODBC クラス"
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# トランザクション (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 トランザクションとは、[データ ソース](../../data/odbc/data-source-odbc.md)に対する一連の更新操作をまとめてバッチ処理することです。トランザクション内の更新操作は、すべて一度にコミットされるか、まったく処理されない \(ロールバックされる\) かのいずれかです。  トランザクションを使わないときは、コミットを発行しなくても、データ ソースに対する更新操作が自動的に行われます。  
  
> [!NOTE]
>  ODBC データベース ドライバーによっては、トランザクションをサポートしていないものもあります。  ドライバーがサポートするトランザクションを調べるには、[CDatabase](../../mfc/reference/cdatabase-class.md) オブジェクトまたは [CRecordset](../Topic/CRecordset%20Class.md) オブジェクトのメンバー関数 `CanTransact` を呼び出します。  ただし、`CanTransact` はデータ ソースが全トランザクションをフル サポートしているかどうかを確認できないので注意してください。  また、開いている `CRecordset` オブジェクトに対するトランザクションの影響を調べるには、**CommitTrans** と **Rollback** の後にそれぞれ `CDatabase::GetCursorCommitBehavior` と `CDatabase::GetCursorRollbackBehavior` を必ず呼び出してください。  
  
 `CRecordset` オブジェクトのメンバー関数 `AddNew` や **Edit** の呼び出しは、**Update** を呼び出すとすぐにデータ ソースに反映されます。  **Delete** の呼び出しもすぐに反映されます。  これに対して、`AddNew`、**Edit**、**Update**、**Delete** への複数の呼び出しで構成したトランザクションによる操作は、明示的に **CommitTrans** を呼び出さない限りコミットされません。  トランザクションを利用すると、複数の操作を一度に実行できます。  必要なリソースが確保できなかったか、その他の条件によってトランザクション全体が実行できなかった場合は、トランザクションをコミットせずに、ロールバックして操作を無効にします。  この場合、トランザクション内のすべての更新操作はデータ ソースに反映されません。  
  
> [!NOTE]
>  バルク行フェッチが実装されている場合、現段階の `CRecordset` クラスでは、データ ソースへの更新をサポートしていません。  つまり、`AddNew`、**Edit**、**Delete**、または **Update** を呼び出すことはできません。  ただし、更新を処理するための関数を独自に記述し、その関数をトランザクション内で呼び出すことはできます。  バルク行フェッチの詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
> [!NOTE]
>  `CDatabase` オブジェクトに関連付けられた ODBC **HDBC**、またはその **HDBC** に基づいた ODBC **HSTMT** を使用する限り、トランザクションは、レコードセットだけではなく、直接実行した SQL ステートメントにも影響を及ぼします。  
  
 複数のレコードを同時に更新する場合は、特にトランザクションが便利です。  複数のレコードを使用しているときは、最後のレコードが更新される前に例外がスローされると、問題が起こります。  このような一連の操作を 1 つのトランザクションにグループ化すると、更新処理をやり直して \(ロールバックして\) 各レコードをトランザクション実行前の状態に戻すことができます。  たとえば、銀行預金処理で口座 A から口座 B に振り替えるとき、A からの引き落とし操作と B への預け入れ操作は、必ず両方とも成功させるか、両方とも失敗させるかのいずれかにする必要があります。  
  
 データベース クラスでは、トランザクションは `CDatabase` オブジェクトを通じて行います。  `CDatabase` オブジェクトは、データ ソースへの接続を表します。`CDatabase` オブジェクトに結び付けられている 1 つ以上のレコードセットが、レコードセット メンバー関数を使って、データベース内のテーブルを操作します。  
  
> [!NOTE]
>  サポートされるトランザクションのレベルは 1 つだけです。  つまり、トランザクションを入れ子にすることも、複数のデータベース オブジェクトにわたるトランザクションを使用することもできません。  
  
 トランザクション実行のしくみの詳細については、次のトピックを参照してください。  
  
-   [トランザクション : レコードセットからのトランザクション実行 \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [トランザクション : トランザクションが更新処理に与える影響 \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)