---
title: "標準コマンド ルーティングのオーバーライド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a8f926a2aa9ed48dac24f75850876bbd1e04ef4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-the-standard-command-routing"></a>標準のコマンド ルーティングのオーバーライド
まれなケースで、標準的なフレームワークのルーティングのいくつかのバリエーションを実装する必要がありますとオーバーライドできます。 つまり、オーバーライドすることで、1 つまたは複数のクラスでルーティングを変更する`OnCmdMsg`それらのクラスです。 そのための操作を行います。  
  
-   クラスには、既定以外のオブジェクトに渡す順序を中断します。  
  
-   またはコマンド ターゲットで新しい既定以外のオブジェクトでさらにコマンドを渡すこと可能性があります。  
  
 ルーティングにいくつかの新しいオブジェクトを挿入する場合、そのクラスは、コマンド ターゲット クラスをする必要があります。 オーバーライド元のバージョンの`OnCmdMsg`、オーバーライドしているバージョンを呼び出してください。 参照してください、 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg)クラスのメンバー関数`CCmdTarget`で、 *『 MFC リファレンス*とバージョンのようなクラスを`CView`と**CDocument**で、例については、ソース コードを指定します。  
  
## <a name="see-also"></a>参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

