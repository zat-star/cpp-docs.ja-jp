---
title: "プロパティとプロパティ ページ クラス | Microsoft Docs"
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
  - "vc.atl.properties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロパティ [ATL]"
  - "プロパティ [ATL], クラス"
  - "プロパティ ページ, クラス"
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロパティとプロパティ ページ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティとプロパティ ページをサポートするクラスを次に示します。  
  
-   [CComDispatchDriver](../Topic/CComDispatchDriver.md) のを取得または設定 `IDispatch` のポインターを通じてオブジェクトのプロパティ。  
  
-   [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) は、ATL によってサポートされるストック プロパティを実装します。  
  
-   [IPerPropertyBrowsingImpl](../Topic/IPerPropertyBrowsingImpl%20Class.md) は、オブジェクトのプロパティ ページ内の情報にアクセスします。  
  
-   [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) は、クライアントが提供するプロパティ バッグにオブジェクトのプロパティを格納します。  
  
-   [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) は、プロパティ シート内の特定のプロパティ ページを管理します。  
  
-   `IPropertyPageImpl`に似た[IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) が、クライアントがプロパティ ページの特定のプロパティを選択できるようにします。  
  
-   [ISpecifyPropertyPagesImpl](../Topic/ISpecifyPropertyPagesImpl%20Class.md) は、オブジェクトによってサポートされるプロパティ ページの CLSID を取得します。  
  
## 関連トピック  
 [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
 [ATL COM プロパティ ページ](../atl/atl-com-property-pages.md)  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)   
 [プロパティ マップに関するマクロ](../atl/reference/property-map-macros.md)