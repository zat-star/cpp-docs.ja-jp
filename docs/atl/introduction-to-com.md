---
title: "COM の概要 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM"
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# COM の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM は、ActiveX コントロールをビルドおよび OLE かの基本的な「オブジェクト モデル」です。  COM は、オブジェクトが他のコンポーネントとホスト アプリケーションに機能を公開するようにします。  これは、オブジェクトが公開する方法と、この脆弱性がプロセスとネットワーク経由で動作するかを定義します。  COM は、オブジェクトの有効期間を定義します。  
  
 COM に Foundation では、これらの概念です:  
  
-   [インターフェイス](../atl/interfaces-atl.md) —オブジェクトに機能を公開する機構。  
  
-   [IUnknown](../atl/iunknown.md) —他に基づく基本インターフェイス。  これは、COM を通じて実行機構を照会参照カウント、およびインターフェイスを実装します。  
  
-   —[参照カウント](../atl/reference-counting.md) ために、自身を削除可用性使用されているかオブジェクト \(、\)、インターフェイスを決定する方法。  
  
-   —[QueryInterface](../atl/queryinterface.md) 特定のインターフェイスのオブジェクトをクエリに使用されるメソッド。  
  
-   [マーシャリング](../atl/marshaling.md) —スレッド、プロセス、ネットワークの境界を越えて使用するオブジェクトを有効にする機構の場所に依存ができます。  
  
-   —[集計](../atl/aggregation.md) が他のオブジェクトを使用できるいずれの方法。  
  
## 参照  
 [COM および ATL の概要](../atl/introduction-to-com-and-atl.md)   
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)