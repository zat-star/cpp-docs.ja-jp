---
title: "単純な読み取り専用プロバイダーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b5f840a6f401d8eb1bcca598d86622deb8f86cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成
ATL プロジェクト ウィザードと ATL OLE DB プロバイダー ウィザードを使用して、OLE DB プロバイダーを作成した場合は、サポートするその他の機能を追加できます。 コンシューマーにし、どのような条件を送信するデータの種類を確認するには、プロバイダーのデザインを開始します。 これは、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートするために必要かどうかを判断するのには特に重要です。 優れた設計では、事前には、実装とテストに高速化されます。  
  
 2 つの部分の例を示します。  
  
-   最初の部分の表示方法[単純な読み取り専用プロバイダーの作成](../../data/oledb/implementing-the-simple-read-only-provider.md)1 組の文字列を読み取る。  
  
-   2 番目の部分の表示方法[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)追加することによって、`IRowsetLocate`インターフェイスです。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)