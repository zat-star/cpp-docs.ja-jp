---
title: "マーシャ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f89b64794c50e381c07749984ce61579951fa02f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling"></a>マーシャ リング
マーシャ リングの COM 手法では、別のプロセスで使用する 1 つのプロセス内のオブジェクトによって公開されるインターフェイスを使用します。 マーシャ リングすると、COM コードを示します (またはインターフェイスの実装者により提供されるコードを使用) プロセス全体にわたり (だけでなく、他のコンピューターで実行されているプロセスをネットワーク経由で) に移動することができる形式にメソッドのパラメーターをパックし、これらのパラメーターをアンパックするのにはもう一方の端。 同様に、COM では、呼び出しから返された場合は、同じ手順を実行する必要があります。  
  
> [!NOTE]
>  マーシャ リングは通常必要ありませんオブジェクトと同じプロセスでオブジェクトによって提供されるインターフェイスを使用する場合です。 ただし、スレッド間でマーシャ リングを必要になる可能性です。  
  
## <a name="see-also"></a>参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [マーシャ リングの詳細](http://msdn.microsoft.com/library/windows/desktop/ms692621)

