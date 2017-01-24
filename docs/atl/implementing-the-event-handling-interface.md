---
title: "イベント処理インターフェイスの実装 | Microsoft Docs"
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
  - "ATL, イベント処理"
  - "イベント処理, ATL"
  - "インターフェイス, イベントとイベント シンク"
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント処理インターフェイスの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL は、イベントの処理に必要な 3 つすべての要素の使用: イベント インターフェイスを実装し、イベント ソースとイベント ソースを unadvising に指示されます。  に実行する必要がある正確な手順は、イベント インターフェイスの型と、アプリケーションのパフォーマンス要件によって異なります。  
  
 ATL を使用してインターフェイスを実装する最も一般的な方法は次のとおりです:  
  
-   カスタム インターフェイスから直接派生します。  
  
-   タイプ ライブラリに記述されているデュアル インターフェイスの [IDispatchImpl](../atl/reference/idispatchimpl-class.md) から派生します。  
  
-   タイプ ライブラリに記述されているディスパッチ インターフェイスの [IDispEventImpl](../atl/reference/idispeventimpl-class.md) から派生します。  
  
-   実行時に型情報を読み込まないことで、効率を改善する場合のタイプ ライブラリに記述されていないディスパッチ インターフェイスの [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) から取得するか。  
  
 カスタム、デュアル インターフェイスを実装する場合は、[AtlAdvise](../Topic/AtlAdvise.md) か [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)を呼び出して、イベント ソースに指示する必要があります。  独自の呼び出しによって返されるクッキーを追跡する必要があります。  接続を解除呼び出し [AtlUnadvise](../Topic/AtlUnadvise.md)。  
  
 `IDispEventImpl` か `IDispEventSimpleImpl`を使用してディスパッチ インターフェイスを実装すると、[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)を呼び出して、イベント ソースに指示する必要があります。  接続を解除呼び出し [IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)。  
  
 複合コントロールの基本クラスとして `IDispEventImpl` を使用すると、シンク マップに示されたイベント ソースが自動的に表示され、[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)を使用して unadvised です。  
  
 `IDispEventImpl` と `IDispEventSimpleImpl` のクラスは、のクッキーを管理します。  
  
## 参照  
 [イベント処理](../Topic/Event%20Handling%20and%20ATL.md)