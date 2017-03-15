---
title: "CToolBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBar
dev_langs:
- C++
helpviewer_keywords:
- Windows toolbar common controls [C++]
- control bars [C++], CToolBar class
- toolbars [C++], CToolBar class
- buttons [C++], MFC toolbars
- bitmaps [C++], button controls
- CToolBar class
- Windows common controls [C++], CToolBar class
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: d7fea85426eef09f3694bd26e037acaaccc63f01
ms.lasthandoff: 02/24/2017

---
# <a name="ctoolbar-class"></a>CToolBar クラス
一連のビットマップ ボタンおよびオプションの区切り記号を含むコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|`CToolBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|指定されたコマンド ID を持つボタンのインデックスを返します|  
|[用意されて](#create)|Windows ツールバーを作成し、それをアタッチ、`CToolBar`オブジェクトです。|  
|[CToolBar::CreateEx](#createex)|作成、 `CToolBar` embedded 用の他のスタイルを使用してオブジェクト`CToolBarCtrl`オブジェクトです。|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|ID、スタイル、およびボタンのイメージ数を取得します。|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|ボタンのスタイルを取得します。|  
|[CToolBar::GetButtonText](#getbuttontext)|ボタンに表示されるテキストを取得します。|  
|[CToolBar::GetItemID](#getitemid)|ボタンまたは指定したインデックスに区切り線のコマンド ID を返します。|  
|[CToolBar::GetItemRect](#getitemrect)|指定したインデックス位置にある項目を表示する四角形を取得します。|  
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
|[CToolBar::LoadBitmap](#loadbitmap)|ビットマップ ボタンの画像を含むビットマップを読み込みます。|  
|[CToolBar::LoadToolBar](#loadtoolbar)|リソース エディターで作成したツール バー リソースを読み込みます。|  
|[CToolBar::SetBitmap](#setbitmap)|ビットマップ イメージを設定します。|  
|[CToolBar::SetButtonInfo](#setbuttoninfo)|ID、スタイル、およびボタンのイメージ数を設定します。|  
|[CToolBar::SetButtons](#setbuttons)|ボタンのスタイルとボタンのイメージ、ビットマップ内のインデックスを設定します。|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを設定します。|  
|[CToolBar::SetButtonText](#setbuttontext)|ボタンに表示されるテキストを設定します。|  
|[CToolBar::SetHeight](#setheight)|ツールバーの高さを設定します。|  
|[CToolBar::SetSizes](#setsizes)|ボタンおよびビットマップのサイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 ボタンは、プッシュ ボタン、チェック ボックス ボタン、またはオプション ボタンのように動作します。 `CToolBar`オブジェクトは、クラスから派生するフレーム ウィンドウ オブジェクトの通常の埋め込みメンバー [CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)します。  
  
 [CToolBar::GetToolBarCtrl](#gettoolbarctrl)、メンバー関数新しい MFC 4.0 を使用するツールバーをカスタマイズおよびその他の機能の Windows コモン コントロールのサポートを活用します。 `CToolBar`メンバー関数は、Windows のコモン コントロール; の機能のほとんどを提供します。ただし、呼び出す`GetToolBarCtrl`、Windows 95/98 ツールバーの特性をさらに多くのツールバーを与えることができます。 呼び出すと`GetToolBarCtrl`への参照を返すには、`CToolBarCtrl`オブジェクトです。 参照してください[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 Visual C は、ツールバーを作成する&2; つのメソッドを提供します。 リソース エディターを使用してツール バー リソースを作成するには、次の手順を実行します。  
  
1.  ツール バー リソースを作成します。  
  
2.  構築、`CToolBar`オブジェクトです。  
  
3.  呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、添付、`CToolBar`オブジェクトです。  
  
4.  呼び出す[LoadToolBar](#loadtoolbar)ツール バー リソースを読み込めません。  
  
 それ以外の場合、これらの手順に従います。  
  
1.  構築、`CToolBar`オブジェクトです。  
  
2.  呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、添付、`CToolBar`オブジェクトです。  
  
3.  呼び出す[LoadBitmap](#loadbitmap)をツール バー ボタンのイメージを含むビットマップを読み込みます。  
  
4.  呼び出す[SetButtons](#setbuttons)ボタン スタイルを設定し、ビットマップ内のイメージを各ボタンを関連付けます。  
  
 ツールバーにあるすべてのボタン イメージは、1 つのビットマップは、各ボタンの&1; つのイメージを含める必要がありますから取得されます。 すべてのイメージが同じサイズにする必要があります。既定では 15 ピクセル、高さ、幅 16 ピクセルです。 イメージは、ビットマップのサイド バイ サイドである必要があります。  
  
 `SetButtons`関数は、コントロール Id と、配列内の要素の数を指定する整数の配列へのポインターを受け取ります。 この関数は、各ボタンの ID は、配列の対応する要素の値を設定し、各ボタンにビットマップのボタンの画像の位置を指定するイメージのインデックスを割り当てます。 配列の要素が値を持つ場合**として**イメージのインデックスが割り当てられていません。  
  
 ビットマップ内のイメージの順序は、通常、画面に描画されますが、使用することができます、[です](#setbuttoninfo)イメージ順序と描画順序との間のリレーションシップを変更する関数。  
  
 ツールバー内のすべてのボタンは、同じサイズです。 既定値では、24 x 22 (ピクセル単位) はに従って*ソフトウェア設計のための Windows インターフェイスのガイドライン*します。 イメージとボタンのディメンション間でさらに空き領域を使用すると、イメージの周囲に罫線を形成します。  
  
 各ボタンは、1 つのイメージです。 ボタンの状態のさまざまなし (、押されたダウン、無効になり、ダウンしている無効な不確定な) のスタイルが&1; つのイメージから生成します。 ビットマップできますが、任意の色は黒と灰色の網掛けでイメージで最良の結果を実現できます。  
  
> [!WARNING]
> `CToolBar`最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに Visual Studio は自動的に、必要に応じて、16 色のビットマップ イメージを変換し、イメージが変換された場合に警告メッセージを表示します。 (画像を編集するのには外部エディターを使用して) 以上の 16 の色の画像を使用するアプリケーションが予期しない動作があります。  
  
 ツール バー ボタンは、既定では、プッシュ ボタンを模倣します。 ただし、チェック ボックスまたはオプション ボタンのツール バー ボタンを模倣もできます。 チェック ボックスのボタンがある&3; つの状態: チェック、オフ、および中間です。 オプション ボタンがある&2; つの状態: オンおよびオフにします。  
  
 配列を指すことがなく、各ボタンまたは区分線のスタイルを設定するには、呼び出す[に](#getbuttonstyle)、スタイルを取得し、呼び出す[ツール](#setbuttonstyle)の代わりに`SetButtons`します。 `SetButtonStyle`実行時にボタンのスタイルを変更する場合に適しています。  
  
 ボタンに表示されるテキストを割り当てるを呼び出す[GetButtonText](#getbuttontext) 、ボタンに表示し、呼び出すテキストを取得する[setbuttontext の各](#setbuttontext)テキストを設定します。  
  
 チェック ボックス ボタンを作成するには、そのスタイル**TBBS_CHECKBOX**か使用して、`CCmdUI`オブジェクトの`SetCheck`でメンバー関数、`ON_UPDATE_COMMAND_UI`ハンドラー。 呼び出す`SetCheck`チェック ボックス ボタンにプッシュ ボタンをオンにします。 渡す`SetCheck`0 の引数のオフ、または 2 つの場合はオフの場合、1 の不確定です。  
  
 オプション ボタンを作成するには、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトの[SetRadio](../../mfc/reference/ccmdui-class.md#setradio)メンバー関数から、`ON_UPDATE_COMMAND_UI`ハンドラー。 渡す`SetRadio`チェック以外の 0 の引数。 無線グループの相互に排他的な動作を提供するために必要`ON_UPDATE_COMMAND_UI`すべてのグループ内のボタンのハンドラーです。  
  
 使用する方法について`CToolBar`、記事を参照して[MFC ツールバーの実装](../../mfc/mfc-toolbar-implementation.md)と[テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="a-namecommandtoindexa--ctoolbarcommandtoindex"></a><a name="commandtoindex"></a>CToolBar::CommandToIndex  
 このメンバー関数は、最初のツールバーのボタンの位置 0 から始まるコマンド ID と一致するインデックスを返します`nIDFind`します。  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFind`  
 ツール バー ボタンのコマンド ID です。  
  
### <a name="return-value"></a>戻り値  
 ボタン、またはボタンに指定されたコマンド ID があるない場合は –&1; のインデックス  
  
##  <a name="a-namecreatea--ctoolbarcreate"></a><a name="create"></a>用意されて  
 このメンバー関数は、Windows ツールバー (子ウィンドウ) を作成し、関連付けます、`CToolBar`オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ツールバーの親ウィンドウへのポインター。  
  
 `dwStyle`  
 ツールバーのスタイル。 追加のスタイルは次のとおりです。  
  
- `CBRS_TOP`コントロール バーは、フレーム ウィンドウの上部には。  
  
- `CBRS_BOTTOM`コントロール バーでは、フレーム ウィンドウの下部にあります。  
  
- `CBRS_NOALIGN`コントロール バーは、親のサイズが変更されたときに再配置されません。  
  
- `CBRS_TOOLTIPS`コントロール バーには、ツール ヒントが表示されます。  
  
- **CBRS_SIZE_DYNAMIC**コントロール バーは動的です。  
  
- **CBRS_SIZE_FIXED**コントロール バーを固定します。  
  
- **CBRS_FLOATING**コントロール バーがフローティングします。  
  
- `CBRS_FLYBY`ステータス バーには、ボタンについての情報が表示されます。  
  
- **CBRS_HIDE_INPLACE**コントロール バーがユーザーに表示されません。  
  
 `nID`  
 ツールバーの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、ツールバーの高さを既定値に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&179;](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="a-namecreateexa--ctoolbarcreateex"></a><a name="createex"></a>CToolBar::CreateEx  
 Windows のツールバー (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CToolBar`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,  
    CRect rcBorders = CRect(
    0, 
    0, 
    0, 
    0), 
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ツールバーの親ウィンドウへのポインター。  
  
 `dwCtrlStyle`  
 埋め込みを作成するための追加のスタイル[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)オブジェクトです。 既定では、この値に設定**TBSTYLE_FLAT**します。 ツール バー スタイルの一覧については、次を参照してください。`dwStyle`します。  
  
 `dwStyle`  
 ツールバーのスタイル。 参照してください[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の適切なスタイルの一覧です。  
  
 *rcBorders*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md)ウィンドウのツールバーの境界線の幅を定義するオブジェクト。 これらの罫線は、既定では、境界線なしのツールバーのウィンドウで、0,0,0,0 に設定されます。  
  
 `nID`  
 ツールバーの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、ツールバーの高さを既定値に設定します。  
  
 使用`CreateEx`の代わりに[作成](#create)、特定のスタイルは、組み込みのツール バー コントロールの作成時に存在する必要がある場合。 たとえば、設定`dwCtrlStyle`に**TBSTYLE_FLAT |バーオブジェクト**Internet Explorer 4 ツールバーのようなツールバーを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&180;](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="a-namectoolbara--ctoolbarctoolbar"></a><a name="ctoolbar"></a>CToolBar::CToolBar  
 このメンバー関数を作成、`CToolBar`オブジェクトし、既定のサイズを設定します。  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、[作成](#create)ツールバー ウィンドウを作成します。  
  
##  <a name="a-namegetbuttoninfoa--ctoolbargetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBar::GetButtonInfo  
 このメンバー関数は、コントロールの ID、スタイル、およびツール バー ボタンまたはで指定された場所に区切り線イメージのインデックスを取得*nIndex します。*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ツール バー ボタンまたは区切り記号の情報を取得するインデックス。  
  
 `nID`  
 参照、 **UINT**ボタンのコマンド ID に設定されています。  
  
 `nStyle`  
 参照、 **UINT**ボタンのスタイルに設定されています。  
  
 `iImage`  
 ボタンのイメージ、ビットマップ内のインデックスに設定されている整数への参照。  
  
### <a name="remarks"></a>コメント  
 これらの値がによって参照される変数に割り当てられた`nID`、 `nStyle`、および`iImage`です。 イメージのインデックスは、すべてのツール バー ボタンのイメージを含むビットマップ内の画像の位置です。 最初の画像は、位置 0 です。  
  
 場合`nIndex`、区切り文字を指定`iImage`区切り記号の幅 (ピクセル単位) に設定されています。  
  
##  <a name="a-namegetbuttonstylea--ctoolbargetbuttonstyle"></a><a name="getbuttonstyle"></a>CToolBar::GetButtonStyle  
 このメンバー関数を呼び出してボタンまたはツールバーの区分線のスタイルを取得します。  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得するツールバーのボタンまたは区切り記号のスタイルのインデックス。  
  
### <a name="return-value"></a>戻り値  
 ボタンまたはで指定された区切り記号のスタイル`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 ボタンのスタイルは、ボタンの表示方法と、ユーザー入力に応答する方法を決定します。 参照してください[ツール](#setbuttonstyle)のボタンのスタイルの例を示します。  
  
##  <a name="a-namegetbuttontexta--ctoolbargetbuttontext"></a><a name="getbuttontext"></a>CToolBar::GetButtonText  
 このメンバー関数を呼び出して、ボタンに表示されるテキストを取得します。  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得するテキストのインデックス。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得するテキストを格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`CString`ボタンのテキストを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバーの&2; 番目の形式の関数の塗りつぶし、`CString`文字列のテキストを持つオブジェクト。  
  
##  <a name="a-namegetitemida--ctoolbargetitemid"></a><a name="getitemid"></a>CToolBar::GetItemID  
 このメンバー関数は、ボタンまたはで指定された区切り記号のコマンド ID を返す`nIndex`します。  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ID を取得する項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ボタンまたはで指定された区切り記号のコマンド ID`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 区切り記号を返す**として**します。  
  
##  <a name="a-namegetitemrecta--ctoolbargetitemrect"></a><a name="getitemrect"></a>CToolBar::GetItemRect  
 このメンバー関数によって、`RECT`構造体にあるアドレスが含まれている`lpRect`ボタンまたはで指定された区切り記号の座標を持つ`nIndex`です。  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 四角形の座標の項目 (ボタンまたは区切り記号) のインデックスでは、取得します。  
  
 `lpRect`  
 アドレス、 [RECT](../../mfc/reference/rect-structure1.md)アイテムの座標を格納する構造です。  
  
### <a name="remarks"></a>コメント  
 座標は、ツールバーの左上隅に対して相対的 (ピクセル単位)。  
  
 使用`GetItemRect`コンボ ボックスまたは他のコントロールを置換する区切り記号の座標を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CToolBar::SetSizes](#setsizes)します。  
  
##  <a name="a-namegettoolbarctrla--ctoolbargettoolbarctrl"></a><a name="gettoolbarctrl"></a>CToolBar::GetToolBarCtrl  
 このメンバー関数では、基になる一般的なコントロールに直接アクセスができます。  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CToolBarCtrl` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 使用`GetToolBarCtrl`Windows ツール バー コモン コントロールの機能を利用して、サポートを活用するために[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)のツールバーのカスタマイズを提供します。  
  
 コモン コントロールの使い方の詳細については、記事を参照してください。[コントロール](../../mfc/controls-mfc.md)と[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI&#15;](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="a-nameloadbitmapa--ctoolbarloadbitmap"></a><a name="loadbitmap"></a>CToolBar::LoadBitmap  
 指定されるビットマップを読み込むには、このメンバー関数を呼び出す`lpszResourceName`または`nIDResource`です。  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込むビットマップのリソース名へのポインター。  
  
 `nIDResource`  
 リソースを読み込むには、ビットマップの ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、各ツール バー ボタンの&1; つのイメージを含める必要があります。 イメージがない場合、標準のサイズ (幅 16 ピクセル、高さ 15 ピクセル) の呼び出し[SetSizes](#setsizes)ボタンのサイズとそのイメージを設定します。  
  
> [!WARNING]
> `CToolBar`最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに Visual Studio は自動的に、必要に応じて、16 色のビットマップ イメージを変換し、イメージが変換された場合に警告メッセージを表示します。 (画像を編集するのには外部エディターを使用して) 以上の 16 の色の画像を使用するアプリケーションが予期しない動作があります。  
  
##  <a name="a-nameloadtoolbara--ctoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CToolBar::LoadToolBar  
 指定されたツールバーを読み込むには、このメンバー関数を呼び出す`lpszResourceName`または`nIDResource`です。  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込まれる、ツールバーのリソース名へのポインター。  
  
 `nIDResource`  
 リソースを読み込むには、ツールバーの ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[ツール バー エディター](../../windows/toolbar-editor.md)の詳細については、ツール バー リソースを作成します。  
  
### <a name="example"></a>例  
  例を参照してください[CToolBar::CreateEx](#createex)します。  
  
##  <a name="a-namesetbitmapa--ctoolbarsetbitmap"></a><a name="setbitmap"></a>CToolBar::SetBitmap  
 ツールバーのビットマップ イメージを設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>パラメーター  
 *hbmImageWell*  
 ツールバーに関連付けられているビットマップ イメージのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`SetBitmap`をユーザーがボタンの操作によって変更された文書でアクションを実行した後は、ビットマップ イメージを変更します。  
  
##  <a name="a-namesetbuttoninfoa--ctoolbarsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBar::SetButtonInfo  
 ボタンのコマンド ID、スタイル、およびイメージの数を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ボタンまたは情報を設定する対象の区切り記号の&0; から始まるインデックス。  
  
 `nID`  
 ボタンのコマンド ID を設定する値です。  
  
 `nStyle`  
 新しいボタン スタイル。 次のボタンのスタイルがサポートされています。  
  
- **TBBS_BUTTON**標準プッシュ ボタン (既定値)  
  
- **TBBS_SEPARATOR**区切り記号  
  
- **TBBS_CHECKBOX**自動チェック ボックス ボタン  
  
- **TBBS_GROUP**ボタンのグループの先頭をマーク  
  
- **TBBS_CHECKGROUP**チェック ボックス ボタンのグループの先頭をマーク  
  
- **TBBS_DROPDOWN**ドロップダウン リスト ボタンを作成します。  
  
- **TBBS_AUTOSIZE**ボタンのテキストではなく、イメージのサイズに基づくボタンの幅が計算されます。  
  
- **TBBS_NOPREFIX**ボタンのテキストには、関連付けられているアクセラレータ プレフィックスはありません。  
  
 `iImage`  
 ボタンのイメージ、ビットマップ内の新しいインデックス。  
  
### <a name="remarks"></a>コメント  
 スタイルが設定されて区切り記号、 **TBBS_SEPARATOR**、この関数では、区切り記号の幅を設定に格納された値をピクセル単位で`iImage`します。  
  
> [!NOTE]
>  使用してボタンの状態を設定することも、`nStyle`パラメーター。 ただし、ボタンの状態がによって制御されるため、 [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)ハンドラー、いずれかのステータスを使用して設定する`SetButtonInfo`は、次のアイドル状態の処理中に失われます。 参照してください[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031: コントロール バー](../../mfc/tn031-control-bars.md)の詳細。  
  
 詳細については、ビットマップ イメージとボタンは、次を参照してください。、 [CToolBar](../../mfc/reference/ctoolbar-class.md)の概要と[CToolBar::LoadBitmap](#loadbitmap)します。  
  
##  <a name="a-namesetbuttonsa--ctoolbarsetbuttons"></a><a name="setbuttons"></a>CToolBar::SetButtons  
 このメンバー関数では、各ツール バー ボタンのコマンド ID を配列の対応する要素で指定された値に設定`lpIDArray`します。  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpIDArray`  
 コマンド Id の配列へのポインター。 できます**NULL**空のボタンを割り当てることです。  
  
 `nIDCount`  
 配列内の要素の数が指す`lpIDArray`します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 配列の要素が値を持つ場合**として**、区切り記号は、ツールバーの対応する位置に作成します。 この関数に各ボタンのスタイルを設定するも**TBBS_BUTTON**と区分線のスタイルを**TBBS_SEPARATOR**、し、各ボタンにイメージのインデックスを割り当てます。 イメージのインデックスでは、ボタンのイメージ、ビットマップ内の位置を指定します。  
  
 この関数は区切り記号にイメージのインデックスを割り当てませんアカウント、ビットマップ内の区切り記号をする必要はありません。 ツールバーは、0 の位置にあるボタンを持つ場合、1 と 3、2、イメージ、ビットマップ内の位置 0、1、および 2 での位置に区切り線に割り当てられますボタンの位置 0、1、および 3 にそれぞれします。  
  
 場合`lpIDArray`は**NULL**、この関数は指定される項目の数の領域を割り当てて`nIDCount`します。 使用[です](#setbuttoninfo)各項目の属性を設定します。  
  
##  <a name="a-namesetbuttonstylea--ctoolbarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CToolBar::SetButtonStyle  
 ボタンまたは区切り記号、またはボタンをグループ化のスタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ボタンまたはその情報を設定する区切り記号のインデックス。  
  
 `nStyle`  
 ボタンのスタイル。 次のボタンのスタイルがサポートされています。  
  
- **TBBS_BUTTON**標準プッシュ ボタン (既定値)  
  
- **TBBS_SEPARATOR**区切り記号  
  
- **TBBS_CHECKBOX**自動チェック ボックス ボタン  
  
- **TBBS_GROUP**ボタンのグループの先頭をマーク  
  
- **TBBS_CHECKGROUP**チェック ボックス ボタンのグループの先頭をマーク  
  
- **TBBS_DROPDOWN**ドロップダウン リスト ボタンを作成  
  
- **TBBS_AUTOSIZE**ボタンのテキストではなく、イメージのサイズに基づくボタンの幅が計算されます  
  
- **TBBS_NOPREFIX**ボタンのテキストには、関連付けられているアクセラレータ プレフィックスはありません。  
  
### <a name="remarks"></a>コメント  
 ボタンのスタイルは、ボタンの表示方法と、ユーザー入力に応答する方法を決定します。  
  
 呼び出しの前に`SetButtonStyle`を呼び出す、[に](#getbuttonstyle)ボタンまたは区切り記号のスタイルを取得します。  
  
> [!NOTE]
>  使用してボタンの状態を設定することも、`nStyle`パラメーター。 ただし、ボタンの状態がによって制御されるため、 [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)ハンドラー、いずれかのステータスを使用して設定する`SetButtonStyle`は、次のアイドル状態の処理中に失われます。 参照してください[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031: コントロール バー](../../mfc/tn031-control-bars.md)の詳細。  
  
##  <a name="a-namesetbuttontexta--ctoolbarsetbuttontext"></a><a name="setbuttontext"></a>CToolBar::SetButtonText  
 ボタンにテキストを設定するには、この関数を呼び出します。  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 テキストを設定するボタンのインデックス。  
  
 `lpszText`  
 ボタンに設定するテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CToolBar::GetToolBarCtrl](#gettoolbarctrl)します。  
  
##  <a name="a-namesetheighta--ctoolbarsetheight"></a><a name="setheight"></a>CToolBar::SetHeight  
 このメンバー関数、ツールバーの高さをピクセル単位で指定された値に設定する`cyHeight`です。  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `cyHeight`  
 ツールバーのピクセル単位の高さ。  
  
### <a name="remarks"></a>コメント  
 呼び出した後[SetSizes](#setsizes)、標準ツールバーの高さをオーバーライドするこのメンバー関数を使用します。 高さが小さすぎる場合は、下部にあるボタンがクリップされます。  
  
 この関数が呼び出されない場合、フレームワークは、ツールバーの高さを決定する、ボタンのサイズを使用します。  
  
##  <a name="a-namesetsizesa--ctoolbarsetsizes"></a><a name="setsizes"></a>CToolBar::SetSizes  
 ツールバーのボタンをピクセル単位で指定された単位のサイズに設定するには、このメンバー関数を呼び出す*sizeButton*します。  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizeButton*  
 各ボタンのピクセル単位のサイズ。  
  
 `sizeImage`  
 各イメージのピクセル単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 `sizeImage`パラメーターは、ツールバーのビットマップ内のイメージのピクセル単位のサイズを含める必要があります。 内のディメンション*sizeButton*イメージと 7 ピクセル幅と高さに 6 ピクセルを保持するのに十分である必要があります。 この関数では、ボタンの高さにツールバーの高さも設定します。  
  
 このメンバー関数の呼び出しのみに従っていないツールバー*ソフトウェア設計のための Windows インターフェイスのガイドライン*ボタンとイメージのサイズに関する推奨事項です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCListView&#8;](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [MFC サンプル DLGCBR32](../../visual-cpp-samples.md)   
 [MFC サンプル DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)

