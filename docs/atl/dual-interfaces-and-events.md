---
title: "デュアル インターフェイスとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87774f0237eb42c4bd2f97185230b3c869688ca8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dual-interfaces-and-events"></a>デュアル インターフェイスとイベント
デュアルとしてイベント インターフェイスを設計することはできますは、さまざまなしないように適切な設計上の理由があります。 基本的な理由は、イベントのソースが、vtable を使用して、またはを使用してイベントを発生させるだけこと`Invoke`、両方は必要ありません。 イベント ソースが直接 vtable メソッドの呼び出しとしてイベントを発生させる場合、`IDispatch`メソッドは使用されず、インターフェイスが vtable の純粋なインターフェイスであった明確であるとします。 呼び出しと、イベント ソースがイベントを発生させるかどうか`Invoke`vtable メソッドは使用されず、およびが、インターフェイスがディスパッチ インターフェイスであったクリアします。 イベント インターフェイスをデュアル インターフェイスとして定義する場合は、使用されることはありませんインターフェイスの一部を実装するクライアントを必要とするします。  
  
> [!NOTE]
>  この引数は一般にデュアル インターフェイスには適用されません。 実装の観点からは、デュアルは、さまざまなクライアントにアクセス可能であるインターフェイスを実装するすばやく、便利で、かつ適切にサポートされている方法です。  
  
 さらにデュアル イベント インターフェイスを使用しない理由があります。Visual Basic でもインターネット エクスプ ローラーをサポートしています。  
  
## <a name="see-also"></a>参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

