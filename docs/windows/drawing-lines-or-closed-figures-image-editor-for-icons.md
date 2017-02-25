---
title: "Drawing Lines or Closed Figures (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "closed figures, drawing"
  - "lines [C++], painting"
  - "lines [C++], drawing"
  - "Image editor [C++], drawing lines"
  - "shapes, drawing"
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Drawing Lines or Closed Figures (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ エディターで線と閉じた図形の描画に使用するツールの動作形式はすべて同じです。つまり、挿入する場所にカーソルを置き、別の場所までドラッグします。  線の場合は、この 2 つの点がエンド ポイントになります。  閉じた図形の場合は、この 2 つの点が図形の境界となる四角形の対角点になります。  
  
 描画する線の太さは現在のブラシの選択内容によって決定され、枠付きの図形の幅は現在の幅の選択内容によって決定されます。  線とすべての図形は、枠付きであっても塗りつぶされていても、マウスの左ボタンをクリックすると現在の前景色、右ボタンをクリックすると現在の背景色で描画されます。  
  
### 線を描画するには  
  
1.  [&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md) \(または \[イメージ\] メニューの \[ツール\] コマンド\) で、\[直線\] ツールをクリックします。  
  
2.  必要に応じて、色とブラシを選択します。  
  
    -   [カラー パレット](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)で、マウスの左ボタンをクリックして前景色を選択するか、またはマウスの右ボタンをクリックして背景色を選択します。  
  
    -   [オプション セレクター](../mfc/toolbar-image-editor-for-icons.md)で、使用するブラシの形をクリックします。  
  
3.  線の始点にポインターを置きます。  
  
4.  線のエンド ポイントにドラッグします。  
  
### 閉じた図形を描画するには  
  
1.  \[イメージ エディター\] ツール バー \(または \[イメージ\] メニューの \[ツール\] コマンド\) で、図形ツールのいずれかをクリックします。  
  
     図形ツールを使用すると、各ボタンに示されている図形を作成できます。  
  
2.  必要に応じて、色と線の幅を選択します。  
  
3.  図形を描画する四角形の 1 つの角にポインターを移動します。  
  
4.  対角にポインターをドラッグします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)