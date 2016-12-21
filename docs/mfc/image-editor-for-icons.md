---
title: "Image Editor for Icons | Microsoft Docs"
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
  - "vc.editors.cursor.F1"
  - "vc.editors.icon.F1"
  - "vc.editors.cursor"
  - "vc.editors.bitmap.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, images"
  - "resource editors, graphics"
  - "Image editor [C++]"
  - "resource editors, Image editor"
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Image Editor for Icons
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ エディターには、イメージの作成と編集に使用できる広範なツール セットと、ツール バーのビットマップの作成に役立つ機能が用意されています。**\[イメージ\]** メニューのコマンドや、**\[イメージ エディター\]** ツール バーのツールを使用して、ビットマップ、アイコン、カーソルだけでなく、GIF 形式や JPEG 形式のイメージも編集できます。  
  
 イメージ エディターでは、次の作業ができます。  
  
-   [グラフィカル リソースの編集](../mfc/editing-graphical-resources-image-editor-for-icons.md)  
  
-   [色の調整](../mfc/working-with-color-image-editor-for-icons.md)  
  
-   [アイコンとカーソル : ディスプレイ デバイスのイメージ リソース](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
  
-   [イメージ エディターのアクセラレータ キー](../mfc/accelerator-keys-image-editor-for-icons.md)  
  
 イメージ エディター ウィンドウには 2 つのイメージ ビューが表示され、2 つのペインは分割バーで区切られています。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。  
  
 イメージ エディター ウィンドウは、必要に応じて調整できます。[拡大率を変更](../mfc/changing-the-magnification-factor-image-editor-for-icons.md)したり、[ピクセル グリッドの表示と非表示を切り替え](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)たりできます。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
## Visual Studio Image Library  
 アプリケーションで使用できるアニメーション、ビットマップ、およびアイコンが多数含まれる Visual Studio Image Library は、無料でダウンロードできます。 ライブラリをダウンロードする方法の詳細については、「[Visual Studio Image Library](../Topic/The%20Visual%20Studio%20Image%20Library.md)」を参照してください。  
  
## マネージ リソース  
 イメージ エディターと[バイナリ エディター](../mfc/binary-editor.md)を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
### 必要条件  
 なし  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)   
 [アイコン](http://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)