---
title: "CTabCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
dev_langs:
- C++
helpviewer_keywords:
- tab controls
- CTabCtrl class, common controls
- CTabCtrl class
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
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
ms.openlocfilehash: e1d8497b444e4dd5ee1e2803c1a763f67e2e0054
ms.lasthandoff: 02/24/2017

---
# <a name="ctabctrl-class"></a>CTabCtrl クラス
Windows のコモン タブ コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|`CTabCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|ウィンドウの四角形を指定したタブ コントロールの表示領域を計算または特定の表示領域に対応して、ウィンドウの四角形を計算します。|  
|[CTabCtrl::Create](#create)|タブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクトです。|  
|[CTabCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してタブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクトです。|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|タブ コントロールからすべての項目を削除します。|  
|[CTabCtrl::DeleteItem](#deleteitem)|タブ コントロールから項目を削除します。|  
|[CTabCtrl::DeselectAll](#deselectall)|いずれかの押されたキーがオフにすると、タブ コントロールの項目にリセットします。|  
|[CTabCtrl::DrawItem](#drawitem)|タブ コントロールの指定した項目を描画します。|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|タブ コントロールの現在のフォーカスを持つタブを取得します。|  
|[CTabCtrl::GetCurSel](#getcursel)|タブ コントロールで現在選択されているタブを決定します。|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|現在、タブ コントロールの使用になっている拡張スタイルを取得します。|  
|[CTabCtrl::GetImageList](#getimagelist)|タブ コントロールに関連付けられているイメージ リストを取得します。|  
|[CTabCtrl::GetItem](#getitem)|タブ コントロールのタブについての情報を取得します。|  
|[CTabCtrl::GetItemCount](#getitemcount)|タブ コントロールのタブの数を取得します。|  
|[CTabCtrl::GetItemRect](#getitemrect)|タブ コントロールのタブの外接する四角形を取得します。|  
|[CTabCtrl::GetItemState](#getitemstate)|指定されたタブ コントロールの項目の状態を取得します。|  
|[CTabCtrl::GetRowCount](#getrowcount)|タブ コントロールのタブの行の現在の数を取得します。|  
|[CTabCtrl::GetToolTips](#gettooltips)|タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。|  
|[CTabCtrl::HighlightItem](#highlightitem)|タブ アイテムの強調表示状態を設定します。|  
|[CTabCtrl::HitTest](#hittest)|どの タブをクリックすると、ある場合、指定した画面位置を決定します。|  
|[として](#insertitem)|タブ コントロールに新しいタブを挿入します。|  
|[CTabCtrl::RemoveImage](#removeimage)|タブ コントロールのイメージ リストからイメージを削除します。|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|タブ コントロールの指定したタブにフォーカスを設定します。|  
|[CTabCtrl::SetCurSel](#setcursel)|タブ コントロールのタブを選択します。|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|タブ コントロールの拡張スタイルを設定します。|  
|[CTabCtrl::SetImageList](#setimagelist)|タブ コントロールへのイメージ リストを割り当てます。|  
|[CTabCtrl::SetItem](#setitem)|タブの属性の一部またはすべてを設定します。|  
|[CTabCtrl::SetItemExtra](#setitemextra)|タブ コントロール内のアプリケーション定義のデータ用に予約されて別のタブのバイト数を設定します。|  
|[CTabCtrl::SetItemSize](#setitemsize)|項目の高さと幅を設定します。|  
|[CTabCtrl::SetItemState](#setitemstate)|指定されたタブ コントロールの項目の状態を設定します。|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|タブ コントロールの項目の最小の幅を設定します。|  
|[CTabCtrl::SetPadding](#setpadding)|各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域のサイズを設定します。|  
|[CTabCtrl::SetToolTips](#settooltips)|タブ コントロールにツール ヒント コントロールを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 「タブ コントロール」は、ノートの仕切りや書類棚にラベルに似ています。 タブ コントロールを使用すると、アプリケーションでウィンドウまたはダイアログ ボックスの同じ領域に複数のページを定義できます。 各ページは、一連の情報または対応するタブを選択すると、アプリケーションで表示するコントロールのグループで構成されます。 特殊な種類のタブ コントロールには、ボタンなどのタブが表示されます。 ボタンをクリックするページを表示する代わりにコマンドが実行されます。  
  
 このコントロール (つまり、`CTabCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 使用する方法について`CTabCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CTabCtrl](../../mfc/using-ctabctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-nameadjustrecta--ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl::AdjustRect  
 ウィンドウの四角形を指定したタブ コントロールの表示領域を計算または特定の表示領域に対応して、ウィンドウの四角形を計算します。  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `bLarger`  
 実行するには、どの操作を示します。 このパラメーターは、する場合**TRUE**、`lpRect`表示する四角形を指定し、対応するウィンドウの四角形を受け取る。 このパラメーターは場合**FALSE**、`lpRect`ウィンドウの四角形を指定し、対応する表示する四角形を受け取る。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)指定された四角形を指定し、計算される四角形を受け取る。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="a-namecreatea--ctabctrlcreate"></a><a name="create"></a>CTabCtrl::Create  
 タブ コントロールを作成しのインスタンスにアタッチ、`CTabCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760549)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 参照してください**解説**コントロールに適用することもできます。 ウィンドウ スタイルの一覧にします。  
  
 `rect`  
 タブ コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 通常、タブ コントロールの親ウィンドウを指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `nID`  
 タブ コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 **TRUE**オブジェクトの初期化が成功、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CTabCtrl`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、し、呼び出す**作成**、タブ コントロールを作成およびそれにアタッチする、`CTabCtrl`オブジェクトです。  
  
 タブ コントロールのスタイルは、タブ コントロールに次のウィンドウ スタイルを適用できます。  
  
- **WS_CHILD**タブ コントロールを表す子ウィンドウを作成します。 `WS_POPUP` スタイルと一緒に使うことはできません。  
  
- **WS_VISIBLE**が最初に表示されるタブ コントロールを作成します。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。  
  
- **WS_GROUP**をユーザーに移動できるコントロール&1; つのコントロールから次の矢印キーでのグループの最初のコントロールを指定します。 定義されたすべてのコントロール、 **WS_GROUP**後、同じグループに属している最初のコントロールのスタイルを設定します。 次のコントロールで、 **WS_GROUP**スタイルがスタイルのグループを終了し、次のグループ (つまり、1 つのグループの最後、次の開始位置) を開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを使用して移動できるコントロールの任意の数のいずれかを指定します。 TAB キーで指定された次のコントロールにユーザーの移動、 **WS_TABSTOP**スタイル。  
  
 拡張ウィンドウ スタイルを使用して、タブ コントロールを作成するには、呼び出す[CTabCtrl::CreateEx](#createex)の代わりに**作成**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="a-namecreateexa--ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CTabCtrl`オブジェクトです。  
  
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
 タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760549)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 参照してください**解説**で[作成](#create)コントロールに適用することもできます。 ウィンドウ スタイルの一覧についてはです。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
 `CreateEx`指定された拡張ウィンドウ スタイルを使用してコントロールが作成され`dwExStyle`します。 拡張を使用してコントロールに固有のスタイル セット[拡張](#setextendedstyle)します。 などを使用して`CreateEx`としてこのようなスタイルを設定する**WS_EX_CONTEXTHELP**を使用して、`SetExtendedStyle`としてこのようなスタイルを設定する**TCS_EX_FLATSEPARATORS**します。 詳細については、「スタイルを参照してください。[タブ コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760546)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namectabctrla--ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 `CTabCtrl` オブジェクトを構築します。  
  
```  
CTabCtrl();
```  
  
##  <a name="a-namedeleteallitemsa--ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 タブ コントロールからすべての項目を削除します。  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namedeleteitema--ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::DeleteItem  
 タブ コントロールから、指定した項目を削除します。  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 削除する項目の&0; から始まる値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl&#3;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="a-namedeselectalla--ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::DeselectAll  
 いずれかの押されたキーがオフにすると、タブ コントロールの項目にリセットします。  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>パラメーター  
 *fExcludeFocus*  
 項目選択解除のスコープを指定するフラグです。 このパラメーターに設定されている場合**FALSE**タブのすべてのボタンはリセットされます。 設定されている場合**TRUE**を現在選択されている&1; つを除くすべてのタブの項目がリセットされます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedrawitema--ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::DrawItem  
 オーナー描画タブ コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)描画する項目を記述する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、この関数をオーバーライド`CTabCtrl`オブジェクトです。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
##  <a name="a-namegetcurfocusa--ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 現在フォーカスがタブのインデックスを取得します。  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在フォーカスがタブの&0; から始まるインデックス。  
  
##  <a name="a-namegetcursela--ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl::GetCurSel  
 タブ コントロールで現在選択されているタブを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、選択されているタブまたはタブが選択されていない場合は 1 の 0 から始まるインデックス。  
  
##  <a name="a-namegetextendedstylea--ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 現在、タブ コントロールの使用になっている拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールの使用されている拡張スタイルを表します。 この値の組み合わせである[タブ コントロールのスタイルを拡張](http://msdn.microsoft.com/library/windows/desktop/bb760546)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetimagelista--ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl::GetImageList  
 タブ コントロールに関連付けられているイメージ リストを取得します。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、タブのイメージ リストへのポインターを制御します。それ以外の場合、 **NULL**します。  
  
##  <a name="a-namegetitema--ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl::GetItem  
 タブ コントロールのタブについての情報を取得します。  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 タブの&0; から始まるインデックス。  
  
 `pTabCtrlItem`  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造体を取得する情報を指定するために使用します。 タブの情報を受信するも使用されます。 この構造体を併用、 `InsertItem`、 `GetItem`、および`SetItem`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合。**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 メッセージが送信されるときに、**マスク**メンバーが返される属性を指定します。 場合、**マスク**メンバーは、指定、`TCIF_TEXT`値、 **pszText**メンバーは、項目のテキストを受け取るバッファーのアドレスを含める必要があります、 **cchTextMax**メンバーは、バッファーのサイズを指定する必要があります。  
  
 **マスク**  
 これを指定する値`TCITEM`メンバーを取得または設定を構成します。 このメンバーは、0、または、次の値の組み合わせを指定できます。  
  
- `TCIF_TEXT`**PszText**メンバーは無効です。  
  
- `TCIF_IMAGE``iImage`メンバーは無効です。  
  
- `TCIF_PARAM`**LParam**メンバーは無効です。  
  
- `TCIF_RTLREADING`テキスト**pszText**ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。  
  
- `TCIF_STATE`**DwState**メンバーは無効です。  
  
 **pszText**  
 構造体には、タブについての情報が含まれている場合は、タブのテキストを含む null で終わる文字列へのポインター。 構造体が情報を受信する場合、このメンバーは、タブのテキストを受け取るバッファーのアドレスを指定します。  
  
 **cchTextMax**  
 バッファーのサイズが指す**pszText**します。 このメンバーには、構造体は、情報を受信していない場合は無視されます。  
  
 `iImage`  
 タブの画像がない場合、タブ コントロールのイメージ リストや – 1 にインデックスを作成します。  
  
 **lParam**  
 タブに関連付けられているアプリケーション定義のデータです。 アプリケーションが構造体を定義する必要があるかどうか、およびの代わりに使用&4; バイトを超えるアプリケーション定義のデータを別のタブがある場合は、`TCITEM`構造体。 アプリケーション定義の構造体の最初のメンバーである必要があります、[アプリケーション定義](http://msdn.microsoft.com/library/windows/desktop/bb760556)構造体。 **アプリケーション定義**構造体と同じ、`TCITEM`構造ですが、 **lParam**メンバーです。 構造のサイズと、サイズの違い、**アプリケーション定義**構造体が別のタブの追加のバイト数と一致する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl&4;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="a-namegetitemcounta--ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl::GetItemCount  
 タブ コントロールのタブの数を取得します。  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロール内の項目の数です。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="a-namegetitemrecta--ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl::GetItemRect  
 タブ コントロールの指定したタブの外接する四角形を取得します。  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 タブ項目の&0; から始まるインデックス。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)  タブの外接する四角形を受け取る。 これらの座標は、ビューポートの現在のマップ モードを使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="a-namegetitemstatea--ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl::GetItemState  
 識別されるタブ コントロールの項目の状態を取得`nItem`します。  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 状態情報を取得する項目の&0; から始まるインデックス番号。  
  
 `dwMask`  
 フラグを返すアイテムの状態のどれを指定するマスク。 一連の値のマスク メンバーを参照してください、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 参照、`DWORD`値の状態情報を受信します。 次のいずれかの値になります。  
  
|値|説明|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|タブ コントロールの項目が選択されます。|  
|**TCIS_HIGHLIGHTED**|タブ コントロールの項目が強調表示され、タブをクリックし、テキストは、現在の強調表示色を使用して描画します。 強調表示色を使用する場合は true。 の補間ディザー カラーではないになります。|  
  
### <a name="remarks"></a>コメント  
 アイテムの状態がで指定された、 **dwState**のメンバー、`TCITEM`構造体。  
  
##  <a name="a-namegetrowcounta--ctabctrlgetrowcount"></a><a name="getrowcount"></a>CTabCtrl::GetRowCount  
 タブ コントロール内の行の現在の数を取得します。  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールのタブの行の数。  
  
### <a name="remarks"></a>コメント  
 のみを持つコントロール タブ、 **TCS_MULTILINE**スタイルは、タブの行を持つことができます。  
  
##  <a name="a-namegettooltipsa--ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::GetToolTips  
 タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のツール ヒント コントロールのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 タブ コントロールがある場合、ツール ヒント コントロールを作成、 **TCS_TOOLTIPS**スタイル。 割り当てることも、ツール ヒント コントロール タブ コントロールを使用して、`SetToolTips`メンバー関数。  
  
##  <a name="a-namehighlightitema--ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::HighlightItem  
 タブ アイテムの強調表示状態を設定します。  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `idItem`  
 タブ コントロールの項目の&0; から始まるインデックス。  
  
 `fHighlight`  
 強調表示状態の設定を指定する値。 場合、この値は**TRUE**、タブが強調表示されます。 場合**FALSE**、タブが既定の状態に設定されています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージを実装して[TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namehittesta--ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::HitTest  
 指定した画面位置には、存在する場合、どのタブを決定します。  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pHitTestInfo`  
 ポインター、 [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553)構造、」の説明に従って、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、テストする画面位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定位置にあるタブがない場合は、タブ、または 1 の 0 から始まるインデックスを返します。  
  
##  <a name="a-nameinsertitema--ctabctrlinsertitem"></a><a name="insertitem"></a>として  
 既存のタブ コントロールに新しいタブを挿入します。  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 新しいタブの&0; から始まるインデックス。  
  
 `pTabCtrlItem`  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)  タブの属性を指定する構造体。  
  
 `lpszItem`  
 タブのテキストを表す null で終わる文字列のアドレスです。  
  
 `nImage`  
 イメージ リストから挿入するイメージの&0; から始まるインデックス。  
  
 `nMask`  
 指定する`TCITEM`設定する属性を構成します。 0、または、次の値の組み合わせになります。  
  
- `TCIF_TEXT`**PszText**メンバーは無効です。  
  
- `TCIF_IMAGE``iImage`メンバーは無効です。  
  
- `TCIF_PARAM`**LParam**メンバーは無効です。  
  
- `TCIF_RTLREADING`テキスト**pszText**ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。  
  
- `TCIF_STATE`**DwState**メンバーは無効です。  
  
 `lParam`  
 タブに関連付けられているアプリケーション定義のデータです。  
  
 `dwState`  
 項目の状態の値を指定します。 詳細については、次を参照してください。 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *dwStateMask*  
 どの状態では、設定を指定します。 詳細については、次を参照してください。 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、新しいタブの 0 から始まるインデックスそれ以外の場合 – 1 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTabCtrl&#5;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="a-nameremoveimagea--ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::RemoveImage  
 タブ コントロールのイメージ リストから、指定されたイメージを削除します。  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 削除するイメージの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 タブ コントロールは、それぞれのタブが同じイメージに関連付けが保持されるように、各タブのイメージのインデックスを更新します。  
  
##  <a name="a-namesetcurfocusa--ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 タブ コントロールの指定したタブにフォーカスを設定します。  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 フォーカスを取得するタブのインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetcursela--ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::SetCurSel  
 タブ コントロールのタブを選択します。  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 選択する項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、以前に選択したタブの 0 から始まるインデックスそれ以外の場合 – 1 です。  
  
### <a name="remarks"></a>コメント  
 タブ コントロールが送信しない、**は、**または**TCN_SELCHANGE**通知メッセージの場合、この関数を使用してタブを選択します。 使用して、これらの通知が送信**WM_NOTIFY**ユーザーがクリックするか、キーボードを使用して、タブを変更します。  
  
##  <a name="a-namesetextendedstylea--ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 タブ コントロールの拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwNewStyle`  
 タブの組み合わせを指定する値は、拡張スタイルを制御します。  
  
 `dwExMask`  
 A`DWORD`のスタイルを示す値`dwNewStyle`の影響を受けています。 拡張のスタイルのみ`dwExMask`は変更されます。 その他のすべてのスタイルが保持されます。 このパラメーターが&0; の場合、すべてのスタイルの場合`dwNewStyle`影響を受けます。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`以前値[タブ コントロールのスタイルを拡張](http://msdn.microsoft.com/library/windows/desktop/bb760546)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetimagelista--ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl::SetImageList  
 タブ コントロールへのイメージ リストを割り当てます。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 タブ コントロールに割り当てられるイメージ リストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 前のイメージ リストへのポインターを返しますまたは**NULL**直前のイメージ リストがない場合。  
  
##  <a name="a-namesetitema--ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl::SetItem  
 タブの属性の一部またはすべてを設定します。  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 項目の&0; から始まるインデックス番号。  
  
 `pTabCtrlItem`  
 ポインター、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)アイテムの新しい属性を格納する構造体。 **マスク**メンバーが設定される属性を指定します。 場合、**マスク**メンバーは、指定、`TCIF_TEXT`値、 **pszText**メンバーは、null で終わる文字列のアドレスと**cchTextMax**メンバーは無視されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[GetItem](#getitem)します。  
  
##  <a name="a-namesetitemextraa--ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 タブ コントロール内のアプリケーション定義のデータ用に予約されて別のタブのバイト数を設定します。  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 設定する追加のバイト数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetitemsizea--ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl::SetItemSize  
 タブ コントロール項目の幅と高さを設定します。  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 タブ コントロール項目の新しい幅と高さ (ピクセル単位)。  
  
### <a name="return-value"></a>戻り値  
 タブ コントロール項目の古い幅と高さを返します。  
  
##  <a name="a-namesetitemstatea--ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl::SetItemState  
 識別されるタブ コントロールの項目の状態を設定`nItem`します。  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 状態情報を設定するアイテムの&0; から始まるインデックス番号。  
  
 `dwMask`  
 フラグを設定するアイテムの状態を指定するマスク。 一連の値のマスク メンバーを参照してください、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwState`  
 参照、`DWORD`状態情報を含む値。 次のいずれかの値になります。  
  
|値|説明|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|タブ コントロールの項目が選択されます。|  
|**TCIS_HIGHLIGHTED**|タブ コントロールの項目が強調表示され、タブをクリックし、テキストは、現在の強調表示色を使用して描画します。 強調表示色を使用する場合は true。 の補間ディザー カラーではないになります。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namesetmintabwidtha--ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 タブ コントロールの項目の最小の幅を設定します。  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 タブ コントロールの項目に設定する最小の幅。 このパラメーターが-1 に設定されている場合、コントロールは既定のタブ幅を使用します。  
  
### <a name="return-value"></a>戻り値  
 前の最小値 タブの幅。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、Win32 メッセージの動作を実装して[TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetpaddinga--ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl::SetPadding  
 各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域のサイズを設定します。  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 各タブのアイコンとタブ コントロールのラベルの周りには、(埋め込み) 領域のサイズを設定します。  
  
##  <a name="a-namesettooltipsa--ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::SetToolTips  
 タブ コントロールにツール ヒント コントロールを割り当てます。  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndTip`  
 ツール ヒント コントロールのハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出すことによって、タブ コントロールに関連付けられているツール ヒント コントロールを取得する`GetToolTips`です。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl クラス](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)

