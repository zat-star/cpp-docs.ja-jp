---
title: "データ ソース: データ ソース (ODBC) のスキーマの判定 |Microsoft ドキュメント"
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
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc425cf767db6939223288ebe74dcbc7fd4cf5b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>データ ソース : データ ソースのスキーマの判定 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 データ メンバーを設定する、`CRecordset`オブジェクト、接続先データ ソースのスキーマを特定する必要があります。 データ ソースのスキーマを決定するには、データ ソース内のテーブルの一覧、各テーブルの列、各列のデータ型のリストとインデックスの有無を取得するが含まれます。  
  
## <a name="see-also"></a>参照  
 [データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)   
 [データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)