---
title: "データ ソースへの接続 |Microsoft ドキュメント"
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
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 08872f9e1034c50ca1468d6834f3a44dc06c1ebe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="connecting-to-a-data-source"></a>データ ソースへの接続
ODBC データ ソースは、特定のデータ、そのデータおよびデータ ソース名を使用して記述されるデータ ソースの場所にアクセスするために必要な情報のセットです。 プログラムの観点から、データ ソースには、データ、DBMS、(存在する場合) は、ネットワーク、および ODBC が含まれています。  
  
 データ ソースによって提供されるデータにアクセスするには、場合は、プログラムに、データ ソースに接続を確立してする必要があります。 すべてのデータ アクセスは、その接続を介して管理されます。  
  
 データ ソースへの接続がクラスによってカプセル化された[CDatabase](../../mfc/reference/cdatabase-class.md)です。 ときに、`CDatabase`オブジェクトがデータ ソースに接続されている、することができます。  
  
-   構築[レコード セット](../../mfc/reference/crecordset-class.md)レコードのテーブルまたはクエリを選択します。  
  
-   管理[トランザクション](../../data/odbc/transaction-odbc.md)、すべてバッチ処理の更新は 1 回に、データ ソースにコミット (または、データ ソースは変更されていないため、戻る、トランザクション全体がロールバックされます): データ ソースは、必要なレベルのトランザクションをサポートしている場合。  
  
-   直接実行[SQL](../../data/odbc/sql.md)ステートメントです。  
  
 データ ソース接続の操作が完了したらを閉じる、`CDatabase`オブジェクトおよび破棄するか、新しい接続の再利用します。 データ ソース接続の詳細については、次を参照してください。[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)です。  
  
## <a name="see-also"></a>参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)