---
title: "CDC クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDC
dev_langs:
- C++
helpviewer_keywords:
- Windows [C++], device contexts
- Windows 95 [C++], screen coordinates
- device contexts [C++], CDC class
- screen coordinates in device contexts
- coordinates in Windows 95/98 [C++]
- Windows 98 [C++], screen coordinates
- CDC class
ms.assetid: 715b3334-cb2b-4c9c-8067-02eb7c66c8b2
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 80ccd3f8bed6bd74e22d4db5e176ee50528d3187
ms.lasthandoff: 02/24/2017

---
# <a name="cdc-class"></a>CDC クラス
デバイス コンテキスト オブジェクトのクラスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDC : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDC::CDC](#cdc)|`CDC` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDC::AbortDoc](#abortdoc)|現在の印刷ジョブの最後に呼び出した後、アプリケーションがデバイスに書き込みがすべて消去を終了、`StartDoc`メンバー関数。|  
|[CDC::AbortPath](#abortpath)|閉じ、デバイス コンテキストの任意のパスを破棄します。|  
|[CDC::AddMetaFileComment](#addmetafilecomment)|バッファーから、指定された拡張メタファイルにコメントをコピーします。|  
|[CDC::AlphaBlend](#alphablend)|透明または半透明ピクセルのビットマップを表示します。|  
|[CDC::AngleArc](#anglearc)|線分と円弧を描画し、現在の位置を円弧の終点に移動します。|  
|[除いて](#arc)|楕円の円弧を描画します。|  
|[CDC::ArcTo](#arcto)|楕円の円弧を描画します。 この機能に似ています`Arc`の現在の位置が更新される点が異なります。|  
|[CDC::Attach](#attach)|この Windows デバイス コンテキストにアタッチ`CDC`オブジェクトです。|  
|[Cdc::beginpath](#beginpath)|デバイス コンテキストでは、パスの角かっこを開きます。|  
|[ビットマップ](#bitblt)|指定したデバイス コンテキストからビットマップをコピーします。|  
|[CDC::Chord](#chord)|弦 (楕円と直線セグメントで囲まれる閉じた図) を描画します。|  
|[CDC::CloseFigure](#closefigure)|パス内の開いている図を閉じます。|  
|[CDC::CreateCompatibleDC](#createcompatibledc)|別のデバイス コンテキストと互換性があるメモリ デバイス コンテキストを作成します。 メモリ内のイメージを準備するのにには、それを使用できます。|  
|[CDC::CreateDC](#createdc)|特定のデバイスのデバイス コンテキストを作成します。|  
|[CDC::CreateIC](#createic)|特定のデバイスの情報コンテキストを作成します。 これは、高速デバイス コンテキストを作成することがなく、デバイスに関する情報を取得する方法を提供します。|  
|[デバイス コンテキストの破棄](#deletedc)|これに関連付けられている Windows デバイス コンテキストを削除`CDC`オブジェクトです。|  
|[CDC::DeleteTempMap](#deletetempmap)|によって呼び出される、`CWinApp`アイドル時間のハンドラーを一時的なを削除する`CDC`によって作成されたオブジェクト`FromHandle`します。 デバイス コンテキストもデタッチします。|  
|[CDC::Detach](#detach)|これから Windows のデバイス コンテキストを切り離します`CDC`オブジェクトです。|  
|[CDC::DPtoHIMETRIC](#dptohimetric)|デバイス単位**HIMETRIC**単位です。|  
|[CDC::DPtoLP](#dptolp)|デバイス単位を論理単位に変換します。|  
|[CDC::Draw3dRect](#draw3drect)|3 次元の四角形を描画します。|  
|[CDC::DrawDragRect](#drawdragrect)|消去し、ドラッグされると、四角形を再描画します。|  
|[CDC::DrawEdge](#drawedge)|四角形のエッジを描画します。|  
|[CDC::DrawEscape](#drawescape)|描画グラフィックス デバイス インターフェイス (GDI) を通じて直接提供されていないビデオ ディスプレイの機能にアクセスします。|  
|[CDC::DrawFocusRect](#drawfocusrect)|フォーカスを示すために使用するスタイルでは、四角形を描画します。|  
|[CDC::DrawFrameControl](#drawframecontrol)|Frame コントロールを描画します。|  
|[CDC::DrawIcon](#drawicon)|アイコンを描画します。|  
|[CDC::DrawState](#drawstate)|イメージを表示し、状態を示すための視覚効果を適用します。|  
|[CDC::DrawText](#drawtext)|書式設定された指定された四角形内のテキストを描画します。|  
|[には](#drawtextex)|書式設定されたその他の形式を使用して指定された四角形内のテキストを描画します。|  
|[CDC::Ellipse](#ellipse)|楕円を描きます。|  
|[CDC::EndDoc](#enddoc)|開始した印刷ジョブを終了、`StartDoc`メンバー関数。|  
|[CDC::EndPage](#endpage)|ページが終了したデバイス ドライバーに通知します。|  
|[CDC::EndPath](#endpath)|パスの角かっこを終了し、デバイス コンテキストに、角かっこで定義されているパスを選択します。|  
|[Cdc::enumobjects](#enumobjects)|ペンを列挙し、デバイス コンテキストで使用できるブラシします。|  
|[CDC::Escape](#escape)|アプリケーションは GDI を介して特定のデバイスから直接利用できない機能にアクセスできます。 Windows エスケープ関数へのアクセスができます。 アプリケーションによって行われたエスケープ呼び出しでは、変換され、デバイス ドライバーに送信することができます。|  
|[CDC::ExcludeClipRect](#excludecliprect)|指定された四角形から既存のクリッピング領域で構成される新しいクリップ領域を作成します。|  
|[CDC::ExcludeUpdateRgn](#excludeupdatergn)|クリッピング領域から更新されたウィンドウ領域を除外することで無効なウィンドウ領域内での描画を防止します。|  
|[CDC::ExtFloodFill](#extfloodfill)|現在のブラシで領域を塗りつぶします。 も柔軟性が、 [CDC::FloodFill](#floodfill)メンバー関数。|  
|[CDC::ExtTextOut](#exttextout)|現在選択されているフォントを使用して四角形領域内に文字列を書き込みます。|  
|[CDC::FillPath](#fillpath)|現在のパス内の開いている図形を閉じ、現在のブラシと多角形の塗りつぶしモードを使用してパスの内部を塗りつぶします。|  
|[CDC::FillRect](#fillrect)|特定のブラシを使用して、指定した四角形を格納します。|  
|[CDC::FillRgn](#fillrgn)|指定されたブラシを使用して特定の領域を塗りつぶします。|  
|[CDC::FillSolidRect](#fillsolidrect)|四角形を純色で塗りつぶします。|  
|[CDC::FlattenPath](#flattenpath)|現在のデバイス コンテキストに選択したパス内の任意の曲線を変換しを一連の行の各曲線をオンにします。|  
|[CDC::FloodFill](#floodfill)|現在のブラシで領域を塗りつぶします。|  
|[CDC::FrameRect](#framerect)|四角形の境界線を描画します。|  
|[CDC::FrameRgn](#framergn)|ブラシを使用して特定の領域の周りに罫線を描画します。|  
|[CDC::FromHandle](#fromhandle)|ポインターを返す、`CDC`デバイス コンテキストを識別するハンドルが指定されるとします。 `CDC` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CDC` オブジェクトが生成され、関連付けられます。|  
|[CDC::GetArcDirection](#getarcdirection)|デバイス コンテキストの現在の円弧の方向を取得します。|  
|[CDC::GetAspectRatioFilter](#getaspectratiofilter)|現在の縦横比フィルターの設定を取得します。|  
|[CDC::GetBkColor](#getbkcolor)|現在の背景色を取得します。|  
|[CDC::GetBkMode](#getbkmode)|バック グラウンド モードを取得します。|  
|[CDC::GetBoundsRect](#getboundsrect)|指定したデバイス コンテキストに現在の累計の外接する四角を返します。|  
|[CDC::GetBrushOrg](#getbrushorg)|現在のブラシの原点を取得します。|  
|[CDC::GetCharABCWidths](#getcharabcwidths)|論理ユニットは、現在のフォントから特定の範囲内で連続する文字の幅を取得します。|  
|[CDC::GetCharABCWidthsI](#getcharabcwidthsi)|現在の TrueType フォントから指定された範囲内の連続したグリフのインデックスの論理単位の幅を取得します。|  
|[CDC::GetCharacterPlacement](#getcharacterplacement)|文字列に関するさまざまな情報を取得します。|  
|[CDC::GetCharWidth](#getcharwidth)|現在のフォントから特定の範囲内で連続する文字の小数部の幅を取得します。|  
|[CDC::GetCharWidthI](#getcharwidthi)|現在のフォントから指定された範囲内の連続したグリフのインデックスの論理座標で表したの幅を取得します。|  
|[CDC::GetClipBox](#getclipbox)|現在のクリップ領域を最小の外接する四角形の寸法を取得します。|  
|[CDC::GetColorAdjustment](#getcoloradjustment)|デバイス コンテキストの色の調整値を取得します。|  
|[CDC::GetCurrentBitmap](#getcurrentbitmap)|現在選択されているポインターを返します`CBitmap`オブジェクトです。|  
|[CDC::GetCurrentBrush](#getcurrentbrush)|現在選択されているポインターを返します`CBrush`オブジェクトです。|  
|[CDC::GetCurrentFont](#getcurrentfont)|現在選択されているポインターを返します`CFont`オブジェクトです。|  
|[CDC::GetCurrentPalette](#getcurrentpalette)|現在選択されているポインターを返します`CPalette`オブジェクトです。|  
|[CDC::GetCurrentPen](#getcurrentpen)|現在選択されているポインターを返します`CPen`オブジェクトです。|  
|[CDC::GetCurrentPosition](#getcurrentposition)|(論理座標) で、ペンの現在位置を取得します。|  
|[CDC::GetDCBrushColor](#getdcbrushcolor)|現在のブラシの色を取得します。|  
|[CDC::GetDCPenColor](#getdcpencolor)|現在のペンの色を取得します。|  
|[について](#getdevicecaps)|指定した特定のディスプレイ デバイスの機能のデバイスに固有の情報の種類を取得します。|  
|[CDC::GetFontData](#getfontdata)|スケーラブルなフォント ファイルからフォント メトリック情報を取得します。 取得する情報は、フォント ファイルと返される情報の長さにオフセットを指定することによって識別されます。|  
|[CDC::GetFontLanguageInfo](#getfontlanguageinfo)|指定した表示のコンテキストで現在選択されているフォントについての情報を返します。|  
|[CDC::GetGlyphOutline](#getglyphoutline)|アウトライン曲線または現在のフォントのアウトライン文字用のビットマップを取得します。|  
|[CDC::GetGraphicsMode](#getgraphicsmode)|指定したデバイス コンテキストの現在のグラフィックス モードを取得します。|  
|[CDC::GetHalftoneBrush](#gethalftonebrush)|ハーフトーン ブラシを取得します。|  
|[CDC::GetKerningPairs](#getkerningpairs)|文字のカーニング、指定したデバイス コンテキストで現在選択されているフォントのペアを取得します。|  
|[CDC::GetLayout](#getlayout)|デバイス コンテキスト (DC) のレイアウトを取得します。 レイアウトでくか、左から右 (既定値) または右左から (ミラー)。|  
|[CDC::GetMapMode](#getmapmode)|現在のマップ モードを取得します。|  
|[CDC::GetMiterLimit](#getmiterlimit)|デバイス コンテキストのマイター リミットを返します。|  
|[CDC::GetNearestColor](#getnearestcolor)|特定のデバイスを表すことができる指定された論理色に最も近い論理色を取得します。|  
|[CDC::GetOutlineTextMetrics](#getoutlinetextmetrics)|TrueType フォントのフォント メトリック情報を取得します。|  
|[CDC::GetOutputCharWidth](#getoutputcharwidth)|出力デバイス コンテキストを使用して現在のフォントの文字の隣接するグループ内の個々 の文字幅を取得します。|  
|[CDC::GetOutputTabbedTextExtent](#getoutputtabbedtextextent)|幅と、出力デバイス コンテキストの文字列の高さを計算します。|  
|[CDC::GetOutputTextExtent](#getoutputtextextent)|大きさを現在のフォントを使用して、出力デバイス コンテキスト上のテキストの行の高さと幅を計算します。|  
|[CDC::GetOutputTextMetrics](#getoutputtextmetrics)|出力デバイス コンテキストから現在のフォント メトリックを取得します。|  
|[CDC::GetPath](#getpath)|行のエンドポイントとデバイス コンテキストに選択されているパスに含まれる曲線の制御点を定義する座標を取得します。|  
|[CDC::GetPixel](#getpixel)|指定したポイントにピクセルの RGB 色の値を取得します。|  
|[CDC::GetPolyFillMode](#getpolyfillmode)|現在の多角形の塗りつぶしモードを取得します。|  
|[CDC::GetROP2](#getrop2)|現在の描画モードを取得します。|  
|[CDC::GetSafeHdc](#getsafehdc)|返します。 [CDC::m_hDC](#m_hdc)、出力デバイス コンテキスト。|  
|[CDC::GetStretchBltMode](#getstretchbltmode)|現在のビットマップの伸縮モードを取得します。|  
|[CDC::GetTabbedTextExtent](#gettabbedtextextent)|幅と高さの属性のデバイス コンテキストでの文字列を計算します。|  
|[CDC::GetTextAlign](#gettextalign)|テキスト配置フラグを取得します。|  
|[CDC::GetTextCharacterExtra](#gettextcharacterextra)|文字間隔の現在の設定を取得します。|  
|[CDC::GetTextColor](#gettextcolor)|現在のテキストの色を取得します。|  
|[CDC::GetTextExtent](#gettextextent)|大きさを現在のフォントを使用して属性のデバイス コンテキスト上のテキストの行の高さと幅を計算します。|  
|[CDC::GetTextExtentExPointI](#gettextextentexpointi)|指定された領域内に収まるし、それらの各文字のテキストのエクステントを配列に設定を指定した文字列の文字数を取得します。|  
|[CDC::GetTextExtentPointI](#gettextextentpointi)|幅と高さの指定されたグリフのインデックスの配列を取得します。|  
|[CDC::GetTextFace](#gettextface)|現在のフォントの書体名を null で終わる文字列としてのバッファーにコピーします。|  
|[CDC::GetTextMetrics](#gettextmetrics)|属性のデバイス コンテキストから現在のフォント メトリックを取得します。|  
|[CDC::GetViewportExt](#getviewportext)|ビューポートの x 範囲と y 範囲を取得します。|  
|[CDC::GetViewportOrg](#getviewportorg)|ビューポートの原点の x 座標と y 座標を取得します。|  
|[CDC::GetWindow](#getwindow)|ディスプレイ デバイス コンテキストに関連付けられているウィンドウを返します。|  
|[CDC::GetWindowExt](#getwindowext)|関連するウィンドウの x 範囲と y 範囲を取得します。|  
|[CDC::GetWindowOrg](#getwindoworg)|関連するウィンドウの原点の x と y 座標を取得します。|  
|[CDC::GetWorldTransform](#getworldtransform)|ページ領域の変換に現在のワールド空間を取得します。|  
|[CDC::GradientFill](#gradientfill)|四角形と三角形の構造体を gradating 色で塗りつぶします。|  
|[Cdc::graystring](#graystring)|描画には、指定された場所に (灰色) のテキストが淡色表示されます。|  
|[CDC::HIMETRICtoDP](#himetrictodp)|変換**HIMETRIC**デバイス単位 (ou) の単位です。|  
|[CDC::HIMETRICtoLP](#himetrictolp)|変換**HIMETRIC**単位の論理単位にします。|  
|[CDC::IntersectClipRect](#intersectcliprect)|現在のリージョンと四角形の交差部分を形成する、新しいクリップ領域を作成します。|  
|[CDC::InvertRect](#invertrect)|四角形の内容を反転します。|  
|[CDC::InvertRgn](#invertrgn)|領域内の色を反転します。|  
|[CDC::IsPrinting](#isprinting)|デバイス コンテキストが印刷に使用されているかどうかを決定します。|  
|[CDC::LineTo](#lineto)|現在の位置が、点の直線を描画します。|  
|[CDC::LPtoDP](#lptodp)|論理ユニットをデバイス単位に変換します。|  
|[CDC::LPtoHIMETRIC](#lptohimetric)|論理単位に変換**HIMETRIC**単位です。|  
|[CDC::MaskBlt](#maskblt)|指定されたマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。|  
|[CDC::ModifyWorldTransform](#modifyworldtransform)|指定されたモードを使用してデバイス コンテキストのワールド変換を変更します。|  
|[CDC::MoveTo](#moveto)|現在の位置に移動します。|  
|[CDC::OffsetClipRgn](#offsetcliprgn)|特定のデバイスのクリッピング領域に移動します。|  
|[CDC::OffsetViewportOrg](#offsetviewportorg)|現在のビューポートの原点の座標を基準とした、ビューポートの原点を変更します。|  
|[CDC::OffsetWindowOrg](#offsetwindoworg)|現在のウィンドウの原点の座標を基準としたウィンドウの原点を変更します。|  
|[CDC::PaintRgn](#paintrgn)|選択されたブラシで領域を塗りつぶします。|  
|[Cdc::patblt](#patblt)|ビット パターンを作成します。|  
|[CDC::Pie](#pie)|作られる扇形を描画します。|  
|[CDC::PlayMetaFile](#playmetafile)|特定のデバイスでは、指定されたメタファイルのコンテンツを再生します。 拡張版`PlayMetaFile`特定の拡張形式メタファイルに格納されている画像が表示されます。 メタファイルを何度でも再生できます。|  
|[CDC::PlgBlt](#plgblt)|元のデバイス コンテキストで指定された四角形から、指定したデバイス コンテキストで指定した平行四辺形に色データのビットのビット ブロック転送を実行します。|  
|[CDC::PolyBezier](#polybezier)|1 つまたは複数のベジエ スプラインを描画します。 現在の位置が使用も更新します。|  
|[CDC::PolyBezierTo](#polybezierto)|1 つまたは複数のベジエ スプラインを描画し、現在の位置を最後のベジエ スプラインの終了点に移動します。|  
|[CDC::PolyDraw](#polydraw)|一連の線分とベジエ スプラインを描画します。 この関数は、現在の位置を更新します。|  
|[CDC::Polygon](#polygon)|2 つ以上の点 (頂点) 折れ線でつないだで構成される多角形を描画します。|  
|[CDC::Polyline](#polyline)|一連の指定した点を結ぶ線分を描画します。|  
|[CDC::PolylineTo](#polylineto)|1 つまたは複数の直線を描画し、現在の位置を最後の行の終了位置に移動します。|  
|[CDC::PolyPolygon](#polypolygon)|現在の多角形の塗りつぶしモードで埋められた&2; つ以上の多角形を作成します。 多角形が切り離されたか、重なる可能性があります。|  
|[CDC::PolyPolyline](#polypolyline)|接続されている直線セグメントの複数の系列を描画します。 現在の位置が使用も、この関数で更新します。|  
|[CDC::PtVisible](#ptvisible)|指定したポイントがクリッピング領域内にあるかどうかを指定します。|  
|[:Realizepalette](#realizepalette)|現在の論理パレットのパレット エントリをシステム パレットにマップします。|  
|[CDC::Rectangle](#rectangle)|現在のペンを使用して四角形を描画し、現在のブラシを使用してそれを塗りつぶします。|  
|[CDC::RectVisible](#rectvisible)|クリップ領域内に指定された四角形の任意の部分があるかどうかを決定します。|  
|[CDC::ReleaseAttribDC](#releaseattribdc)|リリース`m_hAttribDC`属性のデバイス コンテキスト。|  
|[CDC::ReleaseOutputDC](#releaseoutputdc)|リリース`m_hDC`、出力デバイス コンテキスト。|  
|[CDC::ResetDC](#resetdc)|更新プログラム、`m_hAttribDC`デバイス コンテキスト。|  
|[CDC::RestoreDC](#restoredc)|デバイス コンテキストをと共に保存される前の状態に復元され`SaveDC`します。|  
|[CDC::RoundRect](#roundrect)|設定され、現在のペンを使用して、現在のブラシを使用して設定の角の丸い四角形を描画します。|  
|[CDC::SaveDC](#savedc)|デバイス コンテキストの現在の状態を保存します。|  
|[CDC::ScaleViewportExt](#scaleviewportext)|現在の値を基準としたビューポートの範囲を変更します。|  
|[CDC::ScaleWindowExt](#scalewindowext)|現在の値を基準としたウィンドウの範囲を変更します。|  
|[CDC::ScrollDC](#scrolldc)|水平方向および垂直方向には、bits の四角形をスクロールします。|  
|[CDC::SelectClipPath](#selectclippath)|指定のモードを使用して、既存のクリッピング領域で新しい地域を結合したデバイス コンテキストのクリッピング領域として、現在のパスを選択します。|  
|[CDC::SelectClipRgn](#selectcliprgn)|指定されたモードを使用して、現在のクリップ領域と指定された領域を結合します。|  
|[:Selectobject](#selectobject)|ペンなどの GDI 描画オブジェクトを選択します。|  
|[CDC::SelectPalette](#selectpalette)|論理パレットを選択します。|  
|[CDC::SelectStockObject](#selectstockobject)|定義済みのストック ペン、ブラシ、または Windows によって提供されるフォントのいずれかを選択します。|  
|[Cdc::setabortproc](#setabortproc)|Windows を呼び出す場合は、印刷ジョブを中断する必要がありますプログラマが指定したコールバック関数を設定します。|  
|[CDC::SetArcDirection](#setarcdirection)|弧と四角形の関数に使用する描画方向を設定します。|  
|[CDC::SetAttribDC](#setattribdc)|セット`m_hAttribDC`属性のデバイス コンテキスト。|  
|[CDC::SetBkColor](#setbkcolor)|現在の背景色を設定します。|  
|[CDC::SetBkMode](#setbkmode)|バック グラウンド モードを設定します。|  
|[CDC::SetBoundsRect](#setboundsrect)|指定したデバイス コンテキストの外接する四角情報の蓄積を制御します。|  
|[CDC::SetBrushOrg](#setbrushorg)|デバイス コンテキストに選択されている次のブラシの原点を指定します。|  
|[CDC::SetColorAdjustment](#setcoloradjustment)|指定した値を使用してデバイス コンテキストの色の調整値を設定します。|  
|[CDC::SetDCBrushColor](#setdcbrushcolor)|現在のブラシの色を設定します。|  
|[CDC::SetDCPenColor](#setdcpencolor)|現在のペンの色を設定します。|  
|[CDC::SetGraphicsMode](#setgraphicsmode)|指定したデバイス コンテキストの現在のグラフィックス モードを設定します。|  
|[CDC::SetLayout](#setlayout)|デバイス コンテキスト (DC) のレイアウトを変更します。|  
|[CDC::SetMapMode](#setmapmode)|現在のマップ モードを設定します。|  
|[CDC::SetMapperFlags](#setmapperflags)|フォント マッパーが物理フォントの論理フォントをマップするときに使用するアルゴリズムを変更します。|  
|[CDC::SetMiterLimit](#setmiterlimit)|デバイス コンテキストのマイター結合の長さの制限を設定します。|  
|[CDC::SetOutputDC](#setoutputdc)|セット`m_hDC`、出力デバイス コンテキスト。|  
|[CDC::SetPixel](#setpixel)|指定された色の最も近い色を指定したポイントにピクセルを設定します。|  
|[CDC::SetPixelV](#setpixelv)|指定された色の最も近い色を指定した座標にあるピクセルに設定します。 `SetPixelV`も高速`SetPixel`を実際に描画されたポイントの色の値を返す必要はありませんので。|  
|[CDC::SetPolyFillMode](#setpolyfillmode)|多角形の塗りつぶしモードを設定します。|  
|[CDC::SetROP2](#setrop2)|現在の描画モードを設定します。|  
|[CDC::SetStretchBltMode](#setstretchbltmode)|ビットマップの伸縮モードを設定します。|  
|[CDC::SetTextAlign](#settextalign)|テキスト配置フラグを設定します。|  
|[CDC::SetTextCharacterExtra](#settextcharacterextra)|文字間隔の量を設定します。|  
|[CDC::SetTextColor](#settextcolor)|テキストの色を設定します。|  
|[CDC::SetTextJustification](#settextjustification)|文字列の区切り文字にスペースを追加します。|  
|[CDC::SetViewportExt](#setviewportext)|ビューポートの x 範囲と y 範囲を設定します。|  
|[CDC::SetViewportOrg](#setviewportorg)|ビューポートの原点を設定します。|  
|[CDC::SetWindowExt](#setwindowext)|関連するウィンドウの x 範囲と y 範囲を設定します。|  
|[CDC::SetWindowOrg](#setwindoworg)|デバイス コンテキストのウィンドウの原点を設定します。|  
|[CDC::SetWorldTransform](#setworldtransform)|ページ座標に変換するには、現在のワールド空間を設定します。|  
|[CDC::StartDoc](#startdoc)|新しい印刷ジョブが開始されるデバイス ドライバーに通知します。|  
|[CDC::StartPage](#startpage)|新しいページが開始されるデバイス ドライバーに通知します。|  
|[CDC::StretchBlt](#stretchblt)|先の四角形を拡大またはビットマップを圧縮すると、コピー先の四角形の寸法に合わせて必要な場合に、元の四角形とデバイスからビットマップを移動します。|  
|[CDC::StrokeAndFillPath](#strokeandfillpath)|パス内の開いている図形を閉じ、現在のペンを使用して、パスのアウトラインを襲う、現在のブラシを使用して、その内部を塗りつぶします。|  
|[CDC::StrokePath](#strokepath)|現在のペンを使用して、指定されたパスを描画します。|  
|[CDC::TabbedTextOut](#tabbedtextout)|タブを展開する、タブ ストップの位置の配列で指定した値に指定の位置にある文字の文字列を書き込みます。|  
|[CDC::TextOut](#textout)|現在選択されているフォントを使用して指定位置にある文字の文字列を書き込みます。|  
|[CDC::TransparentBlt](#transparentblt)|指定した発信元デバイス コンテキストから色データのビット ブロックを転送に透過的な指定された色を表示、コピー先デバイス コンテキストに転送されます。|  
|[CDC::UpdateColors](#updatecolors)|クライアント領域のピクセルごとにシステム パレットで現在を照合することによって、デバイス コンテキストのクライアント領域の色を更新します。|  
|[CDC::WidenPath](#widenpath)|パスがデバイス コンテキストに現在選択されているペンを使用して描画された場合に描画される領域として、現在のパスを再定義します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDC::operator HDC](#operator_hdc)|デバイス コンテキストのハンドルを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDC::m_hAttribDC](#m_hattribdc)|これで使用される属性デバイス コンテキスト`CDC`オブジェクトです。|  
|[CDC::m_hDC](#m_hdc)|これで使用される出力デバイス コンテキスト`CDC`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CDC`オブジェクトは、ウィンドウのクライアント領域に関連付けられているディスプレイ コンテキストを操作するためのディスプレイやプリンターだけでなく、メンバーなどのデバイス コンテキストを操作するためのメンバー関数を提供します。  
  
 関数、メンバーをすべての描画を行う、`CDC`オブジェクトです。 クラスは、メンバー関数を描画ツール、タイプ セーフなグラフィックス デバイス インターフェイス (GDI) オブジェクトの選択、色とパレットを使用すると、デバイス コンテキストの操作を提供します。 取得および設定のマッピング、動作してビューポートの操作ウィンドウの範囲座標の変換、領域の処理時刻が、線を描画およびと、単純な図形、楕円、多角形を描画が描画属性のメンバー関数も提供します。 メンバー関数は、テキストの描画、フォントの操作、プリンター エスケープを使用して、スクロール、およびメタファイルの再生にも提供されます。  
  
 使用する、`CDC`オブジェクト、構築、および、そのメンバーを呼び出してデバイス コンテキストを使用して Windows 関数を並列関数です。  
  
> [!NOTE]
>  Windows 95/98 では、すべての画面座標は、16 ビットに制限されます。 したがって、`int`に渡される、 `CDC` -32768 ~ 32767 の範囲のメンバー関数がある必要があります。  
  
 Microsoft Foundation Class ライブラリがから派生したいくつかのクラスを提供する特定の用途では、`CDC`です。 `CPaintDC`呼び出しをカプセル化`BeginPaint`と`EndPaint`です。 `CClientDC`ウィンドウのクライアント領域に関連付けられているディスプレイ コンテキストを管理します。 `CWindowDC`フレーム コントロールを含むウィンドウ全体に関連付けられているディスプレイ コンテキストを管理します。 `CMetaFileDC`メタファイルとデバイス コンテキストに関連付けます。  
  
 `CDC`2 つのメンバー関数は、 [GetLayout](#getlayout)と[SetLayout](#setlayout)、ウィンドウからのレイアウトを継承しないデバイス コンテキストのレイアウトの反転のです。 このような右から左の方向は、アラビア語やヘブライ語の文字のレイアウトがヨーロッパの標準ではありませんなどのカルチャ用に記述されたアプリケーションの必要があります。  
  
 `CDC`2 つのデバイス コンテキストを含む[m_hDC](#m_hdc)と[は](#m_hattribdc)、これはの作成時に、`CDC`オブジェクト、同じデバイスを参照してください。 `CDC`すべての出力 GDI の呼び出しを指示`m_hDC`ほとんどオブジェクトおよび`m_hAttribDC`です。 (属性呼び出しの例は、 `GetTextColor`、中に`SetTextColor`出力呼び出しです)。  
  
 フレームワークがこれらの&2; つのデバイス コンテキストを使用して実装するなど、`CMetaFileDC`はメタファイルを物理デバイスからの属性を読み取り中に出力を送信するオブジェクト。 印刷プレビューは、同様の方法で、framework に実装されます。 特定のアプリケーション コードで同様の方法で&2; つのデバイス コンテキストを使用することもできます。  
  
 両方のテキスト メトリック情報を必要があるタイミングは、`m_hDC`と`m_hAttribDC`デバイス コンテキスト。 次の関数のペアは、この機能を提供します。  
  
|使用してください。|M_hDC を使用します。|  
|-----------------------|-----------------|  
|[通常](#gettextextent)|[GetOutputTextExtent](#getoutputtextextent)|  
|[GetTabbedTextExtent](#gettabbedtextextent)|[GetOutputTabbedTextExtent](#getoutputtabbedtextextent)|  
|[GetTextMetrics](#gettextmetrics)|[GetOutputTextMetrics](#getoutputtextmetrics)|  
|[GetCharWidth](#getcharwidth)|[GetOutputCharWidth](#getoutputcharwidth)|  
  
 詳細については`CDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameabortdoca--cdcabortdoc"></a><a name="abortdoc"></a>CDC::AbortDoc  
 現在の印刷ジョブを終了し、最後の呼び出し以降にアプリケーションがデバイスに書き込みがすべてクリア、 [StartDoc](#startdoc)メンバー関数。  
  
```  
int AbortDoc();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以上の値や負の値を使用している場合はエラーが発生しました。 一般的なエラー値とその意味を次に示します。  
  
- **SP_ERROR**一般的なエラーです。  
  
- **させることでより**のに十分なディスク領域が、スプールのため現在使用できると、空き領域がないが表示されます。  
  
- **SP_OUTOFMEMORY**スプールのためのに十分なメモリがあります。  
  
- **SP_USERABORT**ユーザーが印刷マネージャーを使ってジョブを終了します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数、`ABORTDOC`プリンター エスケープします。  
  
 **AbortDoc**を次を終了するために使用する必要があります。  
  
-   Abort 関数を使用して、指定されていない印刷操作[SetAbortProc](#setabortproc)します。  
  
-   最初に到達していない印刷操作**NEWFRAME**または**NEXTBAND**呼び出しをエスケープします。  
  
 アプリケーションでは、印刷のエラーや印刷操作の中止が発生すると、そのしないでくださいいずれかを使用して操作を終了、 [EndDoc](#enddoc)または**AbortDoc**クラスのメンバー関数`CDC`します。 GDI は、エラー値を返す前に、操作を自動的に終了します。  
  
 呼び出すこと必要がありますが、アプリケーションがユーザーに、印刷操作の取り消しを許可する ダイアログ ボックスが表示される場合**AbortDoc**  ダイアログ ボックスを破棄する前にします。  
  
 印刷ジョブを開始するように印刷マネージャーを使用していた場合を呼び出す**AbortDoc**全体スプール ジョブの消去: プリンターが何も受信します。 以前に印刷ジョブを開始する印刷マネージャーを使用しない場合、データに送信された前に、プリンター **AbortDoc**呼び出されました。 この場合、プリンター ドライバーを使用すると、可能な場合)、プリンタをリセットされ、印刷ジョブを閉じます。  
  
### <a name="example"></a>例  
  例を参照してください[CDC::StartDoc](#startdoc)します。  
  
##  <a name="a-nameabortpatha--cdcabortpath"></a><a name="abortpath"></a>CDC::AbortPath  
 閉じ、デバイス コンテキストの任意のパスを破棄します。  
  
```  
BOOL AbortPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストで開かれたパス ブラケットがある場合は、パスのブラケットが閉じられ、パスが破棄されます。 デバイス コンテキストに閉じたパスがある場合は、パスが破棄されます。  
  
##  <a name="a-nameaddmetafilecommenta--cdcaddmetafilecomment"></a><a name="addmetafilecomment"></a>CDC::AddMetaFileComment  
 バッファーから、指定された拡張メタファイルにコメントをコピーします。  
  
```  
BOOL AddMetaFileComment(
    UINT nDataSize,  
    const BYTE* pCommentData);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDataSize*  
 コメント バッファーの長さをバイト単位で指定します。  
  
 *pCommentData*  
 コメントが含まれているバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コメントは、プライベートな情報を含めることがあります: などの画像と、日付のソースに作成されました。 コメントは、続くデータ アプリケーションの署名で始める必要があります。 コメントには、位置に固有のデータが含まれていない必要があります。 位置に固有のデータは、レコードの場所を指定しに含めてはなりませんので別メタファイル内に&1; つのメタファイルを埋め込むことがあります。 この関数は、拡張メタファイルでのみ使用できます。  
  
##  <a name="a-namealphablenda--cdcalphablend"></a><a name="alphablend"></a>CDC::AlphaBlend  
 透明または半透明ピクセルのビットマップを表示するには、このメンバー関数を呼び出します。  
  
```  
BOOL AlphaBlend(
    int xDest,  
    int yDest,  
    int nDestWidth,  
    int nDestHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    BLENDFUNCTION blend);
```  
  
### <a name="parameters"></a>パラメーター  
 `xDest`  
 論理ユニットは、コピー先の四角形の左上隅の x 座標を指定します。  
  
 `yDest`  
 論理ユニットは、コピー先の四角形の左上隅の y 座標を指定します。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅を指定します。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さを指定します。  
  
 `pSrcDC`  
 転送元デバイス コンテキストへのポインター。  
  
 `xSrc`  
 論理ユニットは、元の四角形の左上隅の x 座標を指定します。  
  
 `ySrc`  
 論理ユニットは、元の四角形の左上隅の y 座標を指定します。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅を指定します。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さを指定します。  
  
 *blend*  
 指定する[BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393)構造体。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="a-nameanglearca--cdcanglearc"></a><a name="anglearc"></a>CDC::AngleArc  
 線分と円弧を描画します。  
  
```  
BOOL AngleArc(
    int x,  
    int y,  
    int nRadius,  
    float fStartAngle,  
    float fSweepAngle);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 円の中心となる論理 x 座標を指定します。  
  
 *y*  
 円の中心となる論理 y 座標を指定します。  
  
 *nRadius*  
 論理ユニットでは、円の半径を指定します。 この値は正である必要があります。  
  
 *fStartAngle*  
 X 軸を基準とした角度の開始角度を指定します。  
  
 *fSweepAngle*  
 開始角度を基準とした角度の掃引角度を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 直線セグメントは現在の位置から円弧の始点に描画されます。 指定した半径と中心の円の境界に沿った円弧を描画します。 円弧の長さは、特定の開始および掃引角度によって定義されます。  
  
 `AngleArc`現在の位置を円弧の終点に移動します。 現在の変換とマッピングのモードによっては楕円には、この関数で描画された円弧が表示されます。 円弧を描画する前に、この関数は、現在の位置から直線セグメントを円弧の始点に描画します。 円弧を描画するには、指定された中心点の指定した radius を使って仮想円を作成します。 円弧の開始点は、開始角度で度数で、円の x 軸から反時計回りに計測によって決定されます。 終了点は掃引角度で度数で、開始点から反時計回りに測定することで同様にあります。  
  
 掃引角度が 360 度より大きい場合、円弧は複数回です。 この関数は、現在のペンを使用して線を描画します。 この図は表示されません。  
  
##  <a name="a-namearca--cdcarc"></a><a name="arc"></a>除いて  
 楕円の円弧を描画します。  
  
```  
BOOL Arc(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Arc(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 (論理単位で) に外接する四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 (論理単位で) に外接する四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 (論理単位で) に外接する四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 (論理単位で) に外接する四角形の右下隅の y 座標を指定します。  
  
 *x3*  
 円弧を定義する点の x 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y3`  
 円弧を定義する点の y 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `x4`  
 (論理単位で) 円弧の終点を定義する点の x 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y4`  
 (論理単位で) 円弧の終点を定義する点の y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `lpRect`  
 (論理単位で) に外接する四角形を指定します。 いずれかを渡すことができます、`LPRECT`または[CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 `ptStart`  
 円弧を定義する点の x 座標と y 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
 `ptEnd`  
 (論理単位で) の円弧の終点を定義する点の x 座標と y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数を使用して描画された円弧は、指定された外接する四角形によって定義される楕円のセグメントです。  
  
 円弧の実際の開始点は、指定された開始位置を外接する四角形の中心から描画光線が楕円に当たるポイントです。 円弧の実際の終了点は、指定の終了点を外接する四角形の中心から描画光線が楕円に当たるポイントです。 円弧を反時計回りに描画します。 円弧が閉じた図ではないためは表示されません。 四角形の高さと幅は、2 つのユニットより大きく、32,767 より小さい単位である必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&29;](../../mfc/codesnippet/cpp/cdc-class_1.cpp)]  
  
##  <a name="a-namearctoa--cdcarcto"></a><a name="arcto"></a>CDC::ArcTo  
 楕円の円弧を描画します。  
  
```  
BOOL ArcTo(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL ArcTo(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 (論理単位で) に外接する四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 (論理単位で) に外接する四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 (論理単位で) に外接する四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 (論理単位で) に外接する四角形の右下隅の y 座標を指定します。  
  
 *x3*  
 円弧を定義する点の x 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y3`  
 円弧を定義する点の y 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `x4`  
 (論理単位で) 円弧の終点を定義する点の x 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y4`  
 (論理単位で) 円弧の終点を定義する点の y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `lpRect`  
 (論理単位で) に外接する四角形を指定します。 ポインターを渡すことができます、 [RECT](../../mfc/reference/rect-structure1.md)データ構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 `ptStart`  
 円弧を定義する点の x 座標と y 座標の始点 (論理単位で) を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)データ構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
 `ptEnd`  
 (論理単位で) の円弧の終点を定義する点の x 座標と y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、**ポイント**データ構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この機能に似ています`CDC::Arc`の現在の位置が更新される点が異なります。 ポイント ( `x1`、 `y1`) と ( `x2`、 `y2`) 外接する四角形を指定します。 指定された外接する四角形によって形成される楕円は、円弧の曲線を定義します。 外接する四角形の中心から放射状の線が交差するポイントから円弧に (既定の円弧の方向) は反時計回りに ( *x3*、 `y3`)。 外接する四角形の中心から放射状の線が交差する円弧の終点点 ( `x4`、 `y4`)。 始点と終点が同じ場合は、完全な楕円が描画されます。  
  
 円弧の始点の現在位置から線が描画されます。 エラーが発生しない場合は、現在の位置が円弧の終点に設定されます。 現在のペンを使用して円弧を描画します。入力されていません。  
  
##  <a name="a-nameattacha--cdcattach"></a><a name="attach"></a>CDC::Attach  
 このメンバー関数を使用して、アタッチする、`hDC`に、`CDC`オブジェクトです。  
  
```  
BOOL Attach(HDC hDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 Windows のデバイス コンテキスト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `hDC`両方に格納されて`m_hDC`、出力デバイス コンテキスト  `m_hAttribDC`、属性デバイス コンテキスト。  
  
##  <a name="a-namebeginpatha--cdcbeginpath"></a><a name="beginpath"></a>Cdc::beginpath  
 デバイス コンテキストでは、パスの角かっこを開きます。  
  
```  
BOOL BeginPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 パス ブラケットを開いた後、アプリケーションはパスに存在する地点を定義する GDI 描画関数の呼び出しを開始できます。 アプリケーションが呼び出すことによって開かれたパス ブラケットを閉じることができます、`EndPath`メンバー関数。 アプリケーションを呼び出すと`BeginPath`、前のパスが破棄されます。  
  
 参照してください[アプリケーション](http://msdn.microsoft.com/library/windows/desktop/dd183363)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]パスのポイントを定義する描画関数の一覧にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&30;](../../mfc/codesnippet/cpp/cdc-class_2.cpp)]  
  
##  <a name="a-namebitblta--cdcbitblt"></a><a name="bitblt"></a>ビットマップ  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
```  
BOOL BitBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理でコピー先の四角形の左上隅の x 座標を指定します。  
  
 *y*  
 論理でコピー先の四角形の左上隅の y 座標を指定します。  
  
 `nWidth`  
 コピー先の四角形と元のビットマップの幅を (論理単位で指定します。  
  
 `nHeight`  
 コピー先の四角形と元のビットマップの高さを (論理単位で) 指定します。  
  
 `pSrcDC`  
 ポインター、`CDC`ビットマップのコピー元となるデバイス コンテキストを識別するオブジェクト。 必要があります**NULL**場合*dwRop*をソースを含まないラスター オペレーションを指定します。  
  
 `xSrc`  
 論理で元のビットマップの左上隅の x 座標を指定します。  
  
 `ySrc`  
 論理で元のビットマップの左上隅の y 座標を指定します。  
  
 *dwRop*  
 実行するラスター オペレーションを指定します。 ラスター オペレーション コードは、GDI が出力に関連する操作、現在のブラシ、有効なコピー元ビットマップとコピー先のビットマップの色を結合する方法を定義します。 参照してください[BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]のラスター オペレーション コードの一覧については*dwRop*とその説明  
  
 ラスター オペレーション コードの一覧については、次を参照してください。[ラスター オペレーション コードは](http://msdn.microsoft.com/library/windows/desktop/dd162892)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、windows またはいることを確認するバイト境界上のクライアント領域を揃えることが、`BitBlt`バイト境界で配置の四角形で操作が行われます。 (設定、 **CS_BYTEALIGNWINDOW**または**により**ウィンドウ クラスを登録するときにフラグを設定します)。  
  
 `BitBlt`四角形のバイト境界で配置の操作はよりかなり速く`BitBlt`バイト境界となる四角形で操作します。 デバイス コンテキストのバイト アラインメントなどのクラスのスタイルを指定する場合は、ウィンドウ クラスを登録する必要が行うために Microsoft Foundation class ではなく。 グローバル関数を使用して[AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)します。  
  
 Gdi は`nWidth`と`nHeight`コピー先デバイス コンテキストを使用して、1 回、および元デバイス コンテキストを使用して、1 回です。 GDI は、ウィンドウを使って作成されたエクステントが一致しない場合`StretchBlt`圧縮するか、必要に応じて、元のビットマップを拡大する関数。  
  
 変換先、ソース、およびパターン ビットマップに同じ色の書式があるない場合、`BitBlt`関数が、ソースとパターン ビットマップに合わせて、変換先に変換します。 変換では、コピー先のビットマップの前景色と背景色を使用します。  
  
 ときに、`BitBlt`関数モノクロ ビットマップをカラーに変換する、白のビット (1) を背景色、前景色に黒のビット (0) に設定します。 コピー先デバイス コンテキストの前景色と背景色が使用されます。 カラーをモノクロに変換する`BitBlt`背景色を白に一致するピクセルに設定し、その他のすべてのピクセルを黒に設定します。 `BitBlt`色からモノクロに変換するには、カラーのデバイス コンテキストの前景色と背景色を使用します。  
  
 すべてのデバイス コンテキストをサポートする注`BitBlt`します。 特定のデバイス コンテキストをサポートするかどうかをチェックする`BitBlt`を使用して、`GetDeviceCaps`メンバー関数を指定、 **RASTERCAPS**インデックス。  
  
### <a name="example"></a>例  
  例を参照してください[CDC::CreateCompatibleDC](#createcompatibledc)します。  
  
##  <a name="a-namecdca--cdccdc"></a><a name="cdc"></a>CDC::CDC  
 `CDC` オブジェクトを構築します。  
  
```  
CDC();
```  
  
##  <a name="a-namechorda--cdcchord"></a><a name="chord"></a>CDC::Chord  
 弦 (楕円と直線セグメントで囲まれる閉じた図) を描画します。  
  
```  
BOOL Chord(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Chord(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 コードの左上隅の x 座標外接する四角形 (論理単位で) を指定します。  
  
 `y1`  
 コードの左上隅の y 座標外接する四角形 (論理単位で) を指定します。  
  
 `x2`  
 コードの右下隅の x 座標外接する四角形 (論理単位で) を指定します。  
  
 `y2`  
 コードの右下隅の y 座標外接する四角形 (論理単位で) を指定します。  
  
 *x3*  
 弦点の x 座標の始点 (論理単位で) を指定します。  
  
 `y3`  
 弦点の y 座標の始点 (論理単位で) を指定します。  
  
 `x4`  
 (論理単位で弦のエンドポイントを定義する点の x 座標を指定します。  
  
 `y4`  
 (論理単位で弦のエンドポイントを定義する点の y 座標を指定します。  
  
 `lpRect`  
 (論理単位で) に外接する四角形を指定します。 いずれかを渡すことができます、`LPRECT`または[CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 `ptStart`  
 コードを定義する点の x と y 座標の始点 (論理単位で) を指定します。 このポイントは、コードに正確にする必要はありません。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
 `ptEnd`  
 (論理単位で弦の終点を定義する点の x 座標と y 座標を指定します。 このポイントは、コードに正確にする必要はありません。 いずれかを渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ( `x1`、 `y1`) と ( `x2`、 `y2`) パラメーター隅左上隅および右下、それぞれ指定コードの一部である楕円を囲む四角形。 ( *X3*、 `y3`) と ( `x4`、 `y4`) 楕円を交差する線の端点をパラメーターで指定します。 コードが選択されているペンを使用して描画され、選択されたブラシを使用して入力します。  
  
 描画する図形、`Chord`関数は、まで拡張しますが、右下隅の座標は含まれません。 つまり、figure の高さは`y2`– `y1` 、figure の幅は`x2`–`x1`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&31;](../../mfc/codesnippet/cpp/cdc-class_3.cpp)]  
  
##  <a name="a-nameclosefigurea--cdcclosefigure"></a><a name="closefigure"></a>CDC::CloseFigure  
 パス内の開いている図を閉じます。  
  
```  
BOOL CloseFigure();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、図の最初のポイントに現在の位置から行を描画することによって、図を閉じます (通常は、最新の呼び出しで指定された点、`MoveTo`メンバー関数) し、直線の接合スタイルを使用して線を接続します。 使用して、図が閉じている場合、`LineTo`メンバー関数の代わりに`CloseFigure`端点キャップがされる結合ではなく角を作成するようにします。 `CloseFigure`デバイス コンテキストで開かれたパス ブラケットがある場合にのみ呼び出す必要があります。  
  
 パスの図は、この関数を使用して明示的に閉じられている場合を除き、開かれています。 (図開くことができる場合でも、現在のポイントと、図の開始点は同じです。)直線または曲線の後にパスに追加`CloseFigure`新しい図形を開始します。  
  
##  <a name="a-namecreatecompatibledca--cdccreatecompatibledc"></a><a name="createcompatibledc"></a>CDC::CreateCompatibleDC  
 指定されたデバイスと互換性があるメモリ デバイス コンテキストを作成`pDC`します。  
  
```  
BOOL CreateCompatibleDC(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。 場合`pDC`は**NULL**関数は、システムの表示と互換性があるメモリ デバイス コンテキストを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メモリ デバイス コンテキストは、表示画面を表すメモリ ブロックです。 互換性のあるデバイスの実際のデバイスの画面にコピーするイメージをメモリ内に準備するために使用します。  
  
 メモリ デバイス コンテキストが作成されると、GDI は 1 対 1 でモノクロのストック ビットマップを自動的にそれを選択します。 GDI 関数は、ビットマップが作成され、そのコンテキストに選択されている場合にのみ、メモリ デバイス コンテキストで使用できます。  
  
 この関数は、ラスター オペレーションをサポートするデバイスの互換性のあるデバイス コンテキストの作成にのみ使用できます。 参照してください、[ビットマップ](#bitblt)デバイス コンテキスト間でビット ブロック転送に関する情報のメンバー関数。 デバイス コンテキストがラスター オペレーションをサポートしているかどうかを確認するのを参照してください。、 **RC_BITBLT**メンバー関数の機能はラスター`CDC::GetDeviceCaps`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#32;](../../mfc/codesnippet/cpp/cdc-class_4.cpp)]  
  
##  <a name="a-namecreatedca--cdccreatedc"></a><a name="createdc"></a>CDC::CreateDC  
 指定したデバイスのデバイス コンテキストを作成します。  
  
```  
BOOL CreateDC(
    LPCTSTR lpszDriverName,  
    LPCTSTR lpszDeviceName,  
    LPCTSTR lpszOutput,  
    const void* lpInitData);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDriverName`  
 (拡張子なし)、デバイス ドライバー (たとえば、"EPSON") のファイル名を指定する null で終わる文字列へのポインター。 渡すことも、`CString`このパラメーターにします。  
  
 `lpszDeviceName`  
 サポートされるように (たとえば、「EPSON FX&80;」) の特定のデバイスの名前を指定する null で終わる文字列へのポインター。 `lpszDeviceName`パラメーターは、モジュールは、複数のデバイスをサポートしている場合に使用します。 渡すことも、`CString`このパラメーターにします。  
  
 `lpszOutput`  
 物理出力メディア (ファイルまたは出力ポート) のファイルまたはデバイス名を指定する null で終わる文字列へのポインター。 渡すことも、`CString`このパラメーターにします。  
  
 `lpInitData`  
 指す、`DEVMODE`デバイス ドライバーのデバイスに固有の初期化データを含む構造体。 Windows **DocumentProperties**関数は、特定のデバイスに入力します。 この構造体を取得します。 `lpInitData`パラメーターである必要があります**NULL**かどうか、デバイス ドライバーは、コントロール パネルからユーザーが指定した既定の初期化 (存在する場合) を使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 印刷します。H ヘッダー ファイルが必要、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)構造体を使用します。  
  
 デバイス名がこれらの規則に従います。 コロン (:) は省略可能です。 Windows は、コロンで終わるデバイス名がコロンのない同じ名前と同じポートにマップされるように、終わりのコロンを削除します。 ドライバおよびポートの名前では、先頭または末尾にスペースを含めることはできません。 GDI 関数は、情報のコンテキストでは使用できません。  
  
##  <a name="a-namecreateica--cdccreateic"></a><a name="createic"></a>CDC::CreateIC  
 指定したデバイスの情報コンテキストを作成します。  
  
```  
BOOL CreateIC(
    LPCTSTR lpszDriverName,  
    LPCTSTR lpszDeviceName,  
    LPCTSTR lpszOutput,  
    const void* lpInitData);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDriverName`  
 (拡張子なし)、デバイス ドライバー (たとえば、"EPSON") のファイル名を指定する null で終わる文字列へのポインター。 渡すことができます、`CString`このパラメーターにします。  
  
 `lpszDeviceName`  
 サポートされるように (たとえば、「EPSON FX&80;」) の特定のデバイスの名前を指定する null で終わる文字列へのポインター。 `lpszDeviceName`パラメーターは、モジュールは、複数のデバイスをサポートしている場合に使用します。 渡すことができます、`CString`このパラメーターにします。  
  
 `lpszOutput`  
 (ファイルまたはポート) の物理出力メディアのファイルまたはデバイス名を指定する null で終わる文字列へのポインター。 渡すことができます、`CString`このパラメーターにします。  
  
 `lpInitData`  
 デバイス ドライバーのデバイスに固有の初期化データへのポインター。 `lpInitData`パラメーターである必要があります**NULL**かどうか、デバイス ドライバーは、コントロール パネルからユーザーが指定した既定の初期化 (存在する場合) を使用します。 参照してください`CreateDC`デバイス固有の初期化のデータ形式にします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 情報のコンテキストでは、高速デバイス コンテキストを作成することがなく、デバイスに関する情報を取得する方法を提供します。  
  
 デバイス名がこれらの規則に従います。 コロン (:) は省略可能です。 Windows は、コロンで終わるデバイス名がコロンのない同じ名前と同じポートにマップされるように、終わりのコロンを削除します。 ドライバおよびポートの名前では、先頭または末尾にスペースを含めることはできません。 GDI 関数は、情報のコンテキストでは使用できません。  
  
##  <a name="a-namedeletedca--cdcdeletedc"></a><a name="deletedc"></a>デバイス コンテキストの破棄  
 一般に、この関数を呼び出す必要はありません。デストラクターがそれを実行します。  
  
```  
BOOL DeleteDC();
```  
  
### <a name="return-value"></a>戻り値  
 関数が正常に完了した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `DeleteDC`メンバー関数に関連付けられている Windows デバイス コンテキストを削除する`m_hDC`現在`CDC`オブジェクトです。 この場合`CDC`オブジェクトは、特定のデバイスの最後のデバイス コンテキスト、デバイスに通知し、デバイスによって使用される、すべての記憶域やシステム リソースを解放します。  
  
 アプリケーションが呼び出さないで`DeleteDC`デバイス コンテキストにオブジェクトが選択されている場合。 削除されるまで、デバイス コンテキストからオブジェクトを選択最初必要があります。  
  
 アプリケーションは、ハンドルを呼び出すことによって取得したデバイス コンテキストを削除する必要があります[:getdc](../../mfc/reference/cwnd-class.md#getdc)します。 代わりを呼び出し、 [CWnd::ReleaseDC](../../mfc/reference/cwnd-class.md#releasedc)をデバイス コンテキストを解放します。 [CClientDC](../../mfc/reference/cclientdc-class.md)と[CWindowDC](../../mfc/reference/cwindowdc-class.md)この機能をラップするクラスが用意されています。  
  
 `DeleteDC`関数は、通常で作成したデバイス コンテキストを削除する使用[フォーマット](#createdc)、 [CreateIC](#createic)、または[CreateCompatibleDC](#createcompatibledc)します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::GetPrinterDC](../../mfc/reference/cprintdialog-class.md#getprinterdc)します。  
  
##  <a name="a-namedeletetempmapa--cdcdeletetempmap"></a><a name="deletetempmap"></a>CDC::DeleteTempMap  
 により自動的に呼び出さ、`CWinApp`アイドル ハンドラー`DeleteTempMap`一時的な削除`CDC`によって作成されたオブジェクト`FromHandle`、デバイス コンテキスト ハンドルを破棄しません (`hDC`秒) に一時的に関連付けられている、`CDC`オブジェクトです。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
##  <a name="a-namedetacha--cdcdetach"></a><a name="detach"></a>CDC::Detach  
 デタッチするには、この関数を呼び出す`m_hDC`(出力デバイス コンテキスト) から、`CDC`オブジェクトし、両方を設定`m_hDC`と`m_hAttribDC`に**NULL**します。  
  
```  
HDC Detach();
```  
  
### <a name="return-value"></a>戻り値  
 Windows のデバイス コンテキスト。  
  
##  <a name="a-namedptohimetrica--cdcdptohimetric"></a><a name="dptohimetric"></a>CDC::DPtoHIMETRIC  
 付与する場合、この関数を使用して**HIMETRIC** ole に変換するためのピクセル サイズ**HIMETRIC**します。  
  
```  
void DPtoHIMETRIC(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキスト オブジェクトのマッピング モードがあるかどうか`MM_LOENGLISH`、 `MM_HIENGLISH`、 `MM_LOMETRIC`、または`MM_HIMETRIC`変換がインチの物理ピクセルの数に基づきます。 マップ モードが非強制モードのいずれかのかどうか (など`MM_TEXT`)、変換が論理インチのピクセル数に基づきます。  
  
##  <a name="a-namedptolpa--cdcdptolp"></a><a name="dptolp"></a>CDC::DPtoLP  
 デバイス単位を論理単位に変換します。  
  
```  
void DPtoLP(
    LPPOINT lpPoints,  
    int nCount = 1) const;  
  
void DPtoLP(LPRECT lpRect) const;
void DPtoLP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
 `nCount`  
 配列内の点の数。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトです。 このパラメーターは、簡単な例で論理ポイントをデバイス ポイント&1; つの四角形に変換するのに使用されます。  
  
 `lpSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数は、各ポイントの座標やサイズ、GDI の論理座標系にデバイスの座標系からのディメンションにマップします。 変換は、現在のマップ モードと、元のドメインと、デバイスのウィンドウおよびビューポートのエクステントの設定に依存します。  
  
##  <a name="a-namedraw3drecta--cdcdraw3drect"></a><a name="draw3drect"></a>CDC::Draw3dRect  
 3 次元の四角形を描画するには、このメンバー関数を呼び出します。  
  
```  
void Draw3dRect(
    LPCRECT lpRect,  
    COLORREF clrTopLeft,  
    COLORREF clrBottomRight);

 
void Draw3dRect(
    int x,  
    int y,  
    int cx,  
    int cy,  
    COLORREF clrTopLeft,  
    COLORREF clrBottomRight);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 (論理単位で) に外接する四角形を指定します。 ポインターを渡すことができます、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 *clrTopLeft*  
 3 次元の四角形の上部と左側の辺の色を指定します。  
  
 `clrBottomRight`  
 3 次元の四角形の左右の下部にある色を指定します。  
  
 *x*  
 論理で&3; 次元の四角形の左上隅の x 座標を指定します。  
  
 *y*  
 論理で&3; 次元の四角形の左上隅の y 座標を指定します。  
  
 cx  
 3 次元の四角形の幅を指定します。  
  
 cy  
 3 次元の四角形の高さを指定します。  
  
### <a name="remarks"></a>コメント  
 によって指定された色の上と左方向に四角形を描画する*clrTopLeft*し、下部にあると右辺で指定した色で`clrBottomRight`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&33;](../../mfc/codesnippet/cpp/cdc-class_5.cpp)]  
  
##  <a name="a-namedrawdragrecta--cdcdrawdragrect"></a><a name="drawdragrect"></a>CDC::DrawDragRect  
 ドラッグ四角形を再描画するには、繰り返しには、このメンバー関数を呼び出します。  
  
```  
void DrawDragRect(
    LPCRECT lpRect,  
    SIZE size,  
    LPCRECT lpRectLast,  
    SIZE sizeLast,  
    CBrush* pBrush = NULL,  
    CBrush* pBrushLast = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)四角形の論理座標を指定するオブジェクト: この場合、再描画される四角形の末尾の位置。  
  
 `size`  
 外側の境界線の四角形の内側の境界線 (つまり、境界線の太さなど) の左上隅に左上隅から距離を指定します。  
  
 `lpRectLast`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)四角形の位置の論理座標を指定するオブジェクト: この場合、再描画される四角形の元の位置。  
  
 *sizeLast*  
 外側の境界線の再描画される元の四角形の内側の境界線 (つまり、境界線の太さなど) の左上隅までの左上隅から距離を指定します。  
  
 `pBrush`  
 Brush オブジェクトへのポインター。 設定**NULL**既定ハーフトーン ブラシを使用します。  
  
 *pBrushLast*  
 最後に使用されるブラシ オブジェクトへのポインター。 設定**NULL**既定ハーフトーン ブラシを使用します。  
  
### <a name="remarks"></a>コメント  
 マウスの位置を視覚的なフィードバックを提供するためにサンプリングしているため、ループ内で呼び出します。 呼び出すと`DrawDragRect`、前の四角形が消去され、新しいものを描画します。 たとえば、ユーザーと、画面上で四角形をドラッグ`DrawDragRect`元の四角形を消去して、新しい位置に新しいものを再描画されます。 既定では、`DrawDragRect`ちらつきを滑らかに移動する四角形の外観を作成するハーフトーン ブラシを使用して、四角形を描画します。  
  
 最初に呼び出したとき`DrawDragRect`、`lpRectLast`パラメーターは必ず**NULL**します。  
  
##  <a name="a-namedrawedgea--cdcdrawedge"></a><a name="drawedge"></a>CDC::DrawEdge  
 このメンバー関数を呼び出して、指定した型とスタイルの四角形のエッジを描画します。  
  
```  
BOOL DrawEdge(
    LPRECT lpRect,  
    UINT nEdge,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 ポインター、 **RECT**四角形の論理座標を格納する構造体。  
  
 *nEdge*  
 描画する内側と外側のエッジの種類を指定します。 このパラメーターは、1 つの罫線の内側フラグと外側の境界線の&1; つのフラグの組み合わせを指定する必要があります。 参照してください[DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]パラメーターの型のテーブルにします。  
  
 `nFlags`  
 描画される境界線の種類を指定するフラグ。 参照してください`DrawEdge`で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]パラメーターの値のテーブルにします。 対角線、 **BF_RECT**フラグは四角形のパラメーターで区切られたベクトルの終了位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namedrawescapea--cdcdrawescape"></a><a name="drawescape"></a>CDC::DrawEscape  
 描画グラフィックス デバイス インターフェイス (GDI) を通じて直接提供されていないビデオ ディスプレイの機能にアクセスします。  
  
```  
int DrawEscape(
    int nEscape,  
    int nInputSize,  
    LPCSTR lpszInputData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nEscape`  
 実行するエスケープ関数を指定します。  
  
 `nInputSize`  
 参照するデータのバイト数を指定、`lpszInputData`パラメーター。  
  
 `lpszInputData`  
 指定したエスケープに必要な入力構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数の結果を指定します。 成功すると、以外の場合は&0; より大きい、**関数**描画エスケープ、のみで、実装の場合は&0; には、どのチェックが、エスケープが実装されていません。 または、ゼロより小さい場合はエラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出すと`DrawEscape`、により識別されるデータ`nInputSize`と`lpszInputData`指定ディスプレイ ドライバーに直接渡されます。  
  
##  <a name="a-namedrawfocusrecta--cdcdrawfocusrect"></a><a name="drawfocusrect"></a>CDC::DrawFocusRect  
 四角形にフォーカスがあることを示すために使用するスタイルでは、四角形を描画します。  
  
```  
void DrawFocusRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)に描画する四角形の論理座標を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 これはブール型 XOR 関数であるために、もう一度同じ四角形にこの関数を呼び出すと、四角形が表示から削除します。 この関数で描画する四角形をスクロールすることはできません。 この関数で描画する四角形を含む領域をスクロールするには、まず`DrawFocusRect`画面から四角形を削除する、領域をスクロールし、し、呼び出す`DrawFocusRect`新しい位置に、四角形を描画するには、もう一度です。  
  
> [!CAUTION]
> `DrawFocusRect`のみ動作`MM_TEXT`モードです。 他のモードでは、この関数がフォーカスされた四角形を正しく描画しないが、エラー値を返すことはできません。  
  
##  <a name="a-namedrawframecontrola--cdcdrawframecontrol"></a><a name="drawframecontrol"></a>CDC::DrawFrameControl  
 指定された種類とスタイルのフレームのコントロールを描画するには、このメンバー関数を呼び出します。  
  
```  
BOOL DrawFrameControl(
    LPRECT lpRect,  
    UINT nType,  
    UINT nState);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 ポインター、 **RECT**四角形の論理座標を格納する構造体。  
  
 `nType`  
 描画するフレーム コントロールの種類を指定します。 参照してください、 *uType*パラメーター [DrawFrameControl](http://msdn.microsoft.com/library/windows/desktop/dd162480)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]このパラメーターの有効な値の一覧についてです。  
  
 `nState`  
 Frame コントロールの初期状態を指定します。 説明の値の&1; つ以上指定できます、 *uState*パラメーター`DrawFrameControl`で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 使用して、`nState`値**DFCS_ADJUSTRECT**プッシュ ボタンの周囲の端を除外する外接する四角形を調整します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 いくつかの場合、`nState`異なります、`nType`パラメーター。 次の一覧は、4 つの間のリレーションシップを示しています`nType`値と`nState`:。  
  
- **DFC_BUTTON**  
  
    - **DFCS_BUTTON3STATE**&3; つの状態 ボタンをクリックします。  
  
    - **DFCS_BUTTONCHECK**  チェック ボックス  
  
    - **DFCS_BUTTONPUSH**プッシュ ボタン  
  
    - **DFCS_BUTTONRADIO**オプション ボタン  
  
    - **DFCS_BUTTONRADIOIMAGE**ラジオ ボタンのイメージを (非正方形には、イメージが必要があります)  
  
    - **DFCS_BUTTONRADIOMASK**ラジオ ボタンのマスク (非正方形には、マスクが必要があります)  
  
- **DFC_CAPTION**  
  
    - **DFCS_CAPTIONCLOSE** [閉じる] ボタン  
  
    - **DFCS_CAPTIONHELP** [ヘルプ] ボタン  
  
    - **DFCS_CAPTIONMAX**最大化ボタン  
  
    - **DFCS_CAPTIONMIN**最小化 ボタン  
  
    - **DFCS_CAPTIONRESTORE**復元 ボタン  
  
- **DFC_MENU**  
  
    - **DFCS_MENUARROW**サブメニューの矢印  
  
    - **DFCS_MENUBULLET**行頭文字  
  
    - **DFCS_MENUCHECK**チェック マーク  
  
- **DFC_SCROLL**  
  
    - **DFCS_SCROLLCOMBOBOX**コンボ ボックスのスクロール バー  
  
    - **DFCS_SCROLLDOWN**スクロール バーの下矢印  
  
    - **DFCS_SCROLLLEFT**スクロール バーの左の矢印  
  
    - **DFCS_SCROLLRIGHT**スクロール バーの右矢印  
  
    - **DFCS_SCROLLSIZEGRIP**ウィンドウの右下隅にあるサイズ変更グリップ  
  
    - **DFCS_SCROLLUP**スクロール バーの上向きの矢印  
  
### <a name="example"></a>例  
 このコードは、ウィンドウの右下隅にあるサイズ変更グリップを描画します。 適しているか、`OnPaint`スタイルを持たず、通常、サイズ変更グリップを付けますが (ステータス バー) のようなその他のコントロールが含まれていない ダイアログ ボックスのハンドラーです。  
  
 [!code-cpp[NVC_MFCDocView #&34;](../../mfc/codesnippet/cpp/cdc-class_6.cpp)]  
  
##  <a name="a-namedrawicona--cdcdrawicon"></a><a name="drawicon"></a>CDC::DrawIcon  
 現在のデバイスにアイコンを描画`CDC`オブジェクトです。  
  
```  
BOOL DrawIcon(
    int x,  
    int y,  
    HICON hIcon);

 
BOOL DrawIcon(
    POINT point,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理でアイコンの左上隅の x 座標を指定します。  
  
 *y*  
 論理でアイコンの左上隅の y 座標を指定します。  
  
 `hIcon`  
 描画されるアイコンのハンドルを識別します。  
  
 `point`  
 アイコンの左上隅の論理 x 座標と y 座標を指定します。 渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 関数が正常に完了した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数で指定された位置にあるアイコンの左上隅に配置*x*と*y*します。 場所は、デバイス コンテキストの現在のマップ モードが適用されます。  
  
 アイコン リソース必要がありますが既に読み込まれている関数を使用して`CWinApp::LoadIcon`、 `CWinApp::LoadStandardIcon`、または`CWinApp::LoadOEMIcon`です。 `MM_TEXT`マッピング モードは、この関数を使用する前に選択する必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::IsIconic](../../mfc/reference/cwnd-class.md#isiconic)します。  
  
##  <a name="a-namedrawstatea--cdcdrawstate"></a><a name="drawstate"></a>CDC::DrawState  
 このメンバー関数を呼び出してイメージを表示し、無効になっているなどの状態または既定の状態を示す視覚効果を適用します。  
  
> [!NOTE]
>  すべての`nFlag`を除くという**DSS_NORMAL**、視覚効果が適用される前に、画像はモノクロに変換します。  
  
```  
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HBITMAP hBitmap,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    CBitmap* pBitmap,  
    UINT nFlags,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HICON hIcon,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HICON hIcon,  
    UINT nFlags,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    LPCTSTR lpszText,  
    UINT nFlags,  
    BOOL bPrefixText = TRUE,  
    int nTextLen = 0,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    LPCTSTR lpszText,  
    UINT nFlags,  
    BOOL bPrefixText = TRUE,  
    int nTextLen = 0,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    DRAWSTATEPROC lpDrawProc,  
    LPARAM lData,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    DRAWSTATEPROC lpDrawProc,  
    LPARAM lData,  
    UINT nFlags,  
    CBrush* pBrush = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 イメージの場所を指定します。  
  
 `size`  
 イメージのサイズを指定します。  
  
 `hBitmap`  
 ビットマップへのハンドル。  
  
 `nFlags`  
 イメージの種類と状態を指定するフラグ。 参照してください[DrawState](http://msdn.microsoft.com/library/windows/desktop/dd162496)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 、可能性がある`nFlags`の種類および状態です。  
  
 `hBrush`  
 ブラシへのハンドル。  
  
 `pBitmap`  
 CBitmap オブジェクトへのポインター。  
  
 `pBrush`  
 CBrush オブジェクトへのポインター。  
  
 `hIcon`  
 アイコンのハンドル。  
  
 `lpszText`  
 テキストへのポインター。  
  
 *bPrefixText*  
 アクセラレータ ニーモニックを含む可能性のあるテキスト。 `lData`パラメーター文字列のアドレスを指定し、`nTextLen`パラメーターが長さを指定します。 場合`nTextLen`が 0 の場合、文字列は null で終わると見なされます。  
  
 `nTextLen`  
 テキスト文字列の長さが指す`lpszText`します。 場合`nTextLen`が 0 の場合、文字列は null で終わると見なされます。  
  
 *lpDrawProc*  
 イメージをレンダリングするために使用するコールバック関数へのポインター。 イメージを入力する場合は、このパラメーターは必須`nFlags`は**DST_COMPLEX**します。 これは省略可能であり**NULL**場合は、画像の種類が**DST_TEXT**します。 他のすべての種類のイメージでは、このパラメーターは無視されます。 コールバック関数の詳細については、次を参照してください。、 [DrawStateProc](http://msdn.microsoft.com/library/windows/desktop/dd162497)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lData`  
 イメージに関する情報を指定します。 このパラメーターの意味は、イメージの種類によって異なります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namedrawtexta--cdcdrawtext"></a><a name="drawtext"></a>CDC::DrawText  
 指定した四角形内のテキストの書式を設定するには、このメンバー関数を呼び出します。 その他の書式設定オプションを指定するには使用[には](#drawtextex)です。  
  
```  
virtual int DrawText(
    LPCTSTR lpszString,  
    int nCount,  
    LPRECT lpRect,  
    UINT nFormat);

 
int DrawText(
    const CString& str,  
    LPRECT lpRect,  
    UINT nFormat);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 描画する文字列へのポインター。 場合`nCount`-1 で、null で終わる文字列でなければなりません。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`が –&1;, `lpszString` null で終わる文字列への long ポインターであると想定と`DrawText`文字数を自動的に計算します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md) (論理座標) で、テキストの書式設定する先の四角形を格納するオブジェクト。  
  
 `str`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)を描画する指定された文字を含むオブジェクト。  
  
 `nFormat`  
 テキストを書式設定方法を指定します。 指定された値の任意の組み合わせであることができます、`uFormat`パラメーター [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 (組み合わせのビットごとの OR 演算子を使用)。  
  
> [!NOTE]
>  いくつか`uFormat`フラグの組み合わせには、渡された文字列を変更する可能性があります。 使用して**DT_MODIFYSTRING**いずれかで**DT_END_ELLIPSIS**または**DT_PATH_ELLIPSIS**場合があります、変更する文字列ではアサーションを原因と、`CString`をオーバーライドします。 値`DT_CALCRECT`、 `DT_EXTERNALLEADING`、 **DT_INTERNAL**、 `DT_NOCLIP`、および`DT_NOPREFIX`では使用できません、`DT_TABSTOP`値。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、テキストの高さ。  
  
### <a name="remarks"></a>コメント  
 左、右にテキストの配置に適切なスペース、または指定された四角形の中心にタブを展開してから、指定した四角形内に一致する行をテキストに分割するテキストを設定できます。 書式の種類がで指定された`nFormat`します。  
  
 このメンバー関数では、デバイス コンテキストの選択したフォント、テキストの色と背景色を使用して、テキストを描画します。 しない限り、`DT_NOCLIP`形式を使用すると、`DrawText`テキストが指定された四角形の外側に表示されないように、テキストをクリップします。 しない限り、複数の行があると見なされますすべての書式設定、`DT_SINGLELINE`形式を指定します。  
  
 指定された四角形には、選択したフォントが大きすぎる場合、`DrawText`メンバー関数は小さいフォントを置き換えるしようとはしません。  
  
 場合、`DT_CALCRECT`フラグを指定するで指定された四角形`lpRect`幅と高さはテキストを描画するために必要なを反映するように更新されます。  
  
 場合、 **TA_UPDATECP**テキスト配置フラグが設定されている (を参照してください[CDC::SetTextAlign](#settextalign))、`DrawText`指定した四角形の左にあるではなく、現在の位置で始まるテキストが表示されます。 `DrawText`テキストは折り返されませんときに、 **TA_UPDATECP**フラグが設定されている (つまり、`DT_WORDBREAK`フラグには効果はありません)。  
  
 によって設定されるテキストの色[CDC::SetTextColor](#settextcolor)します。  
  
##  <a name="a-namedrawtextexa--cdcdrawtextex"></a><a name="drawtextex"></a>には  
 指定した四角形内のテキストの書式を設定します。  
  
```  
virtual int DrawTextEx(
    LPTSTR lpszString,  
    int nCount,  
    LPRECT lpRect,  
    UINT nFormat,
    LPDRAWTEXTPARAMS lpDTParams);

 
int DrawTextEx(
    const CString& str,  
    LPRECT lpRect,  
    UINT nFormat,
    LPDRAWTEXTPARAMS lpDTParams);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 描画する文字列へのポインター。 場合`nCount`-1 で、文字列は null 終端である必要があります。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`が –&1;, `lpszString` null で終わる文字列への long ポインターであると想定と`DrawText`文字数を自動的に計算します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md) (論理座標) で、テキストの書式設定する先の四角形を格納するオブジェクト。  
  
 `str`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)を描画する指定された文字を含むオブジェクト。  
  
 `nFormat`  
 テキストを書式設定方法を指定します。 指定された値の任意の組み合わせであることができます、`uFormat`パラメーター [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 (ビット演算の結合`OR`演算子)。  
  
> [!NOTE]
>  いくつか`uFormat`フラグの組み合わせには、渡された文字列を変更する可能性があります。 使用して**DT_MODIFYSTRING**いずれかで**DT_END_ELLIPSIS**または**DT_PATH_ELLIPSIS**場合があります、変更する文字列ではアサーションを原因と、`CString`をオーバーライドします。 値`DT_CALCRECT`、 `DT_EXTERNALLEADING`、 **DT_INTERNAL**、 `DT_NOCLIP`、および`DT_NOPREFIX`では使用できません、`DT_TABSTOP`値。  
  
 `lpDTParams`  
 ポインター、 [DRAWTEXTPARAMS](http://msdn.microsoft.com/library/windows/desktop/dd162500)オプションの追加の書式設定を指定します。 このパラメーターを指定できます**NULL**します。  
  
### <a name="remarks"></a>コメント  
 左、右にテキストの配置に適切なスペース、または指定された四角形の中心にタブを展開してから、指定した四角形内に一致する行をテキストに分割するテキストを設定できます。 書式の種類がで指定された`nFormat`と`lpDTParams`です。 詳細については、次を参照してください。 [CDC::DrawText](#drawtext)と[DrawTextEx](http://msdn.microsoft.com/library/windows/desktop/dd162499)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 によって設定されるテキストの色[CDC::SetTextColor](#settextcolor)します。  
  
##  <a name="a-nameellipsea--cdcellipse"></a><a name="ellipse"></a>CDC::Ellipse  
 楕円を描きます。  
  
```  
BOOL Ellipse(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
BOOL Ellipse(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 論理で楕円の外接する四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 論理で楕円の外接する四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 論理で楕円の外接する四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 論理で楕円の外接する四角形の右下隅の y 座標を指定します。  
  
 `lpRect`  
 楕円の外接する四角形を指定します。 渡すことも、 [CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 楕円の中心で指定された外接する四角形の中心`x1`、 `y1`、 `x2`、および`y2`、または`lpRect`です。 楕円は、現在のペンで描画され、現在のブラシでの内部が塗りつぶされます。  
  
 この関数で描画された図まで拡張は含まれません、右下隅の座標。 つまり、figure の高さは`y2`– `y1` 、figure の幅は`x2`–`x1`します。  
  
 外接する四角形の高さまたは幅のいずれかが 0 の場合、楕円は描画されません。  
  
##  <a name="a-nameenddoca--cdcenddoc"></a><a name="enddoc"></a>CDC::EndDoc  
 呼び出しによって開始された印刷ジョブを終了、 [StartDoc](#startdoc)メンバー関数。  
  
```  
int EndDoc();
```  
  
### <a name="return-value"></a>戻り値  
 以上の場合、関数は成功すると、0 または負の値を使用している場合、エラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数、 **ENDDOC**プリンター エスケープし、成功した印刷ジョブを終了した直後に呼び出す必要があります。  
  
 アプリケーションでは、印刷のエラーや印刷操作の中止が発生すると、ときを使用して、操作を終了する`EndDoc`または[AbortDoc](#abortdoc)します。 GDI は、エラー値を返す前に、操作を自動的に終了します。  
  
 この関数メタファイルの内部を指定しないでください。  
  
### <a name="example"></a>例  
  例を参照してください[CDC::StartDoc](#startdoc)します。  
  
##  <a name="a-nameendpagea--cdcendpage"></a><a name="endpage"></a>CDC::EndPage  
 アプリケーションのページへの書き込みが完了したことをデバイスに通知します。  
  
```  
int EndPage();
```  
  
### <a name="return-value"></a>戻り値  
 以上の場合、関数は成功すると、0 または負の値を使用している場合、エラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は通常、新しいページに進むにデバイス ドライバーを直接に使用されます。  
  
 このメンバー関数、 **NEWFRAME**プリンター エスケープします。 異なり**NEWFRAME**、この関数は、ページを印刷した後は必ず呼び出されます。  
  
### <a name="example"></a>例  
  例を参照してください[CDC::StartDoc](#startdoc)します。  
  
##  <a name="a-nameendpatha--cdcendpath"></a><a name="endpath"></a>CDC::EndPath  
 パスの角かっこを終了し、デバイス コンテキストに、角かっこで定義されているパスを選択します。  
  
```  
BOOL EndPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[cdc::beginpath](#beginpath)します。  
  
##  <a name="a-nameenumobjectsa--cdcenumobjects"></a><a name="enumobjects"></a>Cdc::enumobjects  
 ペンを列挙し、デバイス コンテキストで使用できるブラシします。  
  
```  
int EnumObjects(
    int nObjectType,  
    int (CALLBACK* lpfn)(
    LPVOID,
    LPARAM),  
    LPARAM lpData);
```  
  
### <a name="parameters"></a>パラメーター  
 *nObjectType*  
 オブジェクトの種類を指定します。 値をとります**OBJ_BRUSH**または**OBJ_PEN**します。  
  
 `lpfn`  
 アプリケーションによって提供されるコールバック関数のプロシージャ インスタンスのアドレスです。 以下の「解説」セクションを参照してください。  
  
 `lpData`  
 アプリケーションによって提供されるデータへのポインター。 データは、オブジェクトの情報も含めて、コールバック関数に渡されます。  
  
### <a name="return-value"></a>戻り値  
 によって返される最後の値を示す、[コールバック関数](../../mfc/reference/callback-function-for-cdc-enumobjects.md)します。 その意味では、ユーザー定義されます。  
  
### <a name="remarks"></a>コメント  
 指定された型の各オブジェクトでは、そのオブジェクトの情報を渡すコールバック関数が呼び出されます。 システムは、オブジェクトまたはコールバック関数は 0 を返すまでに、コールバック関数を呼び出します。  
  
 Microsoft Visual C の新機能に渡される関数は、通常の関数を使用することに注意してください`EnumObjects`します。 渡されるアドレス`EnumObjects`と共にエクスポートされる関数へのポインターは、**エクスポート**Pascal 呼び出し規約を使用しています。 保護モードのアプリケーションでは Windows MakeProcInstance 関数でこの関数を作成または FreeProcInstance Windows 関数を使用した後、関数を解放する必要はありません。  
  
 またがありません 関数名をエクスポートする、**エクスポート**アプリケーションのモジュール定義ファイル内のステートメントです。 代わりに使用することができます、**エクスポート**としての関数の修飾子は、  
  
 **コールバックのエクスポート int**関数**(LPSTR**、 **LPSTR) です。**  
  
 エイリアスの名前をエクスポートの適切なエクスポート レコードを生成するコンパイラは、です。 これは、ほとんどのニーズに対して機能します。 特殊ななど、状況によって ordinal またはエイリアスをエクスポートして関数をエクスポートする必要がありますを使用する、**エクスポート**モジュール定義ファイル内のステートメントです。  
  
 Microsoft Foundation プログラムをコンパイルするため、通常は /GA と/GEs コンパイラ オプション。 /Gw コンパイラ オプションは、Microsoft Foundation class では使用されません。 (Windows の機能を使用する場合**MakeProcInstance**から返された関数ポインターを明示的にキャストする必要があります**FARPROC**この API で必要な型にします)。登録のコールバック インターフェイスがタイプ セーフではようになりました (特定のコールバック関数の適切なを指す関数ポインターに渡す必要があります)。  
  
 なお、すべてのコールバック関数がコールバックの境界を越えて例外がスローされることはできませんので、Windows に復帰する前に Microsoft Foundation 例外をトラップする必要があります。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#35;](../../mfc/codesnippet/cpp/cdc-class_7.cpp)]  
  
##  <a name="a-nameescapea--cdcescape"></a><a name="escape"></a>CDC::Escape  
 このメンバー関数は、Win32 プログラミングのために残さです。  
  
```  
virtual int Escape(
    int nEscape,  
    int nCount,  
    LPCSTR lpszInData,  
    LPVOID lpOutData);

 
int Escape(
    int nEscape,  
    int nInputSize,  
    LPCSTR lpszInputData,  
    int nOutputSize,  
    LPSTR lpszOutputData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nEscape`  
 実行するエスケープ関数を指定します。  
  
 エスケープ関数の一覧については、次を参照してください。[エスケープ](http://msdn.microsoft.com/library/windows/desktop/dd162701)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `nCount`  
 参照するデータのバイト数を指定`lpszInData`します。  
  
 `lpszInData`  
 このエスケープに必要な入力データの構造体へのポインター。  
  
 `lpOutData`  
 このエスケープから出力を受け取る構造体へのポインター。 `lpOutData`パラメーターは**NULL**データが返されない場合。  
  
 `nInputSize`  
 参照するデータのバイト数を指定、`lpszInputData`パラメーター。  
  
 `lpszInputData`  
 指定したエスケープに必要な入力構造体へのポインター。  
  
 `nOutputSize`  
 参照するデータのバイト数を指定、`lpszOutputData`パラメーター。  
  
 `lpszOutputData`  
 このエスケープから出力を受け取る構造体へのポインター。 このパラメーターを指定する必要があります**NULL**データが返されない場合。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、以外の場合、正の値が返される、**関数**実装のエスケープします。 エスケープが実装されていない場合は、0 が返されます。 エラーが発生した場合は、負の値が返されます。 一般的なエラー値を次に示します。  
  
- **SP_ERROR**一般的なエラーです。  
  
- **させることでより**のに十分なディスク領域が、スプールのため現在使用できると、空き領域がないが表示されます。  
  
- **SP_OUTOFMEMORY**スプールのためのに十分なメモリがあります。  
  
- **SP_USERABORT**ユーザーが印刷マネージャーを使ってジョブを終了します。  
  
### <a name="remarks"></a>コメント  
 元プリンター エスケープ、のみの**関数**Win32 アプリケーションでサポートされています。 その他のすべてのプリンター エスケープは廃止されており、16 ビット アプリケーションとの互換性についてのみサポートされています。  
  
 Win32 プログラミングで`CDC`これで、対応するプリンター エスケープよりも優先される&6; つのメンバー関数を提供します。  
  
- [CDC::AbortDoc](#abortdoc)  
  
- [CDC::EndDoc](#enddoc)  
  
- [CDC::EndPage](#endpage)  
  
- [Cdc::setabortproc](#setabortproc)  
  
- [CDC::StartDoc](#startdoc)  
  
- [CDC::StartPage](#startpage)  
  
 さらに、[は](#getdevicecaps)は他のプリンター エスケープよりも優先される Win32 インデックスをサポートします。 参照してください[調べるため](http://msdn.microsoft.com/library/windows/desktop/dd144877)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
 このメンバー関数は、アプリケーションは GDI を介して直接利用できない特定のデバイスの機能にアクセスできます。  
  
 アプリケーションは、定義済みのエスケープ値を使用する場合は、最初のバージョンを使用します。 アプリケーションには独自のエスケープ値が定義されている場合は、2 番目のバージョンを使用します。 参照してください[ExtEscape](http://msdn.microsoft.com/library/windows/desktop/dd162708)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]&2; 番目のバージョンの詳細についてです。  
  
##  <a name="a-nameexcludecliprecta--cdcexcludecliprect"></a><a name="excludecliprect"></a>CDC::ExcludeClipRect  
 指定された四角形から既存のクリッピング領域で構成される新しいクリップ領域を作成します。  
  
```  
int ExcludeClipRect(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
int ExcludeClipRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 論理で四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 論理で四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 論理で四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 論理で四角形の右下隅の y 座標を指定します。  
  
 `lpRect`  
 四角形を指定します。 こともできます、`CRect`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 新しいクリップ領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**領域には、重なり合う境界線。  
  
- **エラー**領域は作成されませんでした。  
  
- **NULLREGION**領域が空です。  
  
- **SIMPLEREGION**領域には、重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 絶対値で指定された四角形の幅`x2`– `x1`、32,767 単位を超えることはできません。 同様に、四角形の高さにこの制限が適用されます。  
  
##  <a name="a-nameexcludeupdatergna--cdcexcludeupdatergn"></a><a name="excludeupdatergn"></a>CDC::ExcludeUpdateRgn  
 関連付けられているクリッピング領域から更新されたウィンドウ領域を除外することで無効なウィンドウ領域内での描画を防止、`CDC`オブジェクトです。  
  
```  
int ExcludeUpdateRgn(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 更新されるウィンドウを持つウィンドウ オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 除外されている領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**領域には、重なり合う境界線。  
  
- **エラー**領域は作成されませんでした。  
  
- **NULLREGION**領域が空です。  
  
- **SIMPLEREGION**領域には、重複する境界がありません。  
  
##  <a name="a-nameextfloodfilla--cdcextfloodfill"></a><a name="extfloodfill"></a>CDC::ExtFloodFill  
 現在のブラシで表示画面の領域を塗りつぶします。  
  
```  
BOOL ExtFloodFill(
    int x,  
    int y,  
    COLORREF crColor,  
    UINT nFillType);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 塗りつぶしを開始点の論理の x 座標を指定します。  
  
 *y*  
 塗りつぶしを開始点の論理の y 座標を指定します。  
  
 `crColor`  
 塗りつぶす領域や、境界の色を指定します。 解釈`crColor`の値に依存`nFillType`します。  
  
 `nFillType`  
 実行する塗りつぶしの種類を指定します。 次の値のいずれかを指定する必要があります。  
  
- **FLOODFILLBORDER**塗りつぶし領域に制限されますが、指定された色`crColor`します。 このスタイルは、読み込みが実行を同一`FloodFill`します。  
  
- **返して**で指定された色で塗り領域が定義されている`crColor`します。 色が発生した場合に限り、塗りつぶしはすべての方向に外側続行します。 このスタイルは、マルチカラーの境界で領域を塗りつぶすに便利です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。場合は、読み込みを完了できませんでした、指定したポイントに境界がある場合、それ以外の場合 0 によって指定された色`crColor`(場合**FLOODFILLBORDER**が要求されました) で指定した色が指定したポイントにない場合、 `crColor` (場合**返して**が要求されました)、ポイントがクリッピング領域の外側にある場合、またはです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数より高い柔軟性を提供しています`FloodFill`で塗りつぶしの種類を指定できるため`nFillType`です。  
  
 場合`nFillType`に設定されている**FLOODFILLBORDER**、領域はによって指定された色によって完全に関連付けられる`crColor`です。 指定された時点で、関数の開始*x*と*y*し、色の境界をすべての方向を設定します。  
  
 場合`nFillType`に設定されている**返して**、関数によって指定された位置から始まります*x*と*y*入力で指定された色を含むすべての隣接する領域のすべての方向に引き続きと`crColor`です。  
  
 メモリ デバイス コンテキストとラスター表示テクノロジのサポートをサポートするデバイスだけ`ExtFloodFill`します。 詳細については、次を参照してください。、[調べるため](#getdevicecaps)メンバー関数。  
  
##  <a name="a-nameexttextouta--cdcexttextout"></a><a name="exttextout"></a>CDC::ExtTextOut  
 現在選択されているフォントを使用して四角形領域内の文字の文字列に書き込むには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ExtTextOut(
    int x,  
    int y,  
    UINT nOptions,  
    LPCRECT lpRect,  
    LPCTSTR lpszString,  
    UINT nCount,  
    LPINT lpDxWidths);

 
BOOL ExtTextOut(
    int x,  
    int y,  
    UINT nOptions,  
    LPCRECT lpRect,  
    const CString& str,  
    LPINT lpDxWidths);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 指定した文字列内の最初の文字の文字セルの論理の x 座標を指定します。  
  
 *y*  
 指定した文字列内の最初の文字の文字セルの最上位の論理 y 座標を指定します。  
  
 `nOptions`  
 四角形の種類を指定します。 このパラメーターには、いずれか、両方、またはどちらも、次の値を指定できます。  
  
- **ETO_CLIPPED**四角形にテキストが切り詰められますことを指定します。  
  
- **ETO_OPAQUE**四角形を現在の背景色で塗りつぶすことを指定します。 (設定し、クエリでは、現在の背景色、 [SetBkColor](#setbkcolor)と[GetBkColor](#getbkcolor)メンバー関数)。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)四角形の寸法を決定する構造体。 このパラメーターを指定できます**NULL**します。 渡すことも、 [CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 `lpszString`  
 描画する指定した文字の文字列へのポインター。 渡すことも、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。  
  
 `lpDxWidths`  
 隣接する文字セルの元のドメイン間の距離を示す値の配列を指します。 たとえば、 `lpDxWidths`[*は*] 論理ユニットには文字セルの元のドメインを区切る*は*と文字セル*は*+ 1 です。 場合`lpDxWidths`は**NULL**、`ExtTextOut`文字の既定の間隔を使用します。  
  
 `str`  
 A`CString`を描画する指定された文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 四角形領域できる非透過 (現在の背景色で塗りつぶされます)、ありクリッピング領域を指定できます。  
  
 場合`nOptions`は 0 と`lpRect`は**NULL**関数は、四角形の領域を使用することがなくデバイス コンテキストにテキストを書き込みます。 既定では、関数は現在位置を使用することも、更新することもありません。 アプリケーションを呼び出すときに、現在の位置を更新する必要があるかどうか`ExtTextOut`、アプリケーションが呼び出すことができます、`CDC`メンバー関数[呼び出された](#settextalign)と`nFlags`に設定**TA_UPDATECP**します。 このフラグを設定すると、Windows は無視されます*x*と*y*を以降の呼び出しに`ExtTextOut`代わりに、現在の位置を使用しています。 アプリケーションを使用する場合**TA_UPDATECP**現在位置を更新する`ExtTextOut`が指す配列の最後の要素で指定した位置またはテキストの前の行の末尾にいずれかに現在の位置を設定する`lpDxWidths`、大きい方します。  
  
##  <a name="a-namefillpatha--cdcfillpath"></a><a name="fillpath"></a>CDC::FillPath  
 現在のパス内の開いている図形を閉じ、現在のブラシと多角形の塗りつぶしモードを使用してパスの内部を塗りつぶします。  
  
```  
BOOL FillPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 内部をいっぱいになった後は、デバイス コンテキストからのパスが破棄されます。  
  
##  <a name="a-namefillrecta--cdcfillrect"></a><a name="fillrect"></a>CDC::FillRect  
 指定されたブラシを使用して、指定した四角形を入力するには、このメンバー関数を呼び出します。  
  
```  
void FillRect(
    LPCRECT lpRect,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)塗りつぶす四角形の論理座標を格納する構造体。 渡すことも、 [CRect](../../atl-mfc-shared/reference/crect-class.md)このパラメーターにします。  
  
 `pBrush`  
 四角形の塗りつぶしに使用するブラシを識別します。  
  
### <a name="remarks"></a>コメント  
 関数には、左と上の境界線を含む完全な四角形が埋められますが、右、下罫線に満たない。  
  
 必要があるいずれかにする作成された表示ブラシを使用して、 [CBrush](../../mfc/reference/cbrush-class.md)メンバー関数[CreateHatchBrush](../../mfc/reference/cbrush-class.md#createhatchbrush)、[とき](../../mfc/reference/cbrush-class.md#createpatternbrush)、および[CreateSolidBrush](../../mfc/reference/cbrush-class.md#createsolidbrush)、またはによって取得、 `GetStockObject` Windows の機能です。  
  
 指定された四角形の入力時に`FillRect`四角形の右および下の辺は含まれません。 GDI、四角形を塗りつぶしますは含まれません、右の列と下の行、現在のマッピング モードに関係なく。 `FillRect`値を比較、**上部**、**下部**、**左**、および**右**指定された四角形のメンバーです。 場合**下部にある**と同じかそれよりも少ない**上部**、または**右**と同じかそれよりも少ない**左**、四角形は描画しません。  
  
 `FillRect`ような[CDC::FillSolidRect](#fillsolidrect)。 ただし、`FillRect`ブラシは、したがって、純色、ディザー カラー、ハッチ ブラシ、またはパターン塗りつぶす四角形を使用することができます。 `FillSolidRect`純色のみを使用して (によって示される、 **COLORREF**パラメーター)。 `FillRect`通常よりも低い`FillSolidRect`します。  
  
##  <a name="a-namefillrgna--cdcfillrgn"></a><a name="fillrgn"></a>CDC::FillRgn  
 指定された領域を塗りつぶします`pRgn`で指定されたブラシを使用して`pBrush`します。  
  
```  
BOOL FillRgn(
    CRgn* pRgn,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 塗りつぶす領域へのポインター。 指定された領域の座標は、論理単位で指定されます。  
  
 `pBrush`  
 領域を塗りつぶすに使用されるブラシを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して、ブラシを作成する必要がありますか、`CBrush`メンバー関数`CreateHatchBrush`、 `CreatePatternBrush`、`CreateSolidBrush`を取得または**GetStockObject**します。  
  
### <a name="example"></a>例  
  例を参照してください[CRgn::CreateRoundRectRgn](../../mfc/reference/crgn-class.md#createroundrectrgn)します。  
  
##  <a name="a-namefillsolidrecta--cdcfillsolidrect"></a><a name="fillsolidrect"></a>CDC::FillSolidRect  
 指定した純色で指定された四角形を入力するには、このメンバー関数を呼び出します。  
  
```  
void FillSolidRect(
    LPCRECT lpRect,  
    COLORREF clr);

 
void FillSolidRect(
    int x,  
    int y,  
    int cx,  
    int cy,  
    COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 (論理単位で) に外接する四角形を指定します。 ポインターを渡すことができます、 [RECT](../../mfc/reference/rect-structure1.md)データ構造体、または`CRect`このパラメーターにします。  
  
 `clr`四角形の塗りつぶしに使用する色を指定します。  
  
 *x*  
 論理で四角形の左上隅の x 座標を指定します。  
  
 *y*  
 論理でコピー先の四角形の左上隅の y 座標を指定します。  
  
 `cx`  
 四角形の幅を指定します。  
  
 `cy`  
 四角形の高さを指定します。  
  
### <a name="remarks"></a>コメント  
 `FillSolidRect`よく似ています[CDC::FillRect](#fillrect)。 ただし、`FillSolidRect`純色のみを使用して (によって示される、 **COLORREF**パラメーター)、中に`FillRect`ブラシは、したがって、純色、ディザー カラー、ハッチ ブラシ、またはパターン塗りつぶす四角形を使用することができます。 `FillSolidRect`通常より高速`FillRect`します。  
  
> [!NOTE]
>  呼び出すと`FillSolidRect`、背景色は、以前に使用して設定された[SetBkColor](#setbkcolor)、によって示される色に設定されている`clr`します。  
  
##  <a name="a-nameflattenpatha--cdcflattenpath"></a><a name="flattenpath"></a>CDC::FlattenPath  
 現在のデバイス コンテキストに選択したパス内の任意の曲線を変換しを一連の行の各曲線をオンにします。  
  
```  
BOOL FlattenPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namefloodfilla--cdcfloodfill"></a><a name="floodfill"></a>CDC::FloodFill  
 現在のブラシで表示画面の領域を塗りつぶします。  
  
```  
BOOL FloodFill(
    int x,  
    int y,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 塗りつぶしを開始点の論理の x 座標を指定します。  
  
 *y*  
 塗りつぶしを開始点の論理の y 座標を指定します。  
  
 `crColor`  
 境界の色を指定します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 が返される特定のポイントがで指定された境界の色を持つ場合は、読み込みを完了できませんでした`crColor`、点クリッピング領域の外側ですか。  
  
### <a name="remarks"></a>コメント  
 指定されたとして制限する領域を想定`crColor`します。 `FloodFill`関数で指定した位置から始まります*x*と*y*色の境界をすべての方向は続行されます。  
  
 メモリ デバイス コンテキストとラスター表示テクノロジのサポートをサポートするデバイスだけ、`FloodFill`メンバー関数。 については**RC_BITBLT**機能によりを参照してください、`GetDeviceCaps`メンバー関数。  
  
 `ExtFloodFill`関数は柔軟性が、同様の機能を提供します。  
  
##  <a name="a-nameframerecta--cdcframerect"></a><a name="framerect"></a>CDC::FrameRect  
 指定された四角形の周囲の境界線を描画`lpRect`します。  
  
```  
void FrameRect(
    LPCRECT lpRect,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)四角形の左上隅および右下隅の論理座標を格納しているオブジェクト。 渡すことも、`CRect`このパラメーターにします。  
  
 `pBrush`  
 四角形の境界線に使用するブラシを識別します。  
  
### <a name="remarks"></a>コメント  
 関数では、指定されたブラシを使用して、境界線を描画します。 境界線の高さと幅は、常に 1 の論理単位です。  
  
 場合、四角形の**下部にある**座標は、以下に**上部**、または**右**と同じかそれよりも少ない**左**、四角形は描画しません。  
  
 によって描画される境界線`FrameRect`によって描画される境界線と同じ位置には、**四角形**メンバー関数が同じ座標を使用して (場合**四角形**ワイド論理ユニットが 1 であるペンを使用)。 四角形の内部を入力していない`FrameRect`します。  
  
##  <a name="a-nameframergna--cdcframergn"></a><a name="framergn"></a>CDC::FrameRgn  
 指定される領域の周囲に境界線を描画`pRgn`で指定されたブラシを使用して`pBrush`します。  
  
```  
BOOL FrameRgn(
    CRgn* pRgn,  
    CBrush* pBrush,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 指す、`CRgn`罫線で囲む領域を識別するオブジェクト。 指定された領域の座標は、論理単位で指定されます。  
  
 `pBrush`  
 指す、`CBrush`境界線の描画に使用するブラシを識別するオブジェクト。  
  
 `nWidth`  
 デバイス単位での垂直方向のブラシで、罫線の幅を指定します。  
  
 `nHeight`  
 デバイス単位での水平方向のブラシで、境界線の高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CRgn::CombineRgn](../../mfc/reference/crgn-class.md#combinergn)します。  
  
##  <a name="a-namefromhandlea--cdcfromhandle"></a><a name="fromhandle"></a>CDC::FromHandle  
 ポインターを返す、`CDC`デバイス コンテキストを識別するハンドルが指定されるとします。  
  
```  
static CDC* PASCAL FromHandle(HDC hDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 Windows デバイス コンテキストを識別するハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 ポインターは、一時的な場合があり、を超えてすぐに使用しない格納されている必要があります。  
  
### <a name="remarks"></a>コメント  
 `CDC` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CDC` オブジェクトが生成され、関連付けられます。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::GetPrinterDC](../../mfc/reference/cprintdialog-class.md#getprinterdc)します。  
  
##  <a name="a-namegetarcdirectiona--cdcgetarcdirection"></a><a name="getarcdirection"></a>CDC::GetArcDirection  
 デバイス コンテキストの現在の円弧の方向を取得します。  
  
```  
int GetArcDirection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、現在の円弧の方向を指定します。 有効な戻り値を次に示します。  
  
- **AD_COUNTERCLOCKWISE**円弧や四角形を反時計回りに描画します。  
  
- **AD_CLOCKWISE**円弧や四角形を時計回りに描画します。  
  
 エラーが発生する場合、戻り値は&0; です。  
  
### <a name="remarks"></a>コメント  
 弧と四角形の関数は、円弧の方向を使用します。  
  
##  <a name="a-namegetaspectratiofiltera--cdcgetaspectratiofilter"></a><a name="getaspectratiofilter"></a>CDC::GetAspectRatioFilter  
 現在の縦横比フィルターの設定を取得します。  
  
```  
CSize GetAspectRatioFilter() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CSize`の現在の縦横比フィルターで使用される縦横比を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 縦横比は、デバイスのピクセル幅と高さで形成される比率です。 デバイスの縦横比の情報は、作成、選択した場合、およびフォントの表示に使用されます。 Windows には、すべての利用可能なフォントから特定の縦横比用に設計されたフォントを選択する、縦横比フィルター、特別なフィルターが用意されています。 フィルターで指定した縦横比を使用して、`SetMapperFlags`メンバー関数。  
  
##  <a name="a-namegetbkcolora--cdcgetbkcolor"></a><a name="getbkcolor"></a>CDC::GetBkColor  
 現在の背景色を返します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
 バック グラウンド モードの場合**不透明**システムでは、背景色を使用して、スタイル設定された行のギャップ、ハッチ ブラシ、行と文字セルの背景のギャップを入力します。 システムでは、色とモノクロのデバイス コンテキストのビットマップを変換するときに背景色も使用します。  
  
##  <a name="a-namegetbkmodea--cdcgetbkmode"></a><a name="getbkmode"></a>CDC::GetBkMode  
 バック グラウンド モードを返します。  
  
```  
int GetBkMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のバック グラウンドのモードは、**不透明**または**TRANSPARENT**します。  
  
### <a name="remarks"></a>コメント  
 バック グラウンド モードでは、システムがテキストやハッチ ブラシ、実線ではないペンのスタイルを描画する前に、描画サーフェイスの背景色を取り除くかどうかを定義します。  
  
##  <a name="a-namegetboundsrecta--cdcgetboundsrect"></a><a name="getboundsrect"></a>CDC::GetBoundsRect  
 指定したデバイス コンテキストに現在の累計の外接する四角を返します。  
  
```  
UINT GetBoundsRect(
    LPRECT lpRectBounds,  
    UINT flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectBounds`  
 現在の外接する四角形を受け取るバッファーへのポインター。 四角形は、論理座標で返されます。  
  
 `flags`  
 外接する四角形が返された後、クリアするかどうかを指定します。 このパラメーターは、0 にするか、次の値に設定する必要があります。  
  
- **DCB_RESET**が返された後に消去する外接する四角形を強制します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、外接する四角形の現在の状態を指定します。 次の値の組み合わせを指定できます。  
  
- **DCB_ACCUMULATE**四角形が蓄積されるの境界が発生しています。  
  
- **DCB_RESET**外接する四角形は空です。  
  
- **DCB_SET**外接する四角形は空ではありません。  
  
- **DCB_ENABLE**が蓄積される境界です。  
  
- **DCB_DISABLE**が蓄積される境界は無効になっています。  
  
##  <a name="a-namegetbrushorga--cdcgetbrushorg"></a><a name="getbrushorg"></a>CDC::GetBrushOrg  
 デバイス コンテキストで現在選択されているブラシの原点を (デバイス単位) を取得します。  
  
```  
CPoint GetBrushOrg() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (デバイス単位) としてのブラシの現在の配信元、 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 初期のブラシの原点が (0,&0;) がクライアント領域のです。 戻り値は、デスクトップ ウィンドウの原点に対するデバイス単位で、このポイントを指定します。  
  
##  <a name="a-namegetcharacterplacementa--cdcgetcharacterplacement"></a><a name="getcharacterplacement"></a>CDC::GetCharacterPlacement  
 文字列に関するさまざまな情報を取得します。  
  
```  
DWORD GetCharacterPlacement(
    LPCTSTR lpString,  
    int nCount,  
    int nMaxExtent,  
    LPGCP_RESULTS lpResults,  
    DWORD dwFlags) const;  
  
DWORD GetCharacterPlacement(
    CString& str,  
    int nMaxExtent,  
    LPGCP_RESULTS lpResults,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpString`  
 処理する文字列へのポインター。  
  
 `nCount`  
 文字列の長さを指定します。 ANSI バージョンの場合は BYTE カウント、Unicode 関数の場合は WORD カウントです。 詳細については、次を参照してください。 [GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx)します。  
  
 `nMaxExtent`  
 処理する文字列の最大エクステントを論理単位で指定します。 このエクステントを超えて処理された文字列は無視されます。 並べ替えやグリフの配列に必要な演算は、範囲に含まれている文字だけに適用されます。 このパラメーターは、`dwFlags` パラメーターに GCP_MAXEXTENT 値が指定されている場合にだけ使用します。 入力文字列を処理するときは、エクステントの合計が最大値を超えない限り、各文字と文字のエクステントが出力、エクステント、および他の配列に追加されます。 制限に達すると、処理は停止します。  
  
 lpResults  
 ポインター、 [GCP_Results](http://msdn.microsoft.com/library/windows/desktop/dd144842\(v=vs.85\).aspx)関数の結果を受け取る。  
  
 `dwFlags`  
 必要な配列に挿入される文字列の処理方法を指定します。 このパラメーターは、いずれかを指定できますまたは以上の値に示されている、`dwFlags`のセクションで、 [GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx)トピックです。  
  
 `str`  
 ポインター、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトを処理します。  
  
### <a name="return-value"></a>戻り値  
 関数が正常に終了した場合は、文字列の幅と高さを論理単位で返します。  
  
 関数が失敗した場合は、0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetcharabcwidthsa--cdcgetcharabcwidths"></a><a name="getcharabcwidths"></a>CDC::GetCharABCWidths  
 現在の TrueType フォントから指定された範囲内の連続するいくつかの文字幅を取得します。  
  
```  
BOOL GetCharABCWidths(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPABC lpabc) const;  
  
BOOL GetCharABCWidths(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPABCFLOAT lpABCF) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFirstChar`  
 現在のフォントの文字幅を返す基になる文字の範囲で最初の文字を指定します。  
  
 `nLastChar`  
 現在のフォントの文字幅を返す基になる文字の範囲で、最後の文字を指定します。  
  
 `lpabc`  
 配列を指す[ABC](../../mfc/reference/abc-structure.md)関数が返す場合は、文字幅を受け取る構造体。 この配列は、少なくとも数だけ含める必要があります**ABC**がで指定された範囲の文字としての構造体、`nFirstChar`と`nLastChar`パラメーター。  
  
 *lpABCF*  
 配列で、アプリケーションによって提供されるバッファーを指す[ABCFLOAT](../../mfc/reference/abcfloat-structure.md)関数が返す場合は、文字幅を受信する構造体。 この関数によって返される幅は、IEEE 浮動小数点形式でです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 論理ユニットでは、幅が返されます。 この関数は、TrueType フォントにのみ成功します。  
  
 TrueType ラスタライザーは、特定のポイント サイズを選択した後に、"ABC"の文字間隔を提供します。 "A"の間隔は、グリフを配置する前に、現在の位置に追加される距離です。 "B"の間隔は、グリフの黒い部分の幅です。 "C"の間隔は、グリフの右側に空白文字の対応する現在の位置に追加されます。 文字幅の総計が A で指定された B + C.  
  
 ときに、`GetCharABCWidths`メンバー関数は、負の値"A"を取得または"C"、文字、その文字の幅には、スペーシングまたはオーバー ハングが含まれています。  
  
 ABC 幅をフォント デザイン単位に変換する、アプリケーション作成フォント高さが (の説明に従って、**する**のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造) に格納されている値と等しく、 **ntmSizeEM**のメンバー、 [NEWTEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162741)構造体。 (の値、 **ntmSizeEM**メンバーを呼び出すことによって取得できる、 [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) Windows の機能です)。  
  
 現在選択されているフォントの範囲外にある文字では、既定の文字の ABC 幅が使用されます。  
  
 非 TrueType フォントの文字の幅を取得するアプリケーションを使用する必要があります、 [GetCharWidth](http://msdn.microsoft.com/library/windows/desktop/dd144861) Windows の機能です。  
  
##  <a name="a-namegetcharabcwidthsia--cdcgetcharabcwidthsi"></a><a name="getcharabcwidthsi"></a>CDC::GetCharABCWidthsI  
 現在の TrueType フォントから指定された範囲内の連続したグリフのインデックスの論理単位の幅を取得します。  
  
```  
BOOL GetCharABCWidthsI(
    UINT giFirst,  
    UINT cgi,  
    LPWORD pgi,  
    LPABC lpabc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `giFirst`  
 現在のフォントの連続したグリフのインデックスのグループの最初のグリフのインデックスを指定します。 場合にのみ、このパラメーターが使用、`pgi`パラメーターは**NULL**します。  
  
 `cgi`  
 グリフのインデックスの数を指定します。  
  
 `pgi`  
 グリフのインデックスを含む配列へのポインター。 値の場合**NULL**、`giFirst`パラメーターは、代わりに使用します。 `cgi`パラメーターは、この配列のグリフのインデックスの数を指定します。  
  
 `lpabc`  
 配列を指すポインター [ABC](http://msdn.microsoft.com/library/windows/desktop/dd162454)文字幅を受け取る構造体。 この配列は、少なくとも数だけ含める必要があります**ABC**構造体のグリフのインデックスで指定された行があるため、`cgi`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetCharABCWidthsI](http://msdn.microsoft.com/library/windows/desktop/dd144859)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetcharwidtha--cdcgetcharwidth"></a><a name="getcharwidth"></a>CDC::GetCharWidth  
 現在のフォントの文字の隣接するグループの個々 の文字の幅を取得を使用して`m_hAttribDC`、入力デバイス コンテキスト。  
  
```  
BOOL GetCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPINT lpBuffer) const;  
  
BOOL GetCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    float* lpFloatBuffer) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFirstChar`  
 現在のフォントの文字の隣接するグループの最初の文字を指定します。  
  
 `nLastChar`  
 現在のフォントの文字の隣接するグループの最後の文字を指定します。  
  
 `lpBuffer`  
 現在のフォントの文字の隣接するグループの幅の値を受け取るバッファーへのポインター。  
  
 *lpFloatBuffer*  
 文字幅を受け取るバッファーへのポインター。 返される幅は、32 ビット IEEE 浮動小数点形式でです。 (幅は、文字のベース ライン沿いに測定が)。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば場合、`nFirstChar`文字を識別する 'a' と`nLastChar`文字 'z' では、関数を取得をすべて小文字の幅を識別します。  
  
 関数の値を指すバッファーに格納する`lpBuffer`です。 このバッファーは、すべての幅を保持するのに十分である必要があります。 つまり、必要があります、少なくとも 26 のエントリ例では。  
  
 特定のフォントの文字の隣接するグループ内の文字が存在しない場合は、既定の文字の幅の値が割り当てられます。  
  
##  <a name="a-namegetcharwidthia--cdcgetcharwidthi"></a><a name="getcharwidthi"></a>CDC::GetCharWidthI  
 現在のフォントから指定された範囲内の連続したグリフのインデックスの論理座標で表したの幅を取得します。  
  
```  
BOOL GetCharWidthI(
    UINT giFirst,  
    UINT cgi,  
    LPWORD pgi,  
    LPINT lpBuffer) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `giFirst`  
 現在のフォントの連続したグリフのインデックスのグループの最初のグリフのインデックスを指定します。 場合にのみ、このパラメーターが使用、`pgi`パラメーターは**NULL**します。  
  
 `cgi`  
 グリフのインデックスの数を指定します。  
  
 `pgi`  
 グリフのインデックスを含む配列へのポインター。 値の場合**NULL**、`giFirst`パラメーターは、代わりに使用します。 `cgi`パラメーターは、この配列のグリフのインデックスの数を指定します。  
  
 `lpBuffer`  
 幅を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetCharWidthI](http://msdn.microsoft.com/library/windows/desktop/dd144864)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetclipboxa--cdcgetclipbox"></a><a name="getclipbox"></a>CDC::GetClipBox  
 現在のクリップ領域を最小の外接する四角形の寸法を取得します。  
  
```  
virtual int GetClipBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)を四角形の大きさを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 クリップ領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**クリッピング領域には罫線を重複しています。  
  
- **エラー**デバイス コンテキストが無効です。  
  
- **NULLREGION**クリッピング領域が空です。  
  
- **SIMPLEREGION**クリッピング領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 ディメンションが指すバッファーにコピー`lpRect`します。  
  
##  <a name="a-namegetcoloradjustmenta--cdcgetcoloradjustment"></a><a name="getcoloradjustment"></a>CDC::GetColorAdjustment  
 デバイス コンテキストの色の調整値を取得します。  
  
```  
BOOL GetColorAdjustment(LPCOLORADJUSTMENT lpColorAdjust) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpColorAdjust`  
 指す、 [COLORADJUSTMENT](../../mfc/reference/coloradjustment-structure.md)色の調整値を受信するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namegetcurrentbitmapa--cdcgetcurrentbitmap"></a><a name="getcurrentbitmap"></a>CDC::GetCurrentBitmap  
 現在選択されているポインターを返します`CBitmap`オブジェクトです。  
  
```  
CBitmap* GetCurrentBitmap() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBitmap`成功以外の場合は、オブジェクト、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、一時オブジェクトを返す可能性があります。  
  
##  <a name="a-namegetcurrentbrusha--cdcgetcurrentbrush"></a><a name="getcurrentbrush"></a>CDC::GetCurrentBrush  
 現在選択されているポインターを返します`CBrush`オブジェクトです。  
  
```  
CBrush* GetCurrentBrush() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBrush`成功以外の場合は、オブジェクト、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、一時オブジェクトを返す可能性があります。  
  
##  <a name="a-namegetcurrentfonta--cdcgetcurrentfont"></a><a name="getcurrentfont"></a>CDC::GetCurrentFont  
 現在選択されているポインターを返します`CFont`オブジェクトです。  
  
```  
CFont* GetCurrentFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFont`成功以外の場合は、オブジェクト、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、一時オブジェクトを返す可能性があります。  
  
##  <a name="a-namegetcurrentpalettea--cdcgetcurrentpalette"></a><a name="getcurrentpalette"></a>CDC::GetCurrentPalette  
 現在選択されているポインターを返します`CPalette`オブジェクトです。  
  
```  
CPalette* GetCurrentPalette() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`成功以外の場合は、オブジェクト、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、一時オブジェクトを返す可能性があります。  
  
##  <a name="a-namegetcurrentpena--cdcgetcurrentpen"></a><a name="getcurrentpen"></a>CDC::GetCurrentPen  
 現在選択されているポインターを返します`CPen`オブジェクトです。  
  
```  
CPen* GetCurrentPen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPen`成功以外の場合は、オブジェクト、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、一時オブジェクトを返す可能性があります。  
  
##  <a name="a-namegetcurrentpositiona--cdcgetcurrentposition"></a><a name="getcurrentposition"></a>CDC::GetCurrentPosition  
 (論理座標) 現在の位置を取得します。  
  
```  
CPoint GetCurrentPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の位置として、`CPoint`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 現在の位置を設定できる、`MoveTo`メンバー関数。  
  
##  <a name="a-namegetdcbrushcolora--cdcgetdcbrushcolor"></a><a name="getdcbrushcolor"></a>CDC::GetDCBrushColor  
 現在のブラシの色を取得します。  
  
```  
COLORREF GetDCBrushColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)の現在のブラシの色の値。  
  
 戻り値は、関数が失敗した場合、 **CLR_INVALID**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetDCBrushColor](http://msdn.microsoft.com/library/windows/desktop/dd144872)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetdcpencolora--cdcgetdcpencolor"></a><a name="getdcpencolor"></a>CDC::GetDCPenColor  
 現在のペンの色を取得します。  
  
```  
COLORREF GetDCPenColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)の現在のペンの色の値。  
  
 戻り値は、関数が失敗した場合、 **CLR_INVALID**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数で Win32 関数[GetDCPenColor](http://msdn.microsoft.com/library/windows/desktop/dd144875)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetdevicecapsa--cdcgetdevicecaps"></a><a name="getdevicecaps"></a>について  
 さまざまなディスプレイ デバイスのデバイスに固有の情報を取得します。  
  
```  
int GetDeviceCaps(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 返される情報の種類を指定します。 参照してください[調べるため](http://msdn.microsoft.com/library/windows/desktop/dd144877)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、要求された機能の値です。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::GetDefaults](../../mfc/reference/cprintdialog-class.md#getdefaults)します。  
  
##  <a name="a-namegetfontdataa--cdcgetfontdata"></a><a name="getfontdata"></a>CDC::GetFontData  
 スケーラブルなフォント ファイルからフォント メトリック情報を取得します。  
  
```  
DWORD GetFontData(
    DWORD dwTable,  
    DWORD dwOffset,  
    LPVOID lpData,  
    DWORD cbData) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwTable`  
 返されるメトリック テーブルの名前を指定します。 このパラメーターは、米国 Microsoft Corporation によって発行された TrueType フォント ファイルの仕様に記載されているメトリックのテーブルのいずれかを指定できます。 このパラメーターが 0 の場合は、フォント ファイルの先頭からの情報が取得されます。  
  
 `dwOffset`  
 情報の取得を開始する位置を示すテーブルの先頭からのオフセットを指定します。 指定されたテーブルの先頭から、情報を取得するこのパラメーターが 0 の場合、`dwTable`パラメーター。 この値が、テーブルのサイズ以上である場合`GetFontData`0 を返します。  
  
 `lpData`  
 フォント情報を受け取るバッファーへのポインター。 この値が場合**NULL**で指定されたフォント データに必要なバッファーのサイズを返します、`dwTable`パラメーター。  
  
 `cbData`  
 (バイト単位) を取得する情報の長さを指定します。 このパラメーターが 0 の場合`GetFontData`で指定されるデータのサイズを返す、`dwTable`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 指すバッファーに返されるバイトの数を指定`lpData`関数が成功した場合は、それ以外の場合 –&1; です。  
  
### <a name="remarks"></a>コメント  
 取得する情報は、フォント ファイルと返される情報の長さにオフセットを指定することによって識別されます。  
  
 アプリケーションが使用できる場合があります、`GetFontData`メンバー関数をドキュメントに TrueType フォントを保存します。 これを行うには、アプリケーションかどうかをフォント埋め込み可能の場合は 0 を指定するすべてのフォント ファイルを取得、 `dwTable`、 `dwOffset`、および`cbData`パラメーター。  
  
 アプリケーションでは、チェックして、フォントを埋め込むことが可能かどうかを判断できる、 **otmfsType**のメンバー、 [OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755)構造体。 場合のビット 1 **otmfsType**を設定すると、フォントの埋め込みは許可されていません。 1 ビットがオフの場合は、フォントを埋め込むことができます。 ビット 2 が設定されている場合、埋め込みは読み取り専用です。  
  
 アプリケーションは、この関数を使用して、非 TrueType フォントの情報を取得するしようとすると、`GetFontData`メンバー関数は-1 を返します。  
  
##  <a name="a-namegetfontlanguageinfoa--cdcgetfontlanguageinfo"></a><a name="getfontlanguageinfo"></a>CDC::GetFontLanguageInfo  
 指定した表示のコンテキストで現在選択されているフォントについての情報を返します。  
  
```  
DWORD GetFontLanguageInfo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、現在選択されているフォントの特性を識別します。 使用可能な値の完全な一覧については、次を参照してください。 [GetFontLanguageInfo](http://msdn.microsoft.com/library/windows/desktop/dd144886)します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetFontLanguageInfo](http://msdn.microsoft.com/library/windows/desktop/dd144886)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetglyphoutlinea--cdcgetglyphoutline"></a><a name="getglyphoutline"></a>CDC::GetGlyphOutline  
 アウトライン曲線または現在のフォントのアウトライン文字用のビットマップを取得します。  
  
```  
DWORD GetGlyphOutline(
    UINT nChar,  
    UINT nFormat,  
    LPGLYPHMETRICS lpgm,  
    DWORD cbBuffer,  
    LPVOID lpBuffer,  
    const MAT2* lpmat2) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 情報が返されるの文字を指定します。  
  
 `nFormat`  
 情報を返す関数の形式を指定します。 次の値のいずれか、または 0 を指定できます。  
  
|値|説明|  
|-----------|-------------|  
|**GGO_BITMAP**|グリフのビットマップを返します。 関数が返す場合は、バッファーを指す`lpBuffer`ダブルワード境界に 1 ビット/ピクセルのビットマップが含まれています。|  
|**GGO_NATIVE**|デバイス単位を使用して、ラスタライザーのネイティブ形式でデータ ポイント曲線を返します。 この値を指定すると、すべての変換が指定された`lpmat2`は無視されます。|  
  
 時の値`nFormat`が 0 の場合、関数に格納、 [GLYPHMETRICS](http://msdn.microsoft.com/library/windows/desktop/dd144955)構造体が、グリフのアウトライン データを返しません。  
  
 *lpgm*  
 指す、 **GLYPHMETRICS**文字セル内のグリフの配置を表す構造体。  
  
 `cbBuffer`  
 関数がアウトライン文字についての情報をコピーする先のバッファーのサイズを指定します。 この値が 0 の場合、`nFormat`パラメーターは、いずれか、 **GGO_BITMAP**または**GGO_NATIVE**値、関数が必要なバッファーのサイズを返します。  
  
 `lpBuffer`  
 関数がアウトライン文字についての情報をコピーする先のバッファーへのポインター。 場合`nFormat`指定、 **GGO_NATIVE**の形式で情報の値がコピーされる**TTPOLYGONHEADER**と**それに続く**構造体。 この値がある場合**NULL**と`nFormat`か、 **GGO_BITMAP**または**GGO_NATIVE**値、関数が必要なバッファーのサイズを返します。  
  
 `lpmat2`  
 指す、 [MAT2](http://msdn.microsoft.com/library/windows/desktop/dd145048)文字の変換行列を格納する構造体。 このパラメーターを指定できません**NULL**を場合でも、 **GGO_NATIVE**の値を指定`nFormat`します。  
  
### <a name="return-value"></a>戻り値  
 場合、取得した情報に必要なバッファーのバイト単位のサイズ`cbBuffer`は 0 または`lpBuffer`は**NULL**します。 それ以外の場合、正の値がある場合は、関数成功すると、エラーがある場合は-1 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションが指す構造体で、2-2 での変換行列を指定することで、ビットマップ形式で取得される文字数を回転できます`lpmat2`します。  
  
 グリフのアウトラインは、一連の輪郭として返されます。 各の輪郭、 [TTPOLYGONHEADER](http://msdn.microsoft.com/library/windows/desktop/dd145158)構造が続く多くとして**それに続く**として記述するために必要なの構造体します。 すべてのポイントとして返される[POINTFX](http://msdn.microsoft.com/library/windows/desktop/dd162806)構造体し、絶対位置、いない相対的な移動を表します。 によって指定されたスタート地点、 **pfxStart**のメンバー、 [TTPOLYGONHEADER](http://msdn.microsoft.com/library/windows/desktop/dd145158)構造体は、輪郭のアウトラインの開始位置を示すポイント。 [それに続く](http://msdn.microsoft.com/library/windows/desktop/dd145157)後に続く構造体には、多角形のレコードまたはスプライン レコードを指定できます。 折れ線レコードは、一連のポイントです。点の間に描画された直線では、文字の概要について説明します。 スプライン レコードでは、TrueType (つまり、二次特徴 b スプライン) で使用される二次曲線を表します。  
  
##  <a name="a-namegetgraphicsmodea--cdcgetgraphicsmode"></a><a name="getgraphicsmode"></a>CDC::GetGraphicsMode  
 指定したデバイス コンテキストの現在のグラフィックス モードを取得します。  
  
```  
int GetGraphicsMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合に、現在のグラフィックス モードを返します。 このメソッドが返すことができる値の一覧は、次を参照してください。[については](http://msdn.microsoft.com/library/windows/desktop/dd144892)です。  
  
 失敗した場合は 0 を返します。  
  
 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメソッド[については](http://msdn.microsoft.com/library/windows/desktop/dd144892)です。  
  
##  <a name="a-namegethalftonebrusha--cdcgethalftonebrush"></a><a name="gethalftonebrush"></a>CDC::GetHalftoneBrush  
 このメンバー関数を呼び出してハーフトーン ブラシを取得します。  
  
```  
static CBrush* PASCAL GetHalftoneBrush();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBrush`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 ハーフトーン ブラシは、ディザー パターンを作成する前景色と背景の色またはピクセルを示しています。 ハーフトーン ブラシで作成されたディザー パターンの例を次に示します。  
  
 ![ディザリングされたペンのストロークの詳細](../../mfc/reference/media/vc318s1.gif "vc318s1")  
  
##  <a name="a-namegetkerningpairsa--cdcgetkerningpairs"></a><a name="getkerningpairs"></a>CDC::GetKerningPairs  
 文字のカーニング、指定したデバイス コンテキストで現在選択されているフォントのペアを取得します。  
  
```  
int GetKerningPairs(
    int nPairs,  
    LPKERNINGPAIR lpkrnpair) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPairs`  
 数を指定[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145024)構造体を指す`lpkrnpair`します。 この関数はカーニング ペアで指定されたよりはコピーしません`nPairs`します。  
  
 `lpkrnpair`  
 配列を指す**受け取る**カーニング構造体のペアを関数が返す場合。 この配列で指定された数は、少なくとも構造体を含める必要があります`nPairs`します。 このパラメーターは場合**NULL**、カーニング、フォントのペアの合計数を返します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、取得したカーニング ペアの数またはカーニング、フォントのペアの合計数を指定します。 関数が失敗した、またはフォントのカーニング ペアがない場合は、0 が返されます。  
  
##  <a name="a-namegetlayouta--cdcgetlayout"></a><a name="getlayout"></a>CDC::GetLayout  
 このメンバー関数を呼び出してテキストとグラフィックス メタファイル プリンターなどのデバイス コンテキストのレイアウトを決定します。  
  
```  
DWORD GetLayout() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、レイアウトは、現在のデバイス コンテキストのフラグします。 それ以外の場合、 **GDI_ERROR**します。 拡張エラーについては、呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。 レイアウトのフラグの一覧は、次を参照してください。 [CDC::SetLayout](#setlayout)します。  
  
### <a name="remarks"></a>コメント  
 既定のレイアウトは左右からです。  
  
##  <a name="a-namegetmapmodea--cdcgetmapmode"></a><a name="getmapmode"></a>CDC::GetMapMode  
 現在のマップ モードを取得します。  
  
```  
int GetMapMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マップ モード。  
  
### <a name="remarks"></a>コメント  
 マップ モードの説明は、次を参照してください。、`SetMapMode`メンバー関数。  
  
> [!NOTE]
>  呼び出した場合[SetLayout](#setlayout) DC を右から左のレイアウトに変更する**SetLayout**へのマッピング モードが自動的に変更`MM_ISOTROPIC`します。 後続の呼び出し結果として、`GetMapMode`戻ります`MM_ISOTROPIC`します。  
  
##  <a name="a-namegetmiterlimita--cdcgetmiterlimit"></a><a name="getmiterlimit"></a>CDC::GetMiterLimit  
 デバイス コンテキストのマイター リミットを返します。  
  
```  
float GetMiterLimit() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 マイター結合を持つ幾何学の線が描画、マイター リミットが使用されます。  
  
##  <a name="a-namegetnearestcolora--cdcgetnearestcolor"></a><a name="getnearestcolor"></a>CDC::GetNearestColor  
 指定した論理色に最も一致する塗りつぶしの色を返します。  
  
```  
COLORREF GetNearestColor(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 照合する色を指定します。  
  
### <a name="return-value"></a>戻り値  
 色の RGB (赤、緑、青) 値平面を定義するに最も近い色、`crColor`デバイスを表すことができます。  
  
### <a name="remarks"></a>コメント  
 指定されたデバイスは、この色を表現できる必要があります。  
  
##  <a name="a-namegetoutlinetextmetricsa--cdcgetoutlinetextmetrics"></a><a name="getoutlinetextmetrics"></a>CDC::GetOutlineTextMetrics  
 TrueType フォントのメトリックの情報を取得します。  
  
```  
UINT GetOutlineTextMetrics(
    UINT cbData,  
    LPOUTLINETEXTMETRIC lpotm) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpotm`  
 配列を指す[OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755)構造体。 このパラメーターは場合**NULL**、取得したメトリック データに必要なバッファーのサイズを返します。  
  
 `cbData`  
 情報が返されたバッファーのバイト単位のサイズを指定します。  
  
 `lpotm`  
 指す、 **OUTLINETEXTMETRIC**構造体。 このパラメーターは場合**NULL**、取得したメトリック情報に必要なバッファーのサイズを返します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 [OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755)構造体には、TrueType 形式で提供されるフォント メトリック情報の大部分が含まれています。 など、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体。 最後の&4; つのメンバー、 **OUTLINETEXTMETRIC**構造体は文字列へのポインター。 アプリケーションでは、他のメンバーに必要な容量に加えて、これらの文字列の領域を割り当てる必要があります。 指定する必要なサイズを取得するためにメモリを割り当てるための最も簡単な方法は、文字列のサイズにシステムの制限がないので**NULL**の`lpotm`最初の呼び出しで、`GetOutlineTextMetrics`関数です。  
  
##  <a name="a-namegetoutputcharwidtha--cdcgetoutputcharwidth"></a><a name="getoutputcharwidth"></a>CDC::GetOutputCharWidth  
 出力デバイス コンテキストを使用して`m_hDC`、および現在のフォントの文字の隣接するグループ内の個々 の文字幅を取得します。  
  
```  
BOOL GetOutputCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPINT lpBuffer) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFirstChar`  
 現在のフォントの文字の隣接するグループの最初の文字を指定します。  
  
 `nLastChar`  
 現在のフォントの文字の隣接するグループの最後の文字を指定します。  
  
 `lpBuffer`  
 現在のフォントの文字の隣接するグループの幅の値を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば場合、`nFirstChar`文字を識別する 'a' と`nLastChar`文字 'z' では、関数を取得をすべて小文字の幅を識別します。  
  
 関数の値を指すバッファーに格納する`lpBuffer`です。 このバッファーは、すべての幅を保持するのに十分である必要があります。つまり、必要があります、少なくとも 26 のエントリ例では。  
  
 特定のフォントの文字の隣接するグループ内の文字が存在しない場合は、既定の文字の幅の値が割り当てられます。  
  
##  <a name="a-namegetoutputtabbedtextextenta--cdcgetoutputtabbedtextextent"></a><a name="getoutputtabbedtextextent"></a>CDC::GetOutputTabbedTextExtent  
 幅を使用して文字の文字列の高さを計算するには、このメンバー関数を呼び出す[m_hDC](#m_hdc)、出力デバイス コンテキスト。  
  
```  
CSize GetOutputTabbedTextExtent(
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
  
CSize GetOutputTabbedTextExtent(
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 測定する文字の文字列へのポインター。 渡すことも、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`-1 で、長さを計算します。  
  
 `nTabPositions`  
 指す配列内のタブ ストップの位置の数を指定`lpnTabStopPositions`します。  
  
 `lpnTabStopPositions`  
 論理ユニットのタブ ストップの位置を表す、整数の配列を指します。 タブ ストップは昇順に並べ替え; 並べられていなければなりませんx の最小値は、配列の最初の項目にする必要があります。 バック タブは使用できません。  
  
 `str`  
 A`CString`を測定する指定された文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 (論理単位で) 内の文字列のサイズ、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 文字列の幅がで指定されたタブ ストップをに基づいて、文字列に&1; つまたは複数のタブ文字が含まれている場合`lpnTabStopPositions`します。 関数では、現在選択されているフォントを使用して、文字列の寸法を計算します。  
  
 幅と高さによって返される、現在のクリップ領域はオフセット排出されません、`GetOutputTabbedTextExtent`関数です。  
  
 一部のデバイスは通常のセルの配列に文字を配置しないので (つまり、カーニング、文字の場合)、文字列内の文字のエクステントの合計を文字列の範囲を等しいできない可能性があります。  
  
 場合`nTabPositions`は 0 と`lpnTabStopPositions`は**NULL**タブは、8 つの平均の文字幅に拡張されます。 場合`nTabPositions`1 では、タブ ストップが先の配列の最初の値で指定された距離によって区切られるように`lpnTabStopPositions`ポイントです。 場合`lpnTabStopPositions`ポイントを&1; つの値を超えるにタブ ストップがで指定された数に達するまで、配列内の各値の設定は`nTabPositions`です。  
  
##  <a name="a-namegetoutputtextextenta--cdcgetoutputtextextent"></a><a name="getoutputtextextent"></a>CDC::GetOutputTextExtent  
 出力デバイス コンテキストを使用するには、このメンバー関数を呼び出す[m_hDC](#m_hdc)幅と現在のフォントを使用してテキストの行の高さを計算します。  
  
```  
CSize GetOutputTextExtent(
    LPCTSTR lpszString,  
    int nCount) const;  
  
CSize GetOutputTextExtent(const CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 文字の文字列へのポインター。 渡すことも、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`-1 で、長さを計算します。  
  
 `str`  
 A`CString`を測定する指定された文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返されます (論理単位で) の文字列のディメンション、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 現在のクリップ領域には影響しません幅と高さによって返される`GetOutputTextExtent`です。  
  
 一部のデバイスは通常のセルの配列に文字を配置しないので (つまり、カーニングが実行される)、文字列内の文字のエクステントの合計を文字列の範囲を等しいできない可能性があります。  
  
##  <a name="a-namegetoutputtextmetricsa--cdcgetoutputtextmetrics"></a><a name="getoutputtextmetrics"></a>CDC::GetOutputTextMetrics  
 使用して現在のフォントのメトリックを取得`m_hDC`、出力デバイス コンテキスト。  
  
```  
BOOL GetOutputTextMetrics(LPTEXTMETRIC lpMetrics) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMetrics`  
 指す、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)メトリックを受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namegetpatha--cdcgetpath"></a><a name="getpath"></a>CDC::GetPath  
 行のエンドポイントとデバイス コンテキストに選択されているパスに含まれる曲線の制御点を定義する座標を取得します。  
  
```  
int GetPath(
    LPPOINT lpPoints,  
    LPBYTE lpTypes,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)データ構造体または`CPoint`線の端点と曲線コントロール ポイントのオブジェクトを配置しています。  
  
 `lpTypes`  
 頂点の種類が格納されたバイトの配列を指します。 値は、次のいずれかです。  
  
- **直前**、対応する特定の時点を指定`lpPoints`不整合のある図から開始します。  
  
- **PT_LINETO**前のポイントと、対応するポイントの指定`lpPoints`行のエンドポイントします。  
  
- **PT_BEZIERTO** 、対応する特定の時点を指定`lpPoints`ベジエ曲線の制御点または終了します。  
  
 **PT_BEZIERTO**型が常に&3; つのセットで発生します。 直前のパス内のポイントでは、ベジエ曲線の開始点を定義します。 最初の&2; つ**PT_BEZIERTO**ポイントは、コントロール ポイントし、3 番目**PT_BEZIERTO**ポイントは、エンド ポイント (場合ハード コーディングされた)。  
  
     A **PT_LINETO**または**PT_BEZIERTO**型は、次のフラグと組み合わせることも (ビットごとの演算子を使用して`OR`) することを示し、対応するポイントが、図の最後の点で、図を閉じる必要があります。  
  
- **PT_CLOSEFIGURE**の図は、対応する行の後に自動的に閉じられます。 または、曲線を描画するように指定します。 最後に対応するポイントに直線または曲線のエンドポイントから行を描画することによって、図が閉じられる**直前**します。  
  
 `nCount`  
 合計数を指定[ポイント](../../mfc/reference/point-structure1.md)に格納できるデータ構造、`lpPoints`配列。 この値に格納できるバイト数と同じである必要があります、`lpTypes`配列。  
  
### <a name="return-value"></a>戻り値  
 場合、`nCount`パラメーターが&0; 以外で列挙されるポイント数です。 場合`nCount`が 0 の場合、パス内の地点の合計数 (と`GetPath`nothing をバッファーに書き込みます)。 場合`nCount`がゼロ以外で、ポイントの数よりも少ないパスにある、戻り値は-1。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストでは、閉じたパスを含める必要があります。 論理座標では、パスのポイントが返されます。 ポイントはそのため、デバイスの座標のパスに格納`GetPath`現在の変換の逆関数を使用してデバイス座標から論理座標にポイントを変更します。 `FlattenPath`する前に、メンバー関数を呼び出すことができます`GetPath`パス内のすべての曲線を直線セグメントに変換します。  
  
### <a name="example"></a>例  
  例を参照してください[cdc::beginpath](#beginpath)します。  
  
##  <a name="a-namegetpixela--cdcgetpixel"></a><a name="getpixel"></a>CDC::GetPixel  
 指定した点のピクセルの RGB 色の値を取得*x*と*y*します。  
  
```  
COLORREF GetPixel(
    int x,  
    int y) const;  
  
COLORREF GetPixel(POINT point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理で調査する点の x 座標を指定します。  
  
 *y*  
 論理で調査する点の y 座標を指定します。  
  
 `point`  
 調査する点の論理 x 座標と y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントの色の RGB 色の値、関数のいずれかのバージョン。 座標は、クリッピング領域で、ポイントを指定しない場合は-1 を返します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、クリッピング領域にする必要があります。 クリッピング領域に、ポイントがない場合は、関数も何も起こりませんおよび-1 を返します。  
  
 サポートしないデバイス、 **GetPixel**関数です。 詳細については、次を参照してください。、 **RC_BITBLT** ラスター機能、[調べるため](#getdevicecaps)メンバー関数。  
  
 **GetPixel**メンバー関数が&2; つの形式です。 1 つ目は、2 つの座標値。2 つ目は、いずれかを受け取ります、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
##  <a name="a-namegetpolyfillmodea--cdcgetpolyfillmode"></a><a name="getpolyfillmode"></a>CDC::GetPolyFillMode  
 現在の多角形の塗りつぶしモードを取得します。  
  
```  
int GetPolyFillMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在多角形の塗りつぶしモード**代替**または**ワインディング**関数が成功しました場合。  
  
### <a name="remarks"></a>コメント  
 参照してください、`SetPolyFillMode`多角形塗りつぶしモードの詳細については、メンバー関数。  
  
##  <a name="a-namegetrop2a--cdcgetrop2"></a><a name="getrop2"></a>CDC::GetROP2  
 現在の描画モードを取得します。  
  
```  
int GetROP2() const;  
```  
  
### <a name="return-value"></a>戻り値  
 描画モード。 描画モードの値の一覧は、次を参照してください。、`SetROP2`メンバー関数。  
  
### <a name="remarks"></a>コメント  
 描画モードでは、既にディスプレイ表面における色でペンの色とオブジェクトの内部を組み合わせる方法を指定します。  
  
##  <a name="a-namegetsafehdca--cdcgetsafehdc"></a><a name="getsafehdc"></a>CDC::GetSafeHdc  
 取得するには、このメンバー関数を呼び出す[m_hDC](#m_hdc)、出力デバイス コンテキスト。  
  
```  
HDC GetSafeHdc() const;  
```  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキスト ハンドル。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、null ポインターの使用も機能します。  
  
##  <a name="a-namegetstretchbltmodea--cdcgetstretchbltmode"></a><a name="getstretchbltmode"></a>CDC::GetStretchBltMode  
 現在のビットマップの伸縮モードを取得します。  
  
```  
int GetStretchBltMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、現在のビットマップの伸縮モードを指定: **STRETCH_ANDSCANS**、 **STRETCH_DELETESCANS**、または**終了した**: 関数が成功した場合。  
  
### <a name="remarks"></a>コメント  
 ビットマップの伸縮モードでは、拡大またはでは、圧縮されているビットマップから情報を削除する方法を定義、`StretchBlt`メンバー関数。  
  
 **STRETCH_ANDSCANS**と**終了した**モードは通常モノクロ ビットマップのピクセルを前景色を保持するために使用します。 **STRETCH_DELETESCANS**モードは通常カラー ビットマップの色を保持するために使用されます。  
  
##  <a name="a-namegettabbedtextextenta--cdcgettabbedtextextent"></a><a name="gettabbedtextextent"></a>CDC::GetTabbedTextExtent  
 幅を使用して文字の文字列の高さを計算するには、このメンバー関数を呼び出す[は](#m_hattribdc)属性のデバイス コンテキスト。  
  
```  
CSize GetTabbedTextExtent(
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
  
CSize GetTabbedTextExtent(
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 文字の文字列へのポインター。 渡すことも、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`-1 で、長さを計算します。  
  
 `nTabPositions`  
 指す配列内のタブ ストップの位置の数を指定`lpnTabStopPositions`します。  
  
 `lpnTabStopPositions`  
 論理ユニットのタブ ストップの位置を表す、整数の配列を指します。 タブ ストップは昇順に並べ替え; 並べられていなければなりませんx の最小値は、配列の最初の項目にする必要があります。 バック タブは使用できません。  
  
 `str`  
 A`CString`を描画する指定された文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 (論理単位で) 内の文字列のサイズ、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 文字列の幅がで指定されたタブ ストップをに基づいて、文字列に&1; つまたは複数のタブ文字が含まれている場合`lpnTabStopPositions`します。 関数では、現在選択されているフォントを使用して、文字列の寸法を計算します。  
  
 幅と高さによって返される、現在のクリップ領域はオフセット排出されません、`GetTabbedTextExtent`関数です。  
  
 一部のデバイスは通常のセルの配列に文字を配置しないので (つまり、カーニング、文字の場合)、文字列内の文字のエクステントの合計を文字列の範囲を等しいできない可能性があります。  
  
 場合`nTabPositions`は 0 と`lpnTabStopPositions`は**NULL**タブは、平均の文字幅の 8 倍に拡張されます。 場合`nTabPositions`1 では、タブ ストップが先の配列の最初の値で指定された距離によって区切られるように`lpnTabStopPositions`ポイントです。 場合`lpnTabStopPositions`ポイントを&1; つの値を超えるにタブ ストップがで指定された数に達するまで、配列内の各値の設定は`nTabPositions`です。  
  
##  <a name="a-namegettextaligna--cdcgettextalign"></a><a name="gettextalign"></a>CDC::GetTextAlign  
 デバイス コンテキストのテキスト配置フラグの状態を取得します。  
  
```  
UINT GetTextAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキスト配置フラグの状態。 戻り値は、1 つ以上の次の値には。  
  
- **TA_BASELINE** x 軸方向の配置と外接する四角形内で選択したフォントの基準を指定します。  
  
- **TA_BOTTOM**外接する四角形の下端と x 軸方向の配置を指定します。  
  
- **TA_CENTER** y 軸の配置と外接する四角形の中心を指定します。  
  
- **TA_LEFT**外接する四角形の左端と y 軸の配置を指定します。  
  
- **TA_NOUPDATECP**の現在の位置が更新されないことを指定します。  
  
- **TA_RIGHT** y 軸の配置と外接する四角形の右側にあるを指定します。  
  
- **TA_TOP**外接する四角形の上端と x 軸方向の配置を指定します。  
  
- **TA_UPDATECP**の現在の位置が更新されるように指定します。  
  
### <a name="remarks"></a>コメント  
 テキスト配置フラグ方法`TextOut`と`ExtTextOut`メンバー関数は、文字列の開始点に関連するテキストの文字列を配置します。 テキスト配置フラグは必ずしも単一のビットでありを 0 に等しい場合があります。 フラグが設定されているかどうかをテストするには、アプリケーションは以下の手順を実行する必要があります。  
  
1.  次のようにグループ化、関連するフラグのフラグにビットごとの OR 演算子が適用されます。  
  
    - **TA_LEFT**、 **TA_CENTER**、および**TA_RIGHT**  
  
    - **TA_BASELINE**、 **TA_BOTTOM**、および**TA_TOP**  
  
    - **TA_NOUPDATECP**と**TA_UPDATECP**  
  
2.  ビットごとの適用- と演算子の結果と戻り値を`GetTextAlign`します。  
  
3.  この結果とフラグが等しいかどうかをテストします。  
  
##  <a name="a-namegettextcharacterextraa--cdcgettextcharacterextra"></a><a name="gettextcharacterextra"></a>CDC::GetTextCharacterExtra  
 文字間隔の現在の設定を取得します。  
  
```  
int GetTextCharacterExtra() const;  
```  
  
### <a name="return-value"></a>戻り値  
 文字間隔の量。  
  
### <a name="remarks"></a>コメント  
 GDI は、この間隔をデバイス コンテキストに、行のテキストを書き込むときに、改行文字を含む、各文字を追加します。  
  
 文字間隔の既定値は 0 です。  
  
##  <a name="a-namegettextcolora--cdcgettextcolor"></a><a name="gettextcolor"></a>CDC::GetTextColor  
 現在のテキストの色を取得します。  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値として現在のテキストの色。  
  
### <a name="remarks"></a>コメント  
 テキストの色は、GDI のテキスト出力メンバー関数を使用して描画される文字の前景色[TextOut](#textout)、 [ExtTextOut](#exttextout)、および[TabbedTextOut](#tabbedtextout)します。  
  
##  <a name="a-namegettextextenta--cdcgettextextent"></a><a name="gettextextent"></a>CDC::GetTextExtent  
 幅の大きさを現在のフォントを使用してテキストの行の高さを計算するには、このメンバー関数を呼び出します。  
  
```  
CSize GetTextExtent(
    LPCTSTR lpszString,  
    int nCount) const;  
  
CSize GetTextExtent(const CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 文字の文字列へのポインター。 渡すことも、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。  
  
 `str`  
 A`CString`を指定した文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 (論理単位で) 内の文字列のサイズ、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 情報を取得してから[は](#m_hattribdc)属性のデバイス コンテキスト。  
  
 既定では、`GetTextExtent`を水平方向の寸法を取得するテキストが設定されていると想定しています (つまり、escapement は 0)。 0 以外の傾斜を指定するフォントを作成する場合は、文字列の寸法を取得するには、明示的にテキストの角度を変換する必要があります。  
  
 現在のクリップ領域には影響しません幅と高さによって返される`GetTextExtent`です。  
  
 一部のデバイスは通常のセルの配列に文字を配置しないので (つまり、カーニングが実行される)、文字列内の文字のエクステントの合計を文字列の範囲を等しいできない可能性があります。  
  
##  <a name="a-namegettextextentexpointia--cdcgettextextentexpointi"></a><a name="gettextextentexpointi"></a>CDC::GetTextExtentExPointI  
 指定された領域内に収まるし、それらの各文字のテキストのエクステントを配列に設定を指定した文字列の文字数を取得します。  
  
```  
BOOL GetTextExtentExPointI(
    LPWORD pgiIn,  
    int cgi,  
    int nMaxExtent,  
    LPINT lpnFit,  
    LPINT alpDx,  
    LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pgiIn`  
 エクステントが取得するのにはグリフのインデックスの配列へのポインター。  
  
 `cgi`  
 指す配列内のグリフの数を指定`pgiIn`します。  
  
 `nMaxExtent`  
 論理ユニットは、書式設定された文字列の最大使用可能な幅を指定します。  
  
 `lpnFit`  
 指定された領域に合わせて、文字の最大数のカウントを受け取る整数へのポインター`nMaxExtent`します。 `lpnFit`は**NULL**、`nMaxExtent`は無視されます。  
  
 *alpDx*  
 部分的なグリフのエクステントを受け取る整数の配列へのポインター。 配列内の各要素で指定された領域に収まるようグリフのグリフのインデックスの配列の先頭との間での論理単位の距離は、`nMaxExtent`です。 この配列は、グリフのインデックスで指定された数は、少なくとも要素を持つ必要がありますが`cgi`、関数で指定された数だけのグリフのインデックスに対してのみエクステントを持つ配列を設定する`lpnFit`です。 場合*lpnDx*は**NULL**関数は文字列の一部の幅を計算しません。  
  
 `lpSize`  
 ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)を論理単位でのグリフのインデックスの配列のサイズを受け取る構造体。 この値にすることはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetTextExtentExPointI](http://msdn.microsoft.com/library/windows/desktop/dd144936)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegettextextentpointia--cdcgettextextentpointi"></a><a name="gettextextentpointi"></a>CDC::GetTextExtentPointI  
 幅と高さの指定されたグリフのインデックスの配列を取得します。  
  
```  
BOOL GetTextExtentPointI(
    LPWORD pgiIn,  
    int cgi,  
    LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pgiIn`  
 エクステントが取得するのにはグリフのインデックスの配列へのポインター。  
  
 `cgi`  
 指す配列内のグリフの数を指定`pgiIn`します。  
  
 `lpSize`  
 ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)を論理単位でのグリフのインデックスの配列のサイズを受け取る構造体。 この値にすることはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetTextExtentPointI](http://msdn.microsoft.com/library/windows/desktop/dd144939)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegettextfacea--cdcgettextface"></a><a name="gettextface"></a>CDC::GetTextFace  
 このメンバー関数を呼び出して現在のフォントの書体名をバッファーにコピーします。  
  
```  
int GetTextFace(
    int nCount,  
    LPTSTR lpszFacename) const;  
  
int GetTextFace(CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCount`  
 バイト単位でバッファーのサイズを指定します。 フォント名がこのパラメーターで指定したバイト数よりも長い場合、名前が切り詰められます。  
  
 *lpszFacename*  
 書体名のバッファーへのポインター。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を含まない、バッファーにコピーされたバイト数。 エラーが発生した場合は 0 になります。  
  
### <a name="remarks"></a>コメント  
 フォント名は、null で終わる文字列としてコピーされます。  
  
##  <a name="a-namegettextmetricsa--cdcgettextmetrics"></a><a name="gettextmetrics"></a>CDC::GetTextMetrics  
 属性のデバイス コンテキストを使用して現在のフォントのメトリックを取得します。  
  
```  
BOOL GetTextMetrics(LPTEXTMETRIC lpMetrics) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMetrics`  
 指す、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)メトリックを受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namegetviewportexta--cdcgetviewportext"></a><a name="getviewportext"></a>CDC::GetViewportExt  
 デバイス コンテキストのビューポートの x 範囲と y 範囲を取得します。  
  
```  
CSize GetViewportExt() const;  
```  
  
### <a name="return-value"></a>戻り値  
 X と y の範囲範囲 (デバイス単位) として、`CSize`オブジェクトです。  
  
##  <a name="a-namegetviewportorga--cdcgetviewportorg"></a><a name="getviewportorg"></a>CDC::GetViewportOrg  
 デバイス コンテキストに関連付けられているビューポートの原点の x 座標と y 座標を取得します。  
  
```  
CPoint GetViewportOrg() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビューポート (デバイス座標) での発生元、`CPoint`オブジェクトです。  
  
##  <a name="a-namegetwindowa--cdcgetwindow"></a><a name="getwindow"></a>CDC::GetWindow  
 ディスプレイ デバイス コンテキストに関連付けられているウィンドウを返します。  
  
```  
CWnd* GetWindow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 これは、高度な機能です。 たとえば、このメンバー関数を印刷するとき、または印刷プレビューで [ビュー] ウィンドウを返しません可能性があります。 常に、出力に関連付けられているウィンドウを返します。 特定のドメイン コント ローラーを使用して出力関数は、このウィンドウに描画します。  
  
##  <a name="a-namegetwindowexta--cdcgetwindowext"></a><a name="getwindowext"></a>CDC::GetWindowExt  
 デバイス コンテキストに関連付けられているウィンドウの x 範囲と y 範囲を取得します。  
  
```  
CSize GetWindowExt() const;  
```  
  
### <a name="return-value"></a>戻り値  
 X と y の範囲範囲を (論理単位で) として、`CSize`オブジェクトです。  
  
##  <a name="a-namegetwindoworga--cdcgetwindoworg"></a><a name="getwindoworg"></a>CDC::GetWindowOrg  
 デバイス コンテキストに関連付けられているウィンドウの原点の x 座標と y 座標を取得します。  
  
```  
CPoint GetWindowOrg() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (論理座標) でのウィンドウとしての原点を`CPoint`オブジェクトです。  
  
##  <a name="a-namegetworldtransforma--cdcgetworldtransform"></a><a name="getworldtransform"></a>CDC::GetWorldTransform  
 ページ領域の変換に現在のワールド空間を取得します。  
  
```  
BOOL GetWorldTransform(XFORM& rXform) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rXform`  
 参照、 [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228)ページ領域の変換に現在のワールド空間を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に&0; 以外の値を返します。  
  
 失敗した場合は 0 を返します。  
  
 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメソッド[GetWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd144953)します。  
  
##  <a name="a-namegradientfilla--cdcgradientfill"></a><a name="gradientfill"></a>CDC::GradientFill  
 四角形と三角形の構造をスムーズに別の一方の側から消えて色で塗りつぶすには、このメンバー関数を呼び出します。  
  
```  
BOOL GradientFill(
    TRIVERTEX* pVertices,  
    ULONG nVertices,  
    void* pMesh,  
    ULONG nMeshElements,  
    DWORD dwMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pVertices*  
 配列を指すポインター [TRIVERTEX](http://msdn.microsoft.com/library/windows/desktop/dd145142)構造体の三角形の頂点を定義します。  
  
 *nVertices*  
 頂点の数。  
  
 `pMesh`  
 配列[場合は](http://msdn.microsoft.com/library/windows/desktop/dd144959)三角形のモード、または配列内の構造体[GRADIENT_RECT](http://msdn.microsoft.com/library/windows/desktop/dd144958)四角形のモードでの構造体。  
  
 *nMeshElements*  
 内の要素 (三角形または四角形) の数`pMesh`します。  
  
 `dwMode`  
 グラデーションの塗りつぶしモードを指定します。 使用可能な値の一覧は、次を参照してください。 [GradientFill](http://msdn.microsoft.com/library/windows/desktop/dd144957)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。`GradientFill`で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegraystringa--cdcgraystring"></a><a name="graystring"></a>Cdc::graystring  
 描画には、メモリ ビットマップ内のテキストを書き込む、暗転、ビットマップ、ディスプレイにビットマップをコピーして指定された場所に (灰色) のテキストが淡色表示されます。  
  
```  
virtual BOOL GrayString(
    CBrush* pBrush,  
    BOOL (CALLBACK* lpfnOutput)(
    HDC,
    LPARAM,
    int),  
    LPARAM lpData,  
    int nCount,  
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBrush`  
 淡色 (灰色表示) に使用されるブラシを識別します。  
  
 `lpfnOutput`  
 文字列を描画するアプリケーションによって提供されるコールバック関数のプロシージャ インスタンスのアドレスを指定します。 詳細については、Windows の説明を参照してください。 **OutputFunc** [コールバック関数](../../mfc/reference/callback-function-for-cdc-graystring.md)します。 このパラメーターがある場合**NULL**、システムでは、Windows を使用して`TextOut`関数、文字列を描画して`lpData`出力する文字の文字列への long ポインターであると見なされます。  
  
 `lpData`  
 出力の関数に渡されるデータへの far ポインターを指定します。 場合`lpfnOutput`は**NULL**、`lpData`出力する文字列への long ポインターである必要があります。  
  
 `nCount`  
 出力する文字数を指定します。 このパラメーターが 0 の場合`GrayString`文字列の長さを計算する (ことを前提として`lpData`文字列へのポインターです)。 場合`nCount`は – 1 と指す関数`lpfnOutput`を返すため 0、イメージのの表示が淡色表示にします。  
  
 *x*  
 文字列を囲む四角形の開始位置の論理の x 座標を指定します。  
  
 *y*  
 文字列を囲む四角形の開始位置の論理の y 座標を指定します。  
  
 `nWidth`  
 文字列を囲む四角形の幅を (論理単位で指定します。 場合`nWidth`は 0、 `GrayString` 、領域の幅を計算すると仮定して`lpData`文字列へのポインターです。  
  
 `nHeight`  
 文字列を囲む四角形の高さを (論理単位で指定します。 場合`nHeight`は 0、 `GrayString` 、領域の高さを計算と仮定して`lpData`文字列へのポインターです。  
  
### <a name="return-value"></a>戻り値  
 文字列を描画する場合は 0 以外、またはいずれかの場合は 0、`TextOut`関数、またはアプリケーションによって提供される出力関数に 0 が返される灰色表示のメモリのビットマップを作成するメモリ不足が発生した場合、またはです。  
  
### <a name="remarks"></a>コメント  
 この関数には、選択されたブラシとバック グラウンドに関係なく、テキストが使用できなくなります。 `GrayString`メンバー関数は、現在選択されているフォントを使用します。 `MM_TEXT`マッピング モードは、この関数を使用する前に選択する必要があります。  
  
 淡色表示 (灰色表示) の文字列を呼び出さずに純色の灰色をサポートするデバイスに描画する、`GrayString`メンバー関数。 システム カラー**で**無効なテキストの描画に使用される実線灰色のシステム カラーです。 アプリケーションを呼び出して、 **GetSysColor**の色の値を取得する Windows の機能**で**します。 色が 0 (黒) 以外の場合、アプリケーションを呼び出すことができます、`SetTextColor`テキストの色を色の値に設定し、文字列を直接描画するメンバー関数。 取得した色が黒の場合、アプリケーションを呼び出す必要があります`GrayString`淡色 (灰色) するテキスト。  
  
 場合`lpfnOutput`は**NULL**、GDI は、ウィンドウを使って[TextOut](http://msdn.microsoft.com/library/windows/desktop/dd145133)関数、および`lpData`出力する文字への far ポインターと見なされます。 によって出力される文字を処理できないかどうか、`TextOut`メンバー関数 (たとえば、文字列を格納するビットマップとして)、アプリケーションが独自の出力関数を指定する必要があります。  
  
 なお、すべてのコールバック関数がコールバックの境界を越えて例外がスローされることはできませんので、Windows に復帰する前に Microsoft Foundation 例外をトラップする必要があります。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
 渡されるコールバック関数`GrayString`を使用する必要があります、`__stdcall`呼び出し規約とと共にエクスポートする必要があります`__declspec`します。  
  
 フレームワークがプレビュー モードでの呼び出しの場合、`GrayString`にメンバー関数が変換された、`TextOut`呼び出す、またはコールバック関数は呼び出されません。  
  
##  <a name="a-namehimetrictodpa--cdchimetrictodp"></a><a name="himetrictodp"></a>CDC::HIMETRICtoDP  
 変換するときに、この関数を使用して**HIMETRIC** OLE からピクセルのサイズ。  
  
```  
void HIMETRICtoDP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキスト オブジェクトのマッピング モードがあるかどうか`MM_LOENGLISH`、 `MM_HIENGLISH`、`MM_LOMETRIC`または`MM_HIMETRIC`変換がインチの物理ピクセルの数に基づきます。 マップ モードが非強制モードのいずれかのかどうか (など`MM_TEXT`)、変換が論理インチのピクセル数に基づきます。  
  
##  <a name="a-namehimetrictolpa--cdchimetrictolp"></a><a name="himetrictolp"></a>CDC::HIMETRICtoLP  
 変換するには、この関数を呼び出す**HIMETRIC**単位の論理単位にします。  
  
```  
void HIMETRICtoLP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 表示された場合、この関数を使用して**HIMETRIC**サイズ OLE であり、アプリケーションの自然な割り当てモードに変換するからです。  
  
 変換は、まずは、 **HIMETRIC**単位 (ピクセル) とし、これらの単位をデバイス コンテキストの現在のマップ単位を使用して論理単位に変換します。 デバイスのウィンドウとビューポートのエクステントが結果に影響することに注意してください。  
  
##  <a name="a-nameintersectcliprecta--cdcintersectcliprect"></a><a name="intersectcliprect"></a>CDC::IntersectClipRect  
 現在のリージョンと指定された四角形の交差部分を形成する、新しいクリップ領域を作成`x1`、 `y1`、 `x2`、および`y2`です。  
  
```  
int IntersectClipRect(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
int IntersectClipRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 論理で四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 論理で四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 論理で四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 論理で四角形の右下隅の y 座標を指定します。  
  
 `lpRect`  
 四角形を指定します。 いずれかを渡すことができます、`CRect`オブジェクトまたはへのポインター、`RECT`このパラメーターの構造体。  
  
### <a name="return-value"></a>戻り値  
 新しいクリップ領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**新しいクリップ領域は、重なり合った境界線。  
  
- **エラー**デバイス コンテキストが無効です。  
  
- **NULLREGION**新しいクリップ領域が空です。  
  
- **SIMPLEREGION**新しいクリップ領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 GDI は、新しい境界内に収まるすべての後続出力をクリップします。 幅と高さは、32,767 を超えないです。  
  
##  <a name="a-nameinvertrecta--cdcinvertrect"></a><a name="invertrect"></a>CDC::InvertRect  
 指定した四角形の内容を反転します。  
  
```  
void InvertRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`RECT`反転される四角形の論理座標を格納しています。 渡すことも、`CRect`このパラメーターにします。  
  
### <a name="remarks"></a>コメント  
 反転は、論理操作および各ピクセルのビットを反転できません。 モノクロ モニターでこの関数では黒と黒のピクセルを白のピクセル白です。 色のディスプレイで異なります表示の色を生成する方法です。 呼び出す`InvertRect`同じ四角形で&2; 回の色を前に、表示を復元します。  
  
 四角形が空である場合は、何も描画されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#36;](../../mfc/codesnippet/cpp/cdc-class_8.cpp)]  
  
##  <a name="a-nameinvertrgna--cdcinvertrgn"></a><a name="invertrgn"></a>CDC::InvertRgn  
 指定される領域の色を反転`pRgn`します。  
  
```  
BOOL InvertRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 反転する領域を識別します。 領域の座標は、論理単位で指定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 モノクロ モニターでこの関数では黒と黒のピクセルを白のピクセル白です。 色のディスプレイで異なります表示の色を生成する方法です。  
  
##  <a name="a-nameisprintinga--cdcisprinting"></a><a name="isprinting"></a>CDC::IsPrinting  
 デバイス コンテキストが印刷に使用されているかどうかを決定します。  
  
```  
BOOL IsPrinting() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDC`オブジェクトが現在印刷 DC いる場合は 0 です。  
  
##  <a name="a-namelinetoa--cdclineto"></a><a name="lineto"></a>CDC::LineTo  
 現在の位置が、指定された地点を描きます*x*と*y* (または`point`)。  
  
```  
BOOL LineTo(
    int x,  
    int y);  
  
BOOL LineTo(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 線の終点の論理の x 座標を指定します。  
  
 *y*  
 線の終点の論理の y 座標を指定します。  
  
 `point`  
 線の終点を指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 線が描画された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 行が選択されているペンで描画されます。 現在の位置に設定されている*x*、 *y*または`point`です。  
  
### <a name="example"></a>例  
  例を参照してください[CRect::CenterPoint](../../atl-mfc-shared/reference/crect-class.md#centerpoint)します。  
  
##  <a name="a-namelptodpa--cdclptodp"></a><a name="lptodp"></a>CDC::LPtoDP  
 論理ユニットをデバイス単位に変換します。  
  
```  
void LPtoDP(
    LPPOINT lpPoints,  
    int nCount = 1) const;  
  
void LPtoDP(LPRECT lpRect) const;
void LPtoDP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 ポイントの配列を指します。 配列内の各ポイントは、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
 `nCount`  
 配列内の点の数。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトです。 デバイス単位を論理座標から四角形のマッピングの一般的なケースでは、このパラメーターが使用されます。  
  
 `lpSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造体、または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 関数は、各ポイントの座標や GDI の論理座標系デバイス座標系に変換からのサイズの大きさをマップします。 変換は、現在のマップ モードと、元のドメインの設定とデバイスのウィンドウとビューポートのエクステントによって異なります。  
  
 ポイントの x 座標と y 座標は、-32,768 ~ 32,767 に 2 バイト符号付き整数です。 場所のマッピング モードが、これらの制限よりも大きい値になります。 の場合、システム設定値-32,768 および 32,767 にそれぞれします。  
  
##  <a name="a-namelptohimetrica--cdclptohimetric"></a><a name="lptohimetric"></a>CDC::LPtoHIMETRIC  
 論理単位に変換するには、この関数を呼び出す**HIMETRIC**単位です。  
  
```  
void LPtoHIMETRIC(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 指す、**サイズ**構造体、または`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 付与する場合、この関数を使用して**HIMETRIC** ole に、アプリケーションの自然な割り当てモードからの変換のサイズ。 デバイスのウィンドウとビューポートのエクステントが結果に影響することに注意してください。  
  
 デバイス コンテキストの現在のマップ単位を使用して、これらの単位に変換することのピクセルに論理ユニットを変換して、変換を行う**HIMETRIC**単位です。  
  
##  <a name="a-namemhattribdca--cdcmhattribdc"></a><a name="m_hattribdc"></a>CDC::m_hAttribDC  
 この属性のデバイス コンテキスト`CDC`オブジェクトです。  
  
```  
HDC m_hAttribDC;  
```  
  
### <a name="remarks"></a>コメント  
 既定では、このデバイス コンテキストに等しい`m_hDC`します。 一般に、`CDC`デバイス コンテキストから情報を要求が宛て`m_hAttribDC`します。 参照してください、 [CDC](../../mfc/reference/cdc-class.md)クラスの次の&2; つのデバイス コンテキストの使用方法の詳細について説明します。  
  
##  <a name="a-namemhdca--cdcmhdc"></a><a name="m_hdc"></a>CDC::m_hDC  
 この出力デバイス コンテキスト`CDC`オブジェクトです。  
  
```  
HDC m_hDC;  
```  
  
### <a name="remarks"></a>コメント  
 既定では、`m_hDC`に等しい`m_hAttribDC`でラップされたその他のデバイス コンテキスト`CDC`します。 一般に、 `CDC` GDI の呼び出しの出力を作成するには、`m_hDC`デバイス コンテキスト。 初期化することができます`m_hDC`と`m_hAttribDC`にさまざまなデバイス をポイントします。 参照してください、 [CDC](../../mfc/reference/cdc-class.md)クラスの次の&2; つのデバイス コンテキストの使用方法の詳細について説明します。  
  
##  <a name="a-namemaskblta--cdcmaskblt"></a><a name="maskblt"></a>CDC::MaskBlt  
 指定されたマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。  
  
```  
BOOL MaskBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    CBitmap& maskBitmap,  
    int xMask,  
    int yMask,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理でコピー先の四角形の左上隅の x 座標を指定します。  
  
 *y*  
 論理でコピー先の四角形の左上隅の y 座標を指定します。  
  
 `nWidth`  
 論理ユニットは、コピー先の四角形と元のビットマップの幅を指定します。  
  
 `nHeight`  
 論理ユニットは、コピー先の四角形と元のビットマップの高さを指定します。  
  
 `pSrcDC`  
 ビットマップのコピー元デバイス コンテキストを識別します。 場合は&0; である必要があります、 *dwRop*パラメーターは、ソースが含まれていないラスター オペレーションを指定します。  
  
 `xSrc`  
 論理で元のビットマップの左上隅の x 座標を指定します。  
  
 `ySrc`  
 論理で元のビットマップの左上隅の y 座標を指定します。  
  
 `maskBitmap`  
 転送元デバイス コンテキストで、カラー ビットマップと組み合わせて、モノクロ マスク ビットマップを識別します。  
  
 `xMask`  
 指定されたマスク ビットマップの水平方向のピクセルのオフセットを指定、`maskBitmap`パラメーター。  
  
 `yMask`  
 指定されたマスク ビットマップのピクセルの垂直オフセットを指定、`maskBitmap`パラメーター。  
  
 *dwRop*  
 前景色と背景の両方三項ラスター オペレーション コードにより、元とコピー先のデータの組み合わせを制御する関数を使用してこれを指定します。 バック グラウンドのラスター オペレーション コードは、この値には、この値の上位ワードの高いバイトで格納されます。フォア グラウンド ラスター オペレーション コードがこの値には、この値の上位ワードの下位バイトで格納されています。この値の下位ワードは無視され、0 にする必要があります。 マクロ**MAKEROP4**ラスター オペレーション コードの前景色と背景には、このような組み合わせを作成します。 前景色と背景がこの関数のコンテキストでのディスカッションの「解説」セクションを参照してください。 参照してください、`BitBlt`ラスター オペレーション コードにより共通の一覧については、メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 値 1 で指定されたマスクに`maskBitmap`してフォア グラウンド ラスター オペレーション コードを指定することを示します*dwRop*その位置で適用する必要があります。 マスクで 0 の値は、によってバック グラウンドのラスター オペレーション コードが指定されていることを示します*dwRop*その位置で適用する必要があります。 ラスター オペレーションは、ソースを必要とする場合、マスク四角形は、元の四角形を覆って必要があります。 そうでない場合、関数は失敗します。 ラスター オペレーションで、ソースが必要でない場合、マスク四角形にはコピー先の四角形必要がありますについて説明します。 そうでない場合、関数は失敗します。  
  
 この関数が呼び出されると、回転や傾斜変換は元デバイス コンテキストを有効になっている場合、エラーが発生します。 ただし、その他の種類の変換は許可されます。  
  
 ソース、パターン、およびコピー先ビットマップの色形式が異なる場合、この関数は、変換先の形式に一致するようにパターンまたはソース形式に変換します。 マスク ビットマップはモノクロ ビットマップではない場合、エラーが発生します。 拡張メタファイルが記録されているとき、エラーが発生し、0 を返します) 場合はコピー元デバイス コンテキストは拡張メタファイル デバイス コンテキストを識別します。 サポートしないデバイス`MaskBlt`します。 アプリケーションを呼び出す必要があります`GetDeviceCaps`をデバイスにこの関数がサポートしているかどうかを判断します。 この関数のとまったく同じ動作をマスク ビットマップを指定しなかった場合`BitBlt`、フォア グラウンド ラスター オペレーション コードを使用します。 ピクセルのオフセットは、ポイント (0,&0;) にマスク ビットマップで、ソース デバイス コンテキストのビットマップにします。 これは、マスク ビットマップがマスクの設定を含む場合に便利です。アプリケーション簡単に適用、いずれかのマスクの中のタスクにピクセルのオフセットを調整することによってしに四角形のサイズが送信される`MaskBlt`します。  
  
##  <a name="a-namemodifyworldtransforma--cdcmodifyworldtransform"></a><a name="modifyworldtransform"></a>CDC::ModifyWorldTransform  
 指定されたモードを使用してデバイス コンテキストのワールド変換を変更します。  
  
```  
BOOL ModifyWorldTransform(
    const XFORM& rXform,  
    DWORD iMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `rXform`  
 参照、 [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228)構造体の特定のデバイス コンテキストのワールド変換を変更するために使用します。  
  
 `iMode`  
 変換のデータが現在のワールド変換を変更する方法を指定します。 このパラメーターに使用できる値の一覧は、次を参照してください。 [ModifyWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145060)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に&0; 以外の値を返します。  
  
 失敗した場合は 0 を返します。  
  
 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメソッド[ModifyWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145060)します。  
  
##  <a name="a-namemovetoa--cdcmoveto"></a><a name="moveto"></a>CDC::MoveTo  
 現在の位置を指定された位置に移動*x*と*y* (または`point`)。  
  
```  
CPoint MoveTo(
    int x,  
    int y);  
  
CPoint MoveTo(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 新しい位置の論理の x 座標を指定します。  
  
 *y*  
 新しい位置の論理 y 座標を指定します。  
  
 `point`  
 新しい位置を指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 として前の位置の x 座標と y 座標、`CPoint`オブジェクトです。  
  
### <a name="example"></a>例  
  例を参照してください[CRect::CenterPoint](../../atl-mfc-shared/reference/crect-class.md#centerpoint)します。  
  
##  <a name="a-nameoffsetcliprgna--cdcoffsetcliprgn"></a><a name="offsetcliprgn"></a>CDC::OffsetClipRgn  
 指定されたオフセットで、デバイス コンテキストのクリッピング領域に移動します。  
  
```  
int OffsetClipRgn(
    int x,  
    int y);  
  
int OffsetClipRgn(SIZE size);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する論理ユニットの数を指定します。  
  
 *y*  
 上下に移動する論理ユニットの数を指定します。  
  
 `size`  
 オフセット量を指定します。  
  
### <a name="return-value"></a>戻り値  
 新しい領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**クリッピング領域には罫線を重複しています。  
  
- **エラー**デバイス コンテキストが無効です。  
  
- **NULLREGION**クリッピング領域が空です。  
  
- **SIMPLEREGION**クリッピング領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 関数は、領域を移動*x* 、x 軸に沿った単位と*y* y 軸に沿った単位です。  
  
##  <a name="a-nameoffsetviewportorga--cdcoffsetviewportorg"></a><a name="offsetviewportorg"></a>CDC::OffsetViewportOrg  
 現在のビューポートの原点の座標を基準としたビューポートの原点の座標を変更します。  
  
```  
virtual CPoint OffsetViewportOrg(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 現在の原点の x 座標に追加するデバイス単位の数を指定します。  
  
 `nHeight`  
 現在の原点の y 座標に追加するデバイス単位の数を指定します。  
  
### <a name="return-value"></a>戻り値  
 前のビューポートの原点が (デバイス座標で) として、`CPoint`オブジェクトです。  
  
##  <a name="a-nameoffsetwindoworga--cdcoffsetwindoworg"></a><a name="offsetwindoworg"></a>CDC::OffsetWindowOrg  
 現在のウィンドウの原点の座標を基準としたウィンドウの原点の座標を変更します。  
  
```  
CPoint OffsetWindowOrg(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 現在の原点の x 座標に追加する論理ユニットの数を指定します。  
  
 `nHeight`  
 現在の原点の y 座標に追加する論理ユニットの数を指定します。  
  
### <a name="return-value"></a>戻り値  
 前のウィンドウの原点が (論理座標で) として、`CPoint`オブジェクトです。  
  
##  <a name="a-nameoperatorhdca--cdcoperator-hdc"></a><a name="operator_hdc"></a>CDC::operator HDC  
 この演算子を使用してのデバイス コンテキスト ハンドルを取得する、`CDC`オブジェクトです。  
  
```  
operator HDC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、デバイス コンテキスト オブジェクトのハンドルそれ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 ハンドルを使用して、Windows Api を直接呼び出すことができます。  
  
##  <a name="a-namepaintrgna--cdcpaintrgn"></a><a name="paintrgn"></a>CDC::PaintRgn  
 指定された領域を塗りつぶします`pRgn`現在のブラシを使用します。  
  
```  
BOOL PaintRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 塗りつぶす領域を識別します。 指定された領域の座標は、論理単位で指定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namepatblta--cdcpatblt"></a><a name="patblt"></a>Cdc::patblt  
 デバイス上には、ビット パターンを作成します。  
  
```  
BOOL PatBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理でパターンを受け取るには、四角形の左上隅の x 座標を指定します。  
  
 *y*  
 論理でパターンを受け取るには、四角形の左上隅の y 座標を指定します。  
  
 `nWidth`  
 パターンを受け取るには、四角形の幅を (論理単位で指定します。  
  
 `nHeight`  
 パターンを受け取るには、四角形の高さを (論理単位で指定します。  
  
 *dwRop*  
 ラスター オペレーション コードを指定します。 ラスター オペレーション コード (Rop) は、GDI が出力に関連する操作、現在のブラシ、有効なコピー元ビットマップとコピー先のビットマップの色を結合する方法を定義します。 このパラメーターは、次の値のいずれかになります。  
  
- **PATCOPY**コピー先ビットマップにパターンをコピーします。  
  
- **PATINVERT**ブール型 XOR 演算子を使用するパターンとコピー先ビットマップを組み合わせたものです。  
  
- **DSTINVERT**変換先のビットマップを反転します。  
  
- **BLACKNESS**すべて出力を黒です。  
  
- **WHITENESS**すべての出力を白にします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 パターンは、選択されたブラシと、デバイスに既に存在パターンの組み合わせです。 指定されたラスター オペレーション コード*dwRop*パターンを結合する方法を定義します。 この関数の一覧表示するラスター オペレーションは、256 の三項ラスター オペレーション コードの一部のサブセット具体的には、ソースを参照するラスター オペレーション コードは使用できません。  
  
 すべてのデバイス コンテキストのサポート、`PatBlt`関数です。 デバイス コンテキストをサポートするかどうかを確認`PatBlt`を呼び出す、`GetDeviceCaps`メンバー関数を**RASTERCAPS**インデックスを作成しの戻り値を確認して、 **RC_BITBLT**フラグ。  
  
##  <a name="a-namepiea--cdcpie"></a><a name="pie"></a>CDC::Pie  
 中心と&2; つのエンドポイントが線で参加している楕円の円弧を描画することによって作られる扇形を描画します。  
  
```  
BOOL Pie(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Pie(
    LPCRECT lpRect,
    POINT ptStart,
    POINT ptEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 (論理単位で) に外接する四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 (論理単位で) に外接する四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 (論理単位で) に外接する四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 (論理単位で) に外接する四角形の右下隅の y 座標を指定します。  
  
 *x3*  
 (論理単位で) の円弧の始点の x 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y3`  
 (論理単位で) の円弧の始点の y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `x4`  
 (論理単位で) 円弧の終点の x 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `y4`  
 (論理単位で) 円弧の終点の y 座標を指定します。 このポイントは、円弧上正確にする必要はありません。  
  
 `lpRect`  
 外接する四角形を指定します。 いずれかを渡すことができます、`CRect`オブジェクトまたはへのポインター、`RECT`このパラメーターの構造体。  
  
 `ptStart`  
 円弧の始点を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
 `ptEnd`  
 円弧の終点を指定します。 このポイントは、円弧上正確にする必要はありません。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 円弧の中心で指定された外接する四角形の中心`x1`、 `y1`、 `x2`、および`y2`(または`lpRect`)。 始点と円弧の終点が指定された*x3*、 `y3`、 `x4`、および`y4`(または`ptStart`と`ptEnd`)。  
  
 円弧を反時計回りに回転方向に移動したペンで描画します。 次の&2; 行は、各エンドポイントから円弧の中心に描画されます。 扇形の領域には、現在のブラシが挿入されます。 場合*x3* equals`x4`と`y3`equals `y4`、楕円の中心からポイントに&1; 行で楕円になります ( *x3*、 `y3`) または ( `x4`、 `y4`)。  
  
 この関数によって作成されます。 図では、まで拡張が、右下隅の座標は含まれません。 つまり、figure の高さは`y2`– `y1` 、figure の幅は`x2`–`x1`します。 外接する四角形の高さと幅の両方に 2 つのユニットより大きくより小さい 32,767 の単位を使用する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&37;](../../mfc/codesnippet/cpp/cdc-class_9.cpp)]  
  
##  <a name="a-nameplaymetafilea--cdcplaymetafile"></a><a name="playmetafile"></a>CDC::PlayMetaFile  
 デバイス コンテキストでは、指定されたメタファイルのコンテンツを再生します。  
  
```  
BOOL PlayMetaFile(HMETAFILE hMF);

 
BOOL PlayMetaFile(
    HENHMETAFILE hEnhMetaFile,  
    LPCRECT lpBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 *hMF*  
 再生できるようにメタファイルを識別します。  
  
 *hEnhMetaFile*  
 拡張メタファイルを識別します。  
  
 `lpBounds`  
 指す、`RECT`構造体、または`CRect`画像を表示するために使用する外接する四角形の座標を格納しているオブジェクト。 座標は、論理単位で指定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メタファイルを何度でも再生できます。  
  
 2 番目のバージョンの`PlayMetaFile`特定の拡張形式メタファイルに格納されている画像が表示されます。 アプリケーションが第&2; のバージョンを呼び出す場合`PlayMetaFile`、Windows を使用して画像フレーム拡張メタファイルのヘッダーにマップによって指される四角形に画像、`lpBounds`パラメーター。 (この図の傾斜またはワールド変換を呼び出す前に、出力デバイスで設定して回転した可能性があります`PlayMetaFile`)。図では、四角形の端点が含まれています。 拡張メタファイルを再生する前に、出力デバイスでクリッピング領域を定義することで拡張メタファイル画像をクリップすることができます。  
  
 拡張メタファイルにオプションのパレットが含まれている場合、アプリケーションがの&2; 番目のバージョンを呼び出す前に、出力デバイスのカラー パレットを設定して色を統一を実現できます`PlayMetaFile`します。 オプションのパレットを取得する、**カラー** Windows の機能です。 拡張メタファイルを新しく作成した拡張メタファイルに埋め込みの&2; 番目のバージョンを呼び出すことによって`PlayMetaFile`とメタファイルを強化、新しいデバイス コンテキストに元の拡張メタファイルを再生します。  
  
 この関数では、出力デバイス コンテキストの状態が保持されます。 この関数では、作成、拡張メタファイルでは削除されませんが、任意のオブジェクトが削除されます。 この関数を停止するアプリケーションを呼び出すことができます、 **CancelDC**操作を終了する別のスレッドからの Windows の機能です。 この場合、この関数は&0; を返します。  
  
##  <a name="a-nameplgblta--cdcplgblt"></a><a name="plgblt"></a>CDC::PlgBlt  
 元のデバイス コンテキストで指定された四角形から、指定したデバイス コンテキストで指定した平行四辺形に色データのビットのビット ブロック転送を実行します。  
  
```  
BOOL PlgBlt(
    LPPOINT lpPoint,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nWidth,  
    int nHeight,  
    CBitmap& maskBitmap,  
    int xMask,  
    int yMask);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 先の平行四辺形の&3; つの角を識別する論理空間内の&3; つの点の配列を指します。 元の四角形の左上隅は、この配列、配列内の&2; つ目のポイントを右上隅および&3; 番目のポイントを左下隅の最初の要素にマップされます。 元の四角形の右下隅は、暗黙の型の&4; 番目の点、平行四辺形内にマップされます。  
  
 `pSrcDC`  
 転送元デバイス コンテキストを識別します。  
  
 `xSrc`  
 論理ユニットは、元の四角形の左上隅の x 座標を指定します。  
  
 `ySrc`  
 論理ユニットは、元の四角形の左上隅の y 座標を指定します。  
  
 `nWidth`  
 論理ユニットは、元の四角形の幅を指定します。  
  
 `nHeight`  
 論理ユニットは、元の四角形の高さを指定します。  
  
 `maskBitmap`  
 元の四角形の色をマスクするために使用されるオプションのモノクロ ビットマップを識別します。  
  
 `xMask`  
 モノクロ ビットマップの左上隅の x 座標を指定します。  
  
 `yMask`  
 モノクロ ビットマップの左上隅の y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたビットマスク ハンドルは、有効なモノクロ ビットマップを識別する場合、関数はこのビットマップを使用して、元の四角形の色データのビット マスクします。  
  
 平行四辺形 (D) の&4; 番目の頂点が最初の&3; つを扱うことで定義されているポイント (A、B、および C) ベクトルでありコンピューティング D = B と C - A.  
  
 対応するビットマスクが存在する場合、マスク内の 1 の値は、ソース ピクセルの色が変換先にコピーされることを示します。 マスクで 0 の値は、移行先のピクセルの色が、変更できないことを示します。  
  
 マスク四角形が元とコピー先の四角形よりも小さい場合は、関数は、マスク パターンをレプリケートします。  
  
 元のデバイス コンテキストで拡大/縮小、平行移動、およびリフレクションの変換が許可されます。ただし、回転と傾斜変換では。 マスク ビットマップはモノクロ ビットマップではない場合、エラーが発生します。 コピー先デバイス コンテキストの伸縮モードを使用すると、必要な場合は、拡大または (ピクセル単位) を圧縮する方法を決定します。 拡張メタファイルを記録中元デバイス コンテキスト拡張メタファイル デバイス コンテキストを識別する場合に、エラーが発生します。  
  
 コピー先の座標は、コピー先デバイス コンテキストに従って変換されます。コピー元の座標は、コピー元デバイス コンテキストに従って変換されます。 ソースの変換には、回転、傾斜が、エラーが返されます。 送信先と送信元の四角形に含まれる同じ色形式がない場合`PlgBlt`コピー先の四角形を一致するように元の四角形に変換します。 サポートしないデバイス`PlgBlt`します。 詳細については、の説明を参照して、 **RC_BITBLT**ラスターの機能、`CDC::GetDeviceCaps`メンバー関数。  
  
 元とコピー先デバイス コンテキストは、互換性のないデバイスを表す場合`PlgBlt`エラーが返されます。  
  
##  <a name="a-namepolybeziera--cdcpolybezier"></a><a name="polybezier"></a>CDC::PolyBezier  
 1 つまたは複数のベジエ スプラインを描画します。  
  
```  
BOOL PolyBezier(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)がエンドポイントおよびスプラインの端を制御するデータ構造です。  
  
 `nCount`  
 内の地点の数を指定、`lpPoints`配列。 この値は、描画されるスプラインの&3; 倍以上の数を&1; つにする必要があります、各ベジエ スプラインには、2 つの制御点と、エンドポイント、および初期スプラインが必要とするために、追加の開始ポイントが必要です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数では、3 次ベジエ スプラインを描画し、エンドポイントとで指定した管理ポイントを使用して、`lpPoints`パラメーター。 最初のスプラインは、コントロール ポイントとして&2; 番目と&3; 番目のポイントを使用して、最初のポイントまで、4 番目の点に描画されます。 必要な&3; つの点をシーケンス内の後各スプライン: 直前のスプラインの終点が開始点として使用される、シーケンス内の次の&2; つのポイント、管理ポイントおよび&3; 番目は、エンド ポイントです。  
  
 現在の位置が使用されるもによって更新された、`PolyBezier`関数です。 この図は表示されません。 この関数は、現在のペンを使用して線を描画します。  
  
##  <a name="a-namepolybeziertoa--cdcpolybezierto"></a><a name="polybezierto"></a>CDC::PolyBezierTo  
 1 つまたは複数のベジエ スプラインを描画します。  
  
```  
BOOL PolyBezierTo(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)エンドポイントとコントロールを含むデータ構造体をポイントします。  
  
 `nCount`  
 内の地点の数を指定、`lpPoints`配列。 この値は、各ベジエ スプラインは、2 つの制御点と終了点が必要なために、スプラインを描画する数の&3; 倍にすることがあります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数で指定された管理ポイントを使用して&3; 次ベジエ スプラインを描画する、`lpPoints`パラメーター。 最初のスプラインは、現在位置からのコントロール ポイントとして最初の&2; つのポイントを使用して&3; 番目のポイントを描画します。 後続の各スプラインは、関数は、3 つの点を必要があり、次の開始点として以前スプラインの終了位置を使用します。 `PolyBezierTo`現在の位置を最後のベジエ スプラインの終了位置に移動します。 この図は表示されません。 この関数は、現在のペンを使用して線を描画します。  
  
### <a name="example"></a>例  
  例を参照してください[cdc::beginpath](#beginpath)します。  
  
##  <a name="a-namepolydrawa--cdcpolydraw"></a><a name="polydraw"></a>CDC::PolyDraw  
 一連の線分とベジエ スプラインを描画します。  
  
```  
BOOL PolyDraw(
    const POINT* lpPoints,  
    const BYTE* lpTypes,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)ごとに、エンドポイントが含まれるデータ構造が行のセグメントと、エンドポイントと各ベジエ スプラインのポイントを制御します。  
  
 `lpTypes`  
 各ポイントにする方法を指定する配列を指す、`lpPoints`配列が使用されています。 値は、次のいずれかになります。  
  
- **直前**このポイントが切り離された図を起動するように指定します。 この時点では、新しい現在の位置になります。  
  
- **PT_LINETO**行が、この時点で新しい現在の位置となる現在の位置から描画することを指定します。  
  
- **PT_BEZIERTO**この点がベジエ スプラインの制御点または終了ことを指定します。  
  
 **PT_BEZIERTO**型が常に&3; つのセットで発生します。 現在の位置では、ベジエ スプラインの始点を定義します。 最初の&2; つ**PT_BEZIERTO**ポイントは、コントロール ポイントし、3 番目**PT_BEZIERTO**ポイントは、終了ポイントです。 終了の時点では、新しい現在の位置になります。 存在しない場合&3; つの連続する**PT_BEZIERTO**ポイント、エラーが発生します。  
  
     A **PT_LINETO**または**PT_BEZIERTO**型は、ビットごとの演算子を使用して次の定数と組み合わせることができますか、対応するポイントが、図と、図の最後の点であることを示すが終了します。  
  
- **PT_CLOSEFIGURE**図が後に自動的に閉じられることを指定、 **PT_LINETO**または**PT_BEZIERTO**については、このポイントを入力します。 最も古いものこのポイントからで線を描画**直前**または`MoveTo`ポイントです。  
  
     このフラグは、 **PT_LINETO**型または行の場合、 **PT_BEZIERTO**種類のビットごとのベジエ スプラインを終点`OR`演算子。 現在の位置は、閉じた直線の終点に設定されます。  
  
 `nCount`  
 内の地点の合計数を指定、`lpPoints`のバイト数と同じ配列、`lpTypes`配列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用してを連続して呼び出す代わりに分離された図を描画`CDC::MoveTo`、 `CDC::LineTo`、および`CDC::PolyBezierTo`メンバー関数。 線およびスプラインは、現在のペンを使用して描画し、数値が入力されていません。 呼び出しによって開始されたアクティブ パスがあるかどうか、`CDC::BeginPath`メンバー関数を`PolyDraw`パスに追加します。 含まれている点、`lpPoints`配列し、`lpTypes`各ポイントの一部であるかどうかを示す、 `CDC::MoveTo`、 `CDC::LineTo`、または**CDC::BezierTo**操作します。 図形を閉じることもできます。 この関数は、現在の位置を更新します。  
  
### <a name="example"></a>例  
  例を参照してください[cdc::beginpath](#beginpath)します。  
  
##  <a name="a-namepolygona--cdcpolygon"></a><a name="polygon"></a>CDC::Polygon  
 2 つ以上の点 (頂点)、現在のペンを使用して、線で接続されているので構成される多角形を描画します。  
  
```  
BOOL Polygon(
    LPPOINT lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 多角形の頂点を指定する点の配列を指します。 配列内の各ポイントは、**ポイント**構造体、または`CPoint`オブジェクトです。  
  
 `nCount`  
 配列では、頂点の数を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 システム多角形自動的に閉じます、必要に応じて、最初最後の頂点から線が描画します。  
  
 現在の多角形の塗りつぶしモードを取得または設定を使用して、`GetPolyFillMode`と`SetPolyFillMode`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&38;](../../mfc/codesnippet/cpp/cdc-class_10.cpp)]  
  
##  <a name="a-namepolylinea--cdcpolyline"></a><a name="polyline"></a>CDC::Polyline  
 一連の指定された点を結ぶ線分を描画`lpPoints`します。  
  
```  
BOOL Polyline(
    LPPOINT lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す**ポイント**構造体または`CPoint`接続されているオブジェクト。  
  
 `nCount`  
 配列内の地点の数を指定します。 この値は、少なくとも 2 を指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 現在のペンを使用して後続のポイントを最初の点から、線が描画されます。 異なり、`LineTo`メンバー関数の場合、`Polyline`関数で使用しても、現在の位置を更新します。  
  
 詳細については、次を参照してください。[ポリライン](http://msdn.microsoft.com/library/windows/desktop/dd162815)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namepolylinetoa--cdcpolylineto"></a><a name="polylineto"></a>CDC::PolylineTo  
 1 つまたは複数の直線を描画します。  
  
```  
BOOL PolylineTo(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す[ポイント](../../mfc/reference/point-structure1.md)行の頂点を格納するデータ構造体。  
  
 `nCount`  
 配列内の地点の数を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された最初のポイントに現在の位置からで線を描画、`lpPoints`現在のペンを使用してパラメーター。 以降の各行の関数から描画前の行の終了位置で指定された次の点に`lpPoints`します。 `PolylineTo`現在の位置を最後の行の終了位置に移動します。 この関数によって描画される直線セグメントでは、閉じた図形をフォームの場合の図は表示されません。  
  
##  <a name="a-namepolypolygona--cdcpolypolygon"></a><a name="polypolygon"></a>CDC::PolyPolygon  
 現在の多角形の塗りつぶしモードで埋められた&2; つ以上の多角形を作成します。  
  
```  
BOOL PolyPolygon(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す**ポイント**構造体または`CPoint`多角形の頂点を定義するオブジェクト。  
  
 `lpPolyCounts`  
 整数の配列へのポインターをそれぞれ指定するポイント数の多角形のいずれかで、`lpPoints`配列。  
  
 `nCount`  
 エントリの数、`lpPolyCounts`配列。 この番号は、描画する多角形の番号を指定します。 この値は、少なくとも 2 を指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 多角形は、分離された、または重複する可能性があります。  
  
 呼び出しで指定された各多角形、`PolyPolygon`関数を閉じる必要があります。 によって作成された多角形とは異なり、**多角形**メンバー関数、多角形のによって作成された`PolyPolygon`自動的に閉じられません。  
  
 この関数では、2 つ以上の多角形を作成します。 単一の多角形を作成するアプリケーションを使用する必要があります、**多角形**メンバー関数。  
  
 現在の多角形の塗りつぶしモードを取得または設定を使用して、`GetPolyFillMode`と`SetPolyFillMode`メンバー関数。  
  
##  <a name="a-namepolypolylinea--cdcpolypolyline"></a><a name="polypolyline"></a>CDC::PolyPolyline  
 接続されている直線セグメントの複数の系列を描画します。  
  
```  
BOOL PolyPolyline(
    const POINT* lpPoints,  
    const DWORD* lpPolyPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 ポリラインの頂点を格納する構造体の配列を指します。 ポリラインが連続的に指定します。  
  
 `lpPolyPoints`  
 内の地点の数を指定する変数の配列を指す、`lpPoints`対応する多角形の配列。 各エントリは、2 以上にする必要があります。  
  
 `nCount`  
 カウントの合計数を指定、`lpPolyPoints`配列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 直線セグメントは、現在のペンを使用して描画されます。 セグメントによって形成される図形は塗りつぶされません。 現在の位置が使用も、この関数で更新します。  
  
##  <a name="a-nameptvisiblea--cdcptvisible"></a><a name="ptvisible"></a>CDC::PtVisible  
 指定したポイントをデバイス コンテキストのクリッピング領域内にあるかどうかを判断します。  
  
```  
virtual BOOL PtVisible(
    int x,  
    int y) const;  
  
BOOL PtVisible(POINT point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ポイントの論理 x 座標を指定します。  
  
 *y*  
 ポイントの論理 y 座標を指定します。  
  
 `point`  
 論理座標で確認するためのポイントを指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントがクリップ領域内にある場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-namequeryaborta--cdcqueryabort"></a><a name="queryabort"></a>CDC::QueryAbort  
 インストールされているアボート関数を呼び出し、 [SetAbortProc](#setabortproc)印刷を終了するかどうかに、印刷アプリケーションとクエリのメンバー関数。  
  
```  
BOOL QueryAbort() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷を続行する場合、または中止プロシージャがない場合は&0; 以外を返します。 印刷ジョブを終了する場合は 0 になります。 戻り値は、アボート関数によって提供されます。  
  
##  <a name="a-namerealizepalettea--cdcrealizepalette"></a><a name="realizepalette"></a>:Realizepalette  
 現在の論理パレットからシステム パレット エントリにマップします。  
  
```  
UINT RealizePalette();
```  
  
### <a name="return-value"></a>戻り値  
 論理パレットのエントリの数は、システム パレット内の異なるエントリにマップされたことを示します。 これは、この関数は、システム パレット内の変更に対応する論理パレットが最後に実現されたために再マップ エントリの数を表します。  
  
### <a name="remarks"></a>コメント  
 論理カラー パレットは、他のウィンドウに表示される色または色集中型アプリケーションと、アプリケーションは、表示される色を独自に干渉することがなく、必要に応じて多くの色を使用することにより、システムの間のバッファーとして機能します。  
  
 ウィンドウが入力フォーカスと呼び出しの場合に`RealizePalette`、Windows により、すべての要求された色、画面に同時に使用できる最大数に達するまで、ウィンドウに表示されます。 Windows では、使用可能な色に一致するによって、ウィンドウのパレットで見つからない色も表示されます。  
  
 さらに、Windows では、非アクティブなウィンドウの色に使用できる限り近くに、関数を呼び出すことによって要求された色と一致します。 これにより、非アクティブなウィンドウに表示される色の望ましくない変更が大幅に減少します。  
  
##  <a name="a-namerectanglea--cdcrectangle"></a><a name="rectangle"></a>CDC::Rectangle  
 現在のペンを使用して四角形を描画します。  
  
```  
BOOL Rectangle(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
BOOL Rectangle(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 (論理単位で) に四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 (論理単位で) に四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 (論理単位で) に四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 (論理単位で) に四角形の右下隅の y 座標を指定します。  
  
 `lpRect`  
 論理ユニットの四角形を指定します。 いずれかを渡すことができます、`CRect`オブジェクトまたはへのポインター、`RECT`このパラメーターの構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 四角形の内部は、現在のブラシを使用して入力されます。  
  
 四角形まで拡張は含まれません、右下隅の座標。 つまり、四角形の高さが`y2`– `y1` 、四角形の幅は`x2`–`x1`します。 四角形の高さと幅の両方に 2 つのユニットより大きくより小さい 32,767 の単位を使用する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#39;](../../mfc/codesnippet/cpp/cdc-class_11.cpp)]  
  
##  <a name="a-namerectvisiblea--cdcrectvisible"></a><a name="rectvisible"></a>CDC::RectVisible  
 ディスプレイ コンテキストのクリッピング領域内で指定された四角形の任意の部分があるかどうかを決定します。  
  
```  
virtual BOOL RectVisible(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`RECT`構造体、または`CRect`指定された四角形の論理座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 指定した四角形の任意の部分がクリップ領域内にある場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-namereleaseattribdca--cdcreleaseattribdc"></a><a name="releaseattribdc"></a>CDC::ReleaseAttribDC  
 設定するには、このメンバー関数を呼び出す`m_hAttribDC`に**NULL**します。  
  
```  
virtual void ReleaseAttribDC();
```  
  
### <a name="remarks"></a>コメント  
 これは、タスクは失敗しません、**デタッチ**が発生します。 出力デバイス コンテキストのみが接続されている、`CDC`オブジェクト、およびそののみをデタッチできます。  
  
##  <a name="a-namereleaseoutputdca--cdcreleaseoutputdc"></a><a name="releaseoutputdc"></a>CDC::ReleaseOutputDC  
 設定するには、このメンバー関数を呼び出す、`m_hDC`メンバー **NULL**します。  
  
```  
virtual void ReleaseOutputDC();
```  
  
### <a name="remarks"></a>コメント  
 出力デバイス コンテキストが関連付けられている場合、このメンバー関数を呼び出すことができない、`CDC`オブジェクトです。 使用して、**デタッチ**出力デバイス コンテキストを切断するメンバー関数。  
  
##  <a name="a-nameresetdca--cdcresetdc"></a><a name="resetdc"></a>CDC::ResetDC  
 ラップされたデバイス コンテキストを更新するには、このメンバー関数を呼び出す、`CDC`オブジェクトです。  
  
```  
BOOL ResetDC(const DEVMODE* lpDevMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDevMode*  
 Windows へのポインター`DEVMODE`構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストは、Windows の情報から更新`DEVMODE`構造体。 このメンバー関数は、属性のデバイス コンテキストのみをリセットします。  
  
 アプリケーションは通常使用して、`ResetDC`ウィンドウを処理するときに、メンバー関数、`WM_DEVMODECHANGE`メッセージです。 ドキュメントの印刷中に、用紙の向きまたは用紙トレイを変更するのに、このメンバー関数を使用することもできます。  
  
 このメンバー関数を使用すると、ドライバー名、デバイス名を変更または、ポートを出力することはできません。 ユーザーがポートの接続またはデバイスの名前を変更するときは、元デバイス コンテキストを削除しての最新情報を新しいデバイス コンテキストを作成する必要があります。  
  
 このメンバー関数を呼び出す前に、アウト デバイス コンテキストに選択されている必要がある (ストック オブジェクト以外のすべてのオブジェクトが選択されていることを確認する必要があります。  
  
##  <a name="a-namerestoredca--cdcrestoredc"></a><a name="restoredc"></a>CDC::RestoreDC  
 デバイス コンテキストで識別される前の状態に復元され`nSavedDC`します。  
  
```  
virtual BOOL RestoreDC(int nSavedDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSavedDC`  
 復元するデバイス コンテキストを指定します。 指定できる値の直前`SaveDC`関数の呼び出しです。 場合`nSavedDC`-1 で、最も最近保存したデバイス コンテキストを復元します。  
  
### <a name="return-value"></a>戻り値  
 指定したコンテキストが復元された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `RestoreDC`状態情報を前の呼び出しで作成したスタックからポップすることで、デバイス コンテキストをリストア、`SaveDC`メンバー関数。  
  
 スタックには、複数のデバイス コンテキストの状態情報を含めることができます。 コンテキストが指定された場合`nSavedDC`、スタックの最上部ではない`RestoreDC`が指定したデバイス コンテキスト間のすべての状態情報を削除`nSavedDC`とスタックの上部とします。 削除済みの情報は失われます。  
  
##  <a name="a-nameroundrecta--cdcroundrect"></a><a name="roundrect"></a>CDC::RoundRect  
 現在のペンを使用して角の丸い四角形を描画します。  
  
```  
BOOL RoundRect(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);

 
BOOL RoundRect(
    LPCRECT lpRect,
    POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 (論理単位で) に四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 (論理単位で) に四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 (論理単位で) に四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 (論理単位で) に四角形の右下隅の y 座標を指定します。  
  
 *x3*  
 (論理単位で) 角の丸い角の描画に使用する楕円の幅を指定します。  
  
 `y3`  
 (論理単位で) 角の丸い角の描画に使用する楕円の高さを指定します。  
  
 `lpRect`  
 論理ユニットの外接する四角形を指定します。 いずれかを渡すことができます、`CRect`オブジェクトまたはへのポインター、`RECT`このパラメーターの構造体。  
  
 `point`  
 X 座標`point`(論理単位で) 丸い角の描画を楕円の幅を指定します。 Y 座標`point`(論理単位で) 角の丸い角の描画に省略記号の高さを指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 四角形の内部は、現在のブラシを使用して入力されます。  
  
 この関数は描画の図は、まで拡張が、右下隅の座標は含まれません。 つまり、figure の高さは`y2`– `y1` 、figure の幅は`x2`–`x1`します。 外接する四角形の幅と高さは共には、2 つのユニットより大きく、32,767 より小さい単位である必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&40;](../../mfc/codesnippet/cpp/cdc-class_12.cpp)]  
  
##  <a name="a-namesavedca--cdcsavedc"></a><a name="savedc"></a>CDC::SaveDC  
 Windows で管理されているコンテキスト スタックに (クリッピング領域、選択したオブジェクトのマッピング モードなど) の状態情報をコピーして、デバイス コンテキストの現在の状態を保存します。  
  
```  
virtual int SaveDC();
```  
  
### <a name="return-value"></a>戻り値  
 保存されているデバイス コンテキストを識別する整数。 エラーが発生した場合は 0 になります。 これは、値を呼び出すことによって、デバイス コンテキストを復元するために使用できますが返される`RestoreDC`です。  
  
### <a name="remarks"></a>コメント  
 保存されているデバイス コンテキストを使用して後で復元する`RestoreDC`です。  
  
 `SaveDC`何回でも任意の数のデバイス コンテキストの状態を保存するために使用します。  
  
##  <a name="a-namescaleviewportexta--cdcscaleviewportext"></a><a name="scaleviewportext"></a>CDC::ScaleViewportExt  
 現在の値を基準としたビューポートの範囲を変更します。  
  
```  
virtual CSize ScaleViewportExt(
    int xNum,  
    int xDenom,  
    int yNum,  
    int yDenom);
```  
  
### <a name="parameters"></a>パラメーター  
 `xNum`  
 現在の x 範囲を乗算する量を指定します。  
  
 `xDenom`  
 値によって現在の x 範囲を乗算した結果を除算する量を指定、`xNum`パラメーター。  
  
 `yNum`  
 現在の y 範囲を乗算する量を指定します。  
  
 `yDenom`  
 値によって現在 y 範囲を乗算した結果を除算する量を指定、`yNum`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 前のビューポートの範囲が (デバイス単位) として、`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 数式は次のように書き込まれます。  
  
 `xNewVE = ( xOldVE * xNum ) / xDenom`  
  
 `yNewVE = ( yOldVE * yNum ) / yDenom`  
  
 新しいビューポートの範囲は、現在の範囲指定された分子を乗算し、指定された分母で割ることによって計算されます。  
  
##  <a name="a-namescalewindowexta--cdcscalewindowext"></a><a name="scalewindowext"></a>CDC::ScaleWindowExt  
 現在の値を基準としたウィンドウの範囲を変更します。  
  
```  
virtual CSize ScaleWindowExt(
    int xNum,  
    int xDenom,  
    int yNum,  
    int yDenom);
```  
  
### <a name="parameters"></a>パラメーター  
 `xNum`  
 現在の x 範囲を乗算する量を指定します。  
  
 `xDenom`  
 値によって現在の x 範囲を乗算した結果を除算する量を指定、`xNum`パラメーター。  
  
 `yNum`  
 現在の y 範囲を乗算する量を指定します。  
  
 `yDenom`  
 値によって現在 y 範囲を乗算した結果を除算する量を指定、`yNum`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 前のウィンドウの範囲が (論理単位で) として、`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 数式は次のように書き込まれます。  
  
 `xNewWE = ( xOldWE * xNum ) / xDenom`  
  
 `yNewWE = ( yOldWE * yNum ) / yDenom`  
  
 新しいウィンドウの範囲は、現在の範囲指定された分子を乗算し、指定された分母で割ることによって計算されます。  
  
##  <a name="a-namescrolldca--cdcscrolldc"></a><a name="scrolldc"></a>CDC::ScrollDC  
 水平方向および垂直方向には、bits の四角形をスクロールします。  
  
```  
BOOL ScrollDC(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* pRgnUpdate,  
    LPRECT lpRectUpdate);
```  
  
### <a name="parameters"></a>パラメーター  
 `dx`  
 水平スクロールの単位の数を指定します。  
  
 *dy*  
 垂直スクロール ユニットの数を指定します。  
  
 `lpRectScroll`  
 指す、`RECT`構造または`CRect`スクロールの四角形の座標を格納しているオブジェクト。  
  
 `lpRectClip`  
 指す、`RECT`構造または`CRect`クリッピング四角形の座標を格納しているオブジェクト。 この四角形が&1; つが指す元よりも小さい場合`lpRectScroll`、スクロール、小さい四角形でだけ行われます。  
  
 `pRgnUpdate`  
 スクロールのプロセスで検出された領域を識別します。 `ScrollDC`関数は、この領域を定義はこれとは限りません四角形。  
  
 `lpRectUpdate`  
 指す、`RECT`構造または`CRect`スクロール更新領域に外接する四角形の座標を受け取るオブジェクト。 これは、再描画が必要な最大の四角形の領域です。 構造体またはオブジェクトを返す、関数の値は、指定したデバイス コンテキストのマッピング モードに関係なく、クライアント座標のです。  
  
### <a name="return-value"></a>戻り値  
 スクロールを実行した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`lpRectUpdate`は**NULL**Windows では、更新の四角形は計算されません。 両方`pRgnUpdate`と`lpRectUpdate`は**NULL**Windows は更新領域を計算しません。 場合`pRgnUpdate`は**NULL**、スクロールのプロセスで検出された領域への有効なポインターが含まれていると見なされます (によって定義された、`ScrollDC`メンバー関数)。 返される更新領域`lpRectUpdate`に渡すことが`CWnd::InvalidateRgn`のために必要な場合です。  
  
 アプリケーションを使用する必要があります、`ScrollWindow`クラスのメンバー関数`CWnd`ウィンドウのクライアント全体の領域をスクロールする必要がある場合。 それ以外の場合、それを使用する必要があります`ScrollDC`します。  
  
##  <a name="a-nameselectclippatha--cdcselectclippath"></a><a name="selectclippath"></a>CDC::SelectClipPath  
 指定のモードを使用して、既存のクリッピング領域で新しい地域を結合したデバイス コンテキストのクリッピング領域として、現在のパスを選択します。  
  
```  
BOOL SelectClipPath(int nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMode`  
 パスを使用する方法を指定します。 次の値は使用できます。  
  
- **RGN_AND**新しいクリッピング領域には、現在のクリップ領域と現在のパスの交差 (重なり合っている範囲) が含まれています。  
  
- **RGN_COPY**新しいクリップ領域は、現在のパス。  
  
- **RGN_DIFF**新しいクリッピング領域には、現在のクリップ領域の領域が含まれています。 され、現在のパスの除外されます。  
  
- **RGN_OR**新しいクリッピング領域には、現在のクリップ領域と現在のパスの和集合 (合計の領域) が含まれています。  
  
- **RGN_XOR**新しいクリップ領域には、現在のクリップ領域と現在のパスが、重複する領域の共用体が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 特定のデバイス コンテキストでは、閉じたパスを含める必要があります。  
  
##  <a name="a-nameselectcliprgna--cdcselectcliprgn"></a><a name="selectcliprgn"></a>CDC::SelectClipRgn  
 デバイス コンテキストの現在のクリップ領域として指定された領域を選択します。  
  
```  
int SelectClipRgn(CRgn* pRgn);

 
int SelectClipRgn(
    CRgn* pRgn,  
    int nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 選択される領域を識別します。  
  
-   この値がある場合、この関数の最初のバージョンの**NULL**、クライアント領域全体が選択されているし、出力は、ウィンドウにはクリップされます。  
  
-   この関数の&2; つ目のバージョンについては、このハンドルができる**NULL**される場合にのみ、 **RGN_COPY**モードを指定します。  
  
 `nMode`  
 実行する操作を指定します。 次の値のいずれかを指定する必要があります。  
  
- **RGN_AND**新しいクリップ領域が現在のクリップ領域とによって識別される領域の重複する領域を組み合わせて`pRgn`します。  
  
- **RGN_COPY**で識別される領域のコピーである新しいクリップ領域`pRgn`します。 これは、機能の最初のバージョンと同じ`SelectClipRgn`します。 リージョンがで識別される場合`pRgn`は**NULL**、クリッピング領域を新しい既定のクリッピング領域 (null リージョン) になります。  
  
- **RGN_DIFF**新しいクリップ領域は、現在のクリッピング領域で結合によって識別される領域から除外した領域`pRgn`します。  
  
- **RGN_OR**新しいクリップ領域は、現在のクリップ領域とによって識別される領域を組み合わせた`pRgn`します。  
  
- **RGN_XOR**新しいクリップ領域は、現在のクリップ領域とによって識別される領域を組み合わせた`pRgn`は、重複する領域を除外します。  
  
### <a name="return-value"></a>戻り値  
 領域の型。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**新しいクリップ領域は、重なり合った境界線。  
  
- **エラー**デバイス コンテキストまたは地域が無効です。  
  
- **NULLREGION**新しいクリップ領域が空です。  
  
- **SIMPLEREGION**新しいクリップ領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 選択された領域のコピーのみが使用されます。 その他のデバイス コンテキストのような領域自体を選択するか、削除することができます。  
  
 関数は、指定された領域の座標がデバイス単位で指定されていると仮定します。 一部のプリンター デバイスは、テキスト メトリックを表現するために必要な正確さを保持するために、グラフィックスの出力より高い解像度のテキスト出力をサポートします。 これらのデバイスは、テキスト単位より高い解像度でデバイス単位を報告します。 デバイス単位のマップを 1 つだけのグラフィック単位に報告いくつかのようにするため、これらのデバイスはグラフィックスの座標をし、スケールします。 常に呼び出す、`SelectClipRgn`テキスト単位を使用して機能します。  
  
 GDI でグラフィックス オブジェクトのスケーリングを行う必要のあるアプリケーションを使用できます、 **GETSCALINGFACTOR**プリンター エスケープされたスケール ファクターを決定します。 このスケール ファクターでは、クリッピングに影響します。 グラフィックスをクリップ領域を使用すると、GDI はスケール ファクターで座標を除算します。 テキストをクリップ領域を使用する場合は、GDI にスケール調整はありません。 スケール係数として 1 と 2 で除算する座標スケール ファクターは 2 と 4 で除算する座標などなど。  
  
##  <a name="a-nameselectobjecta--cdcselectobject"></a><a name="selectobject"></a>:Selectobject  
 デバイス コンテキストにオブジェクトを選択します。  
  
```  
CPen* SelectObject(CPen* pPen);  
CBrush* SelectObject(CBrush* pBrush);  
virtual CFont* SelectObject(CFont* pFont);  
CBitmap* SelectObject(CBitmap* pBitmap);  
int SelectObject(CRgn* pRgn);  
CGdiObject* SelectObject(CGdiObject* pObject);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPen*  
 ポインター、 [CPen](../../mfc/reference/cpen-class.md)を選択するオブジェクト。  
  
 `pBrush`  
 ポインター、 [CBrush](../../mfc/reference/cbrush-class.md)を選択するオブジェクト。  
  
 `pFont`  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)を選択するオブジェクト。  
  
 `pBitmap`  
 ポインター、 [CBitmap](../../mfc/reference/cbitmap-class.md)を選択するオブジェクト。  
  
 `pRgn`  
 ポインター、 [CRgn](../../mfc/reference/crgn-class.md)を選択するオブジェクト。  
  
 `pObject`  
 ポインター、 [CGdiObject](../../mfc/reference/cgdiobject-class.md)を選択するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 置き換えられるオブジェクトへのポインター。 これから派生したクラスのいずれかのオブジェクトへのポインター`CGdiObject`など`CPen`使用される関数のバージョンによって異なります。 戻り値は**NULL**場合はエラーが発生します。 この関数は、一時オブジェクトにポインターを返す可能性があります。 この一時オブジェクトは&1; つの Windows メッセージの処理中にのみ有効です。 詳細については、「`CGdiObject::FromHandle`」を参照してください。  
  
 地域のパラメーターを受け取るメンバー関数のバージョンと同じタスクを実行する、`SelectClipRgn`メンバー関数。 その戻り値は、次のいずれかになります。  
  
- **COMPLEXREGION**新しいクリップ領域は、重なり合った境界線。  
  
- **エラー**デバイス コンテキストまたは地域が無効です。  
  
- **NULLREGION**新しいクリップ領域が空です。  
  
- **SIMPLEREGION**新しいクリップ領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 クラス`CDC`GDI オブジェクト、ペン、ブラシ、フォント、ビットマップ、および地域などの特定の種類に特化した&5; つのバージョンを提供します。 新しく選択されたオブジェクトには、同じ型の前のオブジェクトが置き換えられます。 たとえば場合、`pObject`の一般的なバージョンの`SelectObject`を指す、 [CPen](../../mfc/reference/cpen-class.md)オブジェクト、関数で指定されたペンを使用して、現在のペンを置き換えます`pObject`します。  
  
 アプリケーションを選択、ビットマップ メモリ デバイス コンテキストにのみデバイス コンテキストの&1; つだけのメモリに一度に。 モノクロまたはデバイス コンテキスト; と互換性のあるビットマップの形式でなければなりませんない場合は、`SelectObject`エラーが返されます。  
  
 Windows 3.1 以降の`SelectObject`かメタファイルで使用されているかどうか、関数が同じ値を返します。 以前のバージョンの Windows で `SelectObject`メタファイルで使用した場合の成功は 0 以外の値とエラーの場合は 0 が返されます。  
  
##  <a name="a-nameselectpalettea--cdcselectpalette"></a><a name="selectpalette"></a>CDC::SelectPalette  
 指定されている論理パレットを選択`pPalette`デバイス コンテキストのパレットを選択したオブジェクトとして。  
  
```  
CPalette* SelectPalette(
    CPalette* pPalette,  
    BOOL bForceBackground);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPalette`  
 選択する論理パレットを識別します。 このパレット必要がありますがで既に作成されて、`CPalette`メンバー関数[CreatePalette](../../mfc/reference/cpalette-class.md#createpalette)します。  
  
 `bForceBackground`  
 論理パレットがパレットに強制するかどうかを指定します。 場合`bForceBackground`は&0; 以外の値を選択されたパレットは常にウィンドウ入力フォーカスがあるかどうかに関係なく、バック グラウンド パレット。 場合`bForceBackground`は 0 とデバイス コンテキストがウィンドウに接続されている、ウィンドウに入力フォーカスがあるときに、論理パレットがフォア グラウンド パレットです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`オブジェクトで指定されたパレットに置き換え、論理パレットを識別する`pPalette`です。 **NULL**場合はエラーが発生します。  
  
### <a name="remarks"></a>コメント  
 新しいパレットは、GDI のデバイス コンテキストで表示される色を管理するために使用するパレット オブジェクトになり、前のパレットを置き換えます。  
  
 アプリケーションでは、1 つ以上のデバイス コンテキストに論理パレットを選択できます。 論理パレットの変更が選択されているすべてのデバイス コンテキストでは影響します。 アプリケーションでは、1 つ以上のデバイス コンテキストにパレットを選択した場合、デバイス コンテキスト必要がありますすべてに属している同じ物理デバイス。  
  
##  <a name="a-nameselectstockobjecta--cdcselectstockobject"></a><a name="selectstockobject"></a>CDC::SelectStockObject  
 選択、 [CGdiObject](../../mfc/reference/cgdiobject-class.md)組み込みのストック ペン、ブラシ、フォントのいずれかに対応するオブジェクト。  
  
```  
virtual CGdiObject* SelectStockObject(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 必要に応じてストックのオブジェクトの種類を指定します。 次の値のいずれかを指定できます。  
  
- **BLACK_BRUSH**黒のブラシ。  
  
- **DKGRAY_BRUSH**濃い灰色のブラシ。  
  
- **GRAY_BRUSH**灰色のブラシ。  
  
- **HOLLOW_BRUSH**白抜きのブラシ。  
  
- **LTGRAY_BRUSH**薄い灰色のブラシ。  
  
- **NULL_BRUSH**ブラシは Null です。  
  
- **WHITE_BRUSH**白のブラシ。  
  
- **BLACK_PEN**黒のペンです。  
  
- **NULL_PEN** Null ペンです。  
  
- **WHITE_PEN**白のペンです。  
  
- **ANSI_FIXED_FONT** ANSI 固定システム フォント。  
  
- **ANSI_VAR_FONT** ANSI 変数システム フォント。  
  
- **DEVICE_DEFAULT_FONT**デバイスに依存するフォントです。  
  
- **OEM_FIXED_FONT** OEM に依存するフォントを固定します。  
  
- **SYSTEM_FONT**システム フォント。 既定では、Windows は、メニューのダイアログ ボックス コントロールおよびその他のテキストを描画するのに、システム フォントを使用します。 ただし、ダイアログと windows で使用されるフォントを取得する SYSTEM_FONT に依存しないように、最適なです。 代わりに、使用、`SystemParametersInfo`関数を現在のフォントを取得する SPI_GETNONCLIENTMETRICS パラメーターを使用します。 `SystemParametersInfo`現在のテーマを考慮し、キャプション、メニューのおよびメッセージのダイアログ ボックスのフォントの情報を提供します。  
  
- **SYSTEM_FIXED_FONT**バージョン 3.0 より前の Windows で使用するシステムの固定幅フォント。 このオブジェクトは、Windows の旧バージョンと互換性のために使用します。  
  
- **DEFAULT_PALETTE**既定の色パレット。 このパレットは、システム パレットの 20 の静的な色で構成されます。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CGdiObject`関数が成功した場合、置き換えられたオブジェクト。 示される実際のオブジェクトが、 [CPen](../../mfc/reference/cpen-class.md)、 [CBrush](../../mfc/reference/cbrush-class.md)、または[CFont](../../mfc/reference/cfont-class.md)オブジェクトです。 呼び出しが成功しなかった場合、戻り値は**NULL**します。  
  
##  <a name="a-namesetabortproca--cdcsetabortproc"></a><a name="setabortproc"></a>Cdc::setabortproc  
 印刷ジョブのアボート プロシージャをインストールします。  
  
```  
int SetAbortProc(BOOL (CALLBACK* lpfn)(HDC, int));
```  
  
### <a name="parameters"></a>パラメーター  
 `lpfn`  
 Abort 手順としてインストールするアボート関数へのポインター。 詳細については、コールバック関数は、次を参照してください。 [cdc::setabortproc 用コールバック関数](../../mfc/reference/callback-function-for-cdc-setabortproc.md)します。  
  
### <a name="return-value"></a>戻り値  
 結果を示す、`SetAbortProc`関数です。 次の値の一部は、他よりも該当する可能性がすべて可能です。  
  
- **SP_ERROR**一般的なエラーです。  
  
- **させることでより**のに十分なディスク領域は、スプールのため現在使用して、空き領域がないが使用可能になります。  
  
- **SP_OUTOFMEMORY**スプールのためのに十分なメモリがあります。  
  
- **SP_USERABORT**ユーザーが印刷マネージャーを使ってジョブを終了します。  
  
### <a name="remarks"></a>コメント  
 印刷ジョブを開始する前に、アボート関数を設定する必要がありますいるスプール中に取り消されるようにする印刷ジョブを許可するようにアプリケーションがある場合、 [StartDoc](#startdoc)メンバー関数。 印刷マネージャーでは、印刷ジョブをキャンセルする、またはディスク領域の状態を処理するアプリケーションを許可するようにスプール中に中止関数を呼び出します。 Abort 関数が設定されていない場合、スプールのための十分なディスク領域がない場合、印刷ジョブは失敗します。  
  
 Microsoft Visual C の機能に渡されるコールバック関数の作成を単純化ことに注意してください`SetAbortProc`します。 渡されるアドレス、`EnumObjects`メンバー関数を使用してエクスポート関数へのポインターは、**方式**を使用して、`__stdcall`呼び出し規約です。  
  
 またがありません 関数名をエクスポートする、**エクスポート**アプリケーションのモジュール定義ファイル内のステートメントです。 代わりに使用することができます、**エクスポート**としての関数の修飾子は、  
  
 **BOOL コールバック エクスポート**関数 ( **HDC**、 `int` **) です。**  
  
 エイリアスの名前をエクスポートの適切なエクスポート レコードを生成するコンパイラは、です。 これは、ほとんどのニーズに対して機能します。 特殊ななど、状況によって ordinal またはエイリアスをエクスポートして関数をエクスポートする必要がありますを使用する、**エクスポート**モジュール定義ファイル内のステートメントです。  
  
 登録のコールバック インターフェイスがタイプ セーフではようになりました (特定のコールバック関数の適切なを指す関数ポインターに渡す必要があります)。  
  
 なお、すべてのコールバック関数がコールバックの境界を越えて例外がスローされることはできませんので、Windows に復帰する前に Microsoft Foundation 例外をトラップする必要があります。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
##  <a name="a-namesetarcdirectiona--cdcsetarcdirection"></a><a name="setarcdirection"></a>CDC::SetArcDirection  
 弧と四角形の関数に使用する描画方向を設定します。  
  
```  
int SetArcDirection(int nArcDirection);
```  
  
### <a name="parameters"></a>パラメーター  
 *nArcDirection*  
 新しい円弧の方向を指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **AD_COUNTERCLOCKWISE**図形を反時計回りに描画します。  
  
- **AD_CLOCKWISE**図形を時計回りに描画します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、古い円弧の方向を指定します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の方向は反時計回りに回転します。 `SetArcDirection`関数は、次の関数は描画する方向を指定します。  
  
|円弧|円グラフ|  
|---------|---------|  
|`ArcTo`|**四角形**|  
|`Chord`|`RoundRect`|  
|**楕円**||  
  
##  <a name="a-namesetattribdca--cdcsetattribdc"></a><a name="setattribdc"></a>CDC::SetAttribDC  
 属性のデバイス コンテキストを設定するには、この関数を呼び出す`m_hAttribDC`します。  
  
```  
virtual void SetAttribDC(HDC hDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 Windows のデバイス コンテキスト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数では、デバイス コンテキストを関連付けられていない、`CDC`オブジェクトです。 出力デバイス コンテキストのみが接続されている、`CDC`オブジェクトです。  
  
##  <a name="a-namesetbkcolora--cdcsetbkcolor"></a><a name="setbkcolor"></a>CDC::SetBkColor  
 現在の背景色を指定した色に設定します。  
  
```  
virtual COLORREF SetBkColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 新しい背景色を指定します。  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値として前の背景色です。 エラーが発生する場合は、0x80000000 を返します。  
  
### <a name="remarks"></a>コメント  
 バック グラウンド モードの場合**不透明**システムでは、背景色を使用して、スタイル設定された行のギャップ、ハッチ ブラシ、行と文字セルの背景のギャップを入力します。 システムでは、色とモノクロのデバイス コンテキストのビットマップを変換するときに背景色も使用します。  
  
 デバイスが指定した色を表示できない場合、システムは、背景色を最も近いの物理的な色に設定します。  
  
##  <a name="a-namesetbkmodea--cdcsetbkmode"></a><a name="setbkmode"></a>CDC::SetBkMode  
 バック グラウンド モードを設定します。  
  
```  
int SetBkMode(int nBkMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBkMode*  
 設定するのには、モードを指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **不透明な**テキスト、ハッチ ブラシの前に、現在の背景色と背景を塗りつぶすまたはペンを描画します。 これは、既定のバック グラウンド モードです。  
  
- **透過的な**背景が描画前に変更されていません。  
  
### <a name="return-value"></a>戻り値  
 前のバック グラウンド モード。  
  
### <a name="remarks"></a>コメント  
 バック グラウンド モードでは、システムがテキストやハッチ ブラシ、実線ではないペンのスタイルを描画する前に、描画サーフェイスの背景色を取り除くかどうかを定義します。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)します。  
  
##  <a name="a-namesetboundsrecta--cdcsetboundsrect"></a><a name="setboundsrect"></a>CDC::SetBoundsRect  
 指定したデバイス コンテキストの外接する四角情報の蓄積を制御します。  
  
```  
UINT SetBoundsRect(
    LPCRECT lpRectBounds,  
    UINT flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectBounds`  
 指す、`RECT`構造または`CRect`外接する四角形の設定に使用されるオブジェクト。 四角形の大きさは、論理座標で表されます。 このパラメーターを指定できます**NULL**します。  
  
 `flags`  
 蓄積された四角形を持つ新しい四角形の組み合わせる方法を指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- **DCB_ACCUMULATE**で指定された四角形を追加`lpRectBounds`(四角形の和集合操作を使用して) 外接する四角形にします。  
  
- **DCB_DISABLE**境界が蓄積されるをオフにします。  
  
- **DCB_ENABLE**境界の蓄積を有効にします。 (境界が蓄積される既定の設定は無効です。)  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、外接する四角の現在の状態。 ような`flags`、戻り値の組み合わせをできる**DCB_**値。  
  
- **DCB_ACCUMULATE**外接する四角形は空ではありません。 この値は常に設定します。  
  
- **DCB_DISABLE**境界が蓄積されるは無効になっています。  
  
- **DCB_ENABLE**に境界が蓄積されるは。  
  
### <a name="remarks"></a>コメント  
 Windows では、すべての描画操作の外接する四角形を維持できます。 この四角形のクエリを実行し、アプリケーションによってリセットできます。 描画の境界は、ビットマップのキャッシュを無効にします。  
  
##  <a name="a-namesetbrushorga--cdcsetbrushorg"></a><a name="setbrushorg"></a>CDC::SetBrushOrg  
 アプリケーションがデバイス コンテキストに選択したブラシの次に、GDI が割り当てるした元のドメインを指定します。  
  
```  
CPoint SetBrushOrg(
    int x,  
    int y);  
  
CPoint SetBrushOrg(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 オリジンの新規作成の (デバイス単位) の x 座標を指定します。 この値は、0 ~ 7 の範囲でなければなりません。  
  
 *y*  
 オリジンの新規作成の (デバイス単位) の y 座標を指定します。 この値は、0 ~ 7 の範囲でなければなりません。  
  
 `point`  
 オリジンの新規作成の x 座標と y 座標を指定します。 それぞれの値は、0 ~ 7 の範囲でなければなりません。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 デバイス単位でブラシの前の元です。  
  
### <a name="remarks"></a>コメント  
 既定値は、ブラシの原点の座標は (0, 0)。 ブラシの原点を変更するには、呼び出し、`UnrealizeObject`関数を`CBrush`オブジェクトを呼び出す必要が`SetBrushOrg`、しを呼び出す、`SelectObject`デバイス コンテキストにブラシを選択します。  
  
 使用しないで`SetBrushOrg`在庫と`CBrush`オブジェクトです。  
  
##  <a name="a-namesetcoloradjustmenta--cdcsetcoloradjustment"></a><a name="setcoloradjustment"></a>CDC::SetColorAdjustment  
 指定した値を使用してデバイス コンテキストの色の調整値を設定します。  
  
```  
BOOL SetColorAdjustment(const COLORADJUSTMENT* lpColorAdjust);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpColorAdjust`  
 指す、 [COLORADJUSTMENT](../../mfc/reference/coloradjustment-structure.md)色の調整値を含むデータ構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 色の調整値への呼び出しに元のビットマップの入力の色の調整を使用して、`CDC::StretchBlt`メンバー関数と**ハーフトーン**モードを設定します。  
  
##  <a name="a-namesetdcbrushcolora--cdcsetdcbrushcolor"></a><a name="setdcbrushcolor"></a>CDC::SetDCBrushColor  
 現在のデバイス コンテキスト (DC) ブラシの色を指定した色の値に設定します。  
  
```  
COLORREF SetDCBrushColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 新しいブラシの色を指定します。  
  
### <a name="return-value"></a>戻り値  
 戻り値として前の DC ブラシの色を指定する関数が成功した場合、`COLORREF`値。  
  
 戻り値は、関数が失敗した場合、`CLR_INVALID`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、関数の機能をエミュレート[SetDCBrushColor](http://msdn.microsoft.com/library/windows/desktop/dd162969)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetdcpencolora--cdcsetdcpencolor"></a><a name="setdcpencolor"></a>CDC::SetDCPenColor  
 現在のデバイス コンテキスト (DC) のペンの色を指定した色の値に設定します。  
  
```  
COLORREF SetDCPenColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 新しいペンの色を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数で Win32 関数[SetDCPenColor](http://msdn.microsoft.com/library/windows/desktop/dd162970)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetgraphicsmodea--cdcsetgraphicsmode"></a><a name="setgraphicsmode"></a>CDC::SetGraphicsMode  
 指定したデバイス コンテキストのグラフィックス モードを設定します。  
  
```  
int SetGraphicsMode(int iMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `iMode`  
 グラフィック モードを指定します。 このパラメーターに使用できる値の一覧は、次を参照してください。 [SetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd162977)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に、元のグラフィックス モードを返します。  
  
 失敗した場合は 0 を返します。 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメソッド[SetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd162977)します。  
  
##  <a name="a-namesetlayouta--cdcsetlayout"></a><a name="setlayout"></a>CDC::SetLayout  
 右から左、アラビア語やヘブライ語などのカルチャの標準のレイアウトにテキストとグラフィックス デバイス コンテキストのレイアウトを変更するには、このメンバー関数を呼び出します。  
  
```  
DWORD SetLayout(DWORD dwLayout);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwLayout`  
 デバイス コンテキストのレイアウトとビットマップは、フラグを制御します。 次の値の組み合わせを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|まず|呼び出しのために、リフレクションを無効に[ビットマップ](#bitblt)と[CDC::StretchBlt](#stretchblt)します。|  
|LAYOUT_RTL|右から左にある既定の水平レイアウトを設定します。|  
|LAYOUT_LTR|左右からに既定のレイアウトを設定します。|  
  
### <a name="return-value"></a>戻り値  
 成功した場合、デバイス コンテキストの直前のレイアウト。  
  
 失敗した場合は、 **GDI_ERROR**します。 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 通常、するとは呼ばれません**SetLayout**ウィンドウです。 設定して、ウィンドウで右から左のレイアウトを制御する代わりに、[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)など**WS_EX_RTLREADING**します。 プリンターや、メタファイルなどのデバイス コンテキストは、このレイアウトを継承していません。 右から左のレイアウトが呼び出すことによってですデバイス コンテキストを設定する唯一の方法**SetLayout**します。  
  
 呼び出した場合**SetLayout (LAYOUT_RTL** )、 **SetLayout**へのマッピング モードが自動的に変更`MM_ISOTROPIC`します。 その結果、後続の呼び出しに[この](#getmapmode)戻ります**MM_ISOTROPIC**の代わりに`MM_TEXT`します。  
  
 場合によってなど多くのビットマップを可能性があると左から右のレイアウトを保持します。 このような場合に、呼び出すことによって、イメージをレンダリング`BitBlt`または`StretchBlt`のビットマップ制御フラグを設定`dwLayout`に**まず**します。  
  
 レイアウトを変更すると、 **LAYOUT_RTL**フラグ、通常 権限を指定するフラグを設定または左が取り消されます。 混乱を避けるためには、標準のフラグの代替名を定義します。 推奨される代替フラグ名の一覧は、次を参照してください。 [SetLayout](http://msdn.microsoft.com/library/windows/desktop/dd162979)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetmapmodea--cdcsetmapmode"></a><a name="setmapmode"></a>CDC::SetMapMode  
 マップ モードを設定します。  
  
```  
virtual int SetMapMode(int nMapMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMapMode`  
 新しいマップ モードを指定します。 次の値のいずれかを指定できます。  
  
- `MM_ANISOTROPIC`論理ユニットは、任意にスケーリングされた軸を持つ任意の単位に変換されます。 マップ モードに設定`MM_ANISOTROPIC`現在のウィンドウまたはビュー ポートの設定は変更されません。 単位を変更するには、向き、およびスケーリングを呼び出す、[両](#setwindowext)と[される](#setviewportext)メンバー関数。  
  
- `MM_HIENGLISH`それぞれの論理ユニットは 0.001 インチに変換されます。 正の x が右側には正の y です。  
  
- `MM_HIMETRIC`それぞれの論理単位は 0.01 ミリメートルに変換されます。 正の x が右側には正の y です。  
  
- `MM_ISOTROPIC`論理ユニットが均等にスケーリングされた軸上で任意の単位に変換されます。x 軸に沿って 1 単位は、y 軸に沿って 1 単位と同じです。 使用して、`SetWindowExt`と`SetViewportExt`メンバー関数は、目的の単位と、軸の方向を指定します。 GDI は、調整を必要に応じて、ユニットが同じサイズのまま、x と y のことを確認します。  
  
- `MM_LOENGLISH`それぞれの論理単位は 0.01 インチに変換されます。 正の x が右側には正の y です。  
  
- `MM_LOMETRIC`それぞれの論理ユニットは、0.1 ミリメートルに変換されます。 正の x が右側には正の y です。  
  
- `MM_TEXT`それぞれの論理ユニットは、1 台のデバイスのピクセルに変換されます。 正の x が右側には正の y があります。  
  
- `MM_TWIPS`それぞれの論理ユニットは、点の 1 対 20 に変換されます。 (ポイントは 1/72 インチであるため、twip は 1/1440 インチ) です。正の x が右側には正の y です。  
  
### <a name="return-value"></a>戻り値  
 前のマッピング モード。  
  
### <a name="remarks"></a>コメント  
 マップ モードが論理ユニットをデバイス単位に変換するために使用する単位を定義します。また、デバイスの x 軸および y 軸の向きを定義します。 GDI は、適切なデバイス座標論理座標に変換するのにマップ モードを使用します。 `MM_TEXT`モードでは、アプリケーションがデバイス ピクセル単位で動作する 1 つの単位は 1 ピクセルです。 ピクセルの物理サイズでは、デバイスによって異なります。  
  
 `MM_HIENGLISH`、 `MM_HIMETRIC`、 `MM_LOENGLISH`、 `MM_LOMETRIC`、および`MM_TWIPS`モードが物理的に意味のある単位 (ミリメートルやインチ) などを描画する必要がありますアプリケーションに適しています。 `MM_ISOTROPIC`モードでは、1 対 1 の縦横比では、このは、イメージの正確な形状を保持する必要がある場合に便利です。 `MM_ANISOTROPIC`モードでは個別に調整する x 座標と y 座標。  
  
> [!NOTE]
>  呼び出した場合[SetLayout](#setlayout) DC (デバイス コンテキスト) を右から左のレイアウトに変更する**SetLayout**へのマッピング モードが自動的に変更`MM_ISOTROPIC`します。  
  
### <a name="example"></a>例  
  例を参照してください[付け](../../mfc/reference/cview-class.md#onpreparedc)します。  
  
##  <a name="a-namesetmapperflagsa--cdcsetmapperflags"></a><a name="setmapperflags"></a>CDC::SetMapperFlags  
 フォント マッパーの論理フォントを物理フォントに変換するときに使用する方法を変更します。  
  
```  
DWORD SetMapperFlags(DWORD dwFlag);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlag`  
 フォント マッパーがフォントの高さの比率とデバイスへの幅と一致させようとしたかどうかを指定します。 この値が**ASPECT_FILTERING**しが x 縦横フォントだけを選択して、マッパー y 縦横完全に一致する、指定されたデバイスのです。  
  
### <a name="return-value"></a>戻り値  
 フォント マッパー フラグの前の値。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで使用できる`SetMapperFlags`指定されたデバイスの縦横比と一致する物理フォントだけを選択しようとする、フォント マッパーが発生します。  
  
 ラスター フォントだけを使用するアプリケーションを使用して、`SetMapperFlags`フォント マッパーで選択されているフォントが魅力的で、指定されたデバイスで読み取り可能であることを確認します。 通常、拡張性の高い (TrueType) フォントを使用するアプリケーションは使用しないで`SetMapperFlags`します。  
  
 物理的なフォントの論理フォントの仕様に一致する縦横比がなければ、GDI が新しい縦横比を選択し、この新しい縦横比に一致するフォントを選択します。  
  
##  <a name="a-namesetmiterlimita--cdcsetmiterlimit"></a><a name="setmiterlimit"></a>CDC::SetMiterLimit  
 デバイス コンテキストのマイター結合の長さの制限を設定します。  
  
```  
BOOL SetMiterLimit(float fMiterLimit);
```  
  
### <a name="parameters"></a>パラメーター  
 *fMiterLimit*  
 デバイス コンテキストの新しいマイター リミットを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 角の長さは、外部結合の線の壁の交差部分に、結合の内側の線の壁の積集合からの距離として定義されます。 マイター リミットは、線の幅を角の長さの最大許容比率です。 既定のマイター リミットは、10.0 です。  
  
##  <a name="a-namesetoutputdca--cdcsetoutputdc"></a><a name="setoutputdc"></a>CDC::SetOutputDC  
 出力デバイス コンテキストを設定するには、このメンバー関数を呼び出す`m_hDC`します。  
  
```  
virtual void SetOutputDC(HDC hDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 Windows のデバイス コンテキスト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、デバイス コンテキストにアタッチされていない場合にのみ呼び出すことができる、`CDC`オブジェクトです。 このメンバー関数`m_hDC`デバイス コンテキストにアタッチされませんが、`CDC`オブジェクトです。  
  
##  <a name="a-namesetpixela--cdcsetpixel"></a><a name="setpixel"></a>CDC::SetPixel  
 指定された色の最も近い色を指定した位置にあるピクセル設定`crColor`します。  
  
```  
COLORREF SetPixel(
    int x,  
    int y,  
    COLORREF crColor);

 
COLORREF SetPixel(
    POINT point,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理で設定する点の x 座標を指定します。  
  
 *y*  
 論理で設定する点の y 座標を指定します。  
  
 `crColor`  
 A **COLORREF**点を描画するために使用する色を指定します RGB 値。 参照してください[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]この値の詳細についてです。  
  
 `point`  
 設定する点の論理 x 座標と y 座標を指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 ポイントが実際に描画する色の RGB 値。 この値が異なるによって指定されているものがあります`crColor`その色の概算値を使用する場合。 (ポイントがクリッピング領域の外側にある場合)、関数が失敗した場合は、–&1; を返します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、クリッピング領域にする必要があります。 クリッピング領域に、ポイントがない場合は、何もされません。  
  
 一部のデバイスでは、`SetPixel` 関数がサポートされていません。 デバイスがサポートするかどうかを確認する`SetPixel`を呼び出す、`GetDeviceCaps`メンバー関数を**RASTERCAPS**インデックスを作成しの戻り値を確認して、 **RC_BITBLT**フラグ。  
  
##  <a name="a-namesetpixelva--cdcsetpixelv"></a><a name="setpixelv"></a>CDC::SetPixelV  
 指定された色の最も近い色を指定した座標にあるピクセルに設定します。  
  
```  
BOOL SetPixelV(
    int x,  
    int y,  
    COLORREF crColor);

 
BOOL SetPixelV(
    POINT point,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理単位で設定する点の x 座標を指定します。  
  
 *y*  
 論理単位で設定する点の y 座標を指定します。  
  
 `crColor`  
 ポイントの描画に使用する色を指定します。  
  
 `point`  
 設定する点の論理 x 座標と y 座標を指定します。 いずれかを渡すことができます、[ポイント](../../mfc/reference/point-structure1.md)データ構造体、または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、クリッピング領域と、デバイス画面の表示部分の両方にする必要があります。 すべてのデバイスには、メンバー関数がサポートされます。 詳細については、次を参照してください。、 **RC_BITBLT**の機能は、`CDC::GetDeviceCaps`メンバー関数。 `SetPixelV`も高速`SetPixel`を実際に描画されたポイントの色の値を返す必要はありませんので。  
  
##  <a name="a-namesetpolyfillmodea--cdcsetpolyfillmode"></a><a name="setpolyfillmode"></a>CDC::SetPolyFillMode  
 多角形の塗りつぶしモードを設定します。  
  
```  
int SetPolyFillMode(int nPolyFillMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPolyFillMode`  
 新しい塗りつぶしモードを指定します。 この値は、いずれかの**代替**または**ワインディング**します。 既定のモードが、Windows の設定は**代替**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は以前の塗りつぶしモードそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 多角形の塗りつぶしモードのときは**代替**システムは、各スキャン ラインに奇数し、偶数の多角形の辺の間で領域を塗りつぶします。 つまり、システムは、最初と&2; 番目の側の間で、3 番目と&4; 番目の側との間の領域を塗りつぶします。 このモードは、既定値です。  
  
 多角形の塗りつぶしモードのときは**ワインディング**システムは、図が描いた領域を入力するかどうかを判断する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りのいずれかに表示されます。 閉じた領域から図形の外側に描画架空の線が時計回りの直線セグメントを通過するたびに、カウントがインクリメントされます。 行が反時計回りに回転線セグメントを経過すると、カウントがデクリメントします。 図形の外側の行に達したら、カウントがゼロ以外の領域に入力されます。  
  
##  <a name="a-namesetrop2a--cdcsetrop2"></a><a name="setrop2"></a>CDC::SetROP2  
 現在の描画モードを設定します。  
  
```  
int SetROP2(int nDrawMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawMode`  
 新しい描画モードを指定します。 次の値のいずれかを指定できます。  
  
- **R2_BLACK**ピクセルは黒で常にします。  
  
- **R2_WHITE**ピクセルの色は常に白です。  
  
- **R2_NOP**ピクセルは変更されません。  
  
- **R2_NOT**ピクセルは画面の色の反転します。  
  
- **R2_COPYPEN**ピクセルがペンの色。  
  
- **R2_NOTCOPYPEN**ピクセルがペンの色の反転します。  
  
- **R2_MERGEPENNOT**ピクセルがペンの色の組み合わせと画面の色の反転 (最終的なピクセル = (NOT 画面ピクセル) またはペン)。  
  
- **R2_MASKPENNOT**ピクセルがペンの両方に共通する色の組み合わせと、画面の反転 (最終的なピクセル = (NOT 画面ピクセル) とペン)。  
  
- **R2_MERGENOTPEN**ピクセルは画面の色の組み合わせとペンの色の反転 (最終的なピクセル = (NOT ペン)、または画面ピクセル)。  
  
- **R2_MASKNOTPEN**ピクセルは画面の両方に共通する色の組み合わせと、ペンの反転 (最終的なピクセル = (NOT ペン) と画面ピクセル)。  
  
- **R2_MERGEPEN**ピクセルがペンの色、画面の色の組み合わせ (最終的なピクセル = ペン OR 画面ピクセル)。  
  
- **R2_NOTMERGEPEN**の逆関数のピクセルが、 **R2_MERGEPEN**色 (最終的なピクセル = なし (ペン OR 画面ピクセル))。  
  
- **R2_MASKPEN**ピクセルは、ペンと画面の両方に共通する色の組み合わせ (最終的なピクセル = ペン AND 画面ピクセル)。  
  
- **R2_NOTMASKPEN**の逆関数のピクセルが、 **R2_MASKPEN**色 (最終的なピクセル = なし (ペン AND 画面ピクセル))。  
  
- **R2_XORPEN**ピクセルが画面で、または両方ではなく、ペンでは色の組み合わせ (最終的なピクセル = ペン XOR 画面ピクセル)。  
  
- **R2_NOTXORPEN**の逆関数のピクセルが、 **R2_XORPEN**色 (最終的なピクセル = なし (ペン XOR 画面ピクセル))。  
  
### <a name="return-value"></a>戻り値  
 前の描画モード。  
  
 指定された値のいずれかのことができます、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 描画モードでは、既にディスプレイ表面における色でペンの色とオブジェクトの内部を組み合わせる方法を指定します。  
  
 描画モードは、ラスター デバイスだけです。ベクターのデバイスには適用されません。 描画モードは、ブール型のあらゆる組み合わせの使い方を二項演算子 AND、OR、および XOR (排他的 OR) と単項演算の&2; つの変数を表すバイナリ ラスター オペレーション コードです。  
  
##  <a name="a-namesetstretchbltmodea--cdcsetstretchbltmode"></a><a name="setstretchbltmode"></a>CDC::SetStretchBltMode  
 ビットマップの伸縮モードを設定、`StretchBlt`メンバー関数。  
  
```  
int SetStretchBltMode(int nStretchMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStretchMode*  
 伸縮モードを指定します。 次の値のいずれかを指定できます。  
  
|値|説明|  
|-----------|-----------------|  
|**BLACKONWHITE**|排除し、既存のピクセルの色の値を使用して、論理 AND 演算を実行します。 モノクロ ビットマップは、このモードは白のピクセルを犠牲にして黒のピクセルを保持します。|  
|**COLORONCOLOR**|ピクセルを削除します。 このモードでは、その情報を保持しようとしないでピクセルの削除されたすべての行を削除します。|  
|**ハーフトーン**|元の四角形からピクセルをコピー先の四角形のピクセルのブロックにマップします。 対象ブロックのピクセルの平均的な色では、ソース ピクセルの色を概算します。|  
||設定した後、**ハーフトーン**モードを拡大するには、アプリケーションは、Win32 関数を呼び出す必要があります[SetBrushOrgEx](http://msdn.microsoft.com/library/windows/desktop/dd162967)ブラシの原点を設定します。 これを行う場合は、ブラシの不整合が発生します。|  
|**STRETCH_ANDSCANS**|**Windows 95/98**: と同じ**BLACKONWHITE**|  
|**STRETCH_DELETESCANS**|**Windows 95/98**: と同じ**COLORONCOLOR**|  
|**STRETCH_HALFTONE**|**Windows 95/98**: と同じ**ハーフトーン**します。|  
|**終了しました。**|**Windows 95/98**: と同じ**WHITEONBLACK**|  
|**WHITEONBLACK**|排除し、既存のピクセルの色の値を使用して、論理 OR 演算を実行します。 ビットマップがモノクロ ビットマップの場合は、このモードには、黒のピクセルを犠牲にして白いピクセルが保持されます。|  
  
### <a name="return-value"></a>戻り値  
 直前の伸縮モード。 できます**STRETCH_ANDSCANS**、 **STRETCH_DELETESCANS**、または**終了した**します。  
  
### <a name="remarks"></a>コメント  
 ビットマップの伸縮モードでは、関数を使用して圧縮されたビットマップから情報を削除する方法を定義します。  
  
 **BLACKONWHITE** ( **STRETCH_ANDSCANS**) と**WHITEONBLACK** (**終了した**) モードは通常モノクロ ビットマップのピクセルを前景色を保持するために使用します。 **COLORONCOLOR** ( **STRETCH_DELETESCANS**) モードは通常カラー ビットマップの色を保持するために使用されます。  
  
 **ハーフトーン**モードには、ソース イメージの他の&3; つのモードよりも多くの処理が必要があることは、他よりも遅くなりますが高品質のイメージが生成されます。 いるにも注意してください**SetBrushOrgEx**設定後に呼び出さなければならない、**ハーフトーン**ブラシの不整合を回避するモード。  
  
 ほかの伸縮モードは、デバイス ドライバーの機能によって使用できることもあります。  
  
##  <a name="a-namesettextaligna--cdcsettextalign"></a><a name="settextalign"></a>CDC::SetTextAlign  
 テキスト配置フラグを設定します。  
  
```  
UINT SetTextAlign(UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 テキスト配置フラグを指定します。 フラグは、ポイントと、テキストを外接する四角形の間のリレーションシップを指定します。 ポイントは、現在の位置またはテキスト出力関数によって指定された座標にすることができます。 テキストを外接する四角形は、テキスト文字列内の隣接する文字セルによって定義されます。 `nFlags`パラメーターは、次の&3; つのカテゴリの&1; つまたは複数のフラグを指定できます。 各カテゴリの&1; つだけを選択します。 最初のカテゴリには、x 軸方向のテキストの配置に影響します。  
  
- **TA_CENTER**点と外接する四角形の水平方向の中央に揃えて配置します。  
  
- **TA_LEFT**外接する四角形の左端とポイントを配置します。 これは、既定の設定です。  
  
- **TA_RIGHT**点と外接する四角形の右側に揃えて配置します。  
  
 2 番目のカテゴリには、y 軸方向のテキストの配置に影響します。  
  
- **TA_BASELINE**点と、選択されているフォントのベース ラインを揃えて配置します。  
  
- **TA_BOTTOM**外接する四角形の下部でポイントを配置します。  
  
- **TA_TOP**外接する四角形の上部を使用してポイントを配置します。 これは、既定の設定です。  
  
 3 番目のカテゴリでは、テキストが書き込まれるときに、現在の位置を更新するかどうかを決定します。  
  
- **TA_NOUPDATECP**テキスト出力関数を呼び出すたびに、現在の位置を更新できません。 これは、既定の設定です。  
  
- **TA_UPDATECP**テキスト出力関数を呼び出すたびに現在の x 位置を更新します。 テキストの外接する四角形の右側にある、新しい位置。 このフラグ設定されている場合の呼び出しで指定された座標、`TextOut`メンバー関数は無視されます。  
  
### <a name="return-value"></a>戻り値  
 前のテキスト配置設定、成功した場合です。 下位バイトが水平方向の設定を格納し、高位バイトには、垂直方向の設定が含まれています。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `TextOut`と`ExtTextOut`ディスプレイやデバイス上のテキストの文字列を配置するときに、メンバー関数がこれらのフラグを使用します。 フラグは、特定の時点と、テキストを外接する四角形のリレーションシップを指定します。 この点の座標をパラメーターとして渡される、`TextOut`メンバー関数。 テキストを外接する四角形は、テキスト文字列の文字が隣接するセルによって形成されます。  
  
##  <a name="a-namesettextcharacterextraa--cdcsettextcharacterextra"></a><a name="settextcharacterextra"></a>CDC::SetTextCharacterExtra  
 文字間隔の量を設定します。  
  
```  
int SetTextCharacterExtra(int nCharExtra);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCharExtra`  
 各文字に追加するには、(論理単位で) に余分な領域の量を指定します。 現在のマッピング モードがない場合`MM_TEXT`、`nCharExtra`を変換し、最も近いピクセルに丸められます。  
  
### <a name="return-value"></a>戻り値  
 前の文字間隔の量。  
  
### <a name="remarks"></a>コメント  
 GDI は、この間隔をデバイス コンテキストに、行のテキストを書き込むときに、改行文字を含む、各文字を追加します。 文字間隔の既定値は 0 です。  
  
##  <a name="a-namesettextcolora--cdcsettextcolor"></a><a name="settextcolor"></a>CDC::SetTextColor  
 テキストの色を指定した色に設定します。  
  
```  
virtual COLORREF SetTextColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 RGB 色の値として、テキストの色を指定します。  
  
### <a name="return-value"></a>戻り値  
 前のテキストの色の RGB 値。  
  
### <a name="remarks"></a>コメント  
 このデバイスとも色の間でビットマップを変換する、およびとモノクロ デバイス コンテキストにテキストを書き込むときにこのテキストの色が使用されます。  
  
 デバイスは、指定した色を表すことができない、テキストの色が最も近いの物理的な色に設定されます。 文字の背景色がで指定された、`SetBkColor`と`SetBkMode`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)します。  
  
##  <a name="a-namesettextjustificationa--cdcsettextjustification"></a><a name="settextjustification"></a>CDC::SetTextJustification  
 文字列の区切り文字にスペースを追加します。  
  
```  
int SetTextJustification(
    int nBreakExtra,  
    int nBreakCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBreakExtra`  
 (論理単位で) テキストの行に追加する余分な領域の合計を指定します。 現在のマッピング モードがない場合`MM_TEXT`、このパラメーターによって指定された値が現在のマップ モードに変換され、最も近いデバイス単位に丸められます。  
  
 *nBreakCount*  
 行に改行文字の数を指定します。  
  
### <a name="return-value"></a>戻り値  
 1 の場合は、関数は成功します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで使用できる、`GetTextMetrics`フォントを取得するメンバー関数は、文字を中断します。  
  
 後に、`SetTextJustification`メンバー関数が呼び出されると、テキスト出力関数の呼び出し (よう`TextOut`) 改行文字の指定した数の間で均等に指定された余分なスペースを配布します。 改行文字は通常、その他の文字としてフォントで定義されている可能性があります、空白文字 (ASCII 32) です。  
  
 メンバー関数は、`GetTextExtent`で通常使用される`SetTextJustification`します。 `GetTextExtent`配置する前に指定された行の幅を計算します。 アプリケーションでを指定する領域の量を決定できます、`nBreakExtra`パラメーターによって返される値を減算して`GetTextExtent`配置後の文字列の幅から。  
  
 `SetTextJustification`関数を使用して、さまざまなフォントで複数の実行を含む行を揃えます。 この場合、行を段階的な部分に作成して配置し、それぞれの実行を個別に書き込み必要があります。  
  
 配置の間に発生する丸め誤差、ため、システムは、現在のエラーを定義する実行中の誤差項を保持します。 複数の実行を含む行を揃えて配置する場合`GetTextExtent`自動的に次の実行の程度を計算するときにこのエラーの用語を使用します。 これにより、テキスト出力関数は、新規の実行に blend のエラーです。  
  
 各行が配置された後、次の行に持ち込まれるようにするのにこのエラーの用語をクリアする必要があります。 呼び出してという用語をクリアできます`SetTextJustification`と`nBreakExtra`を 0 に設定します。  
  
##  <a name="a-namesetviewportexta--cdcsetviewportext"></a><a name="setviewportext"></a>CDC::SetViewportExt  
 デバイス コンテキストのビューポートの x 範囲と y 範囲を設定します。  
  
```  
virtual CSize SetViewportExt(
    int cx,  
    int cy);  
  
CSize SetViewportExt(SIZE size);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 デバイス単位で、ビューポートの x 範囲を指定します。  
  
 `cy`  
 デバイス単位で、ビューポートの y 範囲を指定します。  
  
 `size`  
 デバイス単位で、ビューポートの x 範囲と y 範囲を指定します。  
  
### <a name="return-value"></a>戻り値  
 ビューポートの前のエクステント、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。 ときにエラーが発生する、返された x 座標と y 座標`CSize`オブジェクトの両方が 0 に設定します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストのウィンドウと共に、ビューポートは、GDI が実際のデバイスの座標系を指す論理座標系の点をマップする方法を定義します。 つまり、GDI がデバイス座標に論理座標を変換する方法を定義します。  
  
 次のマップ モードが設定するために呼び出す`SetWindowExt`と`SetViewportExt`は無視されます。  
  
|MM_HIENGLISH|MM_LOMETRIC|  
|-------------------|------------------|  
|`MM_HIMETRIC`|`MM_TEXT`|  
|`MM_LOENGLISH`|`MM_TWIPS`|  
  
 `MM_ISOTROPIC`モードが設定されており、アプリケーションを呼び出す必要があります、`SetWindowExt`メンバー関数を呼び出す前に`SetViewportExt`します。  
  
### <a name="example"></a>例  
  例を参照してください[付け](../../mfc/reference/cview-class.md#onpreparedc)します。  
  
##  <a name="a-namesetviewportorga--cdcsetviewportorg"></a><a name="setviewportorg"></a>CDC::SetViewportOrg  
 デバイス コンテキストのビューポートの原点を設定します。  
  
```  
virtual CPoint SetViewportOrg(
    int x,  
    int y);  
  
CPoint SetViewportOrg(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ビューポートの原点の (デバイス単位) の x 座標を指定します。 デバイス座標系の範囲内で指定してください。  
  
 *y*  
 ビューポートの原点の (デバイス単位) の y 座標を指定します。 デバイス座標系の範囲内で指定してください。  
  
 `point`  
 ビューポートの原点を指定します。 値は、デバイス座標系の範囲内である必要があります。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 直前の原点のビューポート (デバイス座標) での`CPoint`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストのウィンドウと共に、ビューポートは、GDI が実際のデバイスの座標系を指す論理座標系の点をマップする方法を定義します。 つまり、GDI がデバイス座標に論理座標を変換する方法を定義します。  
  
 ビューポートの原点が GDI で指定された論理座標系では、ポイント、ウィンドウの原点のマップ先デバイス座標系内の位置をマーク、**変換する**メンバー関数。 GDI は、ウィンドウの原点をビューポートの原点にマップするために必要な同じプロセスに従うことによって、その他のすべてのポイントをマップします。 たとえば、ウィンドウの原点を中心点を中心円で囲まれたすべてのポイントは、ビューポートの原点を中心点を中心円になります。 同様に、ウィンドウの原点を通過する行のすべてのポイントは、ビューポートの原点を通る線になります。  
  
### <a name="example"></a>例  
  例を参照してください[付け](../../mfc/reference/cview-class.md#onpreparedc)します。  
  
##  <a name="a-namesetwindowexta--cdcsetwindowext"></a><a name="setwindowext"></a>CDC::SetWindowExt  
 デバイス コンテキストに関連付けられているウィンドウの x 範囲と y 範囲を設定します。  
  
```  
virtual CSize SetWindowExt(
    int cx,  
    int cy);  
  
CSize SetWindowExt(SIZE size);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 ウィンドウの (論理単位で) x の範囲を指定します。  
  
 `cy`  
 ウィンドウの (論理単位で) y の範囲を指定します。  
  
 `size`  
 X 範囲と y の範囲を (論理単位で) ウィンドウを指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ (論理単位で) の前のエクステント、`CSize`オブジェクトです。 エラーがあった場合、返された x 座標と y 座標`CSize`オブジェクトの両方が 0 に設定します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストのビューポートとは、GDI がデバイス座標系の点を論理座標系の点をマップする方法を定義します。  
  
 次のマップ モードが設定するために呼び出す`SetWindowExt`と`SetViewportExt`関数は無視されます。  
  
- `MM_HIENGLISH`  
  
- `MM_HIMETRIC`  
  
- `MM_LOENGLISH`  
  
- `MM_LOMETRIC`  
  
- `MM_TEXT`  
  
- `MM_TWIPS`  
  
 `MM_ISOTROPIC`モードが設定されており、アプリケーションを呼び出す必要があります、`SetWindowExt`メンバー関数呼び出しの前に`SetViewportExt`します。  
  
### <a name="example"></a>例  
  例を参照してください[付け](../../mfc/reference/cview-class.md#onpreparedc)します。  
  
##  <a name="a-namesetwindoworga--cdcsetwindoworg"></a><a name="setwindoworg"></a>CDC::SetWindowOrg  
 デバイス コンテキストのウィンドウの原点を設定します。  
  
```  
CPoint SetWindowOrg(
    int x,  
    int y);  
  
CPoint SetWindowOrg(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ウィンドウのオリジンの新規作成の論理の x 座標を指定します。  
  
 *y*  
 ウィンドウのオリジンの新規作成の論理の y 座標を指定します。  
  
 `point`  
 ウィンドウのオリジンの新規作成の論理座標を指定します。 いずれかを渡すことができます、**ポイント**構造体、または`CPoint`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 直前の原点をウィンドウとしての`CPoint`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストのビューポートとは、GDI がデバイス座標系の点を論理座標系の点をマップする方法を定義します。  
  
 ウィンドウの原点がビューポートの原点座標系では、デバイスで指定されたポイントが gdi 元となる論理座標系で位置をマーク、**変換する**関数です。 GDI は、ウィンドウの原点をビューポートの原点にマップするために必要な同じプロセスに従うことによって、その他のすべてのポイントをマップします。 たとえば、ウィンドウの原点を中心点を中心円で囲まれたすべてのポイントは、ビューポートの原点を中心点を中心円になります。 同様に、ウィンドウの原点を通過する行のすべてのポイントは、ビューポートの原点を通る線になります。  
  
##  <a name="a-namesetworldtransforma--cdcsetworldtransform"></a><a name="setworldtransform"></a>CDC::SetWorldTransform  
 世界中の領域と指定したデバイス コンテキストのページ領域の&2; 次元の線形変換を設定します。 この変換は、拡大縮小、回転、傾斜、またはグラフィックスの出力を変換に使用できます。  
  
```  
BOOL SetWorldTransform(const XFORM& rXform);
```  
  
### <a name="parameters"></a>パラメーター  
 `rXform`  
 参照、 [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228)変換データを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に&0; 以外の値を返します。  
  
 失敗した場合は 0 を返します。  
  
 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメソッド[SetWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145104)します。  
  
##  <a name="a-namestartdoca--cdcstartdoc"></a><a name="startdoc"></a>CDC::StartDoc  
 新しい印刷ジョブが開始されるデバイス ドライバーに通知し、後続のすべての`StartPage`と`EndPage`まで、同じジョブでの呼び出しをスプールする必要があります、`EndDoc`呼び出しが行われます。  
  
```  
int StartDoc(LPDOCINFO lpDocInfo);  
int StartDoc(LPCTSTR lpszDocName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDocInfo*  
 指す、[持つ](http://msdn.microsoft.com/library/windows/desktop/dd183574)ドキュメント ファイルの名前と出力ファイルの名前を含む構造体。  
  
 *lpszDocName*  
 ドキュメント ファイルの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は&0; より大きいです。 この値は、ドキュメントの印刷ジョブの識別子です。  
  
 関数が失敗した場合、戻り値は&0; 以下です。  
  
### <a name="remarks"></a>コメント  
 これにより、1 つのページよりも長いドキュメントを他のジョブと混在しないされます。  
  
 Windows 3.1 以降のバージョンでは、この関数が置き換えられます、 **STARTDOC**プリンター エスケープします。 この関数を使用することで他の印刷ジョブに複数のページを含むドキュメントが混在しません。  
  
 `StartDoc`メタファイル内でない使用する必要があります。  
  
### <a name="example"></a>例  
 次のコード片は、通常使うプリンターを取得し、印刷ジョブを開き「こんにちは, World!」の&1; ページにスプール 取得します。 このコードで印刷されるテキストは、プリンターの論理ユニットにスケーリングされていないので、テキストを出力する場合がありますこのような小文字で結果を読み取ることができないことです。 など、機能を拡大/縮小 CDC `SetMapMode`、 `SetViewportOrg`、および`SetWindowExt`、拡大/縮小を修正するために使用できます。  
  
 [!code-cpp[NVC_MFCDocView #&41;](../../mfc/codesnippet/cpp/cdc-class_13.cpp)]  
  
##  <a name="a-namestartpagea--cdcstartpage"></a><a name="startpage"></a>CDC::StartPage  
 このメンバー関数を呼び出してデータを受信するプリンター ドライバーを準備します。  
  
```  
int StartPage();
```  
  
### <a name="return-value"></a>戻り値  
 以上の場合、関数は成功すると、0 または負の値を使用している場合、エラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 `StartPage`も優先されます、 **NEWFRAME**と**BANDINFO**をエスケープします。  
  
 印刷の呼び出しのシーケンスの概要については、次を参照してください。、 [StartDoc](#startdoc)メンバー関数。  
  
 システムを無効に、`ResetDC`メンバー関数への呼び出しの間で`StartPage`と`EndPage`です。  
  
### <a name="example"></a>例  
  例を参照してください[CDC::StartDoc](#startdoc)します。  
  
##  <a name="a-namestretchblta--cdcstretchblt"></a><a name="stretchblt"></a>CDC::StretchBlt  
 コピー元の四角形から、必要に応じてコピー先の四角形に合うようにビットマップを拡大または縮小してコピーします。  
  
```  
BOOL StretchBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 コピー先の四角形の左上隅を示す X 座標を (論理単位で) 指定します。  
  
 *y*  
 コピー先の四角形の左上隅を示す Y 座標を (論理単位で) 指定します。  
  
 `nWidth`  
 コピー先の四角形の幅を (論理単位で) 指定します。  
  
 `nHeight`  
 コピー先の四角形の高さを (論理単位で) 指定します。  
  
 `pSrcDC`  
 コピー元のデバイス コンテキストを指定します。  
  
 `xSrc`  
 コピー元の四角形の左上隅を示す X 座標を (論理単位で) 指定します。  
  
 `ySrc`  
 コピー元の四角形の左上隅を示す Y 座標を (論理単位で) 指定します。  
  
 `nSrcWidth`  
 コピー元の四角形の幅を (論理単位で) 指定します。  
  
 `nSrcHeight`  
 コピー元の四角形の高さを (論理単位で) 指定します。  
  
 *dwRop*  
 実行するラスター オペレーションを指定します。 ラスター オペレーション コードにより、現在のブラシ、有効なコピー元のビットマップ、およびコピー先のビットマップが関連する出力操作における、GDI による色の組み合わせが定義されます。 このパラメーターには、次のいずれかの値を指定できます。  
  
- **BLACKNESS**すべて出力を黒です。  
  
- **DSTINVERT**変換先のビットマップを反転します。  
  
- **MERGECOPY**パターンとブール型 AND 演算子を使用して元のビットマップを結合します。  
  
- **MERGEPAINT**反転されたコピー元ビットマップ、コピー先ビットマップをブール型 OR 演算子を使用するとします。  
  
- **NOTSRCCOPY**反転されたコピー元ビットマップをコピー先にコピーします。  
  
- **NOTSRCERASE**の送信先と送信元のビットマップをブール型 OR 演算子を使用して結果を反転します。  
  
- **PATCOPY**パターンをコピー先ビットマップにコピーします。  
  
- **PATINVERT**とパターンをブール型 XOR 演算子を使用して、コピー先ビットマップを組み合わせます。  
  
- **PATPAINT**とパターンをブール型 OR 演算子を使用して、反転されたコピー元ビットマップを組み合わせます。 さらに、ブール型 OR 演算子を使用して、この演算の結果とコピー先ビットマップを組み合わせます。  
  
- **SRCAND**ブール型 AND 演算子を使用して送信先と送信元のビットマップのピクセルを組み合わせます。  
  
- **SRCCOPY**元ビットマップをコピー先ビットマップにコピーします。  
  
- **SRCERASE**変換先のビットマップを反転し、結果ブール型 AND 演算子を使用して元のビットマップと組み合わせます。  
  
- **SRCINVERT**ブール型 XOR 演算子を使用して送信先と送信元のビットマップのピクセルを組み合わせます。  
  
- **SRCPAINT**ブール型 OR 演算子を使用して送信先と送信元のビットマップのピクセルを組み合わせます。  
  
- **WHITENESS**すべての出力を白にします。  
  
### <a name="return-value"></a>戻り値  
 ビットマップが描画された場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コピー先デバイス コンテキストの伸縮モード (`SetStretchBltMode` で設定) を使用して、ビットマップを拡大または縮小する方法を決定します。  
  
 `StretchBlt` 関数は、ビットマップを、`pSrcDC` によって指定された移動元デバイスから、メンバー関数の呼び出し元デバイス コンテキスト オブジェクトで表される移動先デバイスに移動します。 `xSrc`、`ySrc`、`nSrcWidth`、および `nSrcHeight` の各パラメーターは、移動元の四角形の左上隅および次元を定義します。 *X*、 *y*、 `nWidth`、および`nHeight`パラメーターは、左上隅とコピー先の四角形の寸法を指定します。 指定されたラスター オペレーション*dwRop*元のビットマップと移動先デバイス上のビットを組み合わせる方法を定義します。  
  
 `StretchBlt` 関数は、`nSrcWidth` と `nWidth`、または `nSrcHeight` と `nHeight` のそれぞれのパラメーターの符号が異なる場合に、ビットマップのミラー イメージを作成します。 `nSrcWidth` の符号と `nWidth` の符号が異なる場合、この関数は、ビットマップのミラー イメージを X 軸に沿って作成します。 `nSrcHeight` の符号と `nHeight` の符号が異なる場合、この関数は、ビットマップのミラー イメージを Y 軸に沿って作成します。  
  
 `StretchBlt` 関数は、メモリ内のコピー元ビットマップを拡大または縮小し、その結果をコピー先にコピーします。 パターンを結果とマージする場合、そのパターンは、拡大されたコピー元ビットマップがコピー先にコピーされるまでマージされません。 ブラシを使用する場合、そのブラシは、コピー先デバイス コンテキストで選択されたブラシです。 コピー先の座標は、コピー先デバイス コンテキストに従って変換されます。コピー元の座標は、コピー元デバイス コンテキストに従って変換されます。  
  
 コピー先ビットマップ、コピー元ビットマップ、およびパターン ビットマップの色の形式が異なる場合は、`StretchBlt` によって、コピー元ビットマップとパターン ビットマップが、コピー先ビットマップに合わせて変換されます。 変換では、コピー先デバイス コンテキストの前景色と背景色が使用されます。  
  
 モノクロ ビットマップをカラーに変換する必要がある場合、`StretchBlt` は白のビット (1) を背景色に、黒のビット (0) を前景色に設定します。 カラーをモノクロに変換するには、背景色に一致するピクセルを白 (1) に設定し、その他のすべてのピクセルを黒 (0) に設定します。 カラーのデバイス コンテキストの前景色と背景色は使用されます。  
  
 一部のデバイスでは、`StretchBlt` 関数がサポートされていません。 デバイスがサポートするかどうかを確認する`StretchBlt`を呼び出す、`GetDeviceCaps`メンバー関数を**RASTERCAPS**インデックスを作成しの戻り値を確認して、 **RC_STRETCHBLT**フラグ。  
  
##  <a name="a-namestrokeandfillpatha--cdcstrokeandfillpath"></a><a name="strokeandfillpath"></a>CDC::StrokeAndFillPath  
 パス内の開いている図形を閉じ、現在のペンを使用して、パスの外枠を描画および現在のブラシを使用して、その内部を塗りつぶします。  
  
```  
BOOL StrokeAndFillPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストでは、閉じたパスを含める必要があります。 `StrokeAndFillPath`メンバー関数は、パス内のすべての開いている図形を閉じると同じ効果があり、ペンの幅が線の描画と、塗りつぶされた領域がいても、線の領域に重ならないする点を除いて、個別にパスを入力します。  
  
##  <a name="a-namestrokepatha--cdcstrokepath"></a><a name="strokepath"></a>CDC::StrokePath  
 現在のペンを使用して、指定されたパスを描画します。  
  
```  
BOOL StrokePath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストでは、閉じたパスを含める必要があります。  
  
##  <a name="a-nametabbedtextouta--cdctabbedtextout"></a><a name="tabbedtextout"></a>CDC::TabbedTextOut  
 タブ ストップの位置の配列で指定された値にタブを展開する、指定された場所にある文字の文字列に書き込むには、このメンバー関数を呼び出します。  
  
```  
virtual CSize TabbedTextOut(
    int x,  
    int y,  
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions,  
    int nTabOrigin);

 
CSize TabbedTextOut(
    int x,  
    int y,  
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions,  
    int nTabOrigin);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 文字列の開始位置の論理の x 座標を指定します。  
  
 *y*  
 文字列の開始位置の論理の y 座標を指定します。  
  
 `lpszString`  
 描画する文字列へのポインター。 文字の配列にいずれかにポインターを渡すことができます、または[CString](../../atl-mfc-shared/reference/cstringt-class.md)このパラメーターにします。  
  
 `nCount`  
 文字列の文字数を指定します。 場合`nCount`-1 で、長さを計算します。  
  
 `nTabPositions`  
 タブ ストップの位置の配列内の値の数を指定します。  
  
 `lpnTabStopPositions`  
 (論理単位で) タブ ストップの位置を格納する配列を指します。 タブ ストップは昇順に並べ替え; 並べられていなければなりませんx の最小値は、配列の最初の項目にする必要があります。  
  
 `nTabOrigin`  
 (論理単位で) 元となるタブが展開されて開始位置の x 座標を指定します。  
  
 `str`  
 A`CString`を指定した文字を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 (論理単位で) として文字列のディメンション、`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 テキストは、現在選択されているフォントに書き込まれます。 場合`nTabPositions`は 0 と`lpnTabStopPositions`は**NULL**タブは、平均の文字幅の 8 倍に拡張されます。  
  
 場合`nTabPositions`1、位置が最初の値で指定された距離で区切られた タブには、`lpnTabStopPositions`配列。 場合、`lpnTabStopPositions`配列には、複数の値が含まれる、タブ ストップがで指定された数までの配列の各値に設定されている`nTabPositions`します。 `nTabOrigin`パラメーターにより、アプリケーションを呼び出して、 `TabbedTextOut`&1; 行に数回関数です。 かどうかはアプリケーションが、関数を複数回呼び出し、 `nTabOrigin` 、関数は、すべてのタブで指定された位置を基準としたを拡大するたびに同じ値に設定`nTabOrigin`します。  
  
 既定では、関数は現在位置を使用することも、更新することもありません。 アプリケーションを呼び出して、アプリケーションは、関数を呼び出すときに、現在の位置を更新する必要があるを場合、[呼び出された](#settextalign)メンバー関数を`nFlags`に設定**TA_UPDATECP**します。 Windows このフラグを設定するときは無視、 *x*と*y*に対する後続の呼び出しでパラメーター `TabbedTextOut`、現在位置が代わりに使用します。  
  
##  <a name="a-nametextouta--cdctextout"></a><a name="textout"></a>CDC::TextOut  
 現在選択されているフォントを使用して、文字列を指定位置から書き込みます。  
  
```  
virtual BOOL TextOut(
    int x,  
    int y,  
    LPCTSTR lpszString,  
    int nCount);

 
BOOL TextOut(
    int x,
    int y,
    const CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 テキストの始点の論理的な X 座標を指定します。  
  
 *y*  
 テキストの始点の論理的な Y 座標を指定します。  
  
 `lpszString`  
 描画される文字列を指します。  
  
 `nCount`  
 文字列の文字数を指定します。  
  
 `str`  
 描画される文字が含まれる `CString` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 文字の起点は文字セルの左上隅です。 既定では、関数は現在位置を使用することも、更新することもありません。  
  
 アプリケーションを呼び出すときに、現在の位置を更新する必要があるかどうか`TextOut`、アプリケーションを呼び出して、`SetTextAlign`メンバー関数を`nFlags`に設定**TA_UPDATECP**します。 Windows このフラグを設定するときは無視、 *x*と*y*に対する後続の呼び出しでパラメーター `TextOut`、現在位置が代わりに使用します。  
  
### <a name="example"></a>例  
  例を参照してください[cdc::beginpath](#beginpath)します。  
  
##  <a name="a-nametransparentblta--cdctransparentblt"></a><a name="transparentblt"></a>CDC::TransparentBlt  
 このメンバー関数を呼び出して、指定した発信元デバイス コンテキストのコピー先デバイス コンテキストに、ピクセルの四角形に対応する色データのビット ブロック転送します。  
  
```  
BOOL TransparentBlt(
    int xDest,  
    int yDest,
    int nDestWidth,
    int nDestHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    UINT clrTransparent);
```  
  
### <a name="parameters"></a>パラメーター  
 `xDest`  
 論理ユニットは、コピー先の四角形の左上隅の x 座標を指定します。  
  
 `yDest`  
 論理ユニットは、コピー先の四角形の左上隅の y 座標を指定します。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅を指定します。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さを指定します。  
  
 `pSrcDC`  
 転送元デバイス コンテキストへのポインター。  
  
 `xSrc`  
 論理ユニットは、元の四角形の x 座標を指定します。  
  
 `ySrc`  
 論理ユニットは、元の四角形の y 座標を指定します。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅を指定します。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さを指定します。  
  
 `clrTransparent`  
 コピー元のビットマップが透明として扱うの RGB 色です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `TransparentBlt`透過性では、します。は、RGB 色が示される`clrTransparent`透明に転送にレンダリングします。  
  
 詳細については、次を参照してください。 [TransparentBlt](http://msdn.microsoft.com/library/windows/desktop/dd145141)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameupdatecolorsa--cdcupdatecolors"></a><a name="updatecolors"></a>CDC::UpdateColors  
 クライアント領域のピクセルごとにシステム パレットで現在を照合することによって、デバイス コンテキストのクライアント領域の色を更新します。  
  
```  
void UpdateColors();
```  
  
### <a name="remarks"></a>コメント  
 実現論理パレットを持つ、非アクティブなウィンドウを呼び出すことが`UpdateColors`システム パレットが変更されたときに、クライアント領域を再描画する代わりにします。  
  
 詳細については、カラー パレットを使用して、次を参照してください。[この](http://msdn.microsoft.com/library/windows/desktop/dd145166)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `UpdateColors`メンバー関数は通常、更新、クライアント区分、領域を再描画よりも高速です。 ただし、関数は、各ピクセルの色に基づいてシステム パレットを変更する前に色の変換を実行するため、この関数に対する各呼び出しは、色の正確さが失われる発生します。  
  
##  <a name="a-namewidenpatha--cdcwidenpath"></a><a name="widenpath"></a>CDC::WidenPath  
 パスがデバイス コンテキストに現在選択されているペンを使用して描画された場合に描画される領域として、現在のパスを再定義します。  
  
```  
BOOL WidenPath();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数が成功したは、現在のペンが第 2 のバージョンで作成されたジオメトリ ペンである場合にのみ`CreatePen`メンバー関数の最初のバージョンで、ペンが作成された場合、または`CreatePen`デバイス単位、1 以上で、幅をします。 デバイス コンテキストでは、閉じたパスを含める必要があります。 任意のベジエ曲線のパスでは、直線のおおよその拡張の曲線のシーケンスに変換されます。 そのため、ベジエ曲線内に残っていない後パス`WidenPath`が呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPaintDC クラス](../../mfc/reference/cpaintdc-class.md)   
 [CWindowDC クラス](../../mfc/reference/cwindowdc-class.md)   
 [CClientDC クラス](../../mfc/reference/cclientdc-class.md)   
 [CMetaFileDC クラス](../../mfc/reference/cmetafiledc-class.md)

