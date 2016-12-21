---
title: "MFC ActiveX コントロール : ActiveX コントロールの描画 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "MFC ActiveX コントロール, 最適化"
  - "MFC ActiveX コントロール, 描画"
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : ActiveX コントロールの描画
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、プロセスを最適化するように描画コードを変更できるまたは ActiveX コントロールの塗装プロセスについて説明します。\(コントロールを持たないことによって描画を最適化する方法の手法の [Optimizing Control Drawing](../mfc/optimizing-control-drawing.md) を個別に復元する前に指定 GDI オブジェクトを参照してください。  すべてのコントロールの描画、コンテナーは自動的に、元のオブジェクトを復元できます\)。  
  
 このトピックの例では、既定の設定では、MFC ActiveX コントロール ウィザードが作成するコントロールになります。  MFC ActiveX コントロール ウィザードを使用してコントロールのスケルトン アプリケーションの作成の詳細については、記事 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)を参照します。  
  
 次のトピックで説明されている:  
  
-   [描画をサポートする ActiveX コントロール ウィザードが作成するコントロールとコードを描画するための一般的なプロセス](#_core_the_painting_process_of_an_activex_control)  
  
-   [塗装プロセスを最適化する方法](#_core_optimizing_your_paint_code)  
  
-   [メタファイルを使用してコントロールを描画する方法](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> ActiveX コントロールの塗装プロセス  
 ActiveX コントロールが最初に表示したり、再描画されると、1 種類の重要な点が MFC を使用して開発された他のアプリケーションに似た塗装プロセスに従って: ActiveX コントロールがアクティブかアクティブでない状態になる可能性があります。  
  
 アクティブなコントロールは子ウィンドウに、ActiveX コントロール コンテナーで表されます。  他のウィンドウと同様に、`WM_PAINT` メッセージを受け取ったときに自身を描画する必要があります。  コントロールの基本クラス、[COleControl](../mfc/reference/colecontrol-class.md)ハンドル `OnPaint` 関数でこのメッセージ。  この既定の実装は、コントロールの `OnDraw` 関数を呼び出します。  
  
 アクティブでないコントロールは別々に描画されます。  コントロールがアクティブでないと、ウィンドウは非表示になるか、存在しないので、描画メッセージを受け取ることができません。  代わりに、コントロール コンテナーは直接コントロールの `OnDraw` 関数を呼び出します。  これは、アクティブなコントロールの塗装プロセスと `OnPaint` のメンバー関数が呼び出されないことです。  
  
 前に説明したように、ActiveX コントロールをどのように更新されるかどうかはコントロールの状態によって異なります。  ただし、フレームワークが `OnDraw` メンバー関数をどちらの場合と同じように、このメンバー関数の描画コードの大半を追加します。  
  
 `OnDraw` のメンバー関数のハンドルは、レンダリングを制御します。  コントロールがアクティブでないと、コントロール コンテナーにコントロールをコンテナー コントロールのデバイス コンテキストとする四角形領域の座標を渡す `OnDraw`を呼び出します。  
  
 `OnDraw` メンバー関数にフレームワークによって四角形はコントロールが占める領域が含まれています。  コントロールがアクティブな場合は、左上隅 \(0、0\) であり、渡されたデバイス コンテキストはコントロールを含む子ウィンドウ用です。  コントロールがアクティブでなければ、左上の座標が必ずしも \(0、0\) ではなく、渡されたデバイス コンテキストはコントロールを含むコントロール コンテナーです。  
  
> [!NOTE]
>  、`OnDraw`に渡される四角形内でのみ描画できることは `OnDraw`への変更が等しいと四角形の左上の点に依存しない重要です \(0、0\)。  予期しない結果は四角形の領域を超えて描画送られます。  
  
 以下のコントロールの実装ファイル \(.cpp\) の MFC ActiveX コントロール ウィザードに用意されている既定の実装は、白いブラシを使用して四角形を描画し、現在の背景色で楕円を塗りつぶす。  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/CPP/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  コントロールを描画した場合、`OnDraw` 関数に *pdc* パラメーターとして渡されるデバイス コンテキストの状態について想定しないでください。  場合によってはデバイス コンテキストとは、コンテナー アプリケーションによって提供され、既定の状態に対する初期化されません。  特に、明示的にペン、ブラシ、色、フォント、および描画コードが依存するそのほかのリソースを選択します。  
  
##  <a name="_core_optimizing_your_paint_code"></a> 描画コードの最適化  
 コントロールが正常に描画した後、次の手順を `OnDraw` 関数を最適化することです。  
  
 ActiveX コントロールの描画の既定の実装は、コントロールの領域を描画します。  これは簡単なコントロールに対して十分ですが、多くの場合、コントロールを再描画すると、全体のコントロールの代わりにより迅速に必要な更新が再描画された部分だけです。  
  
 `OnDraw` 関数は `rcInvalid`の再描画する必要があるコントロールの四角形領域を渡すことによって最適化の簡単なメソッドを提供します。  全体を制御する小さい塗装プロセスを高速化するには、この領域は、通常使用します。  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> Control Using のメタファイルの描画  
 ほとんどの場合 `OnDraw` 関数への `pdc` パラメーターは画面デバイス コンテキスト \(DC\) を指します。  ただし、コントロールの印刷プレビュー セッション中の印刷イメージが、用に受信 DC 「メタファイル DC」という特殊な型になります。  画面 DC とは異なり、すぐに処理する要求によって、メタファイル DC ストア後に遊ばれることが必要とされる。  あるコンテナー アプリケーションとは、デザイン モードでメタファイル DC を使用してコントロールのイメージを選択する場合もあります。  
  
 メタファイルの描画要求は 2 個のインターフェイス関数によってコンテナーに対して行うことも、T: **IViewObject::Draw** \(この関数は非メタファイルの描画を求めることができます\) と **IDataObject::GetData**。  メタファイル DC がパラメーターの 1 文字として渡された場合、フレームワークは [COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)を呼び出します。  仮想メンバー関数であるため、特別な処理をするコントロール クラスでこの関数をオーバーライドします。  既定の動作では、`COleControl::OnDraw`を呼び出します。  
  
 コントロールを確認するには、画面に描画され、メタファイルのデバイス コンテキスト、画面、メタファイル DC の両方でサポートされているメンバー関数でのみ使用する必要があります。  座標系がピクセル単位されない場合があることに注意してください。  
  
 `OnDrawMetafile` の既定の実装がコントロールの `OnDraw` 関数を呼び出すため、`OnDrawMetafile`をオーバーライドして、メタファイルと画面デバイス コンテキスト用に適しているメンバー関数だけを使用します。  次に、メタファイル画面デバイス コンテキストの両方で利用できる `CDC` のメンバー関数のサブセットが表示されます。  これらの関数の詳細については、" *MFC リファレンス"の*" [CDC](../Topic/CDC%20Class.md) クラスを参照します。  
  
|円弧|BibBlt|弦|  
|--------|------------|-------|  
|**楕円**|**エスケープ特殊文字**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**Polygon**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 `CDC` のメンバー関数に加えて、メタファイル DC で互換性のある他のいくつかの関数があります。  これらは `CBrush`の [CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)、[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)と 3 人が含まれます。: [CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)、[CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)と [CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)。  
  
 メタファイルを記録しない関数は、次の操作: [DrawFocusRect](../Topic/CDC::DrawFocusRect.md)、[DrawIcon](../Topic/CDC::DrawIcon.md)、[DrawText](../Topic/CDC::DrawText.md)、[ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md)、[FillRect](../Topic/CDC::FillRect.md)、[FrameRect](../Topic/CDC::FrameRect.md)、[GrayString](../Topic/CDC::GrayString.md)、[InvertRect](../Topic/CDC::InvertRect.md)、[ScrollDC](../Topic/CDC::ScrollDC.md)と [TabbedTextOut](../Topic/CDC::TabbedTextOut.md)。  メタファイル DC がデバイスによって実際に関連付けられていないため、メタファイル DC の SetDIBits、GetDIBits と CreateDIBitmap を使用できません。  先としてメタファイル DC の SetDIBitsToDevice と StretchDIBits を使用できます。  [CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md)、[CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)と [CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md) はメタファイル DC と意味がありません。  
  
 メタファイル DC を使用する場合、座標系はピクセル単位されないことかを検討する別の点。  したがって、描画コードはすべて `rcBounds` パラメーターの `OnDraw`に渡される四角形の範囲に調整してください。  これは `rcBounds` 制御がウィンドウのサイズを表すため、コントロールの外側の誤ったを描画します。  
  
 コントロールのメタファイルの描画を実装した後、メタファイルをテストするには、テスト コンテナーを使用します。  テスト コンテナーへのアクセス方法については、「[テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)」を参照してください。  
  
#### コントロールのメタファイルをテスト コンテナーでテストするには  
  
1.  テスト コンテナーの **編集** メニューで、**新しいコントロールを挿入**をクリックします。  
  
2.  **新しいコントロールを挿入** ボックスで、コントロールを選択し、**\[OK\]** をクリックします。  
  
     コントロールはテスト コンテナーに表示されます。  
  
3.  **コントロール** メニュー **メタファイルの描画**。  
  
     別のウィンドウはメタファイルが表示される位置に表示されます。  スケーリングがコントロールのメタファイルにどのように影響するかを参照するには、このウィンドウのサイズを変更できます。  このウィンドウをいつでも閉じることができます。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)