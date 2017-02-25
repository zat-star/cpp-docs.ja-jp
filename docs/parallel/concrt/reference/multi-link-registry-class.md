---
title: "multi_link_registry クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::multi_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multi_link_registry クラス"
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# multi_link_registry クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。  
  
## 構文  
  
```  
template<  
   class _Block  
>  
class multi_link_registry : public network_link_registry<_Block>;  
```  
  
#### パラメーター  
 `_Block`  
 `multi_link_registry` オブジェクトに格納されているブロック データ型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[multi\_link\_registry::multi\_link\_registry コンストラクター](../Topic/multi_link_registry::multi_link_registry%20Constructor.md)|`multi_link_registry` オブジェクトを構築します。|  
|[multi\_link\_registry::~multi\_link\_registry デストラクター](../Topic/multi_link_registry::~multi_link_registry%20Destructor.md)|`multi_link_registry` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[multi\_link\_registry::add メソッド](../Topic/multi_link_registry::add%20Method.md)|リンクを `multi_link_registry` オブジェクトに追加します。\([network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md) をオーバーライドします。\)|  
|[multi\_link\_registry::begin メソッド](../Topic/multi_link_registry::begin%20Method.md)|`multi_link_registry` オブジェクトの 1 つ目の要素への反復子を返します。\([network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md) をオーバーライドします。\)|  
|[multi\_link\_registry::contains メソッド](../Topic/multi_link_registry::contains%20Method.md)|指定されたブロックの `multi_link_registry` オブジェクトを検索します。\([network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md) をオーバーライドします。\)|  
|[multi\_link\_registry::count メソッド](../Topic/multi_link_registry::count%20Method.md)|`multi_link_registry` オブジェクト内の項目の数をカウントします。\([network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md) をオーバーライドします。\)|  
|[multi\_link\_registry::remove メソッド](../Topic/multi_link_registry::remove%20Method.md)|`multi_link_registry` オブジェクトからリンクを削除します。\([network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md) をオーバーライドします。\)|  
|[multi\_link\_registry::set\_bound メソッド](../Topic/multi_link_registry::set_bound%20Method.md)|`multi_link_registry` オブジェクトが保持できるリンク数の上限を設定します。|  
  
## 継承階層  
 [network\_link\_registry](../Topic/network_link_registry%20Class.md)  
  
 `multi_link_registry`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry クラス](../Topic/single_link_registry%20Class.md)