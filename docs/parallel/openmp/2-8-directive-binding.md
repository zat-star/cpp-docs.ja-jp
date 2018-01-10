---
title: "2.8 ディレクティブのバインディング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 731c509c0c2f300d7a9d4e39261ffedd1c22a094
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="28-directive-binding"></a>2.8 ディレクティブのバインディング
ディレクティブの動的バインドは、次の規則に従う必要があります。  
  
-   **の**、**セクション**、**単一**、**マスター**、および**バリア**ディレクティブにバインド、動的にそれを囲む**並列**いずれかが存在する場合、いずれかの値に関係なく、**場合**そのディレクティブに存在可能な句です。 並列領域は、現在実行していない場合、ディレクティブは、マスター スレッドでのみで構成されるチームによって実行されます。  
  
-   **注文**ディレクティブに動的にそれを囲むバインド**の**します。  
  
-   **アトミック**ディレクティブに関連する排他アクセスを適用する**アトミック**現在チームだけでなく、すべてのスレッドでのディレクティブ。  
  
-   **重大**ディレクティブに関連する排他アクセスを適用する**重要な**現在チームだけでなく、すべてのスレッドでのディレクティブ。  
  
-   ディレクティブもバインドできません、ディレクティブ、最も近いの外側に動的にそれを囲む**並列**です。