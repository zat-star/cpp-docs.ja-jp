---
title: "Converting Bitmaps to Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "bitmaps [C++], converting to toolbars"
  - "Toolbar editor, converting bitmaps"
  - "toolbars [C++], converting bitmaps"
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Converting Bitmaps to Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビットマップを変換して、新しいツール バーを作成できます。  ビットマップのグラフィックは、ツール バーのボタンのイメージに変換されます。  通常、1 つのビットマップには複数のボタンのイメージがあり、ボタンごとに 1 つのイメージが含まれています。  イメージのサイズは任意で、既定の幅は 16 ピクセル、高さはイメージの高さです。  イメージ エディターで、\[イメージ\] メニューの \[ツール バー エディター\] をクリックすると、[&#91;新規ツール バー&#93; ダイアログ ボックス](../mfc/new-toolbar-resource-dialog-box.md)でボタンのイメージのサイズを指定できます。  
  
### ビットマップをツール バーに変換するには  
  
1.  [イメージ エディター](../mfc/image-editor-for-icons.md)で既存のビットマップ リソースを開きます。  ビットマップが .rc ファイルにない場合は、\[リソースの追加\] ダイアログ ボックスの \[インポート\] をクリックします。.rc ファイルに追加するビットマップに移動し、\[開く\] をクリックします。  
  
2.  \[イメージ\] メニューの \[ツール バー エディター\] をクリックします。  
  
     [&#91;新規ツール バー&#93; ダイアログ ボックス](../mfc/new-toolbar-resource-dialog-box.md)が表示されます。  アイコン イメージの幅と高さは、ビットマップに合わせて変更できます。  その後、ツール バー イメージがツール バー エディターに表示されます。  
  
3.  変換を完了するには、[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用してボタンのコマンド ID を変更します。  新しい ID を入力するか、ドロップダウン リストの ID を選択します。  
  
    > [!TIP]
    >  \[プロパティ\] ウィンドウのタイトル バーには、プッシュピン ボタンがあります。  このボタンをクリックすると、ウィンドウの \[自動的に隠す\] の有効と無効を切り替えることができます。  各プロパティ ウィンドウを開かずに、すべてのツール バー ボタンのプロパティの表示をすばやく切り替えるには、\[プロパティ\] ウィンドウが固定されたままになるように、\[自動的に隠す\] をオフにします。  
  
 また、[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用すると、新しいツール バーのボタンのコマンド ID を変更できます。  新しいツール バーを編集する方法については、「[ツール バー ボタンの作成、移動、および編集](../mfc/creating-moving-and-editing-toolbar-buttons.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 MFC または ATL  
  
## 参照  
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)