---
title: "[イメージ] メニュー (アイコン用イメージ エディター) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "[イメージ] メニュー"
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [イメージ] メニュー (アイコン用イメージ エディター)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\[イメージ\] メニューが表示されるのは、イメージ エディターがアクティブな場合だけです。このメニューのコマンドを使用すると、イメージの編集、カラー パレットの管理、およびイメージ エディター ウィンドウのオプション設定ができます。  また、アイコンとカーソルの操作中は、デバイス イメージを使用するためのコマンドも利用できます。  
  
 **\[色の反転\]**  
 色を反転させます。  詳細については、「[選択領域の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)」を参照してください。  
  
 **\[左右反転\]**  
 イメージまたは選択領域の上下を反転させます。  詳細については、「[イメージの回転](../mfc/flipping-an-image-image-editor-for-icons.md)」を参照してください。  
  
 **\[上下反転\]**  
 イメージまたは選択領域の左右を反転させます。  詳細については、「[イメージの回転](../mfc/flipping-an-image-image-editor-for-icons.md)」を参照してください。  
  
 **\[90 度回転\]**  
 イメージまたは選択領域を 90 度回転させます。  詳細については、「[イメージの回転](../mfc/flipping-an-image-image-editor-for-icons.md)」を参照してください。  
  
 **\[\[色の設定\] ウィンドウの表示\]**  
 [&#91;色&#93; ウィンドウ](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)が開き、イメージに使用する色を選択できます。  詳細については、「[色の調整](../mfc/working-with-color-image-editor-for-icons.md)」を参照してください。  
  
 **\[選択したものをブラシとして使用する\]**  
 イメージの一部からカスタム ブラシを作成できます。  選択領域がカスタム ブラシになり、イメージにまたがって選択領域内の色を使用できます。  選択領域のコピーは、ドラッグするパスに残ります。  ゆっくりドラッグするほど、多数のコピーが作成されます。  詳細については、「[カスタム ブラシの作成](../Topic/Creating%20a%20Custom%20Brush%20\(Image%20Editor%20for%20Icons\).md)」を参照してください。  
  
 **\[コピーして選択範囲をアウトライン\]**  
 現在の選択領域のコピーを作成し、その外枠を描画します。  現在の選択領域に背景色が含まれる場合に[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)を選択していると、背景色は解除されます。  
  
 **\[色の設定\]**  
 [&#91;色の調整&#93; ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が開き、イメージに使用する色をカスタマイズできます。  詳細については、「[色のカスタマイズまたは変更](../windows/customizing-or-changing-colors-image-editor-for-icons.md)」を参照してください。  
  
 **\[パレットの読み込み\]**  
 [&#91;パレットの読み込み&#93; ダイアログ ボックス](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)が開き、以前に .pal ファイルに保存したパレット カラーを読み込むことができます。  
  
 **\[パレットの保存\]**  
 パレット カラーを .pal ファイルに保存します。  
  
 **\[背景色を不透明にする\]**  
 このオプションをオンにすると、現在の選択領域が不透明になります。  オフにすると、現在の選択領域が透明になります。  詳細については、「[透明または不透明な背景の選択](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)」を参照してください。  
  
 **\[ツール バー エディター\]**  
 [&#91;新規ツール バー リソース&#93; ダイアログ ボックス](../mfc/new-toolbar-resource-dialog-box.md)を開きます。  
  
 **\[グリッドの設定\]**  
 [&#91;グリッドの設定&#93; ダイアログ ボックス](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)が開き、イメージに使用するグリッドを指定できます。  
  
 **\[新しいイメージの種類\]**  
 [&#91;\<Device\> イメージ タイプの新規作成&#93; ダイアログ ボックス](../mfc/new-device-image-type-dialog-box-image-editor-for-icons.md)を開きます。  単一のアイコン リソースに、サイズの異なる複数のイメージを含めることができます。ウィンドウでは、表示方法に応じて適切なアイコン サイズを指定できます。  新しいデバイスの種類を指定してもアイコンのサイズは変更されず、アイコンの内側に新しいイメージが作成されます。  このオプションを使用できるのは、アイコンとカーソルだけです。  
  
 **\[現在のアイコン\/カーソルイメージの種類\]**  
 サブメニューを開きます。このサブメニューには、使用可能なカーソルまたはアイコンのイメージが先頭から 9 個表示されます。  このサブメニューの最後のコマンドは \[詳細\] であり、このコマンドをクリックすると [&#91;\<Device\> イメージを開く&#93; ダイアログ ボックス](../Topic/Open%20%3CDevice%3E%20Image%20Dialog%20Box%20\(Image%20Editor%20for%20Icons\).md)が開きます。  
  
 **\[イメージの種類の削除\]**  
 選択したデバイス イメージを削除します。  
  
 **ツール**  
 [&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md)から利用できるすべてのツールを含むサブメニューを表示します。  
  
## 要件  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)