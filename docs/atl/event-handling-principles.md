---
title: "イベント処理の原則 | Microsoft Docs"
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
  - "デュアル インターフェイス, イベント インターフェイス"
  - "イベント処理, アドバイズ (イベント ソースを)"
  - "イベント処理, デュアルのイベント インターフェイス"
  - "イベント処理, 実装"
  - "インターフェイス, イベントとイベント シンク"
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント処理の原則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべてのイベントの処理に共通 3 ステップがあります。  :必要です。  
  
-   では、オブジェクトのイベント インターフェイスを実装します。  
  
-   、オブジェクトがイベントを受信するイベント ソースに指示します。  
  
-   、のオブジェクトが、イベントを受信する必要がない場合に Unadvise イベント ソース。  
  
 ユーザーがイベントのインターフェイスを実装する方法は、型によって異なります。  イベントのインターフェイスは、vtable、デュアル、ディスパッチ インターフェイスまたはのいずれかになります。  また、インターフェイスを定義するイベントのソースまで、デザイナー; これには、インターフェイスを実装するまで、あります。  
  
> [!NOTE]
>  イベントのインターフェイスがデュアルである必要があり、技術的な理由がないと使用を避けるの一部の適切なデザイン理由は、倍になりますあります。  ただし、これは、イベント ソースのデザイナー\/実装によって行われる意思決定です。  イベント `sink`の観点から作業しているため、考慮することを選択できない可能性があるイベント インターフェイスをデュアル必要がありますが、無効を実装する。  デュアル インターフェイスの詳細については、[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)を参照してください。  
  
 イベント ソースに指示することは 3 ステップ分割することがあります:  
  
-   [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)のソース オブジェクトを照会します。  
  
-   目的のイベント インターフェイスの IID を渡す呼び出し [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476)。  成功すると、これはコネクション ポイント オブジェクトの [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) のインターフェイスを返します。  
  
-   イベント シンク **IUnknown** を渡す呼び出し [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815)。  成功すると、これは接続を表す `DWORD` のクッキーを返します。  
  
 正常にイベントの受信の対象を登録した場合は、オブジェクトのイベント インターフェイスのメソッドは、イベントに従ってソース オブジェクトから発生すると呼び出されます。  はイベントを受け取る必要がない場合 [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608)によってコネクション ポイントに、クッキーを渡すことができます。  これは、シンク ソースとの間の接続を解除。  
  
 イベントを処理するときに循環参照が発生しないように注意してください。  
  
## 参照  
 [イベント処理](../Topic/Event%20Handling%20and%20ATL.md)