---
title: "ATL コネクション ポイントの例 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コネクション ポイント [C++], 例"
  - "例 [ATL]"
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL コネクション ポイントの例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この例では、アウトゴーイング インターフェイスとしてサポート [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)。オブジェクトの一覧です:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/CPP/atl-connection-point-example_1.h)]  
  
 `IPropertyNotifySink` をアウトゴーイング インターフェイスとして指定すると、`IConnectionPointImpl`ではなくクラス [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) を使用できます。  以下はその例です。  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/CPP/atl-connection-point-example_2.h)]  
  
## 参照  
 [コネクション ポイント](../atl/atl-connection-points.md)