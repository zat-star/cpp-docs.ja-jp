---
title: "コネクション ポイント クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.connection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], コネクション ポイント"
  - "コネクション ポイント クラス"
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コネクション ポイント クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスは、コネクション ポイントをサポートします:  
  
-   [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) は、コネクション ポイント コンテナーを実装します。  
  
-   [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) は、コネクション ポイントを実装します。  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) は [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) のインターフェイスを表すコネクション ポイントを実装します。  
  
-   [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) は、コネクション ポイント シンクとの間の無制限の接続を管理します。  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) は、コネクション ポイント シンクとの間の接続の数を管理します。  
  
-   [CFirePropNotifyEvent](../Topic/CFirePropNotifyEvent%20Class.md) は、オブジェクトのプロパティが変更された通知しますまたは変更することを通知するクライアント シンクが。  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) は、ATL COM オブジェクトのコネクション ポイントをサポートします。  これらのコネクション ポイントは、の COM オブジェクトによって提供されるイベント シンク マップにマップされます。  
  
-   適切なハンドラーにイベントをルーティング、クラスのイベント シンク マップとともに[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) の 作業が機能します。  
  
## 関連トピック  
 [コネクション ポイント](../atl/atl-connection-points.md)  
  
 [イベント処理と ATL](../Topic/Event%20Handling%20and%20ATL.md)  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)   
 [コネクション ポイントに関するマクロ](../atl/reference/connection-point-macros.md)   
 [コネクション ポイントに関するグローバル関数](../Topic/Connection%20Point%20Global%20Functions.md)