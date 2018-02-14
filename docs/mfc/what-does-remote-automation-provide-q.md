---
title: "リモート オートメーションの機能 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4a82b26a1e6c208a584dfd19ebfd4530b4bdf76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="what-does-remote-automation-provide"></a>リモート オートメーションの機能
リモート オートメーションにより、プログラムを呼び出す`IDispatch`1 台のコンピューターから別の実装です。 具体的には、オートメーションに必要なその他のインターフェイスもサポートしています。 **IEnumVARIANT**のコレクションのサポート。 これに他の任意の COM インターフェイスを分散する機能が用意されていません (を除く**IUnknown**、もちろん) と、標準のオートメーションなどが含まれているオートメーションでサポートされているデータの種類に対してのみマーシャ リングはサポートします。  
  
 この機能のセットには、メソッドとプロパティ、コレクションまたはアクセス可能なネットワーク ノードで実行されているオブジェクトの他のオートメーション オブジェクトを返すものも含めにアクセスするプログラムができるようにします。 場合は、クライアント コンピューターは、適切なソフトウェアを実行している、可能であれば再度 (これは 32 ビットおよび 64 ビット クライアントにのみ、および概念的には似ていますが、イベントには使用されませんが、自動化機能を使って、クライアントにコールバックするサーバー同じ機構)。  
  
 リモート オートメーション サーバーとして動作するアプリケーションは、実行可能ファイルとして実装する必要があります (つまり、「インプロセス サーバー」ではなく、「ローカル サーバー」として)。  
  
## <a name="see-also"></a>参照  
 [ここではリモート オートメーションを使用](where-does-remote-automation-fit-in-q.md)   
 [DCOM の歴史](../mfc/history-of-dcom.md)
