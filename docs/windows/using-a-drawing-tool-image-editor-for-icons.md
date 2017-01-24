---
title: "Using a Drawing Tool (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.drawing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], selecting drawing tools"
  - "Image editor [C++], toolbar"
  - "drawing tools"
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using a Drawing Tool (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ エディターの手描きツールと消しゴム ツールの動作形式はすべて同じです。ツールを選択し、必要に応じて[前景色と背景色を選択](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)し、サイズと形のオプションを選択します。  次に、ポインターをイメージに移動し、クリックまたはドラッグして描画したり消去したりします。  
  
 \[消去\] ツール、\[ブラシ\] ツール、または \[エアブラシ\] ツールを選択すると、そのツールのオプションがオプション セレクターに表示されます。  
  
> [!TIP]
>  \[消去\] ツールを使用する代わりに、描画ツールを使用して背景色で描画する方が便利な場合があります。  
  
 描画ツールは、\[イメージ エディター\] ツール バーまたは \[イメージ\] メニューから選択できます。  
  
### \[イメージ エディター\] ツール バーから描画ツールを選択して使用するには  
  
1.  \[イメージ エディター\] ツール バーのボタンをクリックします。  
  
    -   \[消去\] ツールでは、マウスの左ボタンを押すと、現在の背景色でイメージが上書きされます。  
  
    -   \[鉛筆\] ツールを使用すると、1 ピクセルの固定幅で手描きできます。  
  
    -   \[ブラシ\] ツールの形とサイズはオプション セレクターで指定します。  
  
    -   \[エアブラシ\] ツールを使用すると、ブラシを中心としてランダムにカラー ピクセルを分散させることができます。  
  
        > [!TIP]
        >  [&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md)のボタンの上にカーソルを置くと、ツール ヒントが表示されます。  これらのヒントによって、ここで説明した各ボタンの機能がわかります。  
  
2.  必要に応じて、色とブラシを選択します。  
  
    -   [カラー パレット](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)で、マウスの左ボタンをクリックして前景色を選択するか、またはマウスの右ボタンをクリックして背景色を選択します。  
  
    -   [オプション セレクター](../mfc/toolbar-image-editor-for-icons.md)で、使用するブラシの形をクリックします。  
  
3.  イメージ上で、描画操作またはペイント操作の開始位置をポイントします。  選択したツールに応じてポインターの形が変わります。  
  
4.  前景色の場合はマウスの左ボタン、背景色の場合は右ボタンをクリックしたまま、ドラッグして描画します。  
  
### \[イメージ\] メニューから描画ツールを選択して使用するには  
  
1.  \[イメージ\] メニューをクリックし、\[ツール\] をクリックします。  
  
2.  カスケード サブメニューで、使用するツールをクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)