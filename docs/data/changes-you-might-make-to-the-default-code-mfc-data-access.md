---
title: "変更 (MFC データ アクセス) の既定のコードに加える可能性があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 197277a68131c9d63e3eab2f1404cf97169be1f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>既定の処理の変更 (MFC データ アクセス)
[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)が 1 つのテーブル内のすべてのレコードを選択したレコード セット クラスを書き込みます。 この動作は多くの場合、次の 1 つ以上の方法で変更する必要があります。  
  
-   レコードセットのフィルターまたは並べ替え順序の設定。 これを行う`OnInitialUpdate`レコード セット オブジェクトを構築する前にその**開く**メンバー関数が呼び出されます。 詳細については、次を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../data/odbc/recordset-filtering-records-odbc.md)と[レコード セット: レコードの並べ替え (ODBC)](../data/odbc/recordset-sorting-records-odbc.md)です。  
  
-   レコードセットのパラメーター化。 実際のランタイム パラメーター値はフィルターの後に指定します。 詳細については、次を参照してください[レコード セット: レコード セット (ODBC) のパラメーター化。](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   カスタマイズした SQL 文字列を渡す、[開く](../mfc/reference/crecordset-class.md#open)メンバー関数。 この方法で行うことができますの詳細については、次を参照してください。 [SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
## <a name="see-also"></a>参照  
 [レコード ビューを使用します。](../data/using-a-record-view-mfc-data-access.md)