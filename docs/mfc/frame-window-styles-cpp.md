---
title: "フレーム ウィンドウ スタイル (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30e597a9d8587128e4de1b2bb80db15143620821
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="frame-window-styles-c"></a>フレーム ウィンドウ スタイル (C++)
フレームワークのフレーム ウィンドウが、ほとんどのプログラムに適しているが、高度な関数を使用して、さらに高い柔軟性を得ることができます[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)と MFC のグローバル関数[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow`メンバー関数は、`CWnd`です。  
  
 適用する場合、 **WS_HSCROLL**と**WS_VSCROLL**メイン フレーム ウィンドウにスタイル、代わりに適用される、 **MDICLIENT**ウィンドウのユーザーが、をスクロールできるように**MDICLIENT**領域。  
  
 場合、ウィンドウの**FWS_ADDTOTITLE**スタイル ビットが設定 (既定である)、ビューのドキュメント、ビューの名前に基づいて、ウィンドウのタイトル バーに表示するタイトルをフレーム ウィンドウに通知します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [MDI 子ウィンドウ (クイック ウォッチ) を管理する](../mfc/managing-mdi-child-windows.md)MDI 子ウィンドウを含む MDI フレーム内のウィンドウ  
  
-   [MFC で作成したウィンドウのスタイルを変更します。](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウ](../mfc/frame-windows.md)

