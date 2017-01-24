---
title: "Working with Color (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], background colors"
  - "Image editor [C++], Colors Palette"
  - "colors [C++], image"
  - "Colors Palette, Image editor"
  - "palettes, Image editor colors"
  - "foreground colors, Image editor"
  - "colors [C++]"
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Working with Color (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ エディターには、色を特殊処理してカスタマイズできるように、多くの機能が用意されています。  前景色または背景色を設定したり、内側部分を色で塗りつぶしたり、イメージの色を選択して現在の前景色または背景色として使用したりできます。  [&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md)のツールと [&#91;色&#93; ウィンドウ](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)のカラー パレットを一緒に使用して、イメージを作成できます。  
  
 モノクロ イメージと 16 色イメージの場合は、すべての色が \[色\] ウィンドウのカラー パレットに表示されます。  標準の 16 色のほかにも、独自のカスタム カラーを作成できます。  パレットで色を変更すると、対応する色がイメージ内ですぐに変更されます。  
  
 256 色のアイコン イメージとカーソル イメージを操作する場合は、[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の \[色\] プロパティを使用します。  詳細については、「[256 色のアイコンまたはカーソルの作成](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)」を参照してください。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
 \[True カラー\] のイメージも作成できます。  ただし、\[True カラー\] のサンプルは、\[色\] ウィンドウのパレット全体には表示されず、前景色または背景色のインジケーター領域だけに表示されます。  \[True カラー\] を作成するには、[&#91;色の調整&#93; ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)を使用します。  詳細については、「[色のカスタマイズまたは変更](../windows/customizing-or-changing-colors-image-editor-for-icons.md)」を参照してください。  
  
 カスタマイズしたカラー パレットをディスクに保存し、必要に応じて再読み込みできます。  最後に使用したカラー パレットはレジストリに保存され、次回の Visual Studio の起動時に自動的に読み込まれます。  
  
-   [前景色または背景色の選択](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [イメージの内側の塗りつぶし](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [イメージから選択した色をほかの場所で使用する](../Topic/Picking%20up%20a%20Color%20from%20an%20Image%20to%20Use%20Elsewhere%20\(Image%20Editor%20for%20Icons\).md)  
  
-   [透明または不透明な背景の選択](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [選択領域の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [色のカスタマイズまたは変更](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [さまざまなカラー パレットの保存と読み込み](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [&#91;色&#93; ウィンドウ](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Resources](_win32_Resources)