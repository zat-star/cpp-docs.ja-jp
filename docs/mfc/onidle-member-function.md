---
title: "OnIdle メンバー関数は、|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnIdle
dev_langs: C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dfbc0a1f20cb6cc01143ed6f07a63e84b53be6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="onidle-member-function"></a>OnIdle メンバー関数
Windows メッセージを処理するないときに、フレームワーク、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は、 [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (MFC ライブラリ リファレンス 』 で説明)。  
  
 オーバーライド`OnIdle`バック グラウンド タスクを実行します。 既定のバージョンでは、ツール バー ボタンなどのユーザー インターフェイス オブジェクトの状態を更新し、その操作の過程で、フレームワークによって作成された一時オブジェクトのクリーンアップを実行します。 次の図は、メッセージ ループを呼び出す方法を示しています。`OnIdle`キューにメッセージがない場合にします。  
  
 ![メッセージのループ プロセス](../mfc/media/vc387c1.gif "vc387c1")  
メッセージ ループ  
  
 詳細については、アイドル ループで何ができる、次を参照してください。[アイドル ループ プロセシング](../mfc/idle-loop-processing.md)です。  
  
## <a name="see-also"></a>参照  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
