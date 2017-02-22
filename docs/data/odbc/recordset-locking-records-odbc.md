---
title: "レコードセット: レコードのロック (ODBC) | Microsoft Docs"
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
  - "データ [C++], locking"
  - "ロック [C++], レコードセット"
  - "ODBC レコードセット [C++], ロック (レコードを)"
  - "共有ロック"
  - "共有ロック, ODBC"
  - "排他ロック (ODBC の)"
  - "レコードセット [C++], ロック (レコードを)"
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコードセット: レコードのロック (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [利用できるレコード ロックの種類](#_core_record.2d.locking_modes)  
  
-   [更新時にレコードセットのレコードをロックする方法](#_core_locking_records_in_your_recordset)  
  
 レコードセットを使ってデータ ソース上のレコードを更新するときに、レコードをロックすると、ほかのユーザーによって同時に同じレコードが更新されません。  複数のユーザーによるレコードの同時更新が防止されないシステムで、2 人のユーザーが同時にレコードを更新した場合、結果は保証されません。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを実装しているレコードセットには、一部の説明が該当しません。  たとえば、**Edit** および **Update** の両メンバー関数を呼び出すことはできません。  バルク行フェッチの詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
##  <a name="_core_record.2d.locking_modes"></a> レコード ロックのモード  
 データベース クラスのレコード ロックには、次の 2 つの[モード](../Topic/CRecordset::SetLockingMode.md)が定義されています。  
  
-   共有ロック \(既定\)  
  
-   排他ロック  
  
 レコードの更新処理は、次の 3 段階に分けられます。  
  
1.  メンバー関数 [Edit](../Topic/CRecordset::Edit.md) を呼び出して、処理を開始します。  
  
2.  現在のレコードのフィールド値を変更します。  
  
3.  操作終了後は、通常、[Update](../Topic/CRecordset::Update.md) メンバー関数を呼び出して更新内容をコミットします。  
  
 共有ロックでは、**Update** が呼び出されている間だけ、データ ソース上のレコードがロックされます。  マルチ ユーザー環境で共有ロックを利用する場合は、**Update** 失敗条件をアプリケーションで処理する必要があります。  排他ロックでは、**Edit** が呼び出されるとすぐにレコードがロックされ、**Update** が呼び出されるまで解除されません。エラーは、**Update** の戻り値 **FALSE** ではなく、`CDBException` 機構によって示されます。  排他ロックでは、**Update** 処理が終了するまで同一レコードに対する他のアクセスが待たされるため、他のユーザーの処理効率が低下します。  
  
##  <a name="_core_locking_records_in_your_recordset"></a> レコードをロックする方法  
 レコードセット オブジェクトの[ロック モード](#_core_record.2d.locking_modes)を既定モード以外に変更するときは、**Edit** を呼び出す前に変更します。  
  
#### レコードセットのロック モードを変更するには  
  
1.  メンバー関数 [SetLockingMode](../Topic/CRecordset::SetLockingMode.md) を **CRecordset::pessimistic** または **CRecordset::optimistic** を指定して呼び出します。  
  
 新しく設定したモードは、再びモードを変更するか、レコードセットを閉じるまで有効です。  
  
> [!NOTE]
>  現在排他ロックをサポートしている ODBC ドライバーは比較的少数です。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: 結合 \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)   
 [レコードセット: レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)