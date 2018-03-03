---
title: "ヒント コントロールのツールの設定 |Microsoft ドキュメント"
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
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 406e35b6ab694ca972d4cd6add0dcca7586e5005
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-tool-tip-control"></a>ツール ヒント コントロールの設定値
ツール ヒント コントロール ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) は、アクティブまたは非アクティブに設定できます。 アクティブに設定すると、ツールの上にカーソルがあるときにツール ヒント コントロールが表示されます。 非アクティブに設定すると、ツールの上にカーソルがあってもツール ヒント コントロールは表示されません。 [Activate](../mfc/reference/ctooltipctrl-class.md#activate) を呼び出し、ツール ヒント コントロールをアクティブまたは非アクティブにします。  
  
 ツール ヒント コントロールのオーナー ウィンドウがアクティブか非アクティブかに関係なく、ツールの上にカーソルがあるときにツール ヒントを表示するには、 **TTS_ALWAYSTIP** スタイルを使用してツール ヒントをアクティブに設定します。 このスタイルを使用しない場合、ツール ヒントはツールのオーナー ウィンドウがアクティブのときには表示されますが、ウィンドウが非アクティブのときには表示されません。  
  
 ほとんどのアプリケーションには、メニュー コマンドに対応するツールを組み込んだツールバーがあります。 このようなツールには、対応するメニュー項目と同じテキストのツール ヒント コントロールを表示すると便利です。 コントロールがある場合を除き、ツール ヒント コントロールに渡されるすべての文字列からアンパサンド (&) アクセラレータの文字が、システムによって自動的に取り除か、 **TTS_NOPREFIX**スタイル。  
  
## <a name="see-also"></a>参照  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

