---
title: "Changing Image Properties (Image Editor for Icons) | Microsoft Docs"
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
  - "images [C++], properties"
  - "Image editor [C++], Properties window"
  - "Image editor [C++], image properties"
  - "Properties window, image editor"
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Changing Image Properties (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用して、イメージのプロパティを設定または変更できます。  
  
### イメージのプロパティを変更するには  
  
1.  イメージ エディターでイメージを開きます。  
  
2.  \[プロパティ\] ウィンドウで、イメージの一部またはすべてのプロパティを変更します。  
  
    |プロパティ|Description|  
    |-----------|-----------------|  
    |**Colors**|イメージの配色を指定します。  \[Monochrome\]、\[16 色\]、\[256 色\]、または \[True カラー\] のいずれかを選択します。  既にイメージを 16 色パレットで描画している場合に \[Monochrome\] を選択すると、イメージの色が白黒に変更されます。  コントラストは維持されない場合があります。たとえば、赤と緑の隣接部分はどちらも黒に変換されます。|  
    |**ファイル名**|イメージ ファイルの名前を指定します。  既定では、Visual Studio によって、既定のリソース識別子 \(IDB\_BITMAP1\) から最初の 4 文字 \("IDB\_"\) が削除され、適切な拡張子が追加されたベース ファイル名が割り当てられます。  この例のイメージ ファイル名は BITMAP1.bmp になります。  このファイル名は、MYBITMAP1.bmp に変更できます。|  
    |**高さ**|イメージの高さをピクセル単位で設定します。  既定値は 48 です。  イメージがトリミングされるか、または既存のイメージの下に空白領域が追加されます。|  
    |**ID**|リソースの識別子を設定します。  イメージの場合、Microsoft Visual Studio によって、IDB\_BITMAP1、IDB\_BITMAP2 など、使用できる識別子が順に既定で割り当てられます。  アイコンとカーソルにも同様の名前が使用されます。|  
    |**Palette**|色のプロパティを変更します。  色をダブルクリックして選択し、[&#91;色の調整&#93; ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)を表示します。  該当するテキスト ボックスに RGB 値または HSL 値を入力して色を定義します。|  
    |**SaveCompressed**|イメージが圧縮形式かどうかを示します。  このプロパティは読み取り専用です。  Visual Studio ではイメージを圧縮形式で保存できないため、Visual Studio で作成したイメージについては、このプロパティが \[False\] になります。  別のプログラムで作成された圧縮形式のイメージを Visual Studio で開く場合、このプロパティは \[True\] になります。  Visual Studio を使用して圧縮形式のイメージを保存すると、圧縮は解除され、このプロパティは \[False\] に戻ります。|  
    |**幅**|イメージの幅をピクセル単位で設定します。  ビットマップの既定値は 48 です。  イメージがトリミングされるか、または既存のイメージの右側に空白領域が追加されます。|  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)