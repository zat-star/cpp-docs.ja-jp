---
title: "CPropertySheet クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertySheet
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, tabs
- CPropertySheet class
- property sheets, CPropertySheet class
- tab dialog boxes
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
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
ms.openlocfilehash: 41ad7b598016b1fa04aa7ca63575f853195b5359
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertysheet-class"></a>CPropertySheet クラス
タブ ダイアログ ボックスとしても知られるプロパティ シートを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[呼び出します](#cpropertysheet)|`CPropertySheet` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[が](#addpage)|プロパティ シートにページを追加します。|  
|[まず、](#construct)|`CPropertySheet` オブジェクトを構築します。|  
|[CPropertySheet::Create](#create)|モードレス プロパティ シートを表示します。|  
|[する](#domodal)|モーダル プロパティ シートを表示します。|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|プロパティ シートが積み上げまたはスクロールのタブを使用するかどうかを示します。|  
|[CPropertySheet::EndDialog](#enddialog)|プロパティ シートを終了します。|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|プロパティ シートの現在のページのインデックスを取得します。|  
|[CPropertySheet::GetActivePage](#getactivepage)|アクティブなページ オブジェクトを返します。|  
|[CPropertySheet::GetPage](#getpage)|指定したページへのポインターを取得します。|  
|[CPropertySheet::GetPageCount](#getpagecount)|プロパティ シートのページ数を取得します。|  
|[CPropertySheet::GetPageIndex](#getpageindex)|プロパティ シートの指定したページのインデックスを取得します。|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|タブ コントロールへのポインターを取得します。|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面単位に変換します。|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|プロパティ シートの初期化処理を強化するためにオーバーライドします。|  
|[CPropertySheet::PressButton](#pressbutton)|プロパティ シートで指定したボタンの選択をシミュレートします。|  
|[CPropertySheet::RemovePage](#removepage)|プロパティ シートからページを削除します。|  
|[CPropertySheet::SetActivePage](#setactivepage)|アクティブ ページ オブジェクトをプログラムで設定します。|  
|[CPropertySheet::SetFinishText](#setfinishtext)|[完了] ボタンのテキストを設定します。|  
|[CPropertySheet::SetTitle](#settitle)|プロパティ シートのキャプションを設定します。|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|ウィザードのボタンを有効にします。|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|ウィザードのモードを有効にします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造体。 基本的なプロパティ シートのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 プロパティ シートから成る、`CPropertySheet`オブジェクトと&1; つ以上[CPropertyPage](../../mfc/reference/cpropertypage-class.md)オブジェクトです。 フレームワークは、一連のタブ インデックスを持ち、現在選択されているページが含まれる領域でのウィンドウとプロパティ シートを表示します。 ユーザーは、適切なタブを使用して、特定のページに移動します。  
  
 `CPropertySheet`展開のサポートを提供[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)構造がで導入された[!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)]および Windows NT 2000 です。 構造体には、追加のフラグと「透かし」の背景ビットマップの使用をサポートするメンバーが含まれています。  
  
 プロパティ シート オブジェクトに自動的にこれらの新しいイメージを表示するへの呼び出しでビットマップとパレットのイメージの有効な値を渡す[まず、](#construct)または[呼び出します](#cpropertysheet)します。  
  
 にもかかわらず`CPropertySheet`から派生していない[CDialog](../../mfc/reference/cdialog-class.md)、管理、`CPropertySheet`管理などのオブジェクトが、`CDialog`オブジェクトです。 たとえば、プロパティ シートの作成には&2; つの部分の構築が必要です: コンス トラクターを呼び出します[DoModal](#domodal)モーダル プロパティ シートのまたは[作成](#create)モードレス プロパティ シートのです。 `CPropertySheet`コンス トラクターの&2; つの種類があります:[まず、](#construct)と[呼び出します](#cpropertysheet)します。  
  
 構築する場合、`CPropertySheet`オブジェクト一部[ウィンドウ スタイル](../../mfc/reference/window-styles.md)が発生する初回例外が発生することができます。 これは、結果、シートを作成するには、プロパティ シートのスタイルを変更しようとしました。 システムからです。 この例外を避けるためには、作成するときに、次のスタイルを設定することを確認します、 `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 次のスタイルはオプションであり、初回の例外は発生しません。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 その他の`Window Styles`は禁止していないに有効にする必要があります。  
  
 間のデータ交換、`CPropertySheet`オブジェクトおよび外部のオブジェクトがデータを交換するに似ていますが、`CDialog`オブジェクトです。 重要な違いにはプロパティ シートの設定が通常のメンバー変数、`CPropertyPage`オブジェクトのではなく、`CPropertySheet`オブジェクト自体です。  
  
 デバイスのセットアップやニュースレターを作成するなどの操作の手順を追ってプロパティ ページのシーケンスを持つプロパティ シートから成る、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページのタブがないと、一度に&1; つのプロパティ ページが表示されます。 ではなく、また、 **ok**と**今すぐ適用**ボタン、ウィザードの種類 タブのダイアログ ボックスには、**戻る** ボタンを**次へ**または**完了**  ボタンを**キャンセル** ボタンと**ヘルプ** ボタンをクリックします。  
  
 ウィザードの種類 ダイアログ ボックスを作成する手順は同じ呼び出し以外の標準的なプロパティ シートを作成した後に続きます[SetWizardMode](#setwizardmode)を呼び出す前に[DoModal](#domodal)します。 ウィザードのボタンを有効にする[に](#setwizardbuttons)フラグを使用して、機能と外観をカスタマイズします。 有効にする、**完了**] ボタンを呼び出す[SetFinishText](#setfinishtext)後、ユーザーは、ウィザードの最後のページ [処置を行っています。  
  
 使用する方法の詳細についての`CPropertySheet`オブジェクト、記事を参照して[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)します。 また、サポート技術情報記事 Q146916 を参照してください: HOWTO: 標準のボタンを持つモードレス CPropertySheet を作成し、Q300606 の記事: HOWTO: サイズ変更可能な MFC プロパティ シートを設計します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-nameaddpagea--cpropertysheetaddpage"></a><a name="addpage"></a>が  
 プロパティ シートで指定した右端のタブ ページを追加します。  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 プロパティ シートに追加するページへのポインター。 ことはできません**NULL**します。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを表示する左から右へ順番にページを追加します。  
  
 `AddPage`追加、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)オブジェクトを`CPropertySheet`オブジェクトのページの一覧は、ページのウィンドウを実際には作成されません。 フレームワークは、ユーザーがそのページを選択するまで、ページのウィンドウの作成を延期します。  
  
 使用してプロパティ ページを追加すると`AddPage`、`CPropertySheet`の親である、`CPropertyPage`です。 アクセスするためにプロパティ シートに、プロパティ ページから、呼び出す[CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)します。  
  
 ウィンドウの作成、プロパティ シートを呼び出すまで待機する必要はありません`AddPage`します。 呼び出す通常、`AddPage`呼び出す前に[DoModal](#domodal)または[作成](#create)します。  
  
 呼び出した場合`AddPage`タブ行に、プロパティ ページを表示した後、新しく追加されたページが反映されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&129;](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="a-nameconstructa--cpropertysheetconstruct"></a><a name="construct"></a>まず、  
 `CPropertySheet` オブジェクトを構築します。  
  
```  
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCaption`  
 プロパティ シートに使用されるキャプションの ID です。  
  
 `pParentWnd`  
 プロパティ シートの親ウィンドウへのポインター。 場合**NULL**、親ウィンドウは、アプリケーションのメイン ウィンドウになります。  
  
 `iSelectPage`  
 先頭には最初に、ページのインデックス。 既定値は、最初のページがシートに追加します。  
  
 `pszCaption`  
 プロパティ シートに使用されるキャプションを表す文字列へのポインター。 ことはできません**NULL**します。  
  
 `hbmWatermark`  
 プロパティ ページの透かしビットマップへのハンドルします。  
  
 `hpalWatermark`  
 透かしビットマップやヘッダー ビットマップのパレットへのハンドルします。  
  
 `hbmHeader`  
 プロパティ ページのヘッダー ビットマップへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 クラスのコンス トラクターのいずれかが既に呼び出されていない場合は、このメンバー関数を呼び出します。 たとえば、`Construct`宣言かの配列を割り当てる`CPropertySheet`のオブジェクト。 配列の場合を呼び出す必要があります`Construct`配列内の各メンバーにします。  
  
 プロパティ シートを表示するに[DoModal](#domodal)または[作成](#create)します。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 自動的の&3; 番目か&4; 番目のプロトタイプを使用する場合、ウォーターマークまたはヘッダーのイメージを表示することができます`Construct`、上記およびの有効な値を渡す、 `hbmWatermark`、 `hpalWatermark`、または`hbmHeader`パラメーター。  
  
### <a name="example"></a>例  
 下にある次の例を呼び出します。 どのような場合、`Construct`です。  
  
 [!code-cpp[NVC_MFCDocView #&130;](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="a-namecpropertysheeta--cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>呼び出します  
 `CPropertySheet` オブジェクトを構築します。  
  
```  
CPropertySheet();

 
explicit CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
explicit CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCaption`  
 プロパティ シートに使用されるキャプションの ID です。  
  
 `pParentWnd`  
 プロパティ シートの親ウィンドウへのポインター。 場合**NULL**、親ウィンドウは、アプリケーションのメイン ウィンドウになります。  
  
 `iSelectPage`  
 先頭には最初に、ページのインデックス。 既定値は、最初のページがシートに追加します。  
  
 `pszCaption`  
 プロパティ シートに使用されるキャプションを表す文字列を指します。 ことはできません**NULL**します。  
  
 `hbmWatermark`  
 プロパティ シートの背景ビットマップへのハンドル。  
  
 `hpalWatermark`  
 透かしビットマップやヘッダー ビットマップのパレットへのハンドル。  
  
 `hbmHeader`  
 プロパティ ページのヘッダー ビットマップへのハンドル。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを表示するに[DoModal](#domodal)または[作成](#create)します。 最初のパラメーターに含まれる文字列は、プロパティ シートのキャプション バーに配置されます。  
  
 複数のパラメーター (たとえば、配列を使用している場合) があればを使用して[構築](#construct)の代わりに`CPropertySheet`します。  
  
 自動的の&3; 番目か&4; 番目のプロトタイプを使用する場合、ウォーターマークまたはヘッダーのイメージを表示することができます`CPropertySheet`、上記の有効な値を渡すと、 `hbmWatermark`、 `hpalWatermark`、または`hbmHeader`パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&131;](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="a-namecreatea--cpropertysheetcreate"></a><a name="create"></a>CPropertySheet::Create  
 モードレス プロパティ シートを表示します。  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)–1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 親ウィンドウへのポインター。 場合**NULL**親はデスクトップです。  
  
 `dwStyle`  
 プロパティ シートのウィンドウ スタイル。 使用可能なスタイルの一覧については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 `dwExStyle`  
 プロパティ シートの拡張ウィンドウ スタイル。 使用可能なスタイルの一覧については、次を参照してください[拡張ウィンドウ スタイル。](../../mfc/reference/extended-window-styles.md)  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常に作成される場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し**作成**コンス トラクター内で使用できますか、コンス トラクターが呼び出された後に呼び出すことができます。  
  
 –&1; として渡すことによって表される既定のスタイル`dwStyle`、実際には、 **WS_SYSMENU |**`WS_POPUP`**|WS_CAPTION |DS_MODALFRAME |DS_CONTEXTHELP |WS_VISIBLE**します。 既定の拡張ウィンドウ スタイル、として 0 を渡すことによって表される`dwExStyle`、実際には、 **WS_EX_DLGMODALFRAME**します。  
  
 **作成**メンバー関数は、プロパティ シートを作成した直後に返します。 プロパティ シートを破棄するには、呼び出す[に](../../mfc/reference/cwnd-class.md#destroywindow)します。  
  
 モードレス プロパティ シートへの呼び出しに**作成**モーダル プロパティ シートのように [ok]、[キャンセル] を今すぐ適用、およびヘルプ ボタンはありません。 必要なボタンは、ユーザーが作成する必要があります。  
  
 モーダル プロパティ シートを表示するに[DoModal](#domodal)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&132;](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&133;](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="a-namedomodala--cpropertysheetdomodal"></a><a name="domodal"></a>する  
 モーダル プロパティ シートを表示します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 `IDOK`または`IDCANCEL`関数が成功した。 それ以外の場合 0 または-1 の場合。 ウィザードとプロパティ シートが確定したかどうか (を参照してください[SetWizardMode](#setwizardmode))、`DoModal`いずれかを返す`ID_WIZFINISH`または`IDCANCEL`です。  
  
### <a name="remarks"></a>コメント  
 戻り値は、プロパティ シートを閉じてコントロールの ID に対応します。 この関数が返されると、プロパティ シートとすべてのページに対応する windows は破棄されます。 オブジェクト自体が残っています。 通常からのデータを取得する、 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)後にオブジェクト`DoModal`を返します`IDOK`します。  
  
 モードレス プロパティ シートを表示するに[作成](#create)代わりにします。  
  
 対応するダイアログ リソースからプロパティ ページが作成されると、初回例外を発生することができます。 これは、ページを作成するには、必要なスタイルにダイアログ リソースのスタイルを変更するプロパティ ページに起因します。 リソースが通常読み取り専用であるために、例外が発生します。 システムは、例外を処理し、更新されたリソースのコピーを作成します。 そのため、初回例外は無視できます。  
  
> [!NOTE]
>  この例外は、非同期例外処理モデルを使ってコンパイルする場合、オペレーティング システムで処理する必要があります。 例外処理モデルの詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)します。 この場合への呼び出しをラップできません`CPropertySheet::DoModal`C++ try catch ブロックと catch が処理するすべての例外では、たとえば、`catch (...)`です。 このブロックでは、オペレーティング システム、および予期しない動作の原因は、例外が処理。 ただし、C++ 例外アクセス違反例外がオペレーティング システムに渡される特定の例外の種類または構造化例外処理と処理を安全に使用できます。  
  
 この初回例外が生成されないようにを保証できるは手動でプロパティ シートには、正しいこと[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。 次のプロパティ シートのスタイルを設定する必要があります。  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 初回例外を発生させず、次のオプションのスタイルを使用できます。  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 プロパティ シートとの互換性はないために、他のすべての Windows スタイルを無効にします。 このアドバイスは、拡張スタイルには適用されません。 これらの標準的なスタイルを適切に設定すると、プロパティ シートを変更する必要はありませんし、初回例外が生成されないようにが保証されます。  
  
### <a name="example"></a>例  
  例を参照してください[が](#addpage)です。  
  
##  <a name="a-nameenablestackedtabsa--cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs  
 プロパティ シートのタブの行をスタックするかどうかを示します。  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStacked`  
 プロパティ シートに積み上げタブが有効かどうかを示します。 積み上げ行タグの設定を無効に`bStacked`に**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ シート、プロパティ シートの幅に単一の行に格納できる数以上のタブでは、タブは複数の行に積み重ねられます。 タブではなくスクロールのタブを使用する`EnableStackedTabs`と`bStacked`に設定**FALSE**呼び出す前に[DoModal](#domodal)または[作成](#create)します。  
  
 呼び出す必要があります`EnableStackedTabs`モーダルまたはモードレス プロパティ シートを作成する場合。 このスタイルで、`CPropertySheet`の派生クラスでは、メッセージ ハンドラーの記述の`WM_CREATE`です。 オーバーライドされたバージョンの[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、呼び出す**は、(FALSE)**基本クラスの実装を呼び出す前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&134;](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="a-nameenddialoga--cpropertysheetenddialog"></a><a name="enddialog"></a>CPropertySheet::EndDialog  
 プロパティ シートを終了します。  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nEndID*  
 プロパティ シートの戻り値として使用する識別子です。  
  
### <a name="remarks"></a>コメント  
 [Ok]、[キャンセル] または [閉じる] ボタンが押されたときに、このメンバー関数がフレームワークによって呼び出されます。 呼び出しは、イベントが発生した場合、このメンバー関数は、プロパティ シートを閉じる必要があります。  
  
 このメンバー関数はモーダル ダイアログ ボックスでのみ使用します。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::PressButton](#pressbutton)します。  
  
##  <a name="a-namegetactiveindexa--cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>CPropertySheet::GetActiveIndex  
 インデックスのプロパティ シート ウィンドウのアクティブなページ数を取得しをパラメーターとして返されるインデックス番号を使用し、`GetPage`です。  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のページのインデックス番号。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="a-namegetactivepagea--cpropertysheetgetactivepage"></a><a name="getactivepage"></a>CPropertySheet::GetActivePage  
 プロパティ シート ウィンドウのアクティブ ページを取得します。  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 作業中のページへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用すると、作業中のページに何らかのアクションを実行できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&135;](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="a-namegetpagea--cpropertysheetgetpage"></a><a name="getpage"></a>CPropertySheet::GetPage  
 このプロパティ シートで指定したページへのポインターを返します。  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPage`  
 必要なページのインデックスが 0 から始まります。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいの間である必要があります。  
  
### <a name="return-value"></a>戻り値  
 対応するページへのポインター、`nPage`パラメーター。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)します。  
  
##  <a name="a-namegetpagecounta--cpropertysheetgetpagecount"></a><a name="getpagecount"></a>CPropertySheet::GetPageCount  
 プロパティ シートの現在のページの数を決定します。  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シート内のページの数。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)します。  
  
##  <a name="a-namegetpageindexa--cpropertysheetgetpageindex"></a><a name="getpageindex"></a>CPropertySheet::GetPageIndex  
 プロパティ シートで指定したページのインデックス番号を取得します。  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 検索するインデックスを含むページへのポインター。 ことはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 ページのインデックス番号。  
  
### <a name="remarks"></a>コメント  
 たとえば、使用するよう`GetPageIndex`を使用するためにページのインデックスを取得する[行ったとき](#setactivepage)または[GetPage](#getpage)します。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="a-namegettabcontrola--cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>CPropertySheet::GetTabControl  
 タブ コントロールに固有の作業を行うタブ コントロールへのポインターを取得 (つまり、すべての Api を使用して[CTabCtrl](../../mfc/reference/ctabctrl-class.md))。  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールへのポインター。  
  
### <a name="remarks"></a>コメント  
 たとえば、初期化中に、それぞれのタブにビットマップを追加する場合は、このメンバー関数を呼び出してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&136;](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="a-namempsha--cpropertysheetmpsh"></a><a name="m_psh"></a>CPropertySheet::m_psh  
 構造体のメンバーの特性を保持する[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)します。  
  
### <a name="remarks"></a>コメント  
 表示されるようにするが、構築した後、プロパティ シートの外観を初期化するためにこの構造体を使用して、 [DoModal](#domodal)メンバー関数。 たとえば、設定、`dwSize`のメンバー`m_psh`サイズにして、プロパティ シートにします。  
  
 詳細については、そのメンバーの一覧を含む、この構造体を参照してください。 **PROPSHEETHEADER**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&143;](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="a-namemapdialogrecta--cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>CPropertySheet::MapDialogRect  
 四角形のダイアログ ボックスの単位を画面単位に変換します。  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ単位は、平均的な幅とダイアログ ボックスのテキストに使用するフォントの文字の高さから派生した現在のダイアログ ボックス基本単位として。 水平方向の&1; つの単位 ダイアログ ボックスの基本幅の単位の&4; 分の&1;、垂直方向の&1; つの単位 ダイアログ ボックスの高さの基本単位の&8; 分の&1;。  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows 関数は、システム フォントのサイズ情報を返しますが、プロパティ シートごとに別のフォントを指定するには、使用する場合、 **DS_SETFONT**リソース定義ファイル内のスタイル。 [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502)で説明されている Windows の機能、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、このダイアログ ボックスに適切なフォントを使用します。  
  
 `MapDialogRect`メンバー関数は、ダイアログ ボックスの単位を置き換えます`lpRect`で画面の [作成] ダイアログ ボックスに、ボックス内のコントロールの位置四角形を使用できるようにする単位 (ピクセル単位)。  
  
##  <a name="a-nameoninitdialoga--cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>CPropertySheet::OnInitDialog  
 プロパティ シートの初期化処理を強化するよりも優先されます。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがプロパティ シート内のコントロールのいずれかに入力フォーカスを設定するかどうかを指定します。 場合**OnInitDialog**戻り値は&0; 以外の値、Windows、入力フォーカスを設定プロパティ シートの最初のコントロールです。 アプリケーションは、入力のフォーカスをプロパティ シート内のコントロールのいずれかに明示的に設定した場合にのみ、0 を返すことができます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数への応答で、 **WM_INITDIALOG**メッセージです。 中にプロパティ シートにこのメッセージが送信される、[作成](#create)または[DoModal](#domodal)プロパティ シートを表示する直前に発生する可能性の呼び出しです。  
  
 プロパティ シートが初期化されるときに、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンの基本クラスを呼び出す最初`OnInitDialog`は、その戻り値を無視します。 通常戻ります**TRUE**オーバーライドされるメンバー関数からです。  
  
 このメンバー関数のメッセージ マップ エントリが不要です。  
  
##  <a name="a-namepressbuttona--cpropertysheetpressbutton"></a><a name="pressbutton"></a>CPropertySheet::PressButton  
 プロパティ シートで指定したボタンの選択をシミュレートします。  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nButton`  
 nButton: ボタンが押されるを識別します。 このパラメーターは、次の値のいずれかになります。  
  
- **PSBTN_BACK** [戻る] ボタンを選択します。  
  
- **PSBTN_NEXT**次へ ボタンを選択します。  
  
- **PSBTN_FINISH**が [完了] ボタンを選択します。  
  
- **PSBTN_OK**が [ok] ボタンを選択します。  
  
- **PSBTN_APPLYNOW**適用 ボタンを選択します。  
  
- **PSBTN_CANCEL**が [キャンセル] ボタンを選択します。  
  
- **PSBTN_HELP**ヘルプ ボタンを選択します。  
  
### <a name="remarks"></a>コメント  
 参照してください[PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597)詳細については、Windows SDK Pressbutton メッセージです。  
  
 呼び出し`PressButton`は送信されません、 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)プロパティ ページから、フレームワークに通知します。 この通知を送信する[送るに](../../mfc/reference/cpropertypage-class.md#onok)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&137;](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="a-nameremovepagea--cpropertysheetremovepage"></a><a name="removepage"></a>CPropertySheet::RemovePage  
 プロパティ シートからページを削除し、関連するウィンドウを破棄します。  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPage`  
 プロパティ シートから削除するページへのポインター。 ことはできません`NULL`します。  
  
 `nPage`  
 削除するページのインデックス。 0 と 1 つの包括的に、プロパティ シートのページ数よりも小さいの間である必要があります。  
  
### <a name="remarks"></a>コメント  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)までの所有者はオブジェクト自体は破棄されません、`CPropertySheet`期間が終了します。  
  
##  <a name="a-namesetactivepagea--cpropertysheetsetactivepage"></a><a name="setactivepage"></a>CPropertySheet::SetActivePage  
 作業中のページを変更します。  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPage`  
 設定するページのインデックス。 0 と 1 つのプロパティ シートのページ数よりも小さいか間の可能性があります。  
  
 `pPage`  
 プロパティ シートに設定するページへのポインター。 できません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが正常に有効な場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、使用して`SetActivePage`場合は&1; ページに、ユーザーの操作が発生する別のページに現在のページになる必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetActivePage](#getactivepage)します。  
  
##  <a name="a-namesetfinishtexta--cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>CPropertySheet::SetFinishText  
 [完了] コマンド ボタンのテキストを設定します。  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 [完了] コマンド ボタンに表示されるテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetFinishText`完了コマンド ボタンのテキストを表示し、ユーザーが、ウィザードの最後のページに、アクションが完了した後、次へ および 戻るボタンを非表示にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="a-namesettitlea--cpropertysheetsettitle"></a><a name="settitle"></a>CPropertySheet::SetTitle  
 プロパティ シートのキャプション (フレーム ウィンドウのタイトル バーに表示されるテキスト) を指定します。  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyle`  
 プロパティ シートのタイトルのスタイルを指定します。 0 から、またはスタイルを指定する必要があります**PSH_PROPTITLE**します。 として、スタイルが設定されている場合**PSH_PROPTITLE**、キャプションとして指定されたテキストに続く単語「プロパティ」が表示されます。 たとえばを呼び出す`SetTitle`(「シンプル」 **PSH_PROPTITLE**)「単純なプロパティです」のプロパティ シートのタイトルになります。  
  
 `lpszText`  
 プロパティ シートのタイトル バーのキャプションとして使用するテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ シートは、プロパティ シートのコンス トラクターでキャプション パラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&139;](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="a-namesetwizardbuttonsa--cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons  
 有効またはウィザードのプロパティ シートに戻る、Next、または [完了] ボタンを無効にします。  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 一連の関数とウィザード ボタンの外観をカスタマイズするフラグ。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- **PSWIZB_BACK** [戻る] ボタン  
  
- **PSWIZB_NEXT**次へ ボタン  
  
- **PSWIZB_FINISH** [完了] ボタン  
  
- **PSWIZB_DISABLEDFINISH**無効になっている [完了] ボタン  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetWizardButtons`ダイアログ ボックスが開いている後にのみ呼び出すことができない`SetWizardButtons`を呼び出す前に[DoModal](#domodal)します。 通常を呼び出す必要があります`SetWizardButtons`から[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)します。  
  
 [完了] ボタンのテキストを変更または次を非表示にするし、戻るボタンに&1; 回、ユーザーが、ウィザードでは、呼び出しを完了[SetFinishText](#setfinishtext)します。 [完了] と [進む] の同じボタンが共有されることに注意してください。 完了、または次へ ボタンを一度に&1; つが、両方を表示することができます。  
  
### <a name="example"></a>例  
 A`CPropertySheet`は次の&3; つのウィザードのプロパティ ページがあります: `CStylePage`、 `CColorPage`、および`CShapePage`です。  次のコード片は、有効および無効にする方法を示しています、**戻る**と**次**ウィザードのプロパティ ページのボタンです。  
  
 [!code-cpp[NVC_MFCDocView #&140;](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&141;](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="a-namesetwizardmodea--cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>CPropertySheet::SetWizardMode  
 ウィザードとしてのプロパティ ページを設定します。  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>コメント  
 ウィザードのプロパティ ページの主な特徴、ユーザーが次を使用して移動または [完了]、バックアップをキャンセル ボタンのタブではなく。  
  
 呼び出す`SetWizardMode`呼び出す前に[DoModal](#domodal)します。 呼び出した後`SetWizardMode`、`DoModal`いずれかを返す**ID_WIZFINISH** (この場合、ユーザーは、[完了] ボタンで終了) または**IDCANCEL**します。  
  
 `SetWizardMode`PSH_WIZARD フラグを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&142;](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




