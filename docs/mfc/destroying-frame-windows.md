---
title: "フレーム ウィンドウの破棄 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1cbd96f5044626c7c3c07e8fca115c2b1dca8cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-frame-windows"></a>フレーム ウィンドウの破棄
MFC フレームワークは、フレームワークのドキュメントとビューに関連付けられているこれらのウィンドウの作成とウィンドウの破棄を管理します。 その他のウィンドウを作成する場合を破棄します。  
  
 ユーザーがウィンドウの既定値であるフレーム ウィンドウを閉じるときに、フレームワークで[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラーの呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)です。 Windows のウィンドウが破棄されるときに呼び出されます最後のメンバー関数は、 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)、呼び出しを行って、クリーンアップ処理によって、[既定](../mfc/reference/cwnd-class.md#default)メンバーが、Windows のクリーンアップを実行する関数を呼び出す最後に、仮想メンバー関数[PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)です。 [CFrameWnd](../mfc/reference/cframewnd-class.md)の実装`PostNcDestroy`C++ ウィンドウ オブジェクトを削除します。 C++ を使用しないで**削除**フレーム ウィンドウの演算子。 代わりに、`DestroyWindow` を使用してください。  
  
 メイン ウィンドウの終了時にアプリケーションを閉じます。 未保存のドキュメントが変更がある場合、フレームワークは、ドキュメントを保存するかどうかを確認するメッセージ ボックスを表示され、必要に応じて、適切なドキュメントが保存されていることを確認します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>参照  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

