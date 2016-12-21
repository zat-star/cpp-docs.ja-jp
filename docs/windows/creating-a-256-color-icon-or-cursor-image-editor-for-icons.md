---
title: "Creating a 256-Color Icon or Cursor (Image Editor for Icons) | Microsoft Docs"
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
  - "256-color palette"
  - "cursors, color"
  - "colors, icons"
  - "colors, cursors"
  - "icons, color"
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a 256-Color Icon or Cursor (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ エディターを使用すると、256 色のカラー パレットから色を選択してアイコンとカーソルのサイズを拡大 \(64 × 64\) できます。  リソースの作成後に、デバイス イメージのスタイルが選択されます。  
  
### 256 色のアイコンまたはカーソルを作成するには  
  
1.  [&#91;リソース&#93; ビュー](../windows/resource-view-window.md)で .rc ファイルを右クリックし、ショートカット メニューの \[リソースの追加\] をクリックします。  \(カーソルなどの既存のイメージ リソースが既に .rc ファイルにある場合は、\[Cursor\] フォルダーを右クリックし、ショートカット メニューの \[Cursor を挿入\] をクリックします。\)  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [&#91;リソースの追加&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、\[Icon\] または \[Cursor\] を選択し、\[新規作成\] をクリックします。  
  
3.  \[イメージ\] メニューの \[新しいイメージの種類\] をクリックします。  
  
4.  必要な 256 色イメージのスタイルを選択します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 なし  
  
## 参照  
 [Using the 256\-Color Palette](../Topic/Using%20the%20256-Color%20Palette%20\(Image%20Editor%20for%20Icons\).md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)