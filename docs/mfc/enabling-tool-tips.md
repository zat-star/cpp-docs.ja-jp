---
title: "ツール ヒントを有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0555af785d75c9247eb365a03a51161441a4722a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-tool-tips"></a>ツール ヒントを有効にする方法
(フォーム ビュー、またはダイアログ ボックス コントロール) などのウィンドウの子コントロールのツール ヒントのサポートを有効にすることができます。  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>ウィンドウの子コントロールのツール ヒントを有効にするには  
  
1.  呼び出す`EnableToolTips`ツール ヒントを提供するウィンドウです。  
  
2.  内の各コントロールに、文字列を指定して[TTN_NEEDTEXT 通知の](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)ハンドラー。 ハンドラーは、子コントロール (フォーム ビュー クラスなど) を含むウィンドウのメッセージ マップには。 このハンドラーは関数を呼び出すコントロールを識別し、設定**pszText**ツール ヒント コントロールで使用されるテキストを指定します。  
  
## <a name="see-also"></a>参照  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

