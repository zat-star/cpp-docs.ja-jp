---
title: "ATL コネクション ポイント クラス | Microsoft Docs"
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
  - "CComDynamicUnkArray クラス, コネクション ポイント クラス"
  - "CComUnkArray クラス, コネクション ポイント クラス"
  - "CFirePropNotifyEvent クラス"
  - "CFirePropNotifyEvent クラス, コネクション ポイント クラス"
  - "コネクション ポイント [C++], ATL クラス"
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL コネクション ポイント クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL は、コネクション ポイントをサポートするために次のクラスを使用します:  
  
-   [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) は、コネクション ポイントを実装します。  表すアウトゴーイング インターフェイスの IID は、テンプレート パラメーターとして渡されます。  
  
-   [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) は、コネクション ポイント コンテナーを実装し、`IConnectionPointImpl` オブジェクトのリストを管理します。  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) は [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) のインターフェイスを表すコネクション ポイントを実装します。  
  
-   [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) は、コネクション ポイント シンクとの間の接続の任意の数を管理します。  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) は、テンプレート パラメーターの指定に従って接続の定義済みの数を管理します。  
  
-   [CFirePropNotifyEvent](../Topic/CFirePropNotifyEvent%20Class.md) は、オブジェクトのプロパティが変更された通知しますまたは変更することを通知するクライアント シンクが。  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) は、ATL COM オブジェクトのコネクション ポイントをサポートします。  これらのコネクション ポイントは、の COM オブジェクトによって提供されるイベント シンク マップにマップされます。  
  
-   適切なハンドラーにイベントをルーティング、クラスのイベント シンク マップとともに[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) の 処理は機能します。  
  
## 参照  
 [コネクション ポイント](../atl/atl-connection-points.md)