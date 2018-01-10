---
title: "ATL 接続ポイント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2063bd35627fd86c0cab82e4e50e5e8a126ddfa7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-connection-points"></a>ATL コネクション ポイント
接続可能オブジェクトは、着信インターフェイスをサポートしているオブジェクトです。 着信インターフェイスにより、オブジェクトはクライアントと通信できます。 着信インターフェイスごとに、接続可能なオブジェクトは接続ポイントを公開しています。 各着信インターフェイスは、シンクと呼ばれるオブジェクト上のクライアントによって実装されます。  
  
 ![コネクション ポイント](../atl/media/vc2zw31.gif "vc2zw31")  
  
 各接続ポイントをサポートしている、 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)インターフェイスです。 接続可能なオブジェクトを使用してクライアントを接続ポイントを公開する、 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)インターフェイスです。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ATL コネクション ポイント クラス](../atl/atl-connection-point-classes.md)  
 接続ポイントをサポートする ATL クラスを簡単に説明します。  
  
 [オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)  
 オブジェクトに接続ポイントを追加するためのステップについて説明します。  
  
 [ATL コネクション ポイントの例](../atl/atl-connection-point-example.md)  
 接続ポイントの宣言の例を示します。  
  
## <a name="related-sections"></a>関連項目  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
## <a name="see-also"></a>参照  
 [概念](../atl/active-template-library-atl-concepts.md)

