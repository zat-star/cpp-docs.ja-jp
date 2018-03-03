---
title: "ウィンドウの破棄順序 |Microsoft ドキュメント"
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
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b873d51f585336425537756064582eb709988f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="window-destruction-sequence"></a>ウィンドウの破棄順序
ユーザーがウィンドウの既定値であるフレーム ウィンドウを閉じるときに、MFC フレームワーク[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラーの呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)です。 Windows のウィンドウが破棄されるときに呼び出されます最後のメンバー関数は、 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)、呼び出しを行って、クリーンアップ処理によって、[既定](../mfc/reference/cwnd-class.md#default)メンバーが、Windows のクリーンアップを実行する関数を呼び出す最後に、仮想メンバー関数[PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)です。 [CFrameWnd](../mfc/reference/cframewnd-class.md)の実装`PostNcDestroy`C++ ウィンドウ オブジェクトを削除します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>参照  
 [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

