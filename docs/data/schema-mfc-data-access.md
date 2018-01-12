---
title: "スキーマ (MFC データ アクセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 76a38525f7fdf451d40f555d76d3557cbc155936
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="schema--mfc-data-access"></a>スキーマ (MFC データ アクセス)
データベース スキーマは、データベース内のテーブルとデータベース ビューの現在の構造を記述するものです。 通常、ウィザードで生成されたコードでは、レコードセットからアクセスするテーブルのスキーマは変更されないことを想定しています。ただし、データベース クラスでは、ある程度のスキーマの変更 (バインドされていない列の追加、並べ替え、削除など) に対応できます。 テーブルが変更された場合は、そのテーブルのレコードセットを手動で更新し、アプリケーションを再コンパイルする必要があります。  
  
 ウィザードで生成されるコードを補うことで、コンパイル時にスキーマの詳細が不明なデータベースが処理されるようにできます。 詳細については、次を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
## <a name="see-also"></a>参照  
 [データ アクセス プログラミング (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [レコードセット (ODBC)](../data/odbc/recordset-odbc.md)