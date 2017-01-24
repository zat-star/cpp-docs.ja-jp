---
title: "Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "image resources, display devices"
  - "icons [C++], creating"
  - "cursors [C++], types"
  - "icons [C++]"
  - "Image editor [C++], icons and cursors"
  - "cursors [C++]"
  - "display devices, creating icons for"
  - "cursors [C++], hot spots"
  - "icons [C++], types"
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アイコンとカーソルは、グラフィカルなリソースで、表示デバイスの種類ごとに異なるサイズや色スキームの複数のイメージを含めることができます。 さらに、カーソルには「ホット スポット」があります。これは、その位置を追跡するために Windows で使用されるロケーションです。 アイコンとカーソルのどちらも、ビットマップやその他のイメージと同様、イメージ エディターを使用して作成および編集されます。  
  
 新しいアイコンやカーソルを作成する際、イメージ エディターはまず、標準タイプのイメージを作成します。 イメージは最初、画面の色 \(透明\) で塗られます。 イメージがカーソルの場合、ホット スポットは最初、左上隅 \(座標 0,0\) に置かれます。  
  
 既定では、イメージ エディターは、次の表に示すデバイス用の追加イメージの作成をサポートします。 幅、高さ、色の数のパラメーターを [&#91;カスタム イメージの種類&#93;](../mfc/custom-image-dialog-box-image-editor-for-icons.md) ダイアログ ボックスに入力することにより、その他のデバイス用のイメージを作成することができます。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
|色|幅 \(ピクセル単位\)|高さ \(ピクセル単位\)|  
|-------|------------------|-------------------|  
|白黒|16|16|  
|白黒|32|32|  
|白黒|48|48|  
|白黒|64|64|  
|白黒|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [新しいデバイス イメージの作成 \(アイコンやカーソル\)](../mfc/creating-a-device-image-image-editor-for-icons.md)  
  
-   [別のディスプレイ デバイスのイメージの追加](../mfc/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [デバイス イメージのコピー](../mfc/copying-a-device-image-image-editor-for-icons.md)  
  
-   [デバイス イメージの削除](../Topic/Deleting%20a%20Device%20Image%20\(Image%20Editor%20for%20Icons\).md)  
  
-   [デバイス イメージの透明な領域または反転領域の作成](../mfc/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [256 色のアイコンまたはカーソルの作成](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [カーソルのホット スポットの設定](../Topic/Setting%20a%20Cursor's%20Hot%20Spot%20\(Image%20Editor%20for%20Icons\).md)  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
## 必要条件  
 なし  
  
## 参照  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [アイコン](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [カーソル](http://msdn.microsoft.com/library/windows/desktop/ms646970)