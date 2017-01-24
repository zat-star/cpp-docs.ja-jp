---
title: "レコードセット: レコードを大量に追加する方法 (ODBC) | Microsoft Docs"
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
  - "バルク レコードの追加 (レコードセットへの)"
  - "ODBC レコードセット, 追加 (レコードを)"
  - "レコードセット, 追加 (レコードを)"
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: レコードを大量に追加する方法 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 MFC [CRecordset](../Topic/CRecordset%20Class.md) クラスには最適化機能が組み込まれているため、大量の新しいレコードを効率的にテーブルに追加できます。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを使用する場合は、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 [CRecordset::Open](../Topic/CRecordset::Open.md) メンバー関数の **dwOptions** パラメーターには、新しいオプションとして **optimizeBulkAdd** があります。このオプションを使うと、**Requery** や **Close** を呼び出さずに、複数のレコードを連続して効率的に追加できます。  最初の **Update** 呼び出しの前からダーティなフィールドだけが、以降の `AddNew` または **Update** の呼び出しでもダーティとしてマークされます。  
  
 レコードを追加、編集、削除するときに、データベース クラスを通じて ODBC API 関数 **::SQLSetPos** を使う場合は、この最適化処理は不要です。  
  
 ODBC カーソル ライブラリを読み込んでいる場合、または ODBC ドライバーが **::SQLSetPos** による追加、編集、および削除をサポートしていない場合は、この最適化処理によって大量のレコードを効率的に追加できます。  この最適化処理を有効にするには、レコードセットの **Open** 呼び出しの **dwOptions** パラメーターを次のように設定します。  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [レコードセット: レコードのロック \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)