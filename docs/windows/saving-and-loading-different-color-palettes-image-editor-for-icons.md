---
title: "Saving and Loading Different Color Palettes (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "color palettes [C++]"
  - "palettes"
  - "palettes, Image editor"
  - "colors [C++], Image editor"
  - "Image editor [C++], palettes"
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Saving and Loading Different Color Palettes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタマイズした色](../windows/customizing-or-changing-colors-image-editor-for-icons.md)を含むカラー パレットを保存して読み込むことができます。  既定では、Visual Studio を起動すると、前回使用したカラー パレットが自動的に読み込まれます。  
  
> [!TIP]
>  イメージ エディターには既定のカラー パレットを復元する手段がないため、既定の設定を簡単に復元できるように、既定のカラー パレットに "standard.pal" や "default.pal" などの名前を付けて保存する必要があります。  
  
### カスタム カラー パレットを保存するには  
  
1.  **\[イメージ\]** メニューの **\[パレットの保存\]** をクリックします。  
  
2.  パレットを保存するディレクトリに移動し、パレット名を入力します。  
  
3.  **\[保存\]** をクリックします。  
  
### カスタム カラー パレットを読み込むには  
  
1.  **\[イメージ\]** メニューの **\[パレットの読み込み\]** をクリックします。  
  
2.  [&#91;カラー パレットの読み込み&#93; ダイアログ ボックス](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)で、適切なディレクトリに移動し、読み込むパレットを選択します。  カラー パレットは、拡張子 .pal を付けて保存されています。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)