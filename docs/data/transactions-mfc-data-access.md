---
title: "トランザクション (MFC データ アクセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2f0c028eaf58e828366ae9534ff06b53254e3601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="transactions--mfc-data-access"></a>トランザクション (MFC データ アクセス)
トランザクションの概念は、データベースの結果の状態が、一連の操作の全体的な成功に依存するケースを処理するために開発されました。 このような状況は、連続した操作によって前の操作の結果が変更される場合があるために発生します。 このような場合は、いずれかの操作が失敗すると、最終的な状態が不定になることがあります。  
  
 この問題を解決するため、トランザクションでは最終的な結果の整合性が確保されるように、一連の操作がグループ化されます。 すべての操作に成功してからコミット (データベースに書き込み) するか、トランザクション全体が失敗するかのどちらかとなります。 トランザクションのキャンセルは、ロールバックと呼ばれます。 ロールバックにより、変更を復元し、データベースをトランザクション前の状態に戻すことができます。  
  
 たとえば、自動化された銀行トランザクションで口座 A から口座 B にお金を振り替える場合は、資金を正しく処理するには A からの引き落としと B への預け入れがどちらも成功する必要があります。そうでない場合はトランザクション全体を失敗とします。  
  
 トランザクションは、次の性質を意味する ACID プロパティが必要です。  
  
-   **原子性**か、すべての作業が実行されるかのいずれかには、以外のトランザクションは、作業のアトミック単位と正確に 1 回実行します。  
  
-   **整合性**トランザクションには、データの別の一貫性のある状態に一貫性のある 1 つの状態のデータを変換するデータの一貫性が維持されます。 トランザクションにより連結されたデータの意味は保持される必要があります。  
  
-   **分離**トランザクションは、分離の単位と、それぞれと同時実行トランザクションとは無関係に発生します。 あるトランザクションが、別のトランザクションの中間段階にかかわらないようにする必要があります。  
  
-   **持続性**トランザクションは、復元の単位。 トランザクションが成功した場合、システムがクラッシュまたはシャットダウンしてもその更新内容は保持されます。 トランザクションが失敗した場合、システムは、そのトランザクションをコミットする前の状態のままになります。  
  
 OLE DB のトランザクションをサポートすることができます (を参照してください[OLE db のトランザクションのサポート](../data/oledb/supporting-transactions-in-ole-db.md)) または ODBC (を参照してください[トランザクション (ODBC)](../data/odbc/transaction-odbc.md))。  
  
 分散トランザクションは、分散されたデータ (複数のネットワーク コンピューター システムにあるデータ) を更新するトランザクションです。 分散システムでトランザクションをサポートする場合は、OLE DB トランザクション サポートではなく ADO.NET を使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [データ アクセス プログラミング (MFC/ATL)](../data/data-access-programming-mfc-atl.md)