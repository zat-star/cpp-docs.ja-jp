---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPageSetupDialog
dev_langs:
- C++
helpviewer_keywords:
- page setup
- Print Setup dialog box
- Page Setup dialog box
- OLE Page Setup dialog box
- CPageSetupDialog class
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
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
ms.openlocfilehash: 81d36b3a005a291aca4c77dc9771a4fe92c304ee
ms.lasthandoff: 02/24/2017

---
# <a name="cpagesetupdialog-class"></a>メンバー クラス
印刷マージンの設定や変更の追加サポートと共に [OLE ページの設定] ダイアログ ボックスにより提供されるサービスをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|`CPageSetupDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|印刷用のデバイス コンテキストを作成します。|  
|[CPageSetupDialog::DoModal](#domodal)|ダイアログ ボックスを表示し、ユーザーを選択できます。|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|プリンターのデバイス名を返します。|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|現在を返す`DEVMODE`プリンターのです。|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|プリンターで使用するドライバーを返します。|  
|[CPageSetupDialog::GetMargins](#getmargins)|プリンターの現在の余白の設定を返します。|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|プリンターの用紙サイズを返します。|  
|[CPageSetupDialog::GetPortName](#getportname)|出力ポート名を返します。|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|印刷ページの画面イメージをレンダリングするためにフレームワークによって呼び出されます。|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|印刷ページの画面イメージを表示する前に、フレームワークによって呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|カスタマイズに使用する構造体、`CPageSetupDialog`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、印刷のセットアップ ダイアログ ボックスの代わりに設計されています。  
  
 使用する、`CPageSetupDialog`オブジェクトは、まずを使用してオブジェクトを作成、`CPageSetupDialog`コンス トラクターです。 ダイアログ ボックスを構築すると、設定または任意の値を変更、`m_psd`データ メンバーは、ダイアログ ボックスのコントロールの値を初期化します。 [M_psd](#m_psd)型の構造は、 **PAGESETUPDLG**します。  
  
 ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにします。 `DoModal`ユーザーが [ok] を選択するかどうかを返します ( **IDOK**) またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**、いくつかの操作を使用することができます`CPageSetupDialog`のメンバー関数、またはアクセス、`m_psd`データ メンバーは、ユーザーが入力した情報を取得します。  
  
> [!NOTE]
>  共通の OLE ページの設定 ダイアログ ボックスを閉じ後、フレームワークによって、ユーザーが行った変更は保存されません。 このダイアログ ボックスから、アプリケーションのドキュメントまたはアプリケーションのクラスのメンバーなどの永続的な場所の任意の値を保存するにはアプリケーション自体の責任です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-namecpagesetupdialoga--cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 作成するには、この関数を呼び出して、`CPageSetupDialog`オブジェクトです。  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 1 つまたは複数のフラグ ダイアログ ボックスの設定のカスタマイズを行うこともできます。 ビットごとの OR 演算子を使用して、値を組み合わせることができます。 これらの値には、次の意味があります。  
  
- **PSD_DEFAULTMINMARGINS**プリンターの最小値と同じであるページの余白の最小幅の許容を設定します。 場合にこのフラグは無視されます、 **PSD_MARGINS**と**PSD_MINMARGINS**フラグも指定します。  
  
- **PSD_INWININIINTLMEASURE**実装されていません。  
  
- **PSD_MINMARGINS**で指定された値を使用するシステムによって、**小幅**左、上、右、および上下の余白の最小幅の許容とメンバーです。 システムでは、ユーザーが指定された最小値より小さい幅に入るを防ぎます。 場合**PSD_MINMARGINS**が指定されていない、システムでは、プリンターで許可されているものに許容される最小の幅を設定します。  
  
- **PSD_MARGINS**マージン コントロール領域をアクティブにします。  
  
- **PSD_INTHOUSANDTHSOFINCHES**  ダイアログ ボックスの単位をインチの 1/1000 で測定されます。  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS**  ダイアログ ボックスの単位を 1/100 ミリ単位で測定されます。  
  
- **PSD_DISABLEMARGINS**余白 ダイアログ ボックス コントロールを無効にします。  
  
- **PSD_DISABLEPRINTER** [プリンター] ボタンを無効にします。  
  
- **PSD_NOWARNING**警告メッセージが既定のプリンターがない場合に表示されないようにします。  
  
- **PSD_DISABLEORIENTATION**ページの向きのダイアログ コントロールを無効にします。  
  
- **PSD_RETURNDEFAULT**により`CPageSetupDialog`を返す[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)がダイアログ ボックスを表示せずにシステムの既定のプリンターに対して初期化構造体。 ように仮定両方**と**と**hDevMode**は**NULL**。 そうしないと、エラーを返します。 システムの既定のプリンターが、古いプリンター ドライバー (Windows バージョン 3.0 より前) でサポートされている場合のみ**と**が返されます。**hDevMode** is **NULL**.  
  
- **PSD_DISABLEPAPER**用紙の選択コントロールが無効になります。  
  
- **PSD_SHOWHELP**ダイアログ ボックスの [ヘルプ] ボタンを表示します。 **HwndOwner**メンバーがしなければならない**NULL**このフラグが指定されている場合。  
  
- **PSD_ENABLEPAGESETUPHOOK** 、フック関数で指定された**lpfnSetupHook**します。  
  
- **PSD_ENABLEPAGESETUPTEMPLATE**で識別される テンプレートを使用して、ダイアログ ボックスを作成するオペレーティング システムによって**hInstance**と**されると**です。  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE**ことを示します**hInstance**あらかじめ読み込まれたダイアログ ボックスのテンプレートが含まれるデータ ブロックを指定します。 無視されます**されると**このフラグが指定されている場合。  
  
- **PSD_ENABLEPAGEPAINTHOOK** 、フック関数で指定された**lpfnPagePaintHook**します。  
  
- **PSD_DISABLEPAGEPAINTING**  ダイアログ ボックスの描画領域を無効にします。  
  
 `pParentWnd`  
 ダイアログ ボックスの親または所有者へのポインター。  
  
### <a name="remarks"></a>コメント  
 使用して、 [DoModal](../../mfc/reference/cdialog-class.md#domodal)  ダイアログ ボックスを表示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&94;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="a-namecreateprinterdca--cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 プリンター デバイス コンテキストを作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキスト (DC) へのハンドルします。  
  
##  <a name="a-namedomodala--cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupDialog::DoModal  
 この関数では、Windows に共通の [OLE ページの設定] ダイアログ ボックスを表示し、印刷の余白、サイズと出力先プリンター、用紙の向きなどのさまざまな印刷設定オプションを選択できるようにします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**します。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断します。  
  
 **IDOK**と**IDCANCEL**をユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>コメント  
 さらに、ユーザーはネットワークの場所と、選択したプリンターに固有のプロパティなど、プリンター設定オプションにアクセスできます。  
  
 メンバーを設定して、さまざまなページ設定ダイアログ オプションを初期化する場合、`m_psd`構造体、呼び出す前に行ってください`DoModal`、前後ダイアログ オブジェクトを構築します。 呼び出した後`DoModal`、その他のメンバー ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出します。  
  
 呼び出しを行う場合は、ユーザーが入力した現在の設定を伝達するには、[通知](../../mfc/reference/cwinapp-class.md#selectprinter)します。 この関数から情報を受け取り、`CPageSetupDialog`オブジェクトしを初期化し、適切な属性を持つ新しいプリンター DC を選択します。  
  
 [!code-cpp[NVC_MFCDocView #&95;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>例  
  例を参照してください[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)します。  
  
##  <a name="a-namegetdevicenamea--cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 後は、この関数を呼び出して`DoModal`現在選択されているプリンターの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって使用されるデバイス名、**コモン**オブジェクトです。  
  
##  <a name="a-namegetdevmodea--cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 この関数を呼び出した後`DoModal`のプリンター デバイス コンテキストに関する情報を取得、`CPageSetupDialog`オブジェクトです。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体と Windows によって使用されるメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)で説明されている関数、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetdrivernamea--cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 この関数を呼び出した後[DoModal](../../mfc/reference/cprintdialog-class.md#domodal)プリンターのシステム定義のデバイス ドライバーの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>コメント  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
##  <a name="a-namegetmarginsa--cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupDialog::GetMargins  
 この関数を呼び出した後`DoModal`プリンター デバイス ドライバーの余白を取得します。  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectMargins*  
 ポインター、 [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md) (1/1000 インチまたは 1/100 mm) で現在選択されているプリンターの印刷のマージンを記述するオブジェクト。 渡す**NULL**場合、この四角形に注目するは、このパラメーターにします。  
  
 *lpRectMinMargins*  
 ポインター、`RECT`構造または`CRect`(1/1000 インチまたは 1/100 mm) で現在選択されているプリンターの印刷の余白の最小値を記述するオブジェクト。 渡す**NULL**場合、この四角形に注目するは、このパラメーターにします。  
  
##  <a name="a-namegetpapersizea--cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 この関数では、印刷用に選択、用紙のサイズを取得します。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)印刷用に選択する (1/1000 インチまたは 1/100 mm) で用紙のサイズを表すオブジェクト。  
  
##  <a name="a-namegetportnamea--cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupDialog::GetPortName  
 この関数を呼び出した後`DoModal`現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
##  <a name="a-namempsda--cpagesetupdialogmpsd"></a><a name="m_psd"></a>CPageSetupDialog::m_psd  
 型の構造体**PAGESETUPDLG**、そのメンバーはダイアログ オブジェクトの特性を格納します。  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CPageSetupDialog`オブジェクトを使用する`m_psd`を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定する、`DoModal`メンバー関数。  
  
 変更した場合、`m_psd`データ メンバーを直接、既定の動作をオーバーライドします。  
  
 詳細については、 [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)構造体を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 例を参照してください[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)します。  
  
##  <a name="a-nameondrawpagea--cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 印刷ページの画面イメージを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストへのポインター。  
  
 `nMessage`  
 現在描画中 ページの領域を示すメッセージを指定します。 次のいずれかの値を指定します。  
  
- **WM_PSD_FULLPAGERECT**ページ全体の領域です。  
  
- **WM_PSD_MINMARGINRECT**現在余白の最小値。  
  
- **WM_PSD_MARGINRECT**現在のマージン。  
  
- **WM_PSD_GREEKTEXTRECT**ページの内容。  
  
- **WM_PSD_ENVSTAMPRECT**領域切手を表すのために予約されています。  
  
- **WM_PSD_YAFULLPAGERECT**リターン アドレスを表すのための領域です。 この領域は、サンプル ページ領域の境界に拡張します。  
  
 `lpRect`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)描画領域の座標を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 処理された場合、0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このイメージは、共通の OLE ページの設定 ダイアログ ボックスの一部として表示されます。 既定の実装では、テキストのページのイメージを描画します。  
  
 イメージ、またはイメージ全体の特定の領域の描画をカスタマイズするには、この関数をオーバーライドします。 使用してこれを行う、`switch`ステートメントで**ケース**の値をチェックするステートメント`nMessage`します。 たとえば、ページのイメージの内容の表示をカスタマイズするには、次のコード例を使用できます。  
  
 [!code-cpp[NVC_MFCDocView #&96;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 すべてのケースを処理する必要がないことに注意してください`nMessage`します。 イメージ、イメージ、または全体の領域のいくつかのコンポーネントの&1; つのコンポーネントを処理することができます。  
  
##  <a name="a-namepredrawpagea--cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 印刷ページの画面イメージを描画する前に、フレームワークによって呼び出されます。  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>パラメーター  
 *wPaper*  
 用紙サイズを示す値を指定します。 この値は、のいずれかを指定できます、 **DMPAPER_**値の一覧の説明、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)構造体。  
  
 `wFlags`  
 用紙または封筒の印刷の向きを示すかどうか、プリンターは、ドット マトリックスまたは HPPCL (Hewlett Packard Printer Control Language) デバイスです。 このパラメーターには、次のいずれかの値を指定できます。  
  
-   0x001 用紙横モード (ドット マトリックス)  
  
-   0x003 用紙横モード (HPPCL)  
  
-   0x005 用紙の縦モード (ドット マトリックス)  
  
-   0x007 用紙の縦モード (HPPCL)  
  
-   0x00b 横置きモード (HPPCL) のエンベロープ  
  
-   0x00d 縦モード (ドット マトリックス) エンベロープ  
  
-   0x019 横置きモード (ドット マトリックス) のエンベロープ  
  
-   0x01f 縦モード (ドット マトリックス) エンベロープ  
  
 `pPSD`  
 ポインター、 **PAGESETUPDLG**構造体。 詳細については[PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 処理された場合、0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 イメージの描画をカスタマイズするには、この関数をオーバーライドします。 この関数をオーバーライドして**TRUE**、全体のイメージを描画する必要があります。 この関数をオーバーライドして**FALSE**、フレームワークによって既定のイメージ全体を描画します。  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




