---
title: "IUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM インターフェイス, 基本インターフェイス"
  - "IUnknown インターフェイス"
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) は、他のすべての COM インターフェイスの基本インターフェイスです。このインターフェイスでは、3 つのメソッド \([QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)\) が定義されています。  [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) を使用すると、インターフェイス ユーザーは、オブジェクトに対し、このインターフェイスの別のオブジェクトへのポインターを要求することができます。  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) は、インターフェイスに対する参照カウントを実装します。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [IUnknown and Interface Inheritance](http://msdn.microsoft.com/library/windows/desktop/ms692713)