---
title: "ストアド プロシージャを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a79ca28b3ae509ef5e493a23222ac76ad2352c9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="using-stored-procedures"></a>ストアド プロシージャの使用
ストアド プロシージャは、データベースに格納されている実行可能オブジェクトです。 ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しに似ています。 (またはの代わりに実行するクライアント アプリケーションでステートメントを準備する)、データ ソースでストアド プロシージャを使用すると、パフォーマンスの向上、ネットワーク オーバーヘッドの削減、および一貫性の向上、および精度を含め、いくつかの利点が提供することができます。  
  
 ストアド プロシージャは、任意の数 (0 を含む) を持つことができます入力または出力パラメーターと戻り値を渡すことができます。 特定のデータ値またはパラメーター マーカーを使用して、ハード コード パラメーターの値ことができます (疑問符 () '?')。  
  
> [!NOTE]
>  CLR の SQL Server で Visual C を使用して作成したストアド プロシージャをコンパイルする必要があります、 **/clr:safe**コンパイラ オプション。  
  
 OLE DB プロバイダーの SQL Server (SQLOLEDB) には、データを返すプロシージャを使用して格納されている次のメカニズムがサポートされています。  
  
-   プロシージャで SELECT ステートメントごとでは、結果セットを生成します。  
  
-   プロシージャは、出力パラメーターを使用してデータを返すことができます。  
  
-   プロシージャは、整数のリターン コードを持つことができます。  
  
> [!NOTE]
>  できませんストアド プロシージャを使用する、OLE DB provider for Jet そのプロバイダーがストアド プロシージャをサポートしていないためクエリ文字列では、定数のみを使用します。  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)