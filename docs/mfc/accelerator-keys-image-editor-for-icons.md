---
title: "Accelerator Keys (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.bitmap"
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator keys"
  - "Image editor [C++], accelerator keys"
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Accelerator Keys (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定でキーに結び付けられているイメージ エディターのコマンド用のアクセラレータ キーは、以下の表のとおりです。  アクセラレータ キーを変更するには、**\[ツール\]** メニューの **\[オプション\]** をクリックし、**\[環境\]** フォルダーの **\[キーボード\]** を選択します。  詳細については、「[キーボード ショートカットの識別とカスタマイズ](../Topic/Identifying%20and%20Customizing%20Keyboard%20Shortcuts%20in%20Visual%20Studio.md)」を参照してください。  
  
> [!NOTE]
>  使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。  設定を変更するには、**\[ツール\]** メニューの **\[設定のインポートとエクスポート\]** をクリックします。  詳細については、「[Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ja-jp/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
|コマンド|\[キー\]|Description|  
|----------|------------|-----------------|  
|Image.AirBrushTool|Ctrl \+ A|選択したサイズと色のエアブラシを使用して描画します。|  
|Image.BrushTool|Ctrl \+ B|選択した形、サイズ、および色のブラシを使用して描画します。|  
|Image.CopyAndOutlineSelection|**Ctrl** \+ **Shift** \+ **U**|現在の選択領域のコピーを作成し、その外枠を描画します。  現在の選択領域に背景色が含まれる場合に[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)を選択していると、背景色は解除されます。|  
|Image.DrawOpaque|**Ctrl** \+ **J**|現在の選択領域を[不透明または透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)にします。|  
|Image.EllipseTool|**Ctrl** \+ **P**|選択した線の幅と色で楕円を描画します。|  
|Image.EraserTool|**Ctrl** \+ **Shift** \+ **I**|イメージの一部を現在の背景色を使用して消去します。|  
|Image.FilledEllipseTool|**Ctrl** \+ **Shift** \+ **Alt** \+ **P**|塗りつぶされた楕円を描画します。|  
|Image.FilledRectangleTool|**Ctrl** \+ **Shift** \+ **Alt** \+ **R**|塗りつぶされた四角形を描画します。|  
|Image.FilledRoundRectangleTool|**Ctrl** \+ **Shift** \+ **Alt** \+ **W**|塗りつぶされた角の丸い四角形を描画します。|  
|Image.FillTool|**Ctrl** \+ **F**|領域を塗りつぶします。|  
|Image.FlipHorizontal|**Ctrl** \+ **H**|イメージまたは選択領域の上下を反転させます。|  
|Image.FlipVertical|**Shift** \+ **Alt** \+ **H**|イメージまたは選択領域の左右を反転させます。|  
|Image.LargerBrush|**Ctrl** \+ **\=**|ブラシのサイズを各方向に 1 ピクセルずつ拡大します。  ブラシのサイズを小さくする方法については、この表の「Image.SmallerBrush」を参照してください。|  
|Image.LineTool|**Ctrl** \+ **L**|選択した形、サイズ、および色で直線を描画します。|  
|Image.MagnificationTool|**Ctrl** \+ **M**|\[拡大\] ツールをアクティブにします。これによって、イメージの特定領域を拡大表示できます。|  
|Image.Magnify|**Ctrl** \+ **Shift** \+ **M**|現在の拡大率と 1:1 の間で切り替えます。|  
|Image.NewImageType|Ins|[&#91;\<Device\> イメージ タイプの新規作成&#93; ダイアログ ボックス](../mfc/new-device-image-type-dialog-box-image-editor-for-icons.md)を開きます。これを使用して、さまざまな種類のイメージを作成できます。|  
|Image.NextColor|Ctrl \+ \]<br /><br /> または<br /><br /> **Ctrl** \+ **→**|描画の前景色を次のパレット カラーに変更します。|  
|Image.NextRightColor|**Ctrl** \+ **Shift** \+ 右角かっこ \(**\]**\)<br /><br /> または<br /><br /> **Shift** \+ **Ctrl** \+ **→**|描画の背景色を次のパレット カラーに変更します。|  
|Image.OutlinedEllipseTool|**Shift** \+ **Alt** \+ **P**|塗りつぶされた楕円を外枠付きで描画します。|  
|Image.OutlinedRectangleTool|**Shift** \+ **Alt** \+ **R**|塗りつぶされた四角形を外枠付きで描画します。|  
|Image.OutlinedRoundRectangleTool|**Shift** \+ **Alt** \+ **W**|塗りつぶされた角の丸い四角形を外枠付きで描画します。|  
|Image.PencilTool|**Ctrl** \+ **I**|1 ピクセルのペンシルを使用して描画します。|  
|Image.PreviousColor|**Ctrl** \+ **\[**<br /><br /> または<br /><br /> **Ctrl** \+ **←**|描画の前景色を前のパレット カラーに変更します。|  
|Image.PreviousRightColor|**Ctrl** \+ **Shift** \+ **\[**<br /><br /> または<br /><br /> **Shift** \+ **Ctrl** \+ **←**|描画の背景色を前のパレット カラーに変更します。|  
|Image.RectangleSelectionTool|**Shift** \+ **Alt** \+ **S**|移動、コピー、または編集するイメージの一部を四角形として選択します。|  
|Image.RectangleTool|**ATL** \+ **R**|選択した線の幅と色で四角形を描画します。|  
|Image.Rotate90Degrees|**Ctrl** \+ **Shift** \+ **H**|イメージまたは選択領域を 90 度回転させます。|  
|Image.RoundedRectangleTool|**Alt** \+ **W**|選択した線の幅と色で角の丸い四角形を描画します。|  
|Image.ShowGrid|**Ctrl** \+ **Alt** \+ **S**|ピクセル グリッドを切り替えます。つまり、[&#91;グリッドの設定&#93; ダイアログ ボックス](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)の \[ピクセル表示\] オプションをオンまたはオフにします。|  
|Image.ShowTileGrid|**Ctrl** \+ **Shift** \+ **Alt** \+ **S**|タイル グリッドを切り替えます。つまり、[&#91;グリッドの設定&#93; ダイアログ ボックス](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)の \[タイル表示\] オプションをオンまたはオフにします。|  
|Image.SmallBrush|**Ctrl** \+ **.** \(ピリオド\)|ブラシのサイズを 1 ピクセルに縮小します。  この表の「Image.LargerBrush」と「Image.SmallerBrush」も参照してください。|  
|Image.SmallerBrush|**Ctrl** \+ **\-** \(マイナス\)|ブラシのサイズを各方向に 1 ピクセルずつ縮小します。  ブラシを元のサイズに戻す方法については、この表の「Image.LargerBrush」を参照してください。|  
|Image.TextTool|**Ctrl** \+ **T**|[&#91;テキスト ツール&#93; ダイアログ ボックス](../Topic/Text%20Tool%20Dialog%20Box%20\(Image%20Editor%20for%20Icons\).md)を開きます。|  
|Image.UseSelectionAsBrush|**Ctrl** \+ **U**|現在の選択項目をブラシとして使用して描画します。|  
|Image.ZoomIn|**Ctrl** \+ **Shift** \+ **.** \(ピリオド\)<br /><br /> または<br /><br /> **Ctrl** \+ **↑**|現在のビューの拡大率を上げます。|  
|Image.ZoomOut|**Ctrl** \+ **,** \(コンマ\)<br /><br /> または<br /><br /> **Ctrl** \+ **↓**|現在のビューの拡大率を下げます。|  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 なし  
  
## 参照  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)