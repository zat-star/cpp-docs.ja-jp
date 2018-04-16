---
title: "単純な読み取り専用プロバイダーの作成 |Microsoft ドキュメント"
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
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 830ba99037607f4fc8ceac9bad451381c30c7786
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成
ATL プロジェクト ウィザードと ATL OLE DB プロバイダー ウィザードを使用して、OLE DB プロバイダーを作成した場合は、サポートするその他の機能を追加できます。 コンシューマーにし、どのような条件を送信するデータの種類を確認するには、プロバイダーのデザインを開始します。 これは、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートするために必要かどうかを判断するのには特に重要です。 優れた設計では、事前には、実装とテストに高速化されます。  
  
 2 つの部分の例を示します。  
  
-   最初の部分の表示方法[単純な読み取り専用プロバイダーの作成](../../data/oledb/implementing-the-simple-read-only-provider.md)1 組の文字列を読み取る。  
  
-   2 番目の部分の表示方法[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)追加することによって、`IRowsetLocate`インターフェイスです。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)