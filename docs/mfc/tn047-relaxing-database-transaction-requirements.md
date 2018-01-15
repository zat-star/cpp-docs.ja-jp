---
title: "TN047: データベース トランザクション条件の緩和 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.data
dev_langs: C++
helpviewer_keywords: TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92631d96e8782a80275695ef4bf2623dc1bff833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>テクニカル ノート 47: データベース トランザクション要件の緩和
MFC ODBC データベース クラスのトランザクションの要件を説明するには、このテクニカル ノートでは廃止されました。 データベース クラスがレコード セットの後にカーソルを保持することを必須 MFC 4.2 の前に、 **CommitTrans**または**ロールバック**操作します。 ODBC ドライバーと DBMS がこのレベルのカーソル位置の保存をサポートしていない場合、データベース クラスは、有効にしなかったトランザクションです。  
  
 MFC 4.2 以降では、データベース クラスではカーソル位置を保持する必要がという制限が緩和されてです。 ドライバーによってサポートされる場合、トランザクションを有効にされます。 、の効果が今すぐ確認する必要があります、 **CommitTrans**または**ロールバック**開いているレコード セットで操作します。 メンバー関数を参照してください[CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior)と[CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

