---
title: "ツール ヒント コントロールの設定値 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ツールヒント [C++]、アクティブ化"
  - "CToolTipCtrl クラス、設定"
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール ヒント コントロールの設定値
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツール ヒント コントロール \([CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)\) は、アクティブまたは非アクティブに設定できます。 アクティブに設定すると、ツールの上にカーソルがあるときにツール ヒント コントロールが表示されます。 非アクティブに設定すると、ツールの上にカーソルがあってもツール ヒント コントロールは表示されません。[Activate](../Topic/CToolTipCtrl::Activate.md) を呼び出し、ツール ヒント コントロールをアクティブまたは非アクティブにします。  
  
 ツール ヒント コントロールのオーナー ウィンドウがアクティブか非アクティブかに関係なく、ツールの上にカーソルがあるときにツール ヒントを表示するには、**TTS\_ALWAYSTIP** スタイルを使用してツール ヒントをアクティブに設定します。 このスタイルを使用しない場合、ツール ヒントはツールのオーナー ウィンドウがアクティブのときには表示されますが、ウィンドウが非アクティブのときには表示されません。  
  
 ほとんどのアプリケーションには、メニュー コマンドに対応するツールを組み込んだツールバーがあります。 このようなツールには、対応するメニュー項目と同じテキストのツール ヒント コントロールを表示すると便利です。 コントロールに **TTS\_NOPREFIX** スタイルがなければ、ツール ヒント コントロールに渡されるすべての文字列からアンパサンド \(&\) アクセラレータの文字が自動的に取り除かれます。  
  
## 参照  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)