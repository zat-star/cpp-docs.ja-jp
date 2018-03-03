---
title: "COM の概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a8953949e722265afabc22410174b84c017276c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-com"></a>COM の概要
COM では、どの OLE と ActiveX コントロールのビルドで、基本的な「オブジェクト モデル」がします。 COM は、他のコンポーネントおよびホスト アプリケーションには、その機能を公開するオブジェクトを許可します。 オブジェクトがそれ自体を公開する方法と、プロセス間やネットワークのこの公開の動作を定義します。 COM では、オブジェクトのライフ サイクルも定義します。  
  
 COM を基本にはこれらの概念を示します。  
  
-   [インターフェイス](../atl/interfaces-atl.md)— オブジェクトを使用するには、機能を公開するメカニズムです。  
  
-   [IUnknown](../atl/iunknown.md) -他のすべてのユーザーは基になる基本インターフェイスです。 参照カウントや COM を介して実行メカニズムを照会するインターフェイスを実装します。  
  
-   [参照カウント](../atl/reference-counting.md)— 手法を使用するオブジェクト (または、厳密には、インターフェイス) を決定が使用されていない、つまり、自身を削除するために解放場合にします。  
  
-   [QueryInterface](../atl/queryinterface.md) -特定のインターフェイスのオブジェクトをクエリに使用する方法です。  
  
-   [マーシャ リング](../atl/marshaling.md)— スレッド、プロセス、および場所に依存しないのため、ネットワークの境界を越えて使用するオブジェクトをできる機構です。  
  
-   [集計](../atl/aggregation.md)-別の 1 つのオブジェクトの作成に使用できる方法を使用します。  
  
## <a name="see-also"></a>参照  
 [COM と ATL の概要](../atl/introduction-to-com-and-atl.md)   
 [コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)

