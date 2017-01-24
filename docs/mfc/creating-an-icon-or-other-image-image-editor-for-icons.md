---
title: "Creating an Icon or Other Image (Image Editor for Icons) | Microsoft Docs"
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
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "bitmaps [C++]"
  - "images [C++], creating"
  - "resource toolbars"
  - "resources [Visual Studio], creating images"
  - "bitmaps [C++], creating"
  - "graphics [C++], creating"
  - "Image editor [C++], creating images"
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating an Icon or Other Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビットマップ、アイコン、カーソル、ツール バーなどの新しいイメージを作成し、イメージ エディターを使用してそれらの外観をカスタマイズできます。  また、[テンプレート](../Topic/How%20to:%20Use%20Resource%20Templates.md)の後にパターン化された新しいビットマップを作成することもできます。  
  
### アンマネージ C\+\+ プロジェクトに新しいイメージ リソースを追加するには  
  
1.  [&#91;リソース&#93; ビュー](../windows/resource-view-window.md)で .rc ファイルを右クリックし、ショートカット メニューの \[リソースの追加\] をクリックします。  \(カーソルなどの既存のイメージ リソースが既に .rc ファイルにある場合は、\[Cursor\] フォルダーを右クリックし、ショートカット メニューの \[Cursor を挿入\] をクリックします。\)  
  
    > [!NOTE]
    >  **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [&#91;リソースの追加&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、作成するイメージ リソースの種類 \(\[Bitmap\] など\) を選択し、\[新規作成\] をクリックします。  
  
     \[リソースの追加\] ダイアログ ボックスで、イメージ リソースの種類の横に正符号 \(\+\) が表示される場合は、ツール バーのテンプレートが使用可能であることを示します。  正符号をクリックしてテンプレートの一覧を展開します。次に、テンプレートを選択し、\[新規作成\] をクリックします。  
  
### プログラミング言語でプロジェクトに新しいイメージ リソースを追加するには  
  
1.  **ソリューション エクスプローラー**で、**WindowsApplication1** などのプロジェクト フォルダーを右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[新しい項目の追加\] をクリックします。  
  
3.  \[カテゴリ\] ペインの \[ローカル プロジェクト アイテム\] フォルダーを展開し、\[リソース\] をクリックします。  
  
4.  \[テンプレート\] ペインで、プロジェクトに追加するリソースの種類を選択します。  
  
     ソリューション エクスプローラーでプロジェクトにリソースが追加され、[イメージ エディター](../mfc/image-editor-for-icons.md)でリソースが開かれます。  この時点で、イメージ エディターで提供されているすべてのツールを使用して、イメージを変更できます。  イメージをマネージ プロジェクトに追加する方法については、「[デザイン時でのピクチャの読み込み](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md)」を参照してください。  
  
    > [!NOTE]
    >  編集の対象となるマネージ リソースは、リンク リソースである必要があります。  Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  詳細については、『.NET Framework 開発者ガイド』の「[リソース ファイルの作成](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)