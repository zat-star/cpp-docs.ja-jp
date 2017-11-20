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
ms.openlocfilehash: 67ffacffde8dc13e49a09358efcafefd751619ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの作成
ATL プロジェクト ウィザードと ATL OLE DB プロバイダー ウィザードを使用して、OLE DB プロバイダーを作成した場合は、サポートするその他の機能を追加できます。 コンシューマーにし、どのような条件を送信するデータの種類を確認するには、プロバイダーのデザインを開始します。 これは、コマンド、トランザクション、およびその他の省略可能なオブジェクトをサポートするために必要かどうかを判断するのには特に重要です。 優れた設計では、事前には、実装とテストに高速化されます。  
  
 2 つの部分の例を示します。  
  
-   最初の部分の表示方法[単純な読み取り専用プロバイダーの作成](../../data/oledb/implementing-the-simple-read-only-provider.md)1 組の文字列を読み取る。  
  
-   2 番目の部分の表示方法[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)追加することによって、`IRowsetLocate`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)