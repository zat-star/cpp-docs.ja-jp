---
title: "トランザクション: トランザクションが更新処理に与える影響 (ODBC) | Microsoft Docs"
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
  - "CommitTrans メソッド"
  - "ODBC レコードセット, トランザクション"
  - "Rollback メソッド, ODBC トランザクション"
  - "トランザクション, ロールバック"
  - "トランザクション, 更新 (レコードセットを)"
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# トランザクション: トランザクションが更新処理に与える影響 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

トランザクション中の[データ ソース](../../data/odbc/data-source-odbc.md)の更新は、エディット バッファーを使って管理されます \(トランザクションを利用しない場合も同じです\)。  エディット バッファーは、レコードセットのフィールド データ メンバーの集合であり、現在のレコードが保存されます。`AddNew` や **Edit** の実行中は、エディット バッファーの内容は一時的に待避されます。  **Delete** 処理の場合は、現在のレコードの内容は待避されません。  エディット バッファーと現在のレコードの詳細については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  
  
> [!NOTE]
>  バルク行フェッチを実装している場合は、`AddNew`、**Edit**、または **Delete** を呼び出すことはできません。  その代わり、データ ソースの更新を処理するための関数を独自に記述する必要があります。  バルク行フェッチの詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 トランザクション中の `AddNew`、**Edit**、**Delete** の操作は、コミットすることも、ロールバックすることもできます。  **CommitTrans** と **Rollback** による現在のレコードの操作は、エディット バッファーに正しく反映されないことがあります。  現在のレコードの内容をエディット バッファーに正しく反映させるには、`CRecordset` の更新用関数 AddNew、Edit、Delete と `CDatabase` のメンバー関数 **CommitTrans**、**Rollback** の連係を正しく理解する必要があります。  
  
##  <a name="_core_how_committrans_affects_updates"></a> CommitTrans が更新処理に与える影響  
 次の表に **CommitTrans** がトランザクションに与える影響を示します。  
  
### CommitTrans が更新処理に与える影響  
  
|操作|データ ソースの状態|  
|--------|----------------|  
|`AddNew` と **Update** を実行後、**CommitTrans** を実行|データ ソースに新規レコードが追加されます。|  
|`AddNew` 実行後、\(**Update** を呼び出さずに\) **CommitTrans** を実行|新規レコードは失われ、  データ ソースには追加されません。|  
|**Edit** と **Update** を実行後、**CommitTrans** を実行|更新結果がデータ ソースに反映されます。|  
|**Edit** 実行後、\(**Update** を呼び出さずに\) **CommitTrans** を実行|レコードの更新結果は失われ、  データ ソース上のレコードは変化しません。|  
|**Delete** 実行後、**CommitTrans** を実行|データ ソース上のレコードが削除されます。|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Rollback がトランザクションに与える影響  
 次の表に、**Rollback** がトランザクションに与える影響を示します。  
  
### Rollback がトランザクションに与える影響  
  
|操作|現在のレコードの状態|必要な処理|データ ソースの状態|  
|--------|----------------|-----------|----------------|  
|`AddNew` と **Update** を実行後、**Rollback** を実行|現在のレコードは、新規レコードを作るために一時的に待避されます。  新規レコードは、エディット バッファーに格納されます。  **Update** 実行後、現在のレコードの内容がエディット バッファーに戻されます。||**Update** によるデータ ソースへの追加は無効化されます。|  
|`AddNew` 実行後、\(**Update** を呼び出さずに\) **Rollback** を実行|現在のレコードは、新規レコードを作るために一時的に待避されます。  エディット バッファーには新規レコードが格納されます。|エディット バッファーに空の新規レコードを作るには、もう 1 回 `AddNew` を呼び出します。  エディット バッファーに元の値を復元する場合は、**Move**\(0\) を呼び出します。|**Update** が呼び出されていないので、データ ソースは変更されません。|  
|**Edit** と **Update** を実行後、**Rollback** を実行|編集前の現在のレコードは一時的に待避されます。  エディット バッファーには、編集後のレコードの内容が格納されます。  **Update** が呼び出された後も、編集前のレコードは待避されて残っています。|ダイナセットの場合 : いったん他のレコードにスクロールしてから再び元のレコードに戻ると、編集前のレコードがエディット バッファーに戻されます。<br /><br /> スナップショットの場合 : **Requery** を呼び出すと、データ ソースの内容がレコードセットに呼び戻されます。|**Update** によるデータ ソースへの変更は無効化されます。|  
|**Edit** 実行後、\(**Update** を呼び出さずに\) **Rollback** を実行|編集前の現在のレコードは一時的に待避されます。  エディット バッファーには、編集後のレコードの内容が格納されます。|エディット バッファーに戻すには、もう 1 回 **Edit** を呼び出します。|**Update** が呼び出されていないので、データ ソースは変更されません。|  
|**Delete** 実行後、**Rollback** を実行|現在のレコードの内容が削除されます。|**Requery** を呼び出すと、データ ソースの内容がレコードセットに呼び戻されます。|データ ソースに対する削除は無効化されます。|  
  
## 参照  
 [トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [トランザクション: レコードセットからのトランザクション実行 \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)