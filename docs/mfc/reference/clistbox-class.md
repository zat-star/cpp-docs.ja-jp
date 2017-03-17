---
title: "CListBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
dev_langs:
- C++
helpviewer_keywords:
- CListBox class
- list boxes
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f4df970f2df35d399c0c700cf504a76482ad3f6d
ms.lasthandoff: 02/24/2017

---
# <a name="clistbox-class"></a>CListBox クラス
Windows のリスト ボックスの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CListBox : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CListBox::CListBox](#clistbox)|`CListBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|リスト ボックスに文字列を追加します。|  
|[CListBox::CharToItem](#chartoitem)|ユーザー設定を提供する上書き`WM_CHAR`文字列を持たないオーナー描画のリスト ボックスを処理します。|  
|[CListBox::CompareItem](#compareitem)|オーナー描画の並べ替えられたリスト ボックスで、新しい項目の位置を決定するためにフレームワークによって呼び出されます。|  
|[CListBox::Create](#create)|Windows リスト ボックスを作成し、それをアタッチ、`CListBox`オブジェクトです。|  
|[CListBox::DeleteItem](#deleteitem)|ユーザーは、オーナー描画のリスト ボックスから項目を削除するときに、フレームワークによって呼び出されます。|  
|[CListBox::DeleteString](#deletestring)|リスト ボックスから文字列を削除します。|  
|[CListBox::Dir](#dir)|リスト ボックスに、ファイル名、ドライブ、またはその両方、現在のディレクトリからを追加します。|  
|[CListBox::DrawItem](#drawitem)|オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CListBox::FindString](#findstring)|リスト ボックス内の文字列を検索します。|  
|[CListBox::FindStringExact](#findstringexact)|指定した文字列と一致する最初のリスト ボックスの文字列を検索します。|  
|[CListBox::GetAnchorIndex](#getanchorindex)|リスト ボックス内の現在のアンカー項目の&0; から始まるインデックスを取得します。|  
|[CListBox::GetCaretIndex](#getcaretindex)|複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを決定します。|  
|[CListBox::GetCount](#getcount)|リスト ボックスで、文字列の数を返します。|  
|[CListBox::GetCurSel](#getcursel)|リスト ボックスで現在選択されている文字列の&0; から始まるインデックスを返します。|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|リスト ボックスを水平方向にスクロールできることをピクセル単位の幅を返します。|  
|[CListBox::GetItemData](#getitemdata)|リスト ボックスの項目に関連付けられている 32 ビット値を返します。|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|リスト ボックスの項目へのポインターを返します。|  
|[CListBox::GetItemHeight](#getitemheight)|リスト ボックス内の項目の高さを決定します。|  
|[CListBox::GetItemRect](#getitemrect)|現在表示されてリスト ボックスの項目の外接する四角形を返します。|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|各列の項目の数を取得します。|  
|[CListBox::GetLocale](#getlocale)|リスト ボックスのロケール識別子を取得します。|  
|[CListBox::GetSel](#getsel)|リスト ボックスの項目の選択状態を返します。|  
|[CListBox::GetSelCount](#getselcount)|複数選択のリスト ボックスで現在選択されている文字列の数を返します。|  
|[CListBox::GetSelItems](#getselitems)|リスト ボックスで現在選択されている文字列のインデックスを返します。|  
|[CListBox::GetText](#gettext)|リスト ボックスの項目をバッファーにコピーします。|  
|[CListBox::GetTextLen](#gettextlen)|リスト ボックスの項目のバイト単位の長さを返します。|  
|[CListBox::GetTopIndex](#gettopindex)|リスト ボックスに表示される文字列の最初のインデックスを返します。|  
|[CListBox::InitStorage](#initstorage)|リスト ボックス項目と文字列のメモリのブロックに事前に割り当てます。|  
|[CListBox::InsertString](#insertstring)|リスト ボックス内の特定位置に文字列を挿入します。|  
|[CListBox::ItemFromPoint](#itemfrompoint)|ポイントに最も近いリスト ボックスの項目のインデックスを返します。|  
|[CListBox::MeasureItem](#measureitem)|リスト ボックスのサイズを調べるために、オーナー描画のリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|  
|[中](#resetcontent)|リスト ボックスからのすべてのエントリを削除します。|  
|[CListBox::SelectString](#selectstring)|検索し、単一選択リスト ボックスの文字列を選択します。|  
|[CListBox::SelItemRange](#selitemrange)|選択または複数選択のリスト ボックスで、文字列の範囲の選択を解除します。|  
|[CListBox::SetAnchorIndex](#setanchorindex)|拡張の選択を開始するための複数選択のリスト ボックスで、アンカーを設定します。|  
|[CListBox::SetCaretIndex](#setcaretindex)|フォーカスされた四角形を複数選択のリスト ボックスで指定したインデックス位置にある項目に設定します。|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|複数列のリスト ボックスの列の幅を設定します。|  
|[CListBox::SetCurSel](#setcursel)|リスト ボックスの文字列を選択します。|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|リスト ボックスは水平方向にスクロールできるピクセルの幅を設定します。|  
|[CListBox::SetItemData](#setitemdata)|リスト ボックスの項目に関連付けられている 32 ビット値を設定します。|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|リスト ボックスの項目へのポインターを設定します。|  
|[CListBox::SetItemHeight](#setitemheight)|リスト ボックスの項目の高さを設定します。|  
|[CListBox::SetLocale](#setlocale)|リスト ボックスのロケール識別子を設定します。|  
|[CListBox::SetSel](#setsel)|選択または複数選択のリスト ボックスで、リスト ボックス アイテムの選択を解除します。|  
|[CListBox::SetTabStops](#settabstops)|リスト ボックスのタブ ストップの位置を設定します。|  
|[CListBox::SetTopIndex](#settopindex)|リスト ボックスに表示される文字列の最初の&0; から始まるインデックスを設定します。|  
|[CListBox::VKeyToItem](#vkeytoitem)|ユーザー設定を提供する上書き`WM_KEYDOWN`対処するためのリスト ボックスに、 **LBS_WANTKEYBOARDINPUT**一連のスタイルを設定します。|  
  
## <a name="remarks"></a>コメント  
 リスト ボックスには、ファイル名、ユーザーの表示および選択できるなどのアイテムの一覧が表示されます。  
  
 単一選択リスト ボックスに、ユーザーは、1 つの項目を選択できます。 複数選択のリスト ボックスで、項目の範囲を選択できます。 ユーザーは、項目を選択して強調表示されてリスト ボックスは、親ウィンドウに通知メッセージが送信されます。  
  
 ダイアログ テンプレートから、またはコードで直接、リスト ボックスを作成できます。 直接作成するには、構築、 `CListBox` 、object を呼び出す、[作成](#create)Windows リスト ボックス コントロールを作成し、アタッチして、メンバー関数、`CListBox`オブジェクトです。 ダイアログ テンプレートでリスト ボックスを使用する、ダイアログ ボックス クラスでリスト ボックス変数を宣言し、使用して`DDX_Control`ダイアログ ボックス クラスで`DoDataExchange`関数をメンバー変数をコントロールに接続します。 (これを自動的にダイアログ ボックス クラスを制御変数を追加するとします。)  
  
 構築から派生したクラスにワンステップ プロセス`CListBox`します。 呼び出しと派生クラスのコンス トラクターを記述**作成**からコンス トラクター内です。  
  
 リスト ボックスからその親に送信される Windows の通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップ エントリは、次の形式をとります。  
  
 `ON_Notification( id, memberFxn )`  
  
 ここで`id`通知を送信するリスト ボックス コントロールの子ウィンドウの ID を指定し、`memberFxn`通知を処理する記述した親メンバー関数の名前を指定します。  
  
 親の関数のプロトタイプは次のとおりです。  
  
 `afx_msg void memberFxn( );`  
  
 潜在的なメッセージ マップ エントリと親に送信されるケースの説明の一覧を次に示します。  
  
- **ON_LBN_DBLCLK**ユーザーがリスト ボックス内の文字列をダブルクリックします。 リスト ボックスにのみ、 [LBS_NOTIFY](../../mfc/reference/list-box-styles.md)スタイルでは、この通知メッセージを送信します。  
  
- **ON_LBN_ERRSPACE**リスト ボックスは、要求を満たすために十分なメモリを割り当てることができません。  
  
- **ON_LBN_KILLFOCUS**リスト ボックスが入力フォーカスを失うことです。  
  
- **ON_LBN_SELCANCEL**リスト ボックスの現在の選択が取り消されました。 リスト ボックスがある場合にのみ、このメッセージが送信、 **LBS_NOTIFY**スタイル。  
  
- **ON_LBN_SELCHANGE**リスト ボックスで選択が変更されました。 によって、選択が変更された場合、この通知は送信されませんが、 [CListBox::SetCurSel](#setcursel)メンバー関数。 この通知を持つリスト ボックスにのみ適用されます、 **LBS_NOTIFY**スタイル。 **LBN_SELCHANGE**通知メッセージが複数選択のリスト ボックスのユーザーが方向キーを押す場合でも、送信、選択内容は変わりません。  
  
- **ON_LBN_SETFOCUS**リスト ボックスに入力フォーカスが受信します。  
  
- **ON_WM_CHARTOITEM**文字列がないボックスのオーナー描画を受け取る、`WM_CHAR`メッセージです。  
  
- **ON_WM_VKEYTOITEM**リスト ボックスに、 **LBS_WANTKEYBOARDINPUT**スタイルを受け取る、`WM_KEYDOWN`メッセージです。  
  
 作成する場合、 `CListBox` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、`CListBox`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CListBox`オブジェクトを破棄する必要があります、ウィンドウ内で、`CListBox`オブジェクトです。 作成する場合、`CListBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CListBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を親ウィンドウを閉じると破棄するオブジェクト。  
  
 メモリを割り当てられない場合、`CListBox`オブジェクト、オーバーライド、`CListBox`デストラクターが、割り当てを破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="addstring"></a>CListBox::AddString  
 リスト ボックスに文字列を追加します。  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItem`  
 追加するのには、null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の文字列の&0; から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスで作成されなかった場合、 [LBS_SORT](../../mfc/reference/list-box-styles.md)スタイル、文字列がリストの末尾に追加します。 それ以外の場合、リストに、文字列を挿入し、リストの並べ替え。 リスト ボックスの作成時の**LBS_SORT**スタイルを設定しない場合は、 [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md)スタイル、フレームワークで、1 つまたは複数の呼び出しで、一覧が並べ替えられます、`CompareItem`メンバー関数。  
  
 使用[は](#insertstring)リスト ボックス内の指定位置に文字列を挿入します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#3;](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>CListBox::CharToItem  
 リスト ボックスの親ウィンドウを受信時にフレームワークによって呼び出さ、`WM_CHARTOITEM`リスト ボックスからのメッセージ。  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nKey`  
 ユーザーが入力した文字の ANSI コード。  
  
 `nIndex`  
 リスト ボックスのキャレットの現在の位置。  
  
### <a name="return-value"></a>戻り値  
 1 または 2 操作はこれ以上またはキーストロークの既定のアクションを実行する対象のリスト ボックスの項目のインデックスを指定する正の数値を返します。 既定の実装で、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 `WM_CHARTOITEM`を受信すると、リスト ボックスでメッセージが送信される、`WM_CHAR`のみ場合、リスト ボックスをすべて満たしているこれらの条件が、メッセージ。  
  
-   オーナー描画のリスト ボックスがあります。  
  
-   [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md)一連のスタイルを設定します。  
  
-   少なくとも&1; つの項目があります。  
  
 自分がこの関数を呼び出す必要がありますはことはありません。 キーボード メッセージの独自のカスタム処理を指定するには、この関数をオーバーライドします。  
  
 オーバーライドの中では、どのようなアクションを実行するために、フレームワークに指示する値を返す必要があります。 項目の選択のすべての側面を処理し、リスト ボックスで、これ以上操作は必要ありません、戻り値 – 1 または 2 を示します。 返す前に-1 または-2、選択範囲を設定したりできますキャレットを移動します。 選択範囲を設定するには使用[SetCurSel](#setcursel)または[SetSel](#setsel)します。 キャレットを移動するには使用[には](#setcaretindex)です。  
  
 0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスが、指定したアイテムを既定のアクションを実行するを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&4;](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>CListBox::CListBox  
 `CListBox` オブジェクトを構築します。  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>コメント  
 構築する、 `CListBox`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す**ClistBox**し、呼び出す**作成**に接続を Windows リスト ボックスを初期化し、`CListBox`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#1;](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CListBox::CompareItem  
 オーナー描画の並べ替えられたリスト ボックスで、新しい項目の相対位置を調べるためにフレームワークによって呼び出されます。  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCompareItemStruct`  
 Long ポインター、`COMPAREITEMSTRUCT`構造体。  
  
### <a name="return-value"></a>戻り値  
 説明する&2; つのアイテムの相対位置を示す、 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md)構造体。 次の値のいずれかがある可能性があります。  
  
|値|説明|  
|-----------|-------------|  
|–1|項目 1 は、項目 2 の前に並べ替えられます。|  
|0|アイテム 1 とアイテム 2 は、同じを並べ替えます。|  
|1|項目 1 は、項目 2 の後に並べ替えられます。|  
  
 参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の詳細については、`COMPAREITEMSTRUCT`構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 オーナー描画のリスト ボックスを作成するかどうか、 **LBS_SORT**スタイル、リスト ボックスに追加された新しい項目を並べ替え、フレームワークを支援するには、この関数をオーバーライドする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#5;](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>CListBox::Create  
 Windows リスト ボックスを作成し、それをアタッチ、`CListBox`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 リスト ボックスのスタイルを指定します。 任意の組み合わせを適用[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)します。  
  
 `rect`  
 リスト ボックスのサイズと位置を指定します。 いずれか、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `pParentWnd`  
 リスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 ことはできません**NULL**します。  
  
 `nID`  
 リスト ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CListBox`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず**作成**に接続を Windows リスト ボックスを初期化し、`CListBox`オブジェクトです。  
  
 ときに**作成**実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)リスト ボックス コントロールへのメッセージ。  
  
 既定では、これらのメッセージが処理される、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数、`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CListBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)リスト ボックス コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**垂直スクロール バーを追加するには  
  
- **WS_HSCROLL**水平スクロール バーを追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**コントロールのタブ オーダーを許可するには  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#2;](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>CListBox::DeleteItem  
 ユーザーは、オーナー描画から項目を削除する場合に、フレームワークによって呼び出されます`CListBox`オブジェクト、またはリスト ボックスを破棄します。  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDeleteItemStruct`  
 Windows への long ポインター [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md)削除された項目に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 必要に応じて、オーナー描画のリスト ボックスを再描画するには、この関数をオーバーライドします。  
  
 参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)の詳細については、`DELETEITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&6;](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>CListBox::DeleteString  
 位置に項目を削除`nIndex`リスト ボックスからです。  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する文字列の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 一覧に残っている文字列の数。 戻り値は**返します**場合`nIndex`リストの項目の数より大きいインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 次のすべてのアイテム`nIndex`下の&1; つの位置に移動するようになりました。 たとえば、リスト ボックスに&2; つの項目が含まれている場合の最初の項目を削除するにより最初の位置で今すぐに残りの項目。 `nIndex`=&0; の最初の位置に項目を入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#7;](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>CListBox::Dir  
 ファイル名、ドライブ、またはその両方をリスト ボックスの一覧に追加します。  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>パラメーター  
 `attr`  
 任意の組み合わせを指定できます、`enum`値」に記載**CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus)、または、次の値の任意の組み合わせ。  
  
|値|説明|  
|-----------|-------------|  
|0x0000|ファイルの読み取りやに書き込まれることができます。|  
|0x0001|ファイルを読み書きできますに書き込まれません。|  
|0x0002|ファイルは、非表示には、ディレクトリの一覧にないです。|  
|0x0004|ファイルは、システム ファイルです。|  
|0x0010|指定した名前`lpszWildCard`ディレクトリを指定します。|  
|0x0020|ファイルはアーカイブされました。|  
|0x4000|指定した名前に一致するすべてのドライブに含める`lpszWildCard`します。|  
|0x8000|排他フラグ。 排他フラグが設定されている場合は、指定した種類のファイルのみが表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した型のファイルが一覧表示されます。|  
  
 `lpszWildCard`  
 ファイル指定文字列を指します。 文字列にワイルドカードを含めることができます (たとえば、*.\*)。  
  
### <a name="return-value"></a>戻り値  
 最後のファイル名の一覧に追加の&0; から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**新しい文字列を格納する十分な空き領域がある場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#8;](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>CListBox::DrawItem  
 オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**と**itemState**のメンバー、`DRAWITEMSTRUCT`構造体は、実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、この関数をオーバーライド`CListBox`オブジェクトです。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の詳細については、`DRAWITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#9;](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>CListBox::FindString  
 リスト ボックスの選択を変更することがなく、指定したプレフィックスを含むリスト ボックス内の最初の文字列を検索します。  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartAfter`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスが含まれています。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nStartAfter`します。 場合`nStartAfter`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszItem`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索ではケースを独立しておりを指定するため、この文字列には、任意の大文字と小文字を含めることがあります。  
  
### <a name="return-value"></a>戻り値  
 一致する項目の&0; から始まるインデックスまたは**返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 使用して、 [SelectString](#selectstring)メンバー関数の両方を検索して、文字列を選択します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#10;](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>CListBox::FindStringExact  
 指定された文字列と一致する最初のリスト ボックスの文字列を検索`lpszFind`します。  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndexStart`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスを指定します。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nIndexStart`します。 場合`nIndexStart`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszFind`  
 検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索は大文字と小文字を区別はないため、文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 一致する項目のインデックスまたは**返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 ですが、リスト ボックスがオーナー描画スタイルで作成された場合、 [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md)スタイル、`FindStringExact`メンバー関数の値に対してダブルワード値を照合しようとしています。`lpszFind`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#11;](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>CListBox::GetAnchorIndex  
 リスト ボックス内の現在のアンカー項目の&0; から始まるインデックスを取得します。  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は現在のアンカー項目のインデックスそれ以外の場合**返します**します。  
  
### <a name="remarks"></a>コメント  
 複数選択のリスト ボックスには、アンカー項目は、選択した項目を連続したブロック内で最初または最項目です。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::SetAnchorIndex](#setanchorindex)します。  
  
##  <a name="getcaretindex"></a>CListBox::GetCaretIndex  
 複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを決定します。  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスにフォーカス四角形をされている項目の&0; から始まるインデックス。 単一選択リスト ボックスをリスト ボックスには、存在する場合、戻り値は選択されている項目のインデックスです。  
  
### <a name="remarks"></a>コメント  
 項目もかまいません選択されていない可能性があります。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::SetCaretIndex](#setcaretindex)します。  
  
##  <a name="getcount"></a>CListBox::GetCount  
 リスト ボックス内の項目の数を取得します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目の数または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 返されるカウントは、1 (インデックスは&0; から始まる) の最後の項目のインデックス値よりも大きいです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#12;](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>CListBox::GetCurSel  
 単一選択リスト ボックスで、存在する場合は、現在選択されている項目の&0; から始まるインデックスを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 単一選択リスト ボックスである場合は、現在選択されている項目の&0; から始まるインデックス。 `LB_ERR`項目が現在選択されていない場合。  
  
 複数選択のリスト ボックスで、フォーカスがある項目のインデックス。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません`GetCurSel`複数選択のリスト ボックス。 使用[CListBox::GetSelItems](#getselitems)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#13;](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent  
 リスト ボックスから、(ピクセル) することの水平スクロールできる幅を取得します。  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、リスト ボックスのスクロール可能な幅。  
  
### <a name="remarks"></a>コメント  
 これは、リスト ボックスに水平スクロール バーがある場合にのみ適用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#14;](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>CListBox::GetItemData  
 指定したリスト ボックスの項目に関連付けられているアプリケーションによって提供されるダブルワード値を取得します。  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている 32 ビット値または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 ダブルワード値は、`dwItemData`のパラメーター、 [SetItemData](#setitemdata)呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#15;](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>CListBox::GetItemDataPtr  
 ポインターとして指定されたリスト ボックスの項目に関連付けられているアプリケーションによって提供される 32 ビット値を取得 ( **void\***)。  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生した場合は、ポインター、または –&1; を取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#16;](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>CListBox::GetItemHeight  
 リスト ボックス内の項目の高さを決定します。  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の&0; から始まるインデックスを指定します。 このパラメーターには、リスト ボックスがある場合にのみ、使用、 **LBS_OWNERDRAWVARIABLE**スタイルは 0 にそれ以外の場合、設定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目のピクセル単位の高さ。 リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md)スタイル、戻り値で指定した項目の高さ`nIndex`します。 エラーが発生する場合、戻り値は**返します**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&17;](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>CListBox::GetItemRect  
 リスト ボックス ウィンドウに現在表示されて、その境界のリスト ボックス項目四角形の寸法を取得します。  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の&0; から始まるインデックスを指定します。  
  
 `lpRect`  
 Long ポインターを指定する[RECT 構造体](../../mfc/reference/rect-structure1.md)項目のリスト ボックスのクライアント座標を受け取る。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#18;](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>CListBox::GetListBoxInfo  
 各列の項目の数を取得します。  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 各列の項目の数、`CListBox`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getlocale"></a>CListBox::GetLocale  
 リスト ボックスによって使用されるロケールを取得します。  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の文字列のロケール識別子 (LCID) 値。  
  
### <a name="remarks"></a>コメント  
 ロケールが使用、たとえば、並べ替えられたリスト ボックス内の文字列の並べ替え順序を決定します。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::SetLocale](#setlocale)します。  
  
##  <a name="getsel"></a>CListBox::GetSel  
 項目の選択状態を取得します。  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した項目が選択されている場合は正の数それ以外の場合は 0 です。 戻り値は`LB_ERR`場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、両方の単一および複数選択リスト ボックスでは機能します。  
  
 現在選択されているリスト ボックスの項目のインデックスを取得するには使用[CListBox::GetCurSel](#getcursel)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#19;](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>CListBox::GetSelCount  
 複数選択のリスト ボックスで選択したアイテムの合計数を取得します。  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスで選択したアイテムの数。 戻り値は、リスト ボックスが単一選択リスト ボックスの場合は、**返します**します。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::GetSelItems](#getselitems)します。  
  
##  <a name="getselitems"></a>CListBox::GetSelItems  
 複数選択のリスト ボックスで選択した項目の項目番号を指定する整数の配列をバッファーします。  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxItems`  
 項目番号が、バッファーに配置するのには、選択した項目の最大数を指定します。  
  
 `rgIndex`  
 指定された整数の数に対して十分な大きさのバッファーを指すポインター`nMaxItems`します。  
  
### <a name="return-value"></a>戻り値  
 実際のアイテムの数は、バッファーに格納します。 戻り値は、リスト ボックスが単一選択リスト ボックスの場合は、`LB_ERR`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#20;](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="gettext"></a>CListBox::GetText  
 リスト ボックスから文字列を取得します。  
  
```  
int GetText(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
void GetText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得する文字列の&0; から始まるインデックスを指定します。  
  
 `lpszBuffer`  
 文字列を受け取るバッファーへのポインター。 バッファーには、文字列と終端の null 文字のための十分な領域が必要です。 呼び出して前もって文字列のサイズを決定できる、`GetTextLen`メンバー関数。  
  
 `rString`  
 `CString` オブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を除いた文字列の長さをバイト単位で。 場合`nIndex`有効なインデックスが指定されていない戻り値は**返します**します。  
  
### <a name="remarks"></a>コメント  
 このメンバーの&2; 番目の形式の関数の塗りつぶし、`CString`文字列のテキストを持つオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&21;](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>CListBox::GetTextLen  
 リスト ボックス アイテム内には、文字列の長さを取得します。  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 文字列の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 文字列の終端の null 文字を除いた文字の長さ。 場合`nIndex`有効なインデックスが指定されていない戻り値は**返します**します。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::GetText](#gettext)します。  
  
##  <a name="gettopindex"></a>CListBox::GetTopIndex  
 リスト ボックスに表示される最初の項目の&0; から始まるインデックスを取得します。  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、リスト ボックスに表示される最初の項目の&0; から始まるインデックス**返します**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 最初に、項目 0、リスト ボックスの上部にあるが場合は、リスト ボックスをスクロールすると、別のアイテムが先頭にある場合があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&22;](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="initstorage"></a>CListBox::InitStorage  
 リスト ボックス項目を格納するには、メモリを割り当てます。  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItems`  
 追加する項目の数を指定します。  
  
 `nBytes`  
 割り当てるバイト数、項目の文字列では、メモリの量を指定します。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、項目の最大数をメモリを再割り当てが必要とせずに、それ以外の場合に格納できるリスト ボックス**返します**、つまり、十分なメモリがあります。  
  
### <a name="remarks"></a>コメント  
 多数の項目を追加する前にこの関数を呼び出して、`CListBox`です。  
  
 この関数は、多くのアイテム (100 個以上) を持つリスト ボックスの初期化を高速化を使用します。 特定の容量のための後続のメモリを事前に割り当てる[AddString](#addstring)、[は](#insertstring)、および[Dir](#dir)関数は、最短時間を受け取ります。 見積もりは、パラメーターを使用できます。 多くを指定した場合は、余分なメモリが割り当てられます。過小評価する場合は、通常の割り当ては事前に割り当てられた量を超える項目に対して使用されます。  
  
 Windows 95/98 のみ:`nItems`パラメーターは 16 ビット値に限定します。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数は制限されているが、リスト ボックス内の項目の合計サイズが使用可能なメモリによってのみ制限されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox 第&23;](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>CListBox::InsertString  
 リスト ボックスに文字列を挿入します。  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 文字列を挿入する位置の&0; から始まるインデックスを指定します。 このパラメーターが -1 の場合、文字列はリストの末尾に追加されます。  
  
 `lpszItem`  
 挿入される null で終わる文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 文字列が挿入された位置の&0; から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 異なり、 [AddString](#addstring)メンバー関数を`InsertString`を使用したリストは伴いません、 [LBS_SORT](../../mfc/reference/list-box-styles.md)並べ替えスタイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&24;](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>CListBox::ItemFromPoint  
 指定した位置に最も近いリスト ボックスの項目を決定`pt`します。  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 リスト ボックスのクライアント領域の左上隅に対して相対的に指定された、最も近い項目を検索するためのポイント。  
  
 `bOutside`  
 参照、`BOOL`に設定される変数`TRUE`場合`pt`が最も近いリスト ボックスの項目のクライアント領域の範囲外`FALSE`場合`pt`が最も近いリスト ボックス アイテムのクライアント領域内です。  
  
### <a name="return-value"></a>戻り値  
 指定した位置に最も近い項目のインデックス`pt`します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、マウス カーソルが置かリスト ボックス項目を特定します。  
  
### <a name="example"></a>例  
  例を参照してください[CListBox::SetAnchorIndex](#setanchorindex)します。  
  
##  <a name="measureitem"></a>CListBox::MeasureItem  
 オーナー描画スタイルを持つリスト ボックスが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`構造体、リスト ボックスのサイズの Windows に通知します。 リスト ボックスが作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md)リスト ボックス内の各項目のスタイル、フレームワークと記述します。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
 使用の詳細については、 [LBS_OWNERDRAWFIXED](../../mfc/reference/list-box-styles.md)スタイルで作成された、オーナー描画のリスト ボックスで、`SubclassDlgItem`のメンバー関数`CWnd`の説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md)します。  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造**します。**  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#25;](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>中  
 リスト ボックスからすべての項目を削除します。  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&26;](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>CListBox::SelectString  
 検索リスト ボックス項目の指定した文字列に一致して、一致する項目が見つかった場合、その項目を選択します。  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartAfter`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスが含まれています。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nStartAfter`します。 場合`nStartAfter`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszItem`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索ではケースを独立しておりを指定するため、この文字列には、任意の大文字と小文字を含めることがあります。  
  
### <a name="return-value"></a>戻り値  
 検索が成功した場合は、選択した項目のインデックス。 検索が正常に実行されなかった場合、戻り値は**返します**現在の選択は変更されません。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスをスクロールすると、必要に応じて、選択した項目を表示します。  
  
 リスト ボックスで、このメンバー関数は使用できません、 [LBS_MULTIPLESEL](../../mfc/reference/list-box-styles.md)スタイル。  
  
 項目を選択すると、(始点) から、先頭の文字で指定された文字列内の文字に一致する場合にのみ`lpszItem`します。  
  
 使用して、`FindString`項目を選択せずに文字列を検索するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&27;](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>CListBox::SelItemRange  
 複数選択のリスト ボックス内の複数の連続した項目を選択します。  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `bSelect`  
 選択範囲を設定する方法を指定します。 場合`bSelect`は**TRUE**、文字列が選択され、強調表示される場合は**FALSE**、強調表示が削除され、文字列が選択されていません。  
  
 `nFirstItem`  
 設定するのには、最初の項目の&0; から始まるインデックスを指定します。  
  
 `nLastItem`  
 設定する最後の項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を複数選択のリスト ボックスでのみ使用します。 複数選択のリスト ボックスに&1; つの項目を選択する必要がある場合などは場合、`nFirstItem`に等しい`nLastItem`— を呼び出す、 [SetSel](#setsel)メンバー関数を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&28;](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>CListBox::SetAnchorIndex  
 拡張の選択を開始するための複数選択のリスト ボックスで、アンカーを設定します。  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 アンカー リスト ボックスの項目の&0; から始まるインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 複数選択のリスト ボックスには、アンカー項目は、選択した項目を連続したブロック内で最初または最項目です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&29;](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>CListBox::SetCaretIndex  
 フォーカスされた四角形を複数選択のリスト ボックスで指定したインデックス位置にある項目に設定します。  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスにフォーカス四角形を表示する項目の&0; から始まるインデックスを指定します。  
  
 *bScroll*  
 この値が 0 の場合は、完全に表示されるまで、項目がスクロールされます。 この値がない場合 0 で、項目がスクロールされる基準には、少なくとも部分的に表示されるまでです。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 項目が表示されていない場合、ビューにスクロールされます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&30;](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>CListBox::SetColumnWidth  
 複数列のリスト ボックスで、すべての列のピクセル単位で幅を設定 (で作成された、 [LBS_MULTICOLUMN](../../mfc/reference/list-box-styles.md)スタイル)。  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `cxWidth`  
 すべての列のピクセル単位の幅を指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&31;](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>CListBox::SetCurSel  
 文字列を選択し、必要に応じて表示されるようにスクロールします。  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSelect`  
 選択する文字列の&0; から始まるインデックスを指定します。 場合`nSelect`-1 で、選択範囲がないように、リスト ボックスを設定します。  
  
### <a name="return-value"></a>戻り値  
 `LB_ERR`場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 新しい文字列を選択すると、リスト ボックスは、以前に選択した文字列から、強調表示を削除します。  
  
 このメンバー関数は、単一選択リスト ボックスでのみ使用します。  
  
 設定または複数選択のリスト ボックスで、選択範囲を削除するを使用して[CListBox::SetSel](#setsel)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#32;](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>CListBox::SetHorizontalExtent  
 これによって、リスト ボックスを水平方向にスクロールすることができます (ピクセル単位)、幅を設定します。  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxExtent*  
 これによって、リスト ボックスを水平方向にスクロールすることができます (ピクセル) を指定します。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスのサイズがこの値より小さい場合は、水平スクロール バーは水平方向に項目をリスト ボックス内をスクロールします。 リスト ボックスが、大規模またはこの値より大きい場合は、水平スクロール バーは表示されません。  
  
 呼び出しに応答する`SetHorizontalExtent`、リスト ボックスを定義する必要があります、 [WS_HSCROLL](../../mfc/reference/window-styles.md)スタイル。  
  
 このメンバー関数では、複数列のリスト ボックスを適していません。 複数列のリスト ボックスを呼び出して、`SetColumnWidth`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&33;](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>CListBox::SetItemData  
 リスト ボックスで指定したアイテムに関連付けられている 32 ビット値を設定します。  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の&0; から始まるインデックスを指定します。  
  
 `dwItemData`  
 アイテムに関連する値を指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&34;](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>CListBox::SetItemDataPtr  
 指定されたポインターであるリスト ボックスで指定された項目に関連付けられている 32 ビット値の設定 ( **void\***)。  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の&0; から始まるインデックスを指定します。  
  
 `pData`  
 項目に関連付けられているへのポインターを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このポインターは場合でも、項目の追加または削除、リスト ボックス内のアイテムの相対位置を変更することがあります、リスト ボックスの有効期間に有効です。 そのため、ボックス内の項目のインデックスを変更できますが、ポインターの信頼性を維持します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#35;](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>CListBox::SetItemHeight  
 リスト ボックスの項目の高さを設定します。  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の&0; から始まるインデックスを指定します。 このパラメーターには、リスト ボックスがある場合にのみ、使用、 **LBS_OWNERDRAWVARIABLE**スタイルは 0 にそれ以外の場合、設定する必要があります。  
  
 `cyItemHeight`  
 アイテムのピクセルで高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**インデックスまたは高さが無効な場合です。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md)スタイルでは、この関数は設定で指定した項目の高さ`nIndex`します。 それ以外の場合、この関数は、リスト ボックス内のすべての項目の高さを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#36;](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>CListBox::SetLocale  
 このリスト ボックスのロケール識別子を設定します。  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLocale`  
 リスト ボックスに設定する新しい値のロケール識別子 (LCID)。  
  
### <a name="return-value"></a>戻り値  
 このリスト ボックスの以前のロケール識別子 (LCID) 値です。  
  
### <a name="remarks"></a>コメント  
 場合**SetLocale**既定値が呼び出されないシステムからロケールを取得します。 このシステム既定ロケールがコントロール パネルを使用することも可能地域 (または国際) アプリケーションです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&37;](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>CListBox::SetSel  
 複数選択のリスト ボックスの文字列を選択します。  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 設定される文字列の&0; から始まるインデックスが含まれています。 かどうかは –&1; を選択範囲が追加または削除の値に応じて、すべての文字列から`bSelect`します。  
  
 `bSelect`  
 選択範囲を設定する方法を指定します。 場合`bSelect`は`TRUE`、文字列が選択され、強調表示される場合は`FALSE`、強調表示が削除され、文字列が選択されていません。 指定した文字列が選択され、既定で強調表示されます。  
  
### <a name="return-value"></a>戻り値  
 `LB_ERR`場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を複数選択のリスト ボックスでのみ使用します。  
  
 単一選択リスト ボックスから項目を選択する[CListBox::SetCurSel](#setcursel)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&38;](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="settabstops"></a>CListBox::SetTabStops  
 リスト ボックスのタブ ストップの位置を設定します。  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>パラメーター  
 `cxEachStop`  
 タブ ストップはすべて`cxEachStop`ダイアログ単位です。 参照してください*rgTabStops*ダイアログ単位の詳細についてです。  
  
 `nTabStops`  
 リスト ボックスにタブ ストップの数を指定します。  
  
 `rgTabStops`  
 ダイアログ単位でのタブ ストップの位置を表す、整数の配列の最初のメンバーを指します。 ダイアログ単位は、水平または垂直距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅の単位の&4; 分の&1; と&1; つの垂直方向ダイアログ単位は、現在のダイアログ ベースの高さの単位の&8; 分の&1; に等しい。 ダイアログの基本単位は、高さ、および現在のシステム フォントの幅に基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します。 タブ ストップは昇順に並べ替え; 並べられていなければなりませんバック タブは使用できません。  
  
### <a name="return-value"></a>戻り値  
 すべてのタブが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 2 つのダイアログ単位の既定のサイズにタブ ストップを設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 2 以外のサイズにタブ ストップを設定するとバージョンを呼び出す、`cxEachStop`引数。  
  
 サイズの配列にタブ ストップを設定するとバージョンを使用して、`rgTabStops`と`nTabStops`引数。 タブ ストップはの各値に設定する`rgTabStops`で指定された数に達するまで`nTabStops`します。  
  
 呼び出しに応答する、`SetTabStops`メンバー関数の場合、リスト ボックス必要がありますで作成されている、 [LBS_USETABSTOPS](../../mfc/reference/list-box-styles.md)スタイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox&#39;](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>CListBox::SetTopIndex  
 特定のリスト ボックスの項目が表示されているようにします。  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックス項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、0 または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 システムでは、リスト ボックスをスクロールによって指定された項目まで`nIndex`が表示されます、一覧の上部にあるボックスまたは最大スクロール範囲に達しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&40;](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>CListBox::VKeyToItem  
 リスト ボックスの親ウィンドウを受信時にフレームワークによって呼び出さ、`WM_VKEYTOITEM`リスト ボックスからのメッセージ。  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nKey`  
 ユーザーが押されたキーの仮想キー コードです。 標準的な仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nIndex`  
 リスト ボックスのキャレットの現在の位置。  
  
### <a name="return-value"></a>戻り値  
 これ以上操作用の 2、– 既定のアクションでは、1 またはキーストロークの既定のアクションを実行する対象のリスト ボックス アイテムのインデックスを指定する正の数値を返します。  
  
### <a name="remarks"></a>コメント  
 `WM_VKEYTOITEM`を受信すると、リスト ボックスでメッセージが送信される、`WM_KEYDOWN`のみリスト ボックス満たしている場合、次の両方が、メッセージ。  
  
-   [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md)一連のスタイルを設定します。  
  
-   少なくとも&1; つの項目があります。  
  
 自分がこの関数を呼び出す必要がありますはことはありません。 キーボード メッセージの独自のカスタム処理を指定するには、この関数をオーバーライドします。  
  
 オーバーライドした関数でどのようなアクションをフレームワークに通知する値を返す必要があります。 戻り値 – 2 は、アプリケーションは、アイテムの選択のすべての側面を処理し、リスト ボックスで、これ以上操作は必要ありませんを示します。 2 を返す前に選択範囲を設定したり、キャレットを移動できます。 選択範囲を設定するには使用[SetCurSel](#setcursel)または[SetSel](#setsel)します。 キャレットを移動するには使用[には](#setcaretindex)です。  
  
 戻り値 – 1 では、キー操作への応答でにリスト ボックスが既定のアクションを実行するを示します。既定の実装で、-1 を返します。  
  
 0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスが、指定したアイテムを既定のアクションを実行するを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox #&41;](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)

