---
title: "Editing Parts of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "Image editor [C++], editing images"
  - "Clipboard [C++], pasting"
  - "images [C++], editing"
  - "images [C++], deleting selected parts"
  - "images [C++], copying selected parts"
  - "images [C++], moving selected parts"
  - "images [C++], dragging and replicating selected parts"
  - "images [C++], pasting into"
  - "graphics [C++], editing"
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Editing Parts of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージの[選択領域](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md)では、それがイメージの全体か一部かに関係なく、切り取り、消去、移動などの標準の編集操作を実行できます。  イメージ エディターではWindowsのクリップボードを使用するため、Windowsのイメージ エディターと他のアプリケーションの間でイメージを転送できます。  
  
 また、イメージ全体が含まれるかどうかに関係なく、選択領域のサイズを変更できます。  
  
### 現在の選択領域を切り取ってクリップボードに移動するには  
  
1.  \[編集\] メニューの \[切り取り\] をクリックします。  
  
### 選択領域をコピーするには  
  
1.  ポインターを選択領域内またはその境界上 \(サイズ変更ハンドルを除く\) に置きます。  
  
2.  **Ctrl** キーを押しながら、選択領域を新しい位置にドラッグします。  元の選択領域は変更されません。  
  
3.  選択領域を現在の位置にあるイメージにコピーするには、選択ポインターの外側をクリックします。  
  
### クリップボードの内容をイメージに貼り付けるには  
  
1.  \[編集\] メニューの \[貼り付け\] をクリックします。  
  
     クリップボードの内容が選択境界線で囲まれて、ペインの左上隅に表示されます。  
  
2.  選択境界線の内側にポインターを置き、貼り付けるイメージをイメージ上の必要な位置にドラッグします。  
  
3.  イメージを新しい位置に固定するには、選択境界線の外側をクリックします。  
  
### 現在の選択領域をクリップボードに移動せずに削除するには  
  
1.  \[編集\] メニューの \[削除\] をクリックします。  
  
     元の選択領域が現在の背景色で塗りつぶされます。  
  
    > [!NOTE]
    >  \[リソース ビュー\] ウィンドウ内でマウスの右ボタンをクリックすると、\[切り取り\]、\[コピー\]、\[貼り付け\]、\[削除\] の各コマンドにアクセスできます。  
  
### 選択領域を移動するには  
  
1.  ポインターを選択領域内またはその境界上 \(サイズ変更ハンドルを除く\) に置きます。  
  
2.  選択領域を新しい位置にドラッグします。  
  
3.  イメージの選択領域を新しい位置に固定するには、選択境界線の外側をクリックします。  
  
 選択領域を使用して描画する方法については、「[カスタム ブラシの作成](../Topic/Creating%20a%20Custom%20Brush%20\(Image%20Editor%20for%20Icons\).md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)