---
title: "デュアル インターフェイスとイベント | Microsoft Docs"
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
  - "デュアル インターフェイス, イベント"
  - "イベント [C++], デュアル インターフェイス"
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# デュアル インターフェイスとイベント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

double としてイベント インターフェイスをデザインすることは可能ですが、破棄しないいくつかの適切なデザイン理由があります。  基本的な理由は、イベントのソースが vtable または `Invoke`によってのみイベントを発生させることではありません。  イベント ソースを直接 vtable メソッド呼び出しとしてイベントを発生する場合、`IDispatch` のメソッドが使用されず、インターフェイスが、純粋 vtable インターフェイス必要があることを明示的です。  イベント ソースが `Invoke`の呼び出しとしてイベントを発生する場合、vtable メソッドが使用されず、ディスパッチ インターフェイスが必要であることを明示的です。  定義する場合は、イベントはために、倍になりますが、使用しないインターフェイスの一部を実装する必要があります。クライアントがインターフェイスです。  
  
> [!NOTE]
>  この引数は、デュアル インターフェイスに、一般には適用されません。  実装の観点から、クライアントがアクセスできるインターフェイスを実装するが、便利な、完全サポートされる方法は、倍になります。  
  
 デュアル インターフェイスのイベントを避けるそのほかの理由があります; Visual Basic が Internet Explorer でもサポートされていません。  
  
## 参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)