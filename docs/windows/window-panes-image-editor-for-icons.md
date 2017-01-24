---
title: "Window Panes (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.bitmap"
  - "vc.editors.icon"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "graphics editor [C++]"
  - "Image editor [C++], panes"
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Window Panes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、イメージ エディター ウィンドウでは、分割バーで区切られた 2 つのペインにイメージが表示されます。  一方のビューは実際のサイズを示し、他方は拡大表示されます。既定の拡大率は 6 です。  この 2 つのペインのビューは自動的に更新され、一方のペインで行った変更は他方にすぐに表示されます。  2 つのペインを使用すると、イメージの拡大ビューで各ピクセルを見やすい大きさに表示して作業すると同時に、実サイズ ビューで実際の状態を確認できます。  
  
 左ペインでは、必要な領域 \(\[イメージ\] ウィンドウの半分まで\) を使用して、イメージの 1:1 のビュー \(既定値\) が表示されます。  右ペインには拡大イメージが表示されます。既定の拡大率は 6:1 です。  各ペインの[拡大率を変更](../mfc/changing-the-magnification-factor-image-editor-for-icons.md)するには、[&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md)の \[拡大\] ツールを使用する方法と、アクセラレータ キーを使用する方法があります。  
  
 イメージ エディター ウィンドウの小さい方のペインを拡大し、大きなイメージの別の部分を 2 つのペインに表示できます。  ペイン内でクリックして選択します。  
  
 ペインの相対サイズは、分割バーにポインターを置いて左右に動かすと変更できます。  一方のペインだけで操作する場合は、分割バーを端まで移動できます。  
  
 イメージ エディターのペインの拡大率が 4 以上の場合は、[ピクセル グリッドを表示](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)して、イメージの各ピクセルを区切ることができます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)