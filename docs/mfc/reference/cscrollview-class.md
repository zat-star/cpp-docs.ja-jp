---
title: "CScrollView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CScrollView
dev_langs:
- C++
helpviewer_keywords:
- CScrollView class
- views, scrolling
- scrolling views
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
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
ms.openlocfilehash: 0dc937a9559306ff527779c45af9fdb62cf602df
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollview-class"></a>CScrollView クラス
A [CView](../../mfc/reference/cview-class.md)スクロール機能を持つ。  
  
## <a name="syntax"></a>構文  
  
```  
class CScrollView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CScrollView::CScrollView](#cscrollview)|`CScrollView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](#checkscrollbars)|スクロール ビューが水平方向と垂直スクロール バーを持つかどうかを示します。|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|スクロール領域の外側のビューの領域を塗りつぶします。|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|デバイス単位で現在のスクロール位置を取得します。|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|現在のマップ モード、サイズの合計をスクロール可能なビューの行とページのサイズを取得します。 サイズは、デバイス単位。|  
|[CScrollView::GetScrollPosition](#getscrollposition)|論理ユニットでは、現在のスクロール位置を取得します。|  
|[CScrollView::GetTotalSize](#gettotalsize)|論理ユニットでは、スクロール ビューの合計サイズを取得します。|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|フレームのサイズに合うようにビューのサイズが発生します。|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|論理単位で指定されている、指定された点にビューをスクロールします。|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|スケールの調整モードには、スクロール ビューを追加します。|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|スクロール ビューのマップ モード、全体のサイズ、および水平および垂直方向のスクロール量を設定します。|  
  
## <a name="remarks"></a>コメント  
 Standard から派生したクラスで自分のスクロールを処理する`CView`メッセージ マップをオーバーライドして[OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 `CScrollView`には、次の機能を追加、`CView`機能。  
  
-   ウィンドウとビューポートのサイズとマップ モードを管理します。  
  
-   スクロール バーのメッセージに応答して自動的にスクロールします。  
  
-   キーボード、非スクロールのマウス、または IntelliMouse ホイールからのメッセージに応答して自動的にスクロールします。  
  
 キーボードからのメッセージに対する応答には、自動的にスクロールするには、WM_KEYDOWN メッセージに追加して VK_DOWN、VK_PREV と呼び出しをテスト[SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597)します。  
  
 マウス ホイールを自分でメッセージ マップをオーバーライドしてスクロールを処理する[OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)と[OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel)メンバー関数。 場合と`CScrollView`、これらのメンバー関数の推奨される動作をサポートする[WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617)ホイールの回転メッセージです。  
  
 自動スクロールを活用するからビュー クラスを派生`CScrollView`の代わりにから`CView`します。 ビューが初めて作成すると、呼び出し、ドキュメントのサイズに基づいて、スクロール可能なビューのサイズを計算する場合、`SetScrollSizes`メンバー関数のいずれかのオーバーライドから[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)または[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)します。 (ドキュメントのサイズを照会する、独自のコードを記述する必要があります。 例については、次を参照してください、 [Scribble サンプル](../../visual-cpp-samples.md)。)。  
  
 呼び出し、`SetScrollSizes`メンバー関数は、ビューのマッピング モードでは、スクロール ビュー、および水平方向および垂直方向にスクロールする金額の合計サイズを設定します。 すべてのサイズは、論理ユニットでです。 ビューの論理サイズが、ドキュメントに格納されているデータから計算された通常が、場合によっては固定サイズを指定することがあります。 どちらの方法の例については、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)します。  
  
 論理ユニットに水平方向および垂直方向をスクロールする量を指定します。 既定では、ユーザーが、スクロール バーの突き出しスクロール ボックスの外側をクリックすると`CScrollView`「ページ」をスクロール ユーザーがスクロール バーの端にあるスクロール矢印をクリックすると`CScrollView`「行」にスクロール 既定では、ページには、ビューの合計サイズの 1/10 です。線は、1/10 ページ サイズです。 カスタム サイズを渡すことによってこれらの既定値を上書き、`SetScrollSizes`メンバー関数。 たとえば、現在のフォントで一定の割合の合計サイズと行の高さを垂直方向のサイズの幅を水平方向のサイズを設定する可能性があります。  
  
 スクロールなどではなく`CScrollView`ビューに現在のウィンドウ サイズを自動的にスケールできます。 このモードでは、ビューにスクロール バーがないと論理的なビューを拡大またはウィンドウのクライアント領域を正確に合わせて縮小します。 このスケールの調整機能を使用するのには、呼び出す[CScrollView::SetScaleToFitSize](#setscaletofitsize)します。 (いずれかを呼び出す`SetScaleToFitSize`または`SetScrollSizes`、両方ではありません)。  
  
 前に、`OnDraw`派生ビュー クラスのメンバー関数が呼び出されると、`CScrollView`のビューポートの原点が自動的に調整、`CPaintDC`デバイス コンテキスト オブジェクトに渡される`OnDraw`です。  
  
 スクロール ウィンドウのビューポートの原点を調整する`CScrollView`オーバーライド[付け](../../mfc/reference/cview-class.md#onpreparedc)します。 この調整が自動的に行わ、`CPaintDC`デバイス コンテキストを`CScrollView`に渡す`OnDraw`、呼び出す必要がありますが、 **CScrollView::OnPrepareDC**あなた自身の他のデバイス コンテキストを使用するなど、`CClientDC`です。 オーバーライドできます**CScrollView::OnPrepareDC**ペン、背景色、およびその他の描画属性を設定、スケーリングを実行する基本クラスを呼び出します。  
  
 次の場合に示すようにスクロール バーは、ビューの&3; か所に表示されます。  
  
-   使用してビューのスクロール バーのウィンドウの標準形式を設定できます、 **WS_HSCROLL**と**WS_VSCROLL**[Windows スタイル](../../mfc/reference/window-styles.md)します。  
  
-   フレームワークの場合に転送するビューを含むフレームにスクロール バー コントロールを追加することも`WM_HSCROLL`と`WM_VSCROLL`フレーム ウィンドウから現在アクティブなビューへのメッセージ。  
  
-   また、フレームワークに転送からのメッセージをスクロール、`CSplitterWnd`現在アクティブな分割ウィンドウ (ビュー) に分割線コントロールです。 設定すると、 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)共有スクロール バーを持つ、`CScrollView`オブジェクトがそれ自体を作成するのではなく、共有のものを使用します。  
  
 使用する方法について`CScrollView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecheckscrollbarsa--cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>CScrollView::CheckScrollBars  
 スクロール ビューが水平方向および垂直のバーを確認するのには、このメンバー関数を呼び出します。  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *bHasHorzBar*  
 アプリケーションが、水平スクロール バーを持つことを示します。  
  
 *bHasVertBar*  
 アプリケーションが、垂直スクロール バーを持つことを示します。  
  
##  <a name="a-namecscrollviewa--cscrollviewcscrollview"></a><a name="cscrollview"></a>CScrollView::CScrollView  
 `CScrollView` オブジェクトを構築します。  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>コメント  
 いずれかを呼び出す必要があります`SetScrollSizes`または`SetScaleToFitSize`スクロールする前にビューが使用されます。  
  
##  <a name="a-namefilloutsiderecta--cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>CScrollView::FillOutsideRect  
 呼び出す`FillOutsideRect`スクロール領域の外側に表示されるビューの領域を塗りつぶします。  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストが、読み込みが行われます。  
  
 `pBrush`  
 格納する領域を使用するブラシ。  
  
### <a name="remarks"></a>コメント  
 使用`FillOutsideRect`スクロール ビューの`OnEraseBkgnd`ハンドラー関数に過剰なバック グラウンドで再描画しないようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&164;](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="a-namegetdevicescrollpositiona--cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>CScrollView::GetDeviceScrollPosition  
 呼び出す`GetDeviceScrollPosition`水平および垂直方向の現在の位置のスクロール ボックス、スクロール バーの必要があります。  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スクロール ボックスとしてのデバイス単位で水平および垂直位置、`CPoint`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この座標ペアでは、ビューの左上隅がスクロールされたドキュメントの場所に対応しています。 これは、マウス デバイスの位置をスクロール表示デバイスの位置をオフセットするのに便利です。  
  
 `GetDeviceScrollPosition`デバイス単位で値を返します。 論理ユニットを実行する場合に、使用`GetScrollPosition`代わりにします。  
  
##  <a name="a-namegetdevicescrollsizesa--cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes`現在のマップ モード、サイズの合計をスクロール可能なビューの行とページのサイズを取得します。  
  
```  
void GetDeviceScrollSizes(
    int& nMapMode,  
    SIZE& sizeTotal,  
    SIZE& sizePage,  
    SIZE& sizeLine) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMapMode`  
 このビューの現在のマッピング モードを返します。 使用可能な値の一覧は、次を参照してください。`SetScrollSizes`します。  
  
 `sizeTotal`  
 デバイス単位でスクロール ビューの現在の合計サイズを返します。  
  
 `sizePage`  
 スクロール バーの軸でのクリックしてマウスへの応答では、各方向にスクロールする現在の水平および垂直方向の量を返します。 **Cx**メンバーには、水平方向の量が含まれています。 **Cy**メンバーには、垂直方向の量が含まれています。  
  
 `sizeLine`  
 スクロール バーの矢印でクリックしてマウスへの応答では、各方向にスクロールする現在の水平および垂直方向の量を返します。 **Cx**メンバーには、水平方向の量が含まれています。 **Cy**メンバーには、垂直方向の量が含まれています。  
  
### <a name="remarks"></a>コメント  
 サイズは、デバイス単位。 このメンバー関数と呼ばれることはほとんどありません。  
  
##  <a name="a-namegetscrollpositiona--cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>CScrollView::GetScrollPosition  
 呼び出す`GetScrollPosition`水平および垂直方向の現在の位置のスクロール ボックス、スクロール バーの必要があります。  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 水平および垂直方向の位置 (論理単位で) に応じて、スクロール ボックス、`CPoint`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この座標ペアでは、ビューの左上隅がスクロールされたドキュメントの場所に対応しています。  
  
 `GetScrollPosition`論理単位で値を返します。 デバイス単位にする場合は、使用`GetDeviceScrollPosition`代わりにします。  
  
##  <a name="a-namegettotalsizea--cscrollviewgettotalsize"></a><a name="gettotalsize"></a>CScrollView::GetTotalSize  
 呼び出す`GetTotalSize`スクロール ビューの現在の水平および垂直方向のサイズを取得します。  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 論理単位でスクロール ビューの合計サイズ。 水平方向のサイズは、 **cx**のメンバー、`CSize`の値を返します。 垂直方向のサイズは、 **cy**メンバーです。  
  
##  <a name="a-nameresizeparenttofita--cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>CScrollView::ResizeParentToFit  
 呼び出す`ResizeParentToFit`フレーム ウィンドウのサイズに合う、ビューのサイズをできるようにします。  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShrinkOnly*  
 実行するサイズ変更の種類。 既定値**TRUE**、該当する場合は、フレーム ウィンドウを縮小します。 大規模なビューまたはフレーム ウィンドウが小さいため、スクロール バーが表示されます。 値**FALSE**と正確にフレーム ウィンドウのサイズを変更するには、常に表示します。 これは、フレーム ウィンドウが大きすぎてマルチ ドキュメント インターフェイス (MDI) のフレーム ウィンドウまたは、画面内に収まるようにできるため多少危険です。  
  
### <a name="remarks"></a>コメント  
 MDI 子フレーム ウィンドウ内のビューに対してのみこれをお勧めします。 使用`ResizeParentToFit`で、`OnInitialUpdate`派生のハンドラー関数`CScrollView`クラスです。 このメンバー関数の例は、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)します。  
  
 `ResizeParentToFit`[ビュー] ウィンドウのサイズが設定されていると仮定します。 かどうか、ビュー ウィンドウのサイズが設定されていない場合に`ResizeParentToFit`が呼び出されると、アサーションが取得されます。 そうでないことを確認するには、呼び出す前に次の呼び出しを行う`ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView #&165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="a-namescrolltopositiona--cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>CScrollView::ScrollToPosition  
 呼び出す`ScrollToPosition`ビューの特定の時点までスクロールします。  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 論理ユニットでのスクロールをポイントします。 **X**メンバーが (より大きいまたはビューの合計サイズに達するまで、0 に等しい)、正の値にする必要があります。 場合も同様です、 **y**マッピング モードの場合、メンバー`MM_TEXT`します。 **Y**メンバーは負の値以外のモードのマッピングで`MM_TEXT`します。  
  
### <a name="remarks"></a>コメント  
 このポイントがウィンドウの左上隅にあるように、ビューがスクロールされます。 ビューに合わせてスケーリングされる場合、このメンバー関数は呼び出されません必要があります。  
  
##  <a name="a-namesetscaletofitsizea--cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>CScrollView::SetScaleToFitSize  
 呼び出す`SetScaleToFitSize`を現在のウィンドウのサイズにビューポートのサイズを自動的にスケール変更する場合します。  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeTotal`  
 水平方向および垂直方向のサイズをビューが拡大縮小されます。 スクロール ビューのサイズは、論理単位で測定されます。 水平方向のサイズが含まれている、 **cx**メンバーです。 垂直方向のサイズが含まれている、 **cy**メンバーです。 両方とも**cx**と**cy** 0 以上にする必要があります。  
  
### <a name="remarks"></a>コメント  
 スクロール バーを持つ論理ビューの一部だけ見える可能性がありますいつでもできます。 スケールの調整機能を持つビューにスクロール バーがないと論理的なビューを拡大またはウィンドウのクライアント領域を正確に合わせて縮小します。 ウィンドウのサイズを変更、ビューは、ウィンドウのサイズに基づく新しいスケールにそのデータを描画します。  
  
 通常の呼び出しを配置する`SetScaleToFitSize`のビューのオーバーライドで`OnInitialUpdate`メンバー関数。 自動スケーリングしたくない場合、`SetScrollSizes`メンバー関数を使用します。  
  
 `SetScaleToFitSize`「拡大に合わせて」操作を実装するために使用します。 使用`SetScrollSizes`スクロールを再初期化します。  
  
 `SetScaleToFitSize`[ビュー] ウィンドウのサイズが設定されていると仮定します。 かどうか、ビュー ウィンドウのサイズが設定されていない場合に`SetScaleToFitSize`が呼び出されると、アサーションが取得されます。 そうでないことを確認するには、呼び出す前に次の呼び出しを行う`SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView #&165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="a-namesetscrollsizesa--cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>CScrollView::SetScrollSizes  
 呼び出す`SetScrollSizes`とビューが更新しようとしています。  
  
```  
void SetScrollSizes(
    int nMapMode,  
    SIZE sizeTotal,  
    const SIZE& sizePage = sizeDefault,  
    const SIZE& sizeLine = sizeDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMapMode`  
 このビューに設定するマッピング モード。 次の値を使用できます。  
  
|マップ モード|論理ユニット|正の y 軸拡張しています.|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 ピクセル|下方向|  
|`MM_HIMETRIC`|0.01 mm|上位へ移動|  
|`MM_TWIPS`|1/1440 で|上位へ移動|  
|`MM_HIENGLISH`|0.001 インチ|上位へ移動|  
|`MM_LOMETRIC`|0.1 mm|上位へ移動|  
|`MM_LOENGLISH`|0.01 インチ|上位へ移動|  
  
 これらのモードのすべては、Windows によって定義されます。 2 つの標準マッピング モード`MM_ISOTROPIC`と`MM_ANISOTROPIC`、使用されていない`CScrollView`します。 クラス ライブラリには、`SetScaleToFitSize`メンバー関数をウィンドウ サイズに拡大または縮小します。 上記の表に&3; 番目の列では、座標の方向について説明します。  
  
 `sizeTotal`  
 スクロール ビューの合計サイズ。 **Cx**メンバーには、水平方向のエクステントが含まれています。 **Cy**メンバーには、垂直方向のエクステントが含まれています。 サイズは、論理ユニットでです。 両方とも**cx**と**cy** 0 以上にする必要があります。  
  
 `sizePage`  
 マウスへの応答では、各方向にスクロールする水平および垂直方向の量は、スクロール バーの軸をクリックします。 **Cx**メンバーには、水平方向の量が含まれています。 **Cy**メンバーには、垂直方向の量が含まれています。  
  
 `sizeLine`  
 マウスへの応答では、各方向にスクロールする水平および垂直方向の量は、スクロール バーの矢印をクリックします。 **Cx**メンバーには、水平方向の量が含まれています。 **Cy**メンバーには、垂直方向の量が含まれています。  
  
### <a name="remarks"></a>コメント  
 オーバーライドで呼び出して、`OnUpdate`ドキュメントが最初に表示されるなどのとき、またはサイズが変更されたときに、スクロールの特性を調整するためです。  
  
 おそらくと呼ばれるドキュメントのメンバー関数を呼び出すことによって、ビューの関連するドキュメントのサイズ情報を取得が通常`GetMyDocSize`、派生したドキュメント クラスを使用して指定します。 次のコードは、この方法を示しています。  
  
 [!code-cpp[NVC_MFCDocView #&166;](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 または、次のコードのように、固定サイズを設定する必要がある場合があります。  
  
 [!code-cpp[NVC_MFCDocView #&167;](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 除く Windows マッピング モードのいずれかにマッピング モードを設定する必要があります`MM_ISOTROPIC`または`MM_ANISOTROPIC`です。 制約のないマッピング モードを使用する場合を呼び出す、`SetScaleToFitSize`メンバー関数の代わりに`SetScrollSizes`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&168;](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&169;](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)

