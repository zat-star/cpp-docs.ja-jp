---
title: "コマンド ルーティング クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.command
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7e49c92b909abb01f3daec9e16f0e08b2a31c89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-routing-classes"></a>コマンド ルーティング クラス
ように、ユーザーは、メニューまたはマウスでコントロール バーのボタンを選択して、アプリケーションと対話する、アプリケーションは、適切なコマンド ターゲット オブジェクトに影響を受けるユーザー インターフェイス オブジェクトからメッセージを送信します。 コマンド ターゲット クラスから派生した`CCmdTarget`含める[CWinApp](../mfc/reference/cwinapp-class.md)、 [CWnd](../mfc/reference/cwnd-class.md)、 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)、 [CDocument](../mfc/reference/cdocument-class.md)、 [CView](../mfc/reference/cview-class.md)、およびそれらから派生したクラスです。 フレームワークでは、コマンドの自動ルーティング コマンドは、アプリケーションで現在アクティブな最も適切なオブジェクトで処理できるようにサポートしています。  
  
 クラスのオブジェクト`CCmdUI`コマンド ターゲットの更新コマンド UI に渡される ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) 特定のコマンド用のユーザー インターフェイスの状態を更新するためのハンドラー (たとえば、チェックに削除するメニュー項目から確認) します。 メンバーの関数を呼び出す、 `CCmdUI` UI オブジェクトの状態を更新するオブジェクト。 このプロセスは、特定のコマンドに関連付けられた UI オブジェクトがメニュー項目、ボタン、またはその両方であるかどうかは同じです。  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 受信およびメッセージに応答できるオブジェクトのすべてのクラスの基底クラスとして機能します。  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 メニュー項目またはコントロール バー ボタンなどのユーザー インターフェイス オブジェクトを更新するためのプログラム インターフェイスを提供します。 コマンド ターゲット オブジェクトを有効に、無効に、チェック、およびオブジェクトとユーザー インターフェイス オブジェクトをクリアできます。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

