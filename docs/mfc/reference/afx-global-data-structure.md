---
title: "AFX_GLOBAL_DATA 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GLOBAL_DATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_GLOBAL_DATA 構造体"
  - "AFX_GLOBAL_DATA コンストラクター"
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: 30
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFX_GLOBAL_DATA 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`AFX_GLOBAL_DATA` 構造体は、フレームワークを管理するため、またはアプリケーションの外観および動作をカスタマイズするために使用されるフィールドおよびメソッドを格納します。  
  
## <a name="syntax"></a>構文  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|`AFX_GLOBAL_DATA` 構造体を構築します。|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::CleanUp](#afx_global_data__cleanup)|ブラシ、フォント、DLL など、フレームワークにより割り当てられたリソースを解放します。|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#afx_global_data__d2d1makerotatematrix)|指定した点を中心に指定した角度ずつ回転する回転変換を作成します。|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#afx_global_data__drawparentbackground)|指定領域にコントロールの親の背景を描画します。|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#afx_global_data__drawtextonglass)|指定されたテーマの視覚スタイルで、指定されたテキストを描画します。|  
|[AFX_GLOBAL_DATA::ExcludeTag](#afx_global_data__excludetag)|指定された XML タグ ペアを、指定されたバッファーから削除します。|  
|[AFX_GLOBAL_DATA::GetColor](#afx_global_data__getcolor)|指定されたユーザー インターフェイス要素の現在の色を取得します。|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#afx_global_data__getdirect2dfactory)|グローバル データに格納されている `ID2D1Factory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|  
|[AFX_GLOBAL_DATA::GetHandCursor](#afx_global_data__gethandcursor)|手の形をした組み込みカーソル (識別子は `IDC_HAND`) を取得します。|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#afx_global_data__getitaskbarlist)|ITaskBarList インターフェイスへのポインターを作成し、グローバル データに格納します。|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#afx_global_data__getitaskbarlist3)|ITaskBarList3 インターフェイスへのポインターを作成し、グローバル データに格納します。|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#afx_global_data__getnonclientmetrics)|最小化されていないウィンドウの非クライアント領域に関連付けられたメトリックを取得します。|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#afx_global_data__getshellautohidebars)|シェルの自動非表示バーの位置を決定します。|  
|[AFX_GLOBAL_DATA::GetTextHeight](#afx_global_data__gettextheight)|現在のフォントのテキスト文字の高さを取得します。|  
|[AFX_GLOBAL_DATA::GetWICFactory](#afx_global_data__getwicfactory)|グローバル データに格納されている `IWICImagingFactory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#afx_global_data__getwritefactory)|グローバル データに格納されている `IDWriteFactory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|`D2D`、 `DirectWrite`、および `WIC` の各ファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#afx_global_data__is32biticons)|定義済みの 32 ビット アイコンがサポートされているかどうかを示します。|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|`D2D` が初期化されているかどうかを調べます。|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#afx_global_data__isdwmcompositionenabled)|Windows の [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) のメソッドを簡単な方法で呼び出すことができます。|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#afx_global_data__ishighcontrastmode)|イメージが現在、ハイ コントラストで表示されているかどうかを判定します。|  
|[AFX_GLOBAL_DATA::OnSettingChange](#afx_global_data__onsettingchange)|デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#afx_global_data__registerwindowclass)|指定された MFC ウィンドウ クラスを登録します。|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#afx_global_data__releasetaskbarrefs)|GetITaskbarList メソッドおよび GetITaskbarList3 メソッドを通じて取得されたインターフェイスを解放します。|  
|[AFX_GLOBAL_DATA::Resume](#afx_global_data__resume)|Windows の [テーマと視覚スタイル](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)をサポートするメソッドにアクセスする内部関数ポインターを再初期化します。|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#afx_global_data__setlayeredattrib)|Windows の [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) メソッドを簡単な方法で呼び出すことができます。|  
|[AFX_GLOBAL_DATA::SetMenuFont](#afx_global_data__setmenufont)|指定された論理フォントを作成します。|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#afx_global_data__shellcreateitemfromparsingname)|解析名からシェル項目オブジェクトを作成して初期化します。|  
|[AFX_GLOBAL_DATA::UpdateFonts](#afx_global_data__updatefonts)|フレームワークにより使用される論理フォントを再初期化します。|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#afx_global_data__updatesyscolors)|フレームワークで使用される色、色深度、ブラシ、ペン、およびイメージを初期化します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__enableaccessibilitysupport)|Microsoft Active Accessibility のサポートを有効または無効にします。 Active Accessibility は、ユーザー インターフェイス要素に関する情報を公開するための信頼できる方法を提供します。|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__isaccessibilitysupport)|Microsoft Active Accessibility のサポートが有効かどうかを示します。|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#afx_global_data__iswindowslayersupportavailable)|オペレーティング システムがレイヤード ウィンドウをサポートするかどうかを示します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#afx_global_data__bisosalphablendingsupport)|現在のオペレーティング システムがアルファ ブレンドをサポートするかどうかを示します。|  
|[AFX_GLOBAL_DATA::bIsWindows7](#afx_global_data__biswindows7)|アプリケーションが Windows 7 OS 以上で実行されているかどうかを示します。|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#afx_global_data__clractivecaptiongradient)|アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#afx_global_data__clrinactivecaptiongradient)|アクティブでないキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#afx_global_data__m_busebuiltin32biticons)|事前定義された 32 ビット カラー アイコンと低解像度のアイコンのどちらをフレームワークで使用するかを指定します。|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#afx_global_data__m_busesystemfont)|メニュー、ツール バー、およびリボンに対してシステム フォントが使用されるかどうかを示します。|  
|[AFX_GLOBAL_DATA::m_hcurHand](#afx_global_data__m_hcurhand)|手の形のカーソルのハンドルを格納します。|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#afx_global_data__m_hcurstretch)|水平方向の伸縮カーソルのハンドルを格納します。|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#afx_global_data__m_hcurstretchvert)|垂直方向の伸縮カーソルのハンドルを格納します。|  
|[AFX_GLOBAL_DATA::m_hiconTool](#afx_global_data__m_hicontool)|ツール アイコンのハンドルを格納します。|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#afx_global_data__m_nautohidetoolbarmargin)|左端の自動的に隠すツール バーからドッキング バーの左側までのオフセットを指定します。|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#afx_global_data__m_nautohidetoolbarspacing)|自動的に隠すツール バーの間の間隔を指定します。|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#afx_global_data__m_ndragframethicknessdock)|ドッキング状態を知らせるのに使用するドラッグ フレームの幅を指定します。|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#afx_global_data__m_ndragframethicknessfloat)|フローティング状態を知らせるのに使用するドラッグ フレームの幅を指定します。|  
  
## <a name="remarks"></a>コメント  
 `AFX_GLOBAL_DATA` 構造体内のデータのほとんどは、アプリケーションの起動時に初期化されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxglobals.h  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="a-nameafxglobaldatabisosalphablendingsupporta-afxglobaldatabisosalphablendingsupport"></a><a name="afx_global_data__bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
オペレーティング システムがアルファ ブレンドをサポートしているかどうかを示します。  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
## <a name="remarks"></a>コメント  
 `TRUE` アルファ ブレンドがサポートされていることを示します。それ以外の場合、 `FALSE`です。  
  

## <a name="a-nameafxglobaldatacleanupa-afxglobaldatacleanup"></a><a name="afx_global_data__cleanup"></a> AFX_GLOBAL_DATA::CleanUp
ブラシ、フォント、DLL など、フレームワークにより割り当てられたリソースを解放します。  
  
  
```  
void CleanUp();
```  
## <a name="a-nameafxglobaldatad2d1makerotatematrixa-afxglobaldatad2d1makerotatematrix"></a><a name="afx_global_data__d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
指定した点を中心に指定した角度ずつ回転する回転変換を作成します。  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
#### <a name="parameters"></a>パラメーター  
 `angle`  
 時計回りの回転角度 (度単位)。  
  
 `center`  
 回転の中心点。  
  
 `matrix`  
 このメソッドが戻るときに、新しい回転変換が含まれています。 このパラメーターには、記憶域を割り当てる必要があります。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合や、エラー値を返します。  
  
## <a name="a-nameafxglobaldatadrawparentbackgrounda-afxglobaldatadrawparentbackground"></a><a name="afx_global_data__drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
指定領域にコントロールの親の背景を描画します。  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 コントロールのウィンドウへのポインター。  
  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `lpRect`  
 描画する領域に外接する四角形へのポインター。 既定値は `NULL` です。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。  
  
## <a name="a-nameafxglobaldatadrawtextonglassa-afxglobaldatadrawtextonglass"></a><a name="afx_global_data__drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
指定されたテーマの視覚スタイルで、指定されたテキストを描画します。  
  
  
```  
BOOL DrawTextOnGlass(
    HTHEME hTheme,   
    CDC* pDC,   
    int iPartId,   
    int iStateId,   
    CString strText,   
    CRect rect,   
    DWORD dwFlags,   
    int nGlowSize = 0,   
    COLORREF clrText = (COLORREF)-1);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `hTheme`  
 ウィンドウのテーマ データのハンドル、または `NULL`。 このパラメーターが `NULL` ではなく、テーマがサポートされている場合、フレームワークは、指定されたテーマを使用してテキストを描画します。 それ以外の場合、フレームワークは、テーマを使用せずにテキストを描画します。  
  
 [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) メソッドを使用して `HTHEME`を作成します。  
  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `iPartId`  
 目的のテキストの外観を備えたコントロールのパーツ。 詳細については、「 [Parts and States (パーツと状態)](http://msdn.microsoft.com/library/windows/desktop/bb773210)」の表の「Parts (パーツ)」列を参照してください。 この値が 0 の場合、テキストは既定のフォント、またはデバイス コンテキストに選択されているフォントで描画されます。  
  
 [入力] `iStateId`  
 目的のテキストの外観を備えたコントロールの状態。 詳細については、「 [Parts and States (パーツと状態)](http://msdn.microsoft.com/library/windows/desktop/bb773210)」の表の「States (状態)」列を参照してください。  
  
 [入力] `strText`  
 描画するテキスト。  
  
 [入力] `rect`  
 指定されたテキストが描画される領域の境界。  
  
 [入力] `dwFlags`  
 指定されたテキストの描画方法を指定するフラグのビットごとの組み合わせ (OR)。  
  
 場合、 `hTheme` パラメーターは `NULL` テーマがサポートされていて、有効になっていないか、 `nFormat` のパラメーター、 [CDC::DrawText](../Topic/CDC%20Class.md#cdc__drawtext) メソッドは、有効なフラグを表します。 テーマがサポートされている場合は、 `dwFlags` DrawThemeTextEx [メソッドの](http://msdn.microsoft.com/library/windows/desktop/bb773317) パラメーターで有効なフラグを記述します。  
  
 [入力] `nGlowSize`  
 指定されたテキストを描画する前に背景に描画される光彩効果のサイズ。 既定値は 0 です。  
  
 [入力] `clrText`  
 指定されたテキストの描画に使用される色。 既定値は既定の色です。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` テーマを使用して、指定したテキストを描画する場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 テーマは、アプリケーションの視覚スタイルを定義します。 `hTheme` パラメーターが `NULL`の場合、 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) メソッドがサポートされていない場合、または [デスクトップ ウィンドウ マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) の構成が無効になっている場合は、テキストの描画にテーマが使用されません。  
  
 
## <a name="see-also"></a>関連項目  
 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [パーツと状態](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../Topic/CDC%20Class.md#cdc__drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [デスクトップ ウィンドウ マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 合成を有効化と制御](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataenableaccessibilitysupporta-afxglobaldataenableaccessibilitysupport"></a><a name="afx_global_data__enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Microsoft Active Accessibility のサポートを有効または無効にします。  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` ユーザー補助のサポートを有効にするには `FALSE` ユーザー補助のサポートを無効にします。 既定値は `TRUE` です。  
  
## <a name="remarks"></a>コメント  
 Active Accessibility は、アプリケーションや、Windows オペレーティング システム間の共同作業支援技術製品を向上できる COM ベース テクノロジです。 ユーザー インターフェイス要素に関する情報を公開するための信頼性の高い方法を提供します。 ただし、Microsoft UI オートメーションと呼ばれる新しいユーザー補助モデルでは、使用できるようになりました。 2 つのテクノロジの比較では、次を参照してください。 [UI オートメーションと Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)します。  
  
 使用して、 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md) Microsoft Active Accessibility のサポートが有効になっているかどうかを決定する方法です。  
  
 
## <a name="see-also"></a>関連項目  
 [UI オートメーションと Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md)

## <a name="a-nameafxglobaldataexcludetaga-afxglobaldataexcludetag"></a><a name="afx_global_data__excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
指定された XML タグ ペアを、指定されたバッファーから削除します。  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `strBuffer`  
 テキストのバッファー。  
  
 [入力] `lpszTag`  
 タグと終了の XML タグのペアの名前。  
  
 [出力] `strTag`  
 このメソッドが戻るとき、 `strTag` パラメーターで指定したタグは開始タグと終了 XML の間で、テキストが含まれる、 `lpszTag` パラメーター。 先頭または末尾の空白は結果から除去します。  
  
 [入力] `bIsCharsList`  
 `TRUE` 記号のエスケープ文字に変換する、 `strTag` を実際のエスケープ文字; パラメーター `FALSE` 変換を実行しないことです。既定値は `FALSE`です。 詳細については、「解説」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 XML タグ ペアはのタグと終了を開始および指定したバッファー内のテキストの実行の終了を示すタグをという名前で構成されます。  `strBuffer` パラメーターは、バッファーを指定し、 `lpszTag` パラメーター XML タグの名前を指定します。  
  
 次の表に、記号を使用して、指定したバッファー内のエスケープ文字のセットをエンコードします。 指定 `TRUE` の `bIsCharsList` 内のシンボルを変換するパラメーター、 `strTag` パラメーターの実際のエスケープ文字にします。 次の表には、 [_T()](../../c-runtime-library/data-type-mappings.md) 記号を指定し、文字の文字列をエスケープするマクロ。  
  
|シンボル|エスケープ文字|  
|------------|----------------------|  
|_T("\\\t")|_T("\t")|  
|_T("\\\n")|_T("\n")|  
|_T("\\\r")|_T("\r")|  
|_T("\\\b")|_T("\b")|  
|_T("LT")|_T("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="a-nameafxglobaldatagetcolora-afxglobaldatagetcolor"></a><a name="afx_global_data__getcolor"></a> AFX_GLOBAL_DATA::GetColor
指定されたユーザー インターフェイス要素の現在の色を取得します。  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `nColor`  
 色を取得、ユーザー インターフェイス要素を指定する値。 有効な値の一覧は、次を参照してください。、 `nIndex` のパラメーター、 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) メソッドです。  
  
## <a name="return-value"></a>戻り値  
 指定されたユーザー インターフェイス要素の RGB 色の値。 詳細については、「解説」を参照してください。  
  
## <a name="remarks"></a>コメント  
 場合、 `nColor` パラメーターが範囲外、戻り値は 0 です。 0 は有効な RGB 値でもあるので、システム カラーが現在のオペレーティング システムでサポートされているかどうかを判断するのにこの方法を使用できません。 代わりに、使用、 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) を返すメソッド `NULL` 色がサポートされていない場合。  
  
## <a name="see-also"></a>関連項目  

 [GetSysColor 関数](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="a-nameafxglobaldatagetdirect2dfactorya-afxglobaldatagetdirect2dfactory"></a><a name="afx_global_data__getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 グローバル データに格納されている ID2D1Factory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
## <a name="return-value"></a>戻り値  
 ID2D1Factory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗した場合は NULL または現在のオペレーティング システムへのポインターは、D2D サポートを必要はありません。  
  
AFX_GLOBAL_DATA::GetHandCursor が手の形のような定義済みのカーソルを取得し、識別子を持つは `IDC_HAND`です。  
  
  
```  
HCURSOR GetHandCursor();
```  
  
## <a name="return-value"></a>戻り値  
 手形カーソルのハンドル。  

## <a name="a-nameafxglobaldatagetnonclientmetricsa-afxglobaldatagetnonclientmetrics"></a><a name="afx_global_data__getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
最小化されていないウィンドウの非クライアント領域に関連付けられたメトリックを取得します。  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `info`  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) を最小化されていないウィンドウの非クライアント領域に関連付けられた拡張性の高いメトリックを含む構造体。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。  
 
  
## <a name="see-also"></a>関連項目   
 [NONCLIENTMETRICS 構造体](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="a-nameafxglobaldatagettextheighta-afxglobaldatagettextheight"></a><a name="afx_global_data__gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 現在のフォントのテキスト文字の高さを取得します。  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `bHorz`  
 `TRUE` テキストを水平方向に実行すると、文字の高さを取得するには `FALSE` テキストを垂直方向に実行すると、文字の高さを取得します。 既定値は `TRUE` です。  
  
## <a name="return-value"></a>戻り値  
 測定は、現在のフォントの高さ。  
  
## <a name="a-nameafxglobaldatagetwicfactorya-afxglobaldatagetwicfactory"></a><a name="afx_global_data__getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
グローバル データに格納されている IWICImagingFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
## <a name="return-value"></a>戻り値  
 IWICImagingFactory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗した場合は NULL または現在のオペレーティング システムへのポインターは、WIC サポートを必要はありません。  
  
## <a name="a-nameafxglobaldatagetwritefactorya-afxglobaldatagetwritefactory"></a><a name="afx_global_data__getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
グローバル データに格納されている IDWriteFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
## <a name="return-value"></a>戻り値  
 IDWriteFactory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗した場合は NULL または現在のオペレーティング システムへのポインターは、DirectWrite のサポートを必要はありません。  
 
## <a name="a-nameafxglobaldatainitd2da-afxglobaldatainitd2d"></a><a name="afx_global_data__initd2d"></a> AFX_GLOBAL_DATA::InitD2D
D2D、DirectWrite と WIC のファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
#### <a name="parameters"></a>パラメーター  
 `d2dFactoryType`  
 D2D ファクトリとリソースのスレッド モデルが作成されます。  
  
 `writeFactoryType`  
 書き込みのファクトリ オブジェクトが共有か分離かどうかを指定する値  
  
## <a name="return-value"></a>戻り値  
 かどうか、ファクトリが intilalizrd、false の場合、それ以外の場合は TRUE を返します  
  
## <a name="a-nameafxglobaldatais32biticonsa-afxglobaldatais32biticons"></a><a name="afx_global_data__is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
定義済みの 32 ビット アイコンがサポートされているかどうかを示します。  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` 定義済みの 32 ビット アイコンがサポートされている場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 このメソッドが戻る `TRUE` フレームワークは、32 ビットの組み込みアイコンをサポートしている場合、オペレーティング システムは、16 ビット/ピクセル以上をサポートしている場合とイメージがハイ コントラストで表示されていない場合。  
  
## <a name="a-nameafxglobaldataisaccessibilitysupporta-afxglobaldataisaccessibilitysupport"></a><a name="afx_global_data__isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Microsoft Active Accessibility のサポートが有効かどうかを示します。  
  
  
```  
BOOL IsAccessibilitySupport() const;

 
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` ユーザー補助のサポートが有効の場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 Microsoft Active Accessibility は、アプリケーションにアクセスできるように、以前のソリューションをしました。 Microsoft UI オートメーションは Microsoft Windows の新しいユーザー補助モデルは、目的は、支援技術製品のニーズに対処して、自動テスト ツールです。 詳細については、次を参照してください。 [UI オートメーションと Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)します。  
  
 使用して、 [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__EnableAccessibilitySupport.md) メソッドを有効にする、または Active Accessibility のサポートを無効にします。  
  

## <a name="see-also"></a>関連項目  
 [UI オートメーションと Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)

## <a name="a-nameafxglobaldataisd2dinitializeda-afxglobaldataisd2dinitialized"></a><a name="afx_global_data__isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 D2D が初期化されたかどうかを決定します。  
  
  
```  
BOOL IsD2DInitialized() const;

 
```  
  
## <a name="return-value"></a>戻り値  
 D2D の初期化された場合は TRUE。それ以外の場合は FALSE。  
  
## <a name="a-nameafxglobaldataisdwmcompositionenableda-afxglobaldataisdwmcompositionenabled"></a><a name="afx_global_data__isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Windows の [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) のメソッドを簡単な方法で呼び出すことができます。  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` 場合 [デスクトップ ウィンドウ マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) の構成を有効にするそれ以外の場合、 `FALSE`です。  
  
## <a name="see-also"></a>関連項目    
 [デスクトップ ウィンドウ マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 合成を有効化と制御](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataishighcontrastmodea-afxglobaldataishighcontrastmode"></a><a name="afx_global_data__ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 イメージが現在、ハイ コントラストで表示されているかどうかを判定します。    
```  
BOOL IsHighContrastMode() const;

 
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` イメージは黒と白のハイ コントラスト モードで現在表示されている場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 黒のハイ コントラスト モードでは、光が当たる部分のエッジが白、背景が黒にします。 白のハイ コントラスト モードの場合は、エッジの光が当たる部分が黒、バック グラウンドは白です。  
  
## <a name="a-nameafxglobaldataiswindowslayersupportavailablea-afxglobaldataiswindowslayersupportavailable"></a><a name="afx_global_data__iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
オペレーティング システムがレイヤード ウィンドウをサポートするかどうかを示します。  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const;

 
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` レイヤード ウィンドウがサポートされている場合それ以外の場合、 `FALSE`です。  
  
## <a name="remarks"></a>コメント  
 レイヤード ウィンドウはサポートされている場合 *スマート ドッキング* マーカーがレイヤード ウィンドウを使用します。  
  
## <a name="a-nameafxglobaldatambusebuiltin32biticonsa-afxglobaldatambusebuiltin32biticons"></a><a name="afx_global_data__m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
事前定義された 32 ビット カラー アイコンと低解像度のアイコンのどちらをフレームワークで使用するかを指定します。  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
## <a name="remarks"></a>コメント  
 `TRUE` フレームワークが 32 ビット カラー アイコンを使用することを指定します。 `FALSE` 低解像度アイコンを指定します。  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターにこのメンバーは初期化 `TRUE`します。  
  
 このメンバーは、アプリケーションの起動時に設定する必要があります。  
  
## <a name="a-nameafxglobaldatambusesystemfonta-afxglobaldatambusesystemfont"></a><a name="afx_global_data__m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
メニュー、ツール バー、およびリボンに対してシステム フォントが使用されるかどうかを示します。  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
## <a name="remarks"></a>コメント  
 `TRUE` システムのフォントを使用することを指定します。それ以外の場合、 `FALSE`です。  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターにこのメンバーは初期化 `FALSE`します。  
  
 このメンバーをテストすることは、フォントを調べるためにフレームワークを使用する唯一の方法ではありません。  `AFX_GLOBAL_DATA::UpdateFonts` メソッドはどのような visual スタイルは、メニューのツールバー、およびリボンに適用される使用を決定する既定と代替のフォントもテストします。  
  
## <a name="a-nameafxglobaldatamhcurhanda-afxglobaldatamhcurhand"></a><a name="afx_global_data__m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
手の形のカーソルのハンドルを格納します。  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="a-nameafxglobaldatamhcurstretcha-afxglobaldatamhcurstretch"></a><a name="afx_global_data__m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
水平方向の伸縮カーソルのハンドルを格納します。  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="a-nameafxglobaldatamhcurstretchverta-afxglobaldatamhcurstretchvert"></a><a name="afx_global_data__m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
垂直方向の伸縮カーソルのハンドルを格納します。  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="a-nameafxglobaldatamhicontoola-afxglobaldatamhicontool"></a><a name="afx_global_data__m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
ツール アイコンのハンドルを格納します。  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="a-nameafxglobaldatamnautohidetoolbarmargina-afxglobaldatamnautohidetoolbarmargin"></a><a name="afx_global_data__m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
左端の自動的に隠すツールバーからドッキング バーの左側までのオフセットを指定します。  
  
  
```  
int   m_nAutoHideToolBarMargin;  
```  
  
## <a name="remarks"></a>コメント  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターは、4 ピクセルにこのメンバーを初期化します。  
  
## <a name="a-nameafxglobaldatamnautohidetoolbarspacinga-afxglobaldatamnautohidetoolbarspacing"></a><a name="afx_global_data__m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
自動的に隠すツール バーの間の間隔を指定します。  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
## <a name="remarks"></a>コメント  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターは、14 ピクセルにこのメンバーを初期化します。  
  
## <a name="a-nameafxglobaldatamndragframethicknessdocka-afxglobaldatamndragframethicknessdock"></a><a name="afx_global_data__m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

ドッキング状態を示すために使用するドラッグ フレームの幅を指定します。  
  
  
```  
int   m_nDragFrameThicknessDock;  
```  
  
## <a name="remarks"></a>コメント  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターは、3 ピクセルにこのメンバーを初期化します。  
  
## <a name="a-nameafxglobaldatamndragframethicknessfloata-afxglobaldatamndragframethicknessfloat"></a><a name="afx_global_data__m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
フローティング状態を示すために使用するドラッグ フレームの幅を指定します。  
  
  
```  
int   m_nDragFrameThicknessFloat;  
```  
  
## <a name="remarks"></a>コメント  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` コンス トラクターは、4 ピクセルにこのメンバーを初期化します。  
  
## <a name="a-nameafxglobaldataonsettingchangea-afxglobaldataonsettingchange"></a><a name="afx_global_data__onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。  
  
  
```  
void OnSettingChange();
```  
  
## <a name="remarks"></a>コメント  
 このメソッドは、フレームワーク変数をユーザーのデスクトップの特定の属性の状態に設定します。 このメソッドは、メニューのアニメーション、メニューのフェードおよびタスク バーの自動非表示機能の現在の状態を検出します。  
  
## <a name="a-nameafxglobaldataregisterwindowclassa-afxglobaldataregisterwindowclass"></a><a name="afx_global_data__registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
指定された MFC ウィンドウ クラスを登録します。  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `lpszClassNamePrefix`  
 登録ウィンドウ クラスの名前。  
  
## <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は、登録されているクラスの修飾名それ以外の場合、 [リソース例外](../Topic/AfxThrowResourceException.md)します。  
  
## <a name="remarks"></a>コメント  
 戻り値はコロン区切りの一覧、 `lpszClassNamePrefix` パラメーター文字列、および現在のアプリケーション インスタンスのハンドルを表す 16 進数の文字列識別子を持つは IDC_ARROW; と背景ブラシの矢印カーソルは、アプリケーション カーソル。 MFC ウィンドウ クラスの登録の詳細については、次を参照してください。 [AfxRegisterClass](../Topic/Application%20Information%20and%20Management.md#afxregisterclass)します。  
  
## <a name="see-also"></a>関連項目    
 [AfxRegisterClass](../Topic/Application%20Information%20and%20Management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="a-nameafxglobaldataresumea-afxglobaldataresume"></a><a name="afx_global_data__resume"></a> AFX_GLOBAL_DATA::Resume
 Windows テーマと視覚スタイルをサポートするメソッドにアクセスする内部関数ポインターを再初期化します。 
  
  
```  
BOOL Resume();
```  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。 デバッグ モードでは、このメソッドは、このメソッドが失敗したかどうかをアサートします。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、フレームワークが受信すると、 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) メッセージです。  
  
## <a name="a-nameafxglobaldatasetlayeredattriba-afxglobaldatasetlayeredattrib"></a><a name="afx_global_data__setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Windows の [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) メソッドを簡単な方法で呼び出すことができます。  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `hwnd`  
 レイヤード ウィンドウへのハンドルします。  
  
 [入力] `crKey`  
 透過色キーを [デスクトップ ウィンドウ マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa969540) レイヤード ウィンドウの作成に使用します。  
  
 [入力] `bAlpha`  
 レイヤード ウィンドウの不透明度を説明するためのアルファ値。  
  
 [入力] `dwFlags`  
 使用するメソッド パラメーターを指定するフラグのビットごとの組み合わせ (OR)。 使用する LWA_COLORKEY の指定、 `crKey` 透過色としてパラメーター。 使用する LWA_ALPHA の指定、 `bAlpha` レイヤード ウィンドウの不透明度を決定するパラメーターです。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。   
 
## <a name="see-also"></a>関連項目   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="a-nameafxglobaldatasetmenufonta-afxglobaldatasetmenufont"></a><a name="afx_global_data__setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
指定された論理フォントを作成します。  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `lpLogFont`  
 フォントの属性を格納する構造体へのポインター。  
  
 [入力] `bHorz`  
 `TRUE` テキストを水平方向に実行するよう指定するには `FALSE` にテキストが垂直方向に実行するよう指定します。  
  
## <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、 `FALSE`です。 デバッグ モードでは、このメソッドは、このメソッドが失敗したかどうかをアサートします。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、水平方向通常フォントを下線の付いたフォントを作成し、既定のメニュー項目に使用される、太字のフォント。 このメソッドは、必要に応じて正規縦書きフォントを作成します。 論理フォントの詳細については、次を参照してください。 [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#cfont__createfontindirect)します。  
  
## <a name="a-nameafxglobaldataupdatefontsa-afxglobaldataupdatefonts"></a><a name="afx_global_data__updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
フレームワークにより使用される論理フォントを再初期化します。  
  
  
```  
void UpdateFonts();
```  
  
## <a name="remarks"></a>コメント  
 論理フォントの詳細については、次を参照してください。 `CFont::CreateFontIndirect`します。  
  
## <a name="a-nameafxglobaldataupdatesyscolorsa-afxglobaldataupdatesyscolors"></a><a name="afx_global_data__updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
フレームワークで使用される色、色深度、ブラシ、ペン、およびイメージを初期化します。  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="a-nameafxglobaldatabiswindows7a-afxglobaldatabiswindows7"></a><a name="afx_global_data__biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Windows 7 またはそれ以降、アプリケーションが実行されているかどうかを示します。  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="a-nameafxglobaldataclractivecaptiongradienta-afxglobaldataclractivecaptiongradient"></a><a name="afx_global_data__clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldataclrinactivecaptiongradienta-afxglobaldataclrinactivecaptiongradient"></a><a name="afx_global_data__clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
非アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldatagetitaskbarlista-afxglobaldatagetitaskbarlist"></a><a name="afx_global_data__getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
作成し、グローバル データにへのポインターを格納、 `ITaskBarList` インターフェイスです。  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
## <a name="return-value"></a>戻り値  
 ポインター、 `ITaskbarList` インターフェイスの場合は、タスク バーの list オブジェクトの作成が成功した `NULL` 作成に失敗した場合、または現在のオペレーティング システムが Windows 7 より小さい場合です。  
  
## <a name="a-nameafxglobaldatagetitaskbarlist3a-afxglobaldatagetitaskbarlist3"></a><a name="afx_global_data__getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
作成し、グローバル データにへのポインターを格納、 `ITaskBarList3` インターフェイスです。  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
## <a name="return-value"></a>戻り値  
 ポインター、 `ITaskbarList3` インターフェイスの場合は、タスク バーの list オブジェクトの作成が成功した `NULL` 作成に失敗した場合、または現在のオペレーティング システムが Windows 7 より小さい場合です。  
  
## <a name="a-nameafxglobaldatagetshellautohidebarsa-afxglobaldatagetshellautohidebars"></a><a name="afx_global_data__getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
シェルの自動非表示バーの位置を決定します。  
  
  
```  
int GetShellAutohideBars();
```  
  
## <a name="return-value"></a>戻り値  
 自動の位置を指定するエンコードのフラグを表す整数値には、バーが非表示にします。 次の値を組み合わせることがあります: AFX_AUTOHIDE_BOTTOM、AFX_AUTOHIDE_TOP、AFX_AUTOHIDE_LEFT、AFX_AUTOHIDE_RIGHT です。  
  
## <a name="a-nameafxglobaldatareleasetaskbarrefsa-afxglobaldatareleasetaskbarrefs"></a><a name="afx_global_data__releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
経由で取得したインターフェイスを解放、 `GetITaskbarList` と `GetITaskbarList3` メソッドです。  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="a-nameafxglobaldatashellcreateitemfromparsingnamea-afxglobaldatashellcreateitemfromparsingname"></a><a name="afx_global_data__shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
解析名からシェル項目オブジェクトを作成して初期化します。  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszPath`  
 [in]表示名へのポインター。  
  
 `pbc`  
 解析操作を制御するバインド コンテキストへのポインター。  
  
 `riid`  
 インターフェイス ID への参照  
  
 `ppv`  
 [out]この関数から制御が戻るときに要求されたインターフェイス ポインターが含まれています。 `riid`します。 通常これは `IShellItem` または `IShellItem2`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK を返します。それ以外の場合エラー値。  

