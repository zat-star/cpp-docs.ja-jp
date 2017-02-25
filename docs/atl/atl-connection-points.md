---
title: "ATL コネクション ポイント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, コネクション ポイント"
  - "コネクション ポイント [C++], コネクション ポイントの概要"
  - "接続, コネクション ポイント"
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL コネクション ポイント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

接続可能オブジェクトは、着信インターフェイスをサポートしているオブジェクトです。  着信インターフェイスにより、オブジェクトはクライアントと通信できます。  着信インターフェイスごとに、接続可能なオブジェクトは接続ポイントを公開しています。  各着信インターフェイスは、シンクと呼ばれるオブジェクト上のクライアントによって実装されます。  
  
 ![コネクション ポイント](../atl/media/vc2zw31.gif "vc2ZW31")  
  
 各接続ポイントでは、[IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) インターフェイスがサポートされています。  接続可能オブジェクトは、[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) インターフェイスを通じてクライアントに接続ポイントを公開します。  
  
## このセクションの内容  
 [ATL 接続ポイント クラス](../atl/atl-connection-point-classes.md)  
 接続ポイントをサポートする ATL クラスを簡単に説明します。  
  
 [オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)  
 オブジェクトに接続ポイントを追加するためのステップについて説明します。  
  
 [ATL 接続ポイントの例](../atl/atl-connection-point-example.md)  
 接続ポイントの宣言の例を示します。  
  
## 関連項目  
 [&#91;ATL&#93;](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)