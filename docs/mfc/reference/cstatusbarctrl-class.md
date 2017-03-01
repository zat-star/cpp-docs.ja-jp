---
title: "CStatusBarCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CStatusBarCtrl
- CStatusBarCtrl class
- status bar controls
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
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
ms.openlocfilehash: 619fb88b96f60ab2dc0911cb8ea0b66574ea4287
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl クラス
Windows コモン ステータス バー コントロール の機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|ステータス バー コントロールを作成し、それをアタッチ、`CStatusBarCtrl`オブジェクトです。|  
|[CStatusBarCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してステータス バー コントロールを作成し、それにアタッチ、`CStatusBarCtrl`オブジェクトです。|  
|[CStatusBarCtrl::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分と呼び出されます。|  
|[CStatusBarCtrl::GetBorders](#getborders)|現在のステータス バー コントロールの水平および垂直方向の境界線の幅を取得します。|  
|[CStatusBarCtrl::GetIcon](#geticon)|現在のステータス バー コントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。|  
|[CStatusBarCtrl::GetParts](#getparts)|ステータス バー コントロールのパーツの数を取得します。|  
|[CStatusBarCtrl::GetRect](#getrect)|ステータス バー コントロール内のパーツの外接する四角形を取得します。|  
|[CStatusBarCtrl::GetText](#gettext)|ステータス バー コントロールの特定の部分からテキストを取得します。|  
|[CStatusBarCtrl::GetTextLength](#gettextlength)|ステータス バー コントロールの特定の部分のテキストの文字の長さを取得します。|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|ステータス バー内のウィンドウのツールヒントのテキストを取得します。|  
|[CStatusBarCtrl::IsSimple](#issimple)|簡易モードではステータス ウィンドウのコントロールを確認します。|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|ステータス バーの背景色を設定します。|  
|[CStatusBarCtrl::SetIcon](#seticon)|ステータス バー ペインのアイコンを設定します。|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|バー コントロールの描画領域には、状態の最小の高さを設定します。|  
|[CStatusBarCtrl::SetParts](#setparts)|ステータス バー コントロールと各部分の右端の座標の部分の数を設定します。|  
|[CStatusBarCtrl::SetSimple](#setsimple)|ステータス バー コントロールが単純なテキストが表示されますか、設定を以前の呼び出しによってすべてのコントロール パーツが表示されるかどうかを指定`SetParts`します。|  
|[CStatusBarCtrl::SetText](#settext)|ステータス バー コントロールの特定の部分にテキストを設定します。|  
|[CStatusBarCtrl::SetTipText](#settiptext)|ステータス バー ペインのツールヒント テキストを設定します。|  
  
## <a name="remarks"></a>コメント  
 「ステータス バー コントロール」ウィンドウは、水平方向、通常、アプリケーションがさまざまな種類のステータス情報を表示できる、親ウィンドウの下部に表示されます。 ステータス バー コントロールは、情報の&1; つ以上の型を表示する部分に分けることができます。  
  
 このコントロール (つまり、`CStatusBarCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 使用する方法について`CStatusBarCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-namecreatea--cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::Create  
 ステータス バー コントロールを作成し、それをアタッチ、`CStatusBarCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ステータス バー コントロールのスタイルを指定します。 ステータス バーに示されているコントロールのスタイルの任意の組み合わせを適用[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このパラメーターを含める必要があります、 **WS_CHILD**スタイル。 必要があります、 **WS_VISIBLE**スタイル。  
  
 `rect`  
 ステータス バー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 ステータス バー コントロールの親ウィンドウを通常指定する`CDialog`です。 ことはできません**NULL です。**  
  
 `nID`  
 ステータス バー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CStatusBarCtrl`で&2; つの手順を実行します。 最初に、コンス トラクターを呼び出すし、し、呼び出す**作成**、ステータス バー コントロールを作成およびそれにアタッチする、`CStatusBarCtrl`オブジェクトです。  
  
 ステータス ウィンドウの既定の位置は、親ウィンドウの下部にあるが、指定することができます、`CCS_TOP`スタイルを親ウィンドウのクライアント領域の上部に表示することができます。 指定できます、 **SBARS_SIZEGRIP**対象の状態ウィンドウの右端にあるサイズ変更グリップのスタイル。 結合、`CCS_TOP`と**SBARS_SIZEGRIP**スタイルは使用しないで、システムがステータス ウィンドウに描画場合でも、結果のサイズ変更グリップが機能していないためです。  
  
 拡張ウィンドウ スタイルを使用して、ステータス バーを作成するには、呼び出す[CStatusBarCtrl::CreateEx](#createex)の代わりに**作成**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CStatusBarCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 ステータス バー コントロールのスタイルを指定します。 ステータス バーに示されているコントロールのスタイルの任意の組み合わせを適用[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このパラメーターを含める必要があります、 **WS_CHILD**スタイル。 必要があります、 **WS_VISIBLE**スタイル。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="a-namecstatusbarctrla--cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl  
 `CStatusBarCtrl` オブジェクトを構築します。  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="a-namedrawitema--cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::DrawItem  
 オーナー描画ステータス バー コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、この関数をオーバーライド`CStatusBarCtrl`オブジェクトです。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
##  <a name="a-namegetbordersa--cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl::GetBorders  
 水平および垂直方向の境界線のおよび四角形の領域のステータス バー コントロールの現在の幅を取得します。  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pBorders*  
 3 つの要素を持つ整数配列のアドレスです。 最初の要素は、水平方向の境界線の幅を受け取る、2 つ目が垂直方向の境界線の幅を受け取るおよび四角形の間の境界線の幅を受け取ります。  
  
 *nHorz*  
 水平方向の境界線の幅を受け取る整数への参照。  
  
 *nVert*  
 垂直方向の境界線の幅を受け取る整数への参照。  
  
 *nSpacing*  
 四角形の間の境界線の幅を受け取る整数への参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 これらの罫線は、コントロールの端やテキストを含むコントロール内で四角形の間隔を決定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="a-namegeticona--cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon  
 現在のステータス バー コントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iPart`|取得するアイコンを含む部分の&0; から始まるインデックス。 このパラメーターが-1 の場合は、ステータス バーは簡易モードのステータス バーと見なされます。|  
  
### <a name="return-value"></a>戻り値  
 アイコンへのハンドル場合、メソッドが成功しました。それ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 ステータス バー コントロールは、パーツとも呼ばれますのテキストの出力ペインの行で構成されます。 ステータス バーの詳細については、次を参照してください。 [MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[CStatusBarCtrl オブジェクトのモードの設定](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)します。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_statusBar`つまり、現在のステータス バー コントロールのアクセスに使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在のステータス バー コントロールの&2; つのペインにアイコンをコピーします。 前のセクションのコード例は、3 つのペインで、ステータス バー コントロールを作成し、最初のウィンドウにアイコンを追加します。 この例では、最初のペインからアイコンを取得し、2 番目と&3; 番目のペインに追加されます。  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="a-namegetpartsa--cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl::GetParts  
 ステータス バー コントロールのパーツの数を取得します。  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nParts`  
 座標を取得する対象の部分の数。 このパラメーターがコントロールの部分の数よりも大きい場合は、メッセージは、既存の部品のみ座標を取得します。  
  
 *pParts*  
 指定された部分の数と同じ数の要素を持つ整数配列のアドレス`nParts`です。 配列内の各要素は、対応する一部の右エッジからクライアント座標を受け取ります。 – に要素が設定されている場合は、1、その部分の右端の位置までのステータス バーの右端からです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コントロール内の部分の数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数では、部分の指定した数値の右端の座標も取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#3;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="a-namegetrecta--cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl::GetRect  
 ステータス バー コントロール内のパーツの外接する四角形を取得します。  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPane`  
 外接する四角形を取得する部分の&0; から始まるインデックス。  
  
 `lpRect`  
 アドレス、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&4;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="a-namegettexta--cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText  
 ステータス バー コントロールの特定の部分からテキストを取得します。  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 テキストを受け取るバッファーのアドレス。 このパラメーターは、null で終わる文字列です。  
  
 `nPane`  
 テキストを取得する対象の部分の&0; から始まるインデックス。  
  
 `pType`  
 型情報を受け取る整数へのポインター。 種類は、これらの値のいずれかになります。  
  
- **0**ステータス バーの平面より下位に表示する罫線とテキストを描画します。  
  
- `SBT_NOBORDERS`国境なきテキストを描画します。  
  
- `SBT_POPOUT`ステータス バーの平面より上に表示する罫線とテキストを描画します。  
  
- `SBT_OWNERDRAW`テキストがある場合、`SBT_OWNERDRAW`図面の種類、`pType`このメッセージを受信し、長さと操作の型ではなくテキストに関連付けられている 32 ビット値を返します。  
  
### <a name="return-value"></a>戻り値  
 テキストの文字の長さまたは[CString](../../atl-mfc-shared/reference/cstringt-class.md)現在のテキストを格納します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#5;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="a-namegettextlengtha--cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetTextLength  
 ステータス バー コントロールの特定の部分のテキストの文字の長さを取得します。  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPane`  
 テキストを取得する対象の部分の&0; から始まるインデックス。  
  
 `pType`  
 型情報を受け取る整数へのポインター。 種類は、これらの値のいずれかになります。  
  
- **0**ステータス バーの平面より下位に表示する罫線とテキストを描画します。  
  
- `SBT_NOBORDERS`国境なきテキストを描画します。  
  
- `SBT_OWNERDRAW`親ウィンドウで、テキストを描画します。  
  
- `SBT_POPOUT`ステータス バーの平面より上に表示する罫線とテキストを描画します。  
  
### <a name="return-value"></a>戻り値  
 テキストの文字数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&6;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="a-namegettiptexta--cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText  
 ステータス バー内のウィンドウのツールヒントのテキストを取得します。  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPane`  
 ツールヒントのテキストが表示されるステータス バー ペインの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ツールヒントで使用するテキストを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="a-nameissimplea--cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::IsSimple  
 簡易モードではステータス ウィンドウのコントロールを確認します。  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス ウィンドウ コントロールが単純なモードである場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetbkcolora--cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor  
 ステータス バーの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 **COLORREF**新しい背景色を指定する値。 指定の`CLR_DEFAULT`がステータス バーの既定の背景色を使用する値。  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)を前の既定の背景色を表す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#8;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="a-nameseticona--cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::SetIcon  
 ステータス バー ペインのアイコンを設定します。  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPane`  
 アイコンにお届けする、ウィンドウの&0; から始まるインデックス。 このパラメーターが-1 の場合は、ステータス バーは簡易ステータス バーと見なされます。  
  
 `hIcon`  
 設定するアイコンへのハンドルします。 この値は場合**NULL**、部分から除去されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CStatusBarCtrl::SetBkColor](#setbkcolor)します。  
  
##  <a name="a-namesetminheighta--cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl::SetMinHeight  
 バー コントロールの描画領域には、状態の最小の高さを設定します。  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMin`  
 最小の高さ (ピクセル単位) のコントロールです。  
  
### <a name="remarks"></a>コメント  
 最小の高さの合計は、`nMin`とステータス バー コントロールの垂直方向の境界線の幅&2; 回クリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#9;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="a-namesetpartsa--cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::SetParts  
 ステータス バー コントロールと各部分の右端の座標の部分の数を設定します。  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>パラメーター  
 `nParts`  
 設定する部分の数。 部分の数は 255 より大きい値にすることはできません。  
  
 *pWidths*  
 指定された部分と同じ数の要素を持つ整数配列のアドレス`nParts`です。 配列内の各要素は、対応する一部の右端の位置をクライアント座標を指定します。 要素が 1 の場合、その部分の右端の位置は、コントロールの右端に拡張されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="a-namesetsimplea--cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::SetSimple  
 ステータス バー コントロールが単純なテキストが表示されますか、設定を以前の呼び出しによってすべてのコントロール パーツが表示されるかどうかを指定[呼び出した](#setparts)します。  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSimple`  
 表示タイプのフラグです。 このパラメーターは場合`TRUE`、コントロールがの場合、単純なテキストを表示`FALSE`、複数の部分が表示されます。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションが変更された場合、ステータス バー コントロールから単純ではない単純なまたはその逆システムで、コントロールがすぐに再描画します。  
  
##  <a name="a-namesettexta--cstatusbarctrlsettext"></a><a name="settext"></a>CStatusBarCtrl::SetText  
 ステータス バー コントロールの特定の部分にテキストを設定します。  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 設定されるテキストを指定する null で終わる文字列のアドレス。 `nType` が `SBT_OWNERDRAW` の場合、`lpszText` は 32 ビットのデータを表します。  
  
 `nPane`  
 設定される部分の&0; から始まるインデックス。 この値が 255 の場合、ステータス バー コントロールは 1 つの部分のみで構成される単純なコントロールと見なされます。  
  
 `nType`  
 描画操作の種類。 参照してください[SB_SETTEXT メッセージ](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx)使用可能な値の一覧にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 メッセージによって、変更されたコントロールの部分が無効になり、コントロールが次に `WM_PAINT` のメッセージを受信したときに新しいテキストが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#11;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="a-namesettiptexta--cstatusbarctrlsettiptext"></a><a name="settiptext"></a>CStatusBarCtrl::SetTipText  
 ステータス バー ペインのツールヒント テキストを設定します。  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPane`  
 ツールヒントのテキストが表示されるステータス バー ペインの&0; から始まるインデックス。  
  
 *pszTipText*  
 ツールヒント テキストを含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)

