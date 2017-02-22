---
title: "集約 | Microsoft Docs"
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
  - "集約オブジェクト [C++]"
  - "集約 [C++]"
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 集約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトの implementor が別の提供されるサービスを利用してを取得するときに、ビルド済みのオブジェクトがあります。  さらに、第 1 の自然な部分として表示されるように、この 2 番目のオブジェクトを必要になります。  は COM コンテインメントと集約で、両方の目標を達成します。  
  
 集計が含まれている \(外部\) オブジェクトが作成プロセスの一部として含まれる \(内部\) オブジェクトを作成し、内部オブジェクトのインターフェイスが外部によって公開されることを意味します。  オブジェクト自体では、aggregatable に使用できます。  この場合、正しく動作する集計の特定の規則に従う必要があります。  
  
 主に格納されているオブジェクトのすべての **IUnknown** のメソッドの呼び出しが含まれているオブジェクトに代入する必要があります。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [Reusing Objects](http://msdn.microsoft.com/library/windows/desktop/ms678443)