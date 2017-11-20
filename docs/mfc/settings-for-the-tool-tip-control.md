---
title: "ヒント コントロールのツールの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c7e88956ab7c7fe1c03d10a8519aedad4767e48e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="settings-for-the-tool-tip-control"></a>ツール ヒント コントロールの設定値
ツール ヒント コントロール ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) は、アクティブまたは非アクティブに設定できます。 アクティブに設定すると、ツールの上にカーソルがあるときにツール ヒント コントロールが表示されます。 非アクティブに設定すると、ツールの上にカーソルがあってもツール ヒント コントロールは表示されません。 [Activate](../mfc/reference/ctooltipctrl-class.md#activate) を呼び出し、ツール ヒント コントロールをアクティブまたは非アクティブにします。  
  
 ツール ヒント コントロールのオーナー ウィンドウがアクティブか非アクティブかに関係なく、ツールの上にカーソルがあるときにツール ヒントを表示するには、 **TTS_ALWAYSTIP** スタイルを使用してツール ヒントをアクティブに設定します。 このスタイルを使用しない場合、ツール ヒントはツールのオーナー ウィンドウがアクティブのときには表示されますが、ウィンドウが非アクティブのときには表示されません。  
  
 ほとんどのアプリケーションには、メニュー コマンドに対応するツールを組み込んだツールバーがあります。 このようなツールには、対応するメニュー項目と同じテキストのツール ヒント コントロールを表示すると便利です。 コントロールがある場合を除き、ツール ヒント コントロールに渡されるすべての文字列からアンパサンド (&) アクセラレータの文字が、システムによって自動的に取り除か、 **TTS_NOPREFIX**スタイル。  
  
## <a name="see-also"></a>関連項目  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

