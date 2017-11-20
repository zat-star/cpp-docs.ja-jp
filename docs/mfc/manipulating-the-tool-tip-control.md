---
title: "ツール ヒント コントロールの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c932d90cd2d896ebfe861ccd21d67b0071293c64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="manipulating-the-tool-tip-control"></a>ツール ヒント コントロールの操作
クラス`CToolTipCtrl`メンバーのグループのさまざまな属性を制御する関数を提供、`CToolTipCtrl`オブジェクトとツール ヒントのウィンドウ。  
  
 初期、ポップアップでは、ツール ヒント ウィンドウのセットおよびへの呼び出しを使用して取得できる期間を表示および[GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime)と[SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime)です。  
  
 次の関数で、ツール ヒント ウィンドウの外観を変更します。  
  
-   [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin)と[SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin)幅ツール ヒントの境界線とツール ヒントのテキストの取得および設定します。  
  
-   [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth)と[SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth)ツールの最大の幅のヒント ウィンドウの取得および設定します。  
  
-   [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor)と[SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor)ツールの背景色のヒント ウィンドウの取得および設定します。  
  
-   [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor)と[SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor)ツールのテキストの色のヒント ウィンドウの取得および設定します。  
  
 ツール ヒント コントロールなど、重要なメッセージの通知を受信するために**WM_LBUTTONXXX**メッセージ、ツール ヒント コントロールにメッセージを中継する必要があります。 呼び出しを行うには、このリレーの最適な方法[CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)で、`PreTranslateMessage`オーナー ウィンドウの関数。 次の例では、1 つの可能なメソッド (ツール ヒント コントロールと仮定した場合と呼ばれる`m_ToolTip`)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]  
  
 ツール ヒントのウィンドウをすぐに削除するには、呼び出し、 [Pop](../mfc/reference/ctooltipctrl-class.md#pop)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

