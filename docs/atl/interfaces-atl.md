---
title: "インターフェイス (ATL) | Microsoft Docs"
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
  - "COM インターフェイス"
  - "インターフェイス, COM"
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# インターフェイス (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスは、オブジェクトが外部の環境に機能を公開する方法です。  COM では、インターフェイスはオブジェクトによって実装される関数へのポインターのテーブル \(vtable C \+\+.など\) です。  テーブルは、関数がそのインターフェイスを表しますポイントし、そのインターフェイスのメソッドです。  オブジェクトは、選択するのと同じインターフェイスを公開できます。  
  
 各インターフェイスは、基本的な COM インターフェイス、[IUnknown](../atl/iunknown.md)に基づいています。  **IUnknown** のメソッドは、オブジェクトによって公開される他のインターフェイスに移動できます。  
  
 また、各インターフェイスは、インターフェイス ID \(IID\) が与えられます。  この一意性は、インターフェイスのバージョン管理をサポートすることが容易になります。  インターフェイスの IID の新しいバージョンが、新しいインターフェイスです。  
  
> [!NOTE]
>  標準の COM の IID および OLE インターフェイスが定義されます。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [COM Objects and Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms690343)