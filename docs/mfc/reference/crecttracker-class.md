---
title: "CRectTracker クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
dev_langs:
- C++
helpviewer_keywords:
- displaying items
- CRectTracker class
- resizing items
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
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
ms.openlocfilehash: 444eab5969339cf2a3d5797807eae3dcad32a694
ms.lasthandoff: 02/24/2017

---
# <a name="crecttracker-class"></a>CRectTracker クラス
表示、移動、または異なる方法でのサイズを変更する項目を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[利用](#crecttracker)|`CRectTracker` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|四角形のサイズが変更されたときに呼び出されます。|  
|[CRectTracker::Draw](#draw)|四角形を描画します。|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|境界線を描画するときと呼ばれる、`CRectTracker`オブジェクトです。|  
|[CRectTracker::GetHandleMask](#gethandlemask)|マスクを取得すると呼ばれる、`CRectTracker`アイテムのサイズ変更ハンドル。|  
|[CRectTracker::GetTrueRect](#gettruerect)|サイズ変更ハンドルを含む四角形の幅と高さを返します。|  
|[CRectTracker::HitTest](#hittest)|関連するカーソルの現在位置を返す、`CRectTracker`オブジェクトです。|  
|[CRectTracker::NormalizeHit](#normalizehit)|ヒット テストのコードを正規化します。|  
|[CRectTracker::OnChangedRect](#onchangedrect)|四角形のサイズを変更または移動したときに呼び出されます。|  
|[CRectTracker::SetCursor](#setcursor)|上の四角形の位置によって、カーソルを設定します。|  
|[反転](#track)|四角形を操作できます。|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|ユーザーが「ラバー バンド」を選択をできます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|サイズ変更ハンドルのサイズを決定します。|  
|[CRectTracker::m_nStyle](#m_nstyle)|トラッカーの現在のスタイル。|  
|[裏返し](#m_rect)|四角形のピクセル単位で現在の位置。|  
|[CRectTracker::m_sizeMin](#m_sizemin)|最小の四角形の幅と高さを決定します。|  
  
## <a name="remarks"></a>コメント  
 `CRectTracker`基本クラスはありません。  
  
 ただし、`CRectTracker`クラスがグラフィカル インターフェイスを使用して OLE アイテムと対話するユーザーを許可するように設計された、その使用は OLE 対応アプリケーションに制限されません。 使用できるこのようなユーザー インターフェイスが必要な任意の場所。  
  
 `CRectTracker`枠線が実線できますまたは点線。 アイテムの破線の境界線または斜線パターン、アイテムのさまざまな状態を示すために重なって表示できます。 8 つのサイズ変更ハンドルを配置するには、外部または内部のいずれかのアイテムの罫線。 (サイズ変更ハンドルの詳細については、次を参照してください[GetHandleMask](#gethandlemask)。)。最後に、`CRectTracker`サイズ変更時に、項目の向きを変更することができます。  
  
 使用する`CRectTracker`、構築、`CRectTracker`オブジェクトし、どの表示状態は、初期化を指定します。 関連付けられている OLE アイテムの現在の状態に対するユーザーの視覚的フィードバックを与えるには、このインターフェイスを使用することができますし、`CRectTracker`オブジェクトです。  
  
 使用する方法について`CRectTracker`、記事を参照して[トラッカー](../../mfc/trackers.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRectTracker`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="adjustrect"></a>CRectTracker::AdjustRect  
 サイズ変更ハンドルを使用して追跡四角形のサイズが変更されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHandle`  
 使用されるハンドルのインデックス。  
  
 `lpRect`  
 四角形の現在のサイズへのポインター。 (四角形のサイズが、高さと幅によって指定します。)  
  
### <a name="remarks"></a>コメント  
 この関数の既定の動作が変更される場合にのみ、四角形の向きをにより`Track`と`TrackRubberBand`許可と呼ばれます。  
  
 ドラッグ操作中に追跡四角形の調整を制御するには、この関数をオーバーライドします。 によって指定された座標を調整する方法の&1; つは、`lpRect`を返す前にします。  
  
 直接サポートされていない特殊な機能`CRectTracker`など、グリッドにスナップや縦横比の保持は、この関数をオーバーライドすることで実装できます。  
  
##  <a name="crecttracker"></a>利用  
 作成して初期化、`CRectTracker`オブジェクトです。  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSrcRect`  
 四角形オブジェクトの座標です。  
  
 `nStyle`  
 スタイルを指定、`CRectTracker`オブジェクトです。 次のスタイルがサポートされています。  
  
- **CRectTracker::solidLine**四角形の境界線の実線を使用します。  
  
- **CRectTracker::dottedLine**四角形の境界線の点線を使用します。  
  
- **CRectTracker::hatchedBorder**四角形の境界線にハッチ パターンを使用します。  
  
- **CRectTracker::resizeInside**サイズ変更ハンドルの四角形の内側に配置します。  
  
- **CRectTracker::resizeOutside**四角形の外側にあるハンドルのサイズを変更します。  
  
- **CRectTracker::hatchInside** Hatched パターンは、四角形全体をカバーします。  
  
### <a name="remarks"></a>コメント  
 既定のコンス トラクター、`CRectTracker`から値を持つオブジェクト`lpSrcRect`し、その他のシステムの既定のサイズを初期化します。 パラメーターなしで、オブジェクトが作成された場合、`m_rect`と`m_nStyle`データ メンバーは初期化されていません。  
  
##  <a name="draw"></a>CRectTracker::Draw  
 四角形の外枠と内部の領域を描画するには、この関数を呼び出します。  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画を行うデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 トラッカーのスタイルでは、描画を行う方法を決定します。 コンス トラクターを参照してください`CRectTracker`使用可能なスタイルの詳細についてです。  
  
##  <a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect  
 トラッカーの位置が変更されるたびに、フレームワークが呼び出します内ときに、`Track`または`TrackRubberBand`メンバー関数。  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 ポインター、`RECT`を描画する四角形が含まれています。  
  
 `pWndClipTo`  
 四角形をクリッピングするに使用するウィンドウへのポインター。  
  
 `pDC`  
 描画を行うデバイス コンテキストへのポインター。  
  
 `pWnd`  
 描画を迎えるウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装への呼び出しは、 `CDC::DrawFocusRect`、ピリオドで区切られた四角形を描画します。  
  
 追跡操作中にさまざまなフィードバックを提供するには、この関数をオーバーライドします。  
  
##  <a name="gethandlemask"></a>CRectTracker::GetHandleMask  
 フレームワークでは、四角形のサイズ変更ハンドルのマスクを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マスク、`CRectTracker`アイテムのサイズ変更ハンドル。  
  
### <a name="remarks"></a>コメント  
 サイズ変更ハンドルは、両側または四角形の角に表示され、四角形のサイズと形状を制御するアクセス許可。  
  
 四角形が 8 のサイズ変更ハンドルが 0 ~ 7 の番号です。 各サイズ変更ハンドルによってを表されるビット マスクです。そのビットの値は 2 ^ *n*ここで、 *n*サイズ変更ハンドルの数です。 ビット 0 ~ 3 は、時計回りに左から開始角のサイズ変更ハンドルに対応します。 ビット 4 ~ 7 の側面に対応しているにサイズ変更ハンドルが時計回り上部で開始を指定します。 次の図は、四角形のサイズ変更を処理し、それに対応するハンドル番号と値のサイズを変更します。  
  
 ![ハンドル番号のサイズ変更](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 既定の実装**GetHandleMask**サイズ変更ハンドルが表示されるようにビットのマスクを返します。 1 つのビットがオンの場合は、対応するサイズ変更ハンドルが描画されます。  
  
 指定したサイズ変更ハンドルを表示または非表示には、このメンバー関数をオーバーライドします。  
  
##  <a name="gettruerect"></a>CRectTracker::GetTrueRect  
 四角形の座標を取得するには、この関数を呼び出します。  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTrueRect`  
 ポインター、`RECT`の座標をデバイスを含む構造を`CRectTracker`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 四角形のディメンションには、外側の境界線上にある任意のサイズ変更ハンドルの幅と高さが含まれます。 `lpTrueRect`デバイス座標で正規化された四角形は、常にします。  
  
##  <a name="hittest"></a>CRectTracker::HitTest  
 ユーザーがサイズ変更ハンドルを取得したかどうかを確認するには、この関数を呼び出します。  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テストには、デバイスの座標の点。  
  
### <a name="return-value"></a>戻り値  
 返される値は、その列挙型に基づく**CRectTracker::TrackerHit**し、次の値のいずれかのことができます。  
  
- **CRectTracker::hitNothing** –&1;  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize  
 サイズ (ピクセル単位) の`CRectTracker`ハンドルのサイズを変更します。  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>コメント  
 システムの既定値で初期化されます。  
  
##  <a name="m_rect"></a>裏返し  
 クライアント座標 (ピクセル単位) で、四角形の現在の位置。  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>CRectTracker::m_sizeMin  
 四角形の最小サイズ。  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>コメント  
 両方の既定値**cx**と**cy**罫線の幅に関する既定のシステム値から計算されます。 このデータ メンバーのみが使用、`AdjustRect`メンバー関数。  
  
##  <a name="m_nstyle"></a>CRectTracker::m_nStyle  
 四角形の現在のスタイル。  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>コメント  
 参照してください[利用](#crecttracker)できるスタイルの一覧にします。  
  
##  <a name="normalizehit"></a>CRectTracker::NormalizeHit  
 反転された可能性があるハンドルを変換するには、この関数を呼び出します。  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nHandle`  
 ユーザーが選択されているハンドルです。  
  
### <a name="return-value"></a>戻り値  
 正規化されたハンドルのインデックス。  
  
### <a name="remarks"></a>コメント  
 `CRectTracker::Track`または`CRectTracker::TrackRubberBand`と呼びます許可を反転するには、そのは四角形を x 軸、y 軸、またはその両方に反転させることにします。 この場合、`HitTest`は四角形反転がハンドルを返します。 これは、フィードバックが変更される四角形のデータ構造の部分ではなく四角形の画面上の位置に依存するためいないカーソルのフィードバックの描画に適したです。  
  
##  <a name="onchangedrect"></a>CRectTracker::OnChangedRect  
 トラッカーの四角形の呼び出し中に変更されるたびに、フレームワークが呼び出します`Track`します。  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectOld*  
 古いデバイス座標を格納して、`CRectTracker`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 時にこの関数は、すべてのフィードバックで描画された`DrawTrackerRect`は削除されました。 この関数の既定の実装は、何も行いません。  
  
 四角形のサイズが変更された後、操作を実行している場合は、この関数をオーバーライドします。  
  
##  <a name="setcursor"></a>CRectTracker::SetCursor  
 上では、カーソルの形状を変更するには、この関数を呼び出して、`CRectTracker`のオブジェクトの領域です。  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを現在含まれているウィンドウへのポインター。  
  
 `nHitTest`  
 前のヒット テストの結果から、`WM_SETCURSOR`メッセージです。  
  
### <a name="return-value"></a>戻り値  
 前の検索結果がトラッカー四角形経由の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、処理するウィンドウの関数内から呼び出す、`WM_SETCURSOR`メッセージ (通常`OnSetCursor`)。  
  
##  <a name="track"></a>反転  
 四角形のサイズを変更するユーザー インターフェイスを表示するには、この関数を呼び出します。  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 四角形を含むウィンドウのオブジェクト。  
  
 `point`  
 クライアント領域を基準と現在のマウス位置のデバイス座標です。  
  
 `bAllowInvert`  
 場合**TRUE**、x 軸または y 軸に沿って反転以外の場合、四角形を指定できます**FALSE**します。  
  
 `pWndClipTo`  
 このウィンドウは、描画操作は、クリップされます。 場合**NULL**、`pWnd`クリッピング四角形として使用します。  
  
### <a name="return-value"></a>戻り値  
 ESC キーが押された場合、追跡が停止、トラッカーに格納されている四角形が変更されないため、0 が返されます。 変更がコミットされた場合は、マウスを移動して、マウスの左ボタンを放すで、新しい位置とサイズがトラッカーの四角形に記録がされ、0 以外の値が返されます。  
  
### <a name="remarks"></a>コメント  
 通常、関数を処理するアプリケーションの内部から呼び出されます、`WM_LBUTTONDOWN`メッセージ (通常`OnLButtonDown`)。  
  
 この関数は、ユーザーがマウスの左ボタンを離した、ESC キーを押すかマウスの右ボタンを押すまで、マウスをキャプチャします。 フィードバックが呼び出すことによって更新されたユーザーがマウス カーソルを移動した`DrawTrackerRect`と`OnChangedRect`です。  
  
 場合`bAllowInvert`は**TRUE**が x 軸または y 軸にトラッキング四角形を反転することができます。  
  
##  <a name="trackrubberband"></a>CRectTracker::TrackRubberBand  
 ラバー バンド選択を行うには、この関数を呼び出します。  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 四角形を含むウィンドウのオブジェクト。  
  
 `point`  
 クライアント領域を基準と現在のマウス位置のデバイス座標です。  
  
 `bAllowInvert`  
 場合**true の場合、** x 軸または y 軸に沿って反転以外の場合、四角形を指定できます**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 マウスが移動し、四角形は空です。 ない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、関数を処理するアプリケーションの内部から呼び出された、`WM_LBUTTONDOWN`メッセージ (通常`OnLButtonDown`)。  
  
 この関数は、ユーザーがマウスの左ボタンを離した、ESC キーを押すかマウスの右ボタンを押すまで、マウスをキャプチャします。 フィードバックが呼び出すことによって更新されたユーザーがマウス カーソルを移動した`DrawTrackerRect`と`OnChangedRect`です。  
  
 追跡は右下のハンドルからラバー バンド タイプを選択した場合、実行されます。 反転が許可された場合、四角形がいずれかを左またはし右下をドラッグによるサイズ変更できます。  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプルの追跡ツール](../../visual-cpp-samples.md)   
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleResizeBar クラス](../../mfc/reference/coleresizebar-class.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)

