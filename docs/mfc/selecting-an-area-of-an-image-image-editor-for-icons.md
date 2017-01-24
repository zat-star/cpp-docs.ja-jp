---
title: "Selecting an Area of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], image selection"
  - "Image editor [C++], selecting images"
  - "images [C++], selecting"
  - "cursors [C++], selecting areas of"
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting an Area of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

選択ツールを使用すると、イメージの中で切り取り、コピー、消去、サイズ変更、反転、または移動する領域を定義できます。  \[矩形選択\] ツールでは、イメージの四角形領域を定義して選択できます。  \[不規則選択\] ツールでは、切り取りやコピーなどの操作対象として選択する領域の外枠を手描きできます。  
  
> [!NOTE]
>  [&#91;イメージ エディター&#93; ツール バー](../mfc/toolbar-image-editor-for-icons.md)にある \[矩形選択\] ツールと \[不規則選択\] ツールを参照してください。または、\[イメージ エディター\] ツール バーの各ボタンに関連付けられているツール ヒントを確認してください。  
  
 選択項目からカスタム ブラシを作成することもできます。  詳細については、「[カスタム ブラシの作成](../Topic/Creating%20a%20Custom%20Brush%20\(Image%20Editor%20for%20Icons\).md)」を参照してください。  
  
### イメージの領域を選択するには  
  
1.  \[イメージ エディター\] ツール バー \(または \[イメージ\] メニューの \[ツール\] コマンド\) で、必要な選択ツールをクリックします。  
  
2.  選択するイメージ領域の角の 1 つにカーソルを移動します。  カーソルをイメージの上に置くと、十字カーソルが表示されます。  
  
3.  選択する領域の対角にカーソルをドラッグします。  選択するピクセル数が四角形に表示されます。  四角形内のすべてのピクセル \(四角形の下にあるピクセルも含む\) が選択対象となります。  
  
4.  マウスのボタンを離します。  選択した領域が選択境界線で囲まれます。  
  
### イメージ全体を選択するには  
  
1.  現在の選択領域の外側にあるイメージをクリックします。  選択境界線のフォーカスが変化し、イメージ全体が選択範囲に含まれます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)