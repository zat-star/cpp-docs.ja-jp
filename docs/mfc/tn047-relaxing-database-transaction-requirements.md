---
title: "テクニカル ノート 47: データベース トランザクション条件の緩和 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN047"
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 47: データベース トランザクション条件の緩和
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC ODBC データベース クラスのトランザクションの要件について検討したこのテクニカル ノートは今後使用しません。  MFC 4.2 以前では、データベース クラスは、カーソルが **CommitTrans** または **Rollback** 操作の後でレコードセットに保持されていることが必要です。  ODBC ドライバーは、DBMS カーソルの保持にこのレベルをサポートしない場合は、データベース クラスは、トランザクションを有効にします。  
  
 MFC 4.2 以降では、データベース クラスは、カーソルの保持を要求する場合の制限を緩めました。  トランザクションは、ドライバーでサポートすると有効になります。  ただし、レコードセットを開くには **CommitTrans** または **Rollback** 操作の影響を確認する必要があります。  詳細については、"メンバー関数 [CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md) と [CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md) を参照してください。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)