---
title: "Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], screen regions"
  - "inverse colors, device images"
  - "transparent regions, device images"
  - "transparency, device images"
  - "Image editor [C++], device images"
  - "inverse regions, device images"
  - "cursors [C++], transparent regions"
  - "screen colors"
  - "regions, transparent"
  - "icons [C++], transparent regions"
  - "display devices, transparent and screen regions"
  - "transparent regions in devices"
  - "regions, inverse"
  - "colors [C++], Image editor"
  - "device projects, transparent images"
  - "icons [C++], screen regions"
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[イメージ エディター](../mfc/image-editor-for-icons.md)では、初期のアイコン イメージやカーソル イメージが透明な属性を持っています。  アイコンとカーソルのイメージは四角形ですが、イメージのほとんどは四角で表示されません。これは、イメージの透明な部分では画面上で基になるイメージがアイコンやカーソルを通して透けて見えるためです。  アイコンをドラッグすると、イメージの一部が反転色で表示される場合があります。  この効果を得るには、[&#91;色&#93; ウィンドウ](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)で画面の色と反転色を設定します。  
  
 アイコンとカーソルに適用した画面の色と反転色によって、派生したイメージの形と色が決まり、反転領域が決まります。  イメージのこれらの属性を持つ部分が指定した色で表示されます。  画面の色と反転色の属性を表す色は編集中に変更できます。  変更内容は、アプリケーションにおけるアイコンやカーソルの外観には影響しません。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。  設定を変更するには、**\[ツール\]** メニューの **\[設定のインポートとエクスポート\]** をクリックします。  詳細については、「[Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ja-jp/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### 透明な領域または反転領域を作成するには  
  
1.  \[色\] ウィンドウで、\[画面の色\] セレクターまたは \[反転色\] セレクターをクリックします。  
  
2.  描画ツールを使用して、イメージに画面の色または反転色を適用します。  描画ツールの詳細については、「[Using a Drawing Tool](../mfc/using-a-drawing-tool-image-editor-for-icons.md)」を参照してください。  
  
### 画面の色または反転色を変更するには  
  
1.  \[画面の色\] セレクターまたは \[反転色\] セレクターをクリックします。  
  
2.  \[色\] ウィンドウのカラー パレットで色を選択します。  
  
     他方のセレクターに合わせて補色が自動的に指定されます。  
  
    > [!TIP]
    >  \[画面の色\] セレクターまたは \[反転色\] セレクターをダブルクリックすると、[&#91;色の調整&#93; ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)