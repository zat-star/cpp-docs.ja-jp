---
title: "CTreeCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeCtrl
- AFXCMN/CTreeCtrl
- AFXCMN/CTreeCtrl::CTreeCtrl
- AFXCMN/CTreeCtrl::Create
- AFXCMN/CTreeCtrl::CreateDragImage
- AFXCMN/CTreeCtrl::CreateEx
- AFXCMN/CTreeCtrl::DeleteAllItems
- AFXCMN/CTreeCtrl::DeleteItem
- AFXCMN/CTreeCtrl::EditLabel
- AFXCMN/CTreeCtrl::EndEditLabelNow
- AFXCMN/CTreeCtrl::EnsureVisible
- AFXCMN/CTreeCtrl::Expand
- AFXCMN/CTreeCtrl::GetBkColor
- AFXCMN/CTreeCtrl::GetCheck
- AFXCMN/CTreeCtrl::GetChildItem
- AFXCMN/CTreeCtrl::GetCount
- AFXCMN/CTreeCtrl::GetDropHilightItem
- AFXCMN/CTreeCtrl::GetEditControl
- AFXCMN/CTreeCtrl::GetExtendedStyle
- AFXCMN/CTreeCtrl::GetFirstVisibleItem
- AFXCMN/CTreeCtrl::GetImageList
- AFXCMN/CTreeCtrl::GetIndent
- AFXCMN/CTreeCtrl::GetInsertMarkColor
- AFXCMN/CTreeCtrl::GetItem
- AFXCMN/CTreeCtrl::GetItemData
- AFXCMN/CTreeCtrl::GetItemExpandedImageIndex
- AFXCMN/CTreeCtrl::GetItemHeight
- AFXCMN/CTreeCtrl::GetItemImage
- AFXCMN/CTreeCtrl::GetItemPartRect
- AFXCMN/CTreeCtrl::GetItemRect
- AFXCMN/CTreeCtrl::GetItemState
- AFXCMN/CTreeCtrl::GetItemStateEx
- AFXCMN/CTreeCtrl::GetItemText
- AFXCMN/CTreeCtrl::GetLastVisibleItem
- AFXCMN/CTreeCtrl::GetLineColor
- AFXCMN/CTreeCtrl::GetNextItem
- AFXCMN/CTreeCtrl::GetNextSiblingItem
- AFXCMN/CTreeCtrl::GetNextVisibleItem
- AFXCMN/CTreeCtrl::GetParentItem
- AFXCMN/CTreeCtrl::GetPrevSiblingItem
- AFXCMN/CTreeCtrl::GetPrevVisibleItem
- AFXCMN/CTreeCtrl::GetRootItem
- AFXCMN/CTreeCtrl::GetScrollTime
- AFXCMN/CTreeCtrl::GetSelectedCount
- AFXCMN/CTreeCtrl::GetSelectedItem
- AFXCMN/CTreeCtrl::GetTextColor
- AFXCMN/CTreeCtrl::GetToolTips
- AFXCMN/CTreeCtrl::GetVisibleCount
- AFXCMN/CTreeCtrl::HitTest
- AFXCMN/CTreeCtrl::InsertItem
- AFXCMN/CTreeCtrl::ItemHasChildren
- AFXCMN/CTreeCtrl::MapAccIdToItem
- AFXCMN/CTreeCtrl::MapItemToAccID
- AFXCMN/CTreeCtrl::Select
- AFXCMN/CTreeCtrl::SelectDropTarget
- AFXCMN/CTreeCtrl::SelectItem
- AFXCMN/CTreeCtrl::SelectSetFirstVisible
- AFXCMN/CTreeCtrl::SetAutoscrollInfo
- AFXCMN/CTreeCtrl::SetBkColor
- AFXCMN/CTreeCtrl::SetCheck
- AFXCMN/CTreeCtrl::SetExtendedStyle
- AFXCMN/CTreeCtrl::SetImageList
- AFXCMN/CTreeCtrl::SetIndent
- AFXCMN/CTreeCtrl::SetInsertMark
- AFXCMN/CTreeCtrl::SetInsertMarkColor
- AFXCMN/CTreeCtrl::SetItem
- AFXCMN/CTreeCtrl::SetItemData
- AFXCMN/CTreeCtrl::SetItemExpandedImageIndex
- AFXCMN/CTreeCtrl::SetItemHeight
- AFXCMN/CTreeCtrl::SetItemImage
- AFXCMN/CTreeCtrl::SetItemState
- AFXCMN/CTreeCtrl::SetItemStateEx
- AFXCMN/CTreeCtrl::SetItemText
- AFXCMN/CTreeCtrl::SetLineColor
- AFXCMN/CTreeCtrl::SetScrollTime
- AFXCMN/CTreeCtrl::SetTextColor
- AFXCMN/CTreeCtrl::SetToolTips
- AFXCMN/CTreeCtrl::ShowInfoTip
- AFXCMN/CTreeCtrl::SortChildren
- AFXCMN/CTreeCtrl::SortChildrenCB
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeCtrl class
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
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
ms.openlocfilehash: 5341367b44540e2d0991fd61e52611826bbdcda1
ms.lasthandoff: 02/24/2017

---
# <a name="ctreectrl-class"></a>CTreeCtrl Class
Windows コモン ツリー ビュー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTreeCtrl::CTreeCtrl](#ctreectrl)|`CTreeCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTreeCtrl::Create](#create)|ツリー ビュー コントロールを作成し、それをアタッチ、`CTreeCtrl`オブジェクトです。|  
|[CTreeCtrl::CreateDragImage](#createdragimage)|指定されたツリー ビューのアイテムのドラッグ用のビットマップを作成します。|  
|[CTreeCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してツリー コントロールを作成し、それにアタッチ、`CTreeCtrl`オブジェクトです。|  
|[CTreeCtrl::DeleteAllItems](#deleteallitems)|ツリー ビュー コントロール内のすべての項目を削除します。|  
|[CTreeCtrl::DeleteItem](#deleteitem)|ツリー ビュー コントロールに新しい項目を削除します。|  
|[CTreeCtrl::EditLabel](#editlabel)|指定されたツリー ビュー項目インプレースを編集します。|  
|[CTreeCtrl::EndEditLabelNow](#endeditlabelnow)|現在のツリー ビュー コントロール内のツリー ビュー アイテムのラベルの編集操作をキャンセルします。|  
|[CTreeCtrl::EnsureVisible](#ensurevisible)|により、ツリー ビューの項目がツリー ビュー コントロールに表示されます。|  
|[CTreeCtrl::Expand](#expand)|展開、または、指定されたツリー ビューのアイテムの子項目を折りたたみます。|  
|[CTreeCtrl::GetBkColor](#getbkcolor)|コントロールの現在の背景色を取得します。|  
|[CTreeCtrl::GetCheck](#getcheck)|ツリー コントロール項目のチェックの状態を取得します。|  
|[CTreeCtrl::GetChildItem](#getchilditem)|指定されたツリー ビューのアイテムの子を取得します。|  
|[CTreeCtrl::GetCount](#getcount)|ツリー ビュー コントロールに関連付けられているツリー項目の数を取得します。|  
|[CTreeCtrl::GetDropHilightItem](#getdrophilightitem)|ドラッグ アンド ドロップ操作の対象を取得します。|  
|[CTreeCtrl::GetEditControl](#geteditcontrol)|指定されたビュー アイテムの編集に使用される編集コントロールのハンドルを取得します。|  
|[CTreeCtrl::GetExtendedStyle](#getextendedstyle)|現在のツリー ビュー コントロールを使用している拡張スタイルを取得します。|  
|[CTreeCtrl::GetFirstVisibleItem](#getfirstvisibleitem)|指定されたツリー ビューのアイテムの最初に表示される項目を取得します。|  
|[CTreeCtrl::GetImageList](#getimagelist)|ツリー ビュー コントロールに関連付けられているイメージ リストのハンドルを取得します。|  
|[CTreeCtrl::GetIndent](#getindent)|親からのオフセット (ピクセル単位) のツリー ビューのアイテムを取得します。|  
|[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)|ツリー ビューの挿入マークを描画に使用する色を取得します。|  
|[CTreeCtrl::GetItem](#getitem)|指定されたツリー ビューのアイテムの属性を取得します。|  
|[CTreeCtrl::GetItemData](#getitemdata)|項目に関連付けられている 32 ビット アプリケーションに固有の値を返します。|  
|[CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)|現在のツリー ビュー コントロールの指定した項目が展開された状態を表示するイメージのインデックスを取得します。|  
|[CTreeCtrl::GetItemHeight](#getitemheight)|ツリー ビューのアイテムの現在の高さを取得します。|  
|[CTreeCtrl::GetItemImage](#getitemimage)|項目に関連付けられているイメージを取得します。|  
|[CTreeCtrl::GetItemPartRect](#getitempartrect)|現在のツリー ビュー コントロール内の指定した項目の指定した部分の外接する四角形を取得します。|  
|[CTreeCtrl::GetItemRect](#getitemrect)|ツリー ビューの項目の外接する四角形を取得します。|  
|[CTreeCtrl::GetItemState](#getitemstate)|項目の状態を返します。|  
|[CTreeCtrl::GetItemStateEx](#getitemstateex)|現在のツリー ビュー コントロール内の指定した項目の拡張の状態を取得します。|  
|[CTreeCtrl::GetItemText](#getitemtext)|項目のテキストを返します。|  
|[CTreeCtrl::GetLastVisibleItem](#getlastvisibleitem)|現在のツリー ビュー コントロール内の最後の展開項目を取得します。|  
|[CTreeCtrl::GetLineColor](#getlinecolor)|ツリー ビュー コントロールの現在の線の色を取得します。|  
|[CTreeCtrl::GetNextItem](#getnextitem)|指定されたリレーションシップに一致する次のツリー ビューのアイテムを取得します。|  
|[CTreeCtrl::GetNextSiblingItem](#getnextsiblingitem)|指定されたビュー アイテムの次の兄弟を取得します。|  
|[CTreeCtrl::GetNextVisibleItem](#getnextvisibleitem)|指定されたツリー ビューのアイテムの次に表示される項目を取得します。|  
|[CTreeCtrl::GetParentItem](#getparentitem)|指定されたビュー アイテムの親を取得します。|  
|[CTreeCtrl::GetPrevSiblingItem](#getprevsiblingitem)|指定されたツリー ビューのアイテムの前の兄弟を取得します。|  
|[CTreeCtrl::GetPrevVisibleItem](#getprevvisibleitem)|指定されたツリー ビューのアイテムの前に表示される項目を取得します。|  
|[CTreeCtrl::GetRootItem](#getrootitem)|指定されたビュー アイテムのルートを取得します。|  
|[CTreeCtrl::GetScrollTime](#getscrolltime)|ツリー ビュー コントロールのスクロールの最大時間を取得します。|  
|[CTreeCtrl::GetSelectedCount](#getselectedcount)|現在のツリー ビュー コントロールで選択したアイテムの数を取得します。|  
|[CTreeCtrl::GetSelectedItem](#getselecteditem)|現在選択されているツリー ビューの項目を取得します。|  
|[CTreeCtrl::GetTextColor](#gettextcolor)|コントロールの現在のテキストの色を取得します。|  
|[CTreeCtrl::GetToolTips](#gettooltips)|子ツリー ビュー コントロールによって使用されるツール ヒント コントロールのハンドルを取得します。|  
|[CTreeCtrl::GetVisibleCount](#getvisiblecount)|ツリー ビュー コントロールに関連付けられている表示されているツリー項目の数を取得します。|  
|[CTreeCtrl::HitTest](#hittest)|関連するカーソルの現在位置を返す、`CTreeCtrl`オブジェクトです。|  
|[CTreeCtrl::InsertItem](#insertitem)|ツリー ビュー コントロールに新しい項目を挿入します。|  
|[CTreeCtrl::ItemHasChildren](#itemhaschildren)|指定した項目に子項目がある場合は&0; 以外を返します。|  
|[CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)|現在のツリー ビュー コントロール内のツリー ビュー アイテムを識別するハンドルを指定したアクセシビリティ識別子にマップします。|  
|[CTreeCtrl::MapItemToAccID](#mapitemtoaccid)|指定したハンドルをアクセシビリティ識別子は、現在のツリー ビュー コントロール内のツリー ビュー アイテムにマップします。|  
|[CTreeCtrl::Select](#select)|選択、スクロール、表示または指定されたツリー ビューのアイテムを再描画します。|  
|[CTreeCtrl::SelectDropTarget](#selectdroptarget)|ツリー項目をドラッグ アンド ドロップ操作の対象として再描画します。|  
|[CTreeCtrl::SelectItem](#selectitem)|指定されたツリー ビューのアイテムを選択します。|  
|[CTreeCtrl::SelectSetFirstVisible](#selectsetfirstvisible)|最初に表示される項目として指定されたツリー ビューのアイテムを選択します。|  
|[CTreeCtrl::SetAutoscrollInfo](#setautoscrollinfo)|現在のツリー ビュー コントロールの自動スクロール速度を設定します。|  
|[CTreeCtrl::SetBkColor](#setbkcolor)|コントロールの背景色を設定します。|  
|[CTreeCtrl::SetCheck](#setcheck)|ツリー コントロール項目のチェックの状態を設定します。|  
|[CTreeCtrl::SetExtendedStyle](#setextendedstyle)|現在のツリー ビュー コントロールの拡張スタイルを設定します。|  
|[CTreeCtrl::SetImageList](#setimagelist)|ツリー ビュー コントロールに関連付けられているイメージ リストのハンドルを設定します。|  
|[CTreeCtrl::SetIndent](#setindent)|親からのオフセット (ピクセル単位) のツリー ビューのアイテムを設定します。|  
|[CTreeCtrl::SetInsertMark](#setinsertmark)|ツリー ビュー コントロールの挿入マークを設定します。|  
|[CTreeCtrl::SetInsertMarkColor](#setinsertmarkcolor)|ツリー ビューの挿入マークを描画に使用する色を設定します。|  
|[CTreeCtrl::SetItem](#setitem)|指定されたツリー ビューのアイテムの属性を設定します。|  
|[CTreeCtrl::SetItemData](#setitemdata)|項目に関連付けられている 32 ビット アプリケーションに固有の値を設定します。|  
|[CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)|現在のツリー ビュー コントロールの指定した項目が展開された状態を表示するイメージのインデックスを設定します。|  
|[CTreeCtrl::SetItemHeight](#setitemheight)|アイテムの表示、ツリーの高さを設定します。|  
|[CTreeCtrl::SetItemImage](#setitemimage)|イメージを項目に関連付けます。|  
|[CTreeCtrl::SetItemState](#setitemstate)|項目の状態を設定します。|  
|[CTreeCtrl::SetItemStateEx](#setitemstateex)|現在のツリー ビュー コントロールの指定した項目の拡張の状態を設定します。|  
|[CTreeCtrl::SetItemText](#setitemtext)|項目のテキストを設定します。|  
|[CTreeCtrl::SetLineColor](#setlinecolor)|ツリー ビュー コントロールの現在の線の色を設定します。|  
|[CTreeCtrl::SetScrollTime](#setscrolltime)|ツリー ビュー コントロールのスクロールの最大時間を設定します。|  
|[CTreeCtrl::SetTextColor](#settextcolor)|コントロールのテキストの色を設定します。|  
|[CTreeCtrl::SetToolTips](#settooltips)|ツール ヒント コントロールのツリー ビュー コントロールの子を設定します。|  
|[CTreeCtrl::ShowInfoTip](#showinfotip)|現在のツリー ビュー コントロール内の指定した項目のヒントを表示します。|  
|[CTreeCtrl::SortChildren](#sortchildren)|指定された親アイテムの子が並べ替えられます。|  
|[CTreeCtrl::SortChildrenCB](#sortchildrencb)|アプリケーション定義の並べ替え関数を使用して指定された親アイテムの子が並べ替えられます。|  
  
## <a name="remarks"></a>コメント  
 「ツリー ビュー コントロール」は、ディスク上、文書の見出し、インデックス、またはファイルとディレクトリ内のエントリなどのアイテムの階層リストを表示するウィンドウです。 各項目は、ラベルとオプションのビットマップ イメージと、各項目は、サブ項目が関連付けの一覧を持つことができます。 項目をクリックすると、ユーザーは展開したり、サブ項目の関連付けの一覧を縮小できます。  
  
 このコントロール (つまり、`CTreeCtrl`クラス) は以降、Windows 98 および Windows NT の version 4 で実行するプログラムにのみ使用できます。  
  
 使用する方法について`CTreeCtrl`を参照してください。  
  
- [コントロール](../../mfc/controls-mfc.md)  
  
- [CTreeCtrl の使い方](../../mfc/using-ctreectrl.md)  
  
- [ツリー ビュー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb759988)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
-   サポート技術情報記事 Q222905: HOWTO: CTreeCtrl のコンテキスト メニューを表示  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="create"></a>CTreeCtrl::Create  
 ツリー コントロールをダイアログ ボックス テンプレートで指定する場合、またはを使用している[CTreeView](../../mfc/reference/ctreeview-class.md)、ダイアログ ボックスまたはビューの作成時に、ツリー コントロールが自動的に作成します。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ツリー ビュー コントロールのスタイルを指定します。 説明されているウィンドウ スタイルを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)、および任意に組み合わせた[ツリー ビュー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760013)」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 ツリー ビュー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 ツリー ビュー コントロールの親ウィンドウを通常指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `nID`  
 ツリー ビュー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 その他のいくつかのウィンドウの子ウィンドウとしてツリー ビュー コントロールを作成する場合を使用して、**作成**メンバー関数。 ツリー コントロールを使用して、作成した場合**作成**に渡す必要があります**WS_VISIBLE**、だけでなく他のツリー ビューのスタイル。  
  
 構築する、`CTreeCtrl`で&2; つの手順を実行します。 最初の呼び出し、コンス トラクターを呼び出す**作成**、ツリー ビュー コントロールを作成およびそれにアタッチする、`CTreeCtrl`オブジェクトです。  
  
 拡張ウィンドウ スタイルを使用して、ツリー コントロールを作成するには、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_1.cpp)]  
  
##  <a name="createex"></a>CTreeCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けることは、この関数を呼び出して、`CTreeCtrl`オブジェクトです。  
  
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
 ツリー ビュー コントロールのスタイルを指定します。 説明されているウィンドウ スタイルを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)、および任意に組み合わせた[ツリー ビュー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760013)」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
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
  
##  <a name="createdragimage"></a>CTreeCtrl::CreateDragImage  
 ツリー ビュー コントロールで指定したアイテムのドラッグ用のビットマップを作成し、ビットマップのイメージ リストを作成し、イメージの一覧に、ビットマップを追加するには、この関数を呼び出します。  
  
```  
CImageList* CreateDragImage(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ドラッグされるアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ドラッグ用のビットマップが追加されたイメージ リストへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、イメージ リスト関数を使用して、項目がドラッグされているときにイメージを表示します。  
  
 `CImageList`オブジェクトが保存され、作業完了後に削除する必要があります。 例:  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_2.cpp)]  
  
##  <a name="ctreectrl"></a>CTreeCtrl::CTreeCtrl  
 `CTreeCtrl` オブジェクトを構築します。  
  
```  
CTreeCtrl();
```  
  
##  <a name="deleteallitems"></a>CTreeCtrl::DeleteAllItems  
 ツリー ビュー コントロールからすべての項目を削除するには、この関数を呼び出します。  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_3.cpp)]  
  
##  <a name="deleteitem"></a>CTreeCtrl::DeleteItem  
 ツリー ビュー コントロールから項目を削除するには、この関数を呼び出します。  
  
```  
BOOL DeleteItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 削除するアイテムのハンドル。 場合*hitem*が、 **TVI_ROOT**値、ツリー ビュー コントロールからすべての項目が削除されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_4.cpp)]  
  
##  <a name="editlabel"></a>CTreeCtrl::EditLabel  
 インプレースでは、指定した項目のテキストの編集を開始するには、この関数を呼び出します。  
  
```  
CEdit* EditLabel(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 編集しようとするツリー項目のハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合へのポインター、`CEdit`項目テキストの編集に使用されます。 それ以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 テキストを含む単一行のエディット コントロールで項目のテキストを置き換えることで、編集は行われます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_5.cpp)]  
  
##  <a name="endeditlabelnow"></a>CTreeCtrl::EndEditLabelNow  
 現在のツリー ビュー コントロール内のツリー ビュー アイテムのラベルの編集操作を終了します。  
  
```  
BOOL EndEditLabelNow(BOOL fCancelWithoutSave);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fCancelWithoutSave`|`true`編集操作が完了するとする前に、ツリー ビューの項目への変更を破棄するか、`false`操作が完了するとする前に、ツリー ビューの項目に変更を保存します。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_ENDEDITLABELNOW](http://msdn.microsoft.com/library/windows/desktop/bb773564)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ensurevisible"></a>CTreeCtrl::EnsureVisible  
 この関数では、ツリー ビューのアイテムが表示されていることを確認します。  
  
```  
BOOL EnsureVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 認識されるツリーのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**指定した項目が表示されていることを確認するツリー ビュー コントロール内の項目がスクロールします。 それ以外の場合、戻り値は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、関数は親アイテムを展開または項目が表示されるように、ツリー ビュー コントロールをスクロールします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_6.cpp)]  
  
##  <a name="expand"></a>CTreeCtrl::Expand  
 指定された親アイテムに関連付けられている場合は、子項目のリストを展開または折りたたむには、この関数を呼び出します。  
  
```  
BOOL Expand(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー項目を展開するのハンドル。  
  
 `nCode`  
 実行するアクションの種類を示すフラグです。 このフラグは、次の値のいずれかを設定できます。  
  
- `TVE_COLLAPSE`一覧を折りたたみます。  
  
- `TVE_COLLAPSERESET`一覧を解除し、子項目を削除します。 **TVIS_EXPANDEDONCE**状態を示すフラグをリセットします。 このフラグを使って、`TVE_COLLAPSE`フラグ。  
  
- `TVE_EXPAND`リストを展開します。  
  
- `TVE_TOGGLE`現在折りたたまれている場合は、どのように展開、現在展開されている場合は、リストを折りたたみます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::EnsureVisible](#ensurevisible)します。  
  
##  <a name="getbkcolor"></a>CTreeCtrl::GetBkColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773570)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**コントロールの現在のウィンドウの背景色を表す値。 この値が-1 の場合は、コントロールはウィンドウのシステム カラーを使用しています。 この場合は、使用することができます`::GetSysColor(COLOR_WINDOW)`コントロールを使用している現在のシステム カラーを取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetTextColor](#settextcolor)します。  
  
##  <a name="getcheck"></a>CTreeCtrl::GetCheck  
 アイテムのチェック状態を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetCheck(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 **HTREEITEM**中心とすると、状態情報を受信します。  
  
### <a name="return-value"></a>戻り値  
 ツリー コントロールの項目がチェックされている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetCheck](#setcheck)します。  
  
##  <a name="getchilditem"></a>CTreeCtrl::GetChildItem  
 この関数はツリーを取得するアイテムの表示を呼び出しで指定した項目の子である`hItem`です。  
  
```  
HTREEITEM GetChildItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、子アイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#7;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_7.cpp)]  
  
##  <a name="getcount"></a>CTreeCtrl::GetCount  
 この関数では、ツリー ビュー コントロール内の項目の数を取得します。  
  
```  
UINT GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツリー ビュー コントロール内の項目の数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_8.cpp)]  
  
##  <a name="getdrophilightitem"></a>CTreeCtrl::GetDropHilightItem  
 ドラッグ アンド ドロップ操作の対象となっている項目を取得するには、この関数を呼び出します。  
  
```  
HTREEITEM GetDropHilightItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、アイテムのハンドルが削除されます。それ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="geteditcontrol"></a>CTreeCtrl::GetEditControl  
 この関数では、ツリー ビュー アイテムのテキストを編集するために使用されるエディット コントロールのハンドルを取得します。  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、項目のテキストを編集に使用される編集コントロールへのポインターそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#10;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_10.cpp)]  
  
##  <a name="getextendedstyle"></a>CTreeCtrl::GetExtendedStyle  
 現在のツリー ビュー コントロールを使用している拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のツリー ビュー コントロール内のビットごとの組み合わせ (OR) を表す値での拡張スタイルを使用します。 詳細については、次を参照してください。[ツリー ビュー コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb759981)します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773580)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getfirstvisibleitem"></a>CTreeCtrl::GetFirstVisibleItem  
 この関数では、最初に表示されるツリー ビュー コントロールの項目を取得します。  
  
```  
HTREEITEM GetFirstVisibleItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最初に表示される項目のハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetCheck](#setcheck)します。  
  
##  <a name="getimagelist"></a>CTreeCtrl::GetImageList  
 法線のハンドルまたはツリー ビュー コントロールに関連付けられているイメージ リストを取得するには、この関数を呼び出します。  
  
```  
CImageList* GetImageList(UINT nImageList) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nImageList`  
 取得するイメージ リストの種類です。 イメージ リストには、次の値のいずれかを指定できます。  
  
- `TVSIL_NORMAL`ツリー ビューのアイテムを選択し、選択されていないイメージを含む通常のイメージの一覧を取得します。  
  
- `TVSIL_STATE`ユーザー定義の状態にあるツリー ビューのアイテムのイメージを含んでいる状態のイメージ一覧を取得します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、コントロールのイメージ リストへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 ツリー ビュー コントロール内の各項目には、2 つのビットマップのイメージが関連付けられていることができます。 項目が選択されているし、項目が選択されていないときに、もう一方が表示されたら、1 つのイメージが表示されます。 たとえば、項目が選択されていない時に、開いているフォルダーを選択すると閉じたフォルダーを表示可能性があります。  
  
 イメージ リストの詳細については、次を参照してください。、 [CImageList](../../mfc/reference/cimagelist-class.md)クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#11;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_11.cpp)]  
  
##  <a name="getindent"></a>CTreeCtrl::GetIndent  
 この関数では、金額を取得する、(ピクセル単位) を子項目が親項目の基準としたインデントされます。  
  
```  
UINT GetIndent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 インデントの幅はピクセル単位で測定されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#12;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_12.cpp)]  
  
##  <a name="getinsertmarkcolor"></a>CTreeCtrl::GetInsertMarkColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773590)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**挿入マークの現在の色を表す値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#13;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_13.cpp)]  
  
##  <a name="getitem"></a>CTreeCtrl::GetItem  
 指定されたツリー ビューのアイテムの属性を取得するには、この関数を呼び出します。  
  
```  
BOOL GetItem(TVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::DeleteItem](#deleteitem)します。  
  
##  <a name="getitemdata"></a>CTreeCtrl::GetItemData  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有の値を取得するには、この関数を呼び出します。  
  
```  
DWORD_PTR GetItemData(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 データを取得するアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有値`hItem`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#14;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_14.cpp)]  
  
##  <a name="getitemexpandedimageindex"></a>CTreeCtrl::GetItemExpandedImageIndex  
 現在のツリー ビュー コントロールの指定した項目が展開された状態を表示するイメージのインデックスを取得します。  
  
```  
int GetItemExpandedImageIndex(HTREEITEM hItem)const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|ツリー ビュー コントロールの項目へのハンドルします。|  
  
### <a name="return-value"></a>戻り値  
 指定した項目が展開された状態を表示するイメージのインデックス。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 返します。 メッセージを、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)ツリー ビュー コントロールの項目と、このメソッドを記述する構造体を取得、`iExpandedImage`構造体のメンバーです。  
  
##  <a name="getitemheight"></a>CTreeCtrl::GetItemHeight  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_GETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773599)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
SHORT GetItemHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、項目の高さ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#15;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_15.cpp)]  
  
##  <a name="getitemimage"></a>CTreeCtrl::GetItemImage  
 ツリー ビュー コントロール内の各項目には、2 つのビットマップのイメージが関連付けられていることができます。  
  
```  
BOOL GetItemImage(
    HTREEITEM hItem,  
    int& nImage,  
    int& nSelectedImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 イメージを取得するアイテムのハンドル。  
  
 `nImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目のイメージのインデックスを受け取る整数。  
  
 `nSelectedImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目の選択したイメージのインデックスを受け取る整数。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目のラベルの左側にある、画像が表示されます。 項目が選択されているし、項目が選択されていないときに、もう一方が表示されたら、1 つのイメージが表示されます。 たとえば、項目が選択されていない時に、開いているフォルダーを選択すると閉じたフォルダーを表示可能性があります。  
  
 項目のイメージ、およびツリー ビュー コントロールのイメージ リスト内で選択したイメージのインデックスを取得するには、この関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#16;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_16.cpp)]  
  
##  <a name="getitempartrect"></a>CTreeCtrl::GetItemPartRect  
 現在のツリー ビュー コントロール内の指定した項目の指定した部分の外接する四角形を取得します。  
  
```  
BOOL GetItemPartRect(
    HTREEITEM hItem,   
    int nPart,   
    LPRECT lpRect)const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|ツリー ビュー コントロールの項目へのハンドルします。|  
|[入力] `nPart`|パーツの識別子です。 設定する必要があります`TVGIPR_BUTTON`します。|  
|[出力] `lpRect`|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 このメソッドが成功するが構造体で指定された一部の四角形の座標`hItem`と`nPart`です。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 各ツリー コントロールの項目は、グラフィックスの四角形によって制限されます。 その四角形内のポイントがクリックしたときに、アイテムはモード*ヒット*します。 このメソッドは、四角形内ポイントがクリックされたとき、により識別される項目になるように、最大の四角形を返します、`hItem`パラメーターがヒットします。  
  
 このメソッドは、送信、`TVM_GETITEMPARTRECT`で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。、 [TreeView_GetItemPartRect](http://msdn.microsoft.com/library/windows/desktop/bb773847)マクロです。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例は、ユーザー補助識別子を使用して、 [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)ルート ツリー ビューの項目を識別するハンドルを取得します。 例では、ハンドルを使用して、および[CTreeCtrl::GetItemPartRect](#getitempartrect)そのアイテムの周囲の 3D の四角形を描画するメソッドです。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 使用して、 [CTreeCtrl::MapItemToAccID](#mapitemtoaccid)アクセシビリティ識別子にルート ツリー ビューの項目を関連付けるメソッド。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="getitemrect"></a>CTreeCtrl::GetItemRect  
 外接する四角形を取得するには、この関数を呼び出す`hItem`とするかどうかが表示されているかを判断します。  
  
```  
BOOL GetItemRect(
    HTREEITEM hItem,  
    LPRECT lpRect,  
    BOOL bTextOnly) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビュー コントロールのアイテムのハンドル。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形を受け取る。 座標は、ツリー ビュー コントロールの左上隅に対して相対的です。  
  
 *bTextOnly*  
 このパラメーターが&0; 以外の場合は、外接する四角形には、項目のテキストのみが含まれています。 それ以外の場合、ツリー ビュー コントロールのアイテムが占有する行全体が含まれます。  
  
### <a name="return-value"></a>戻り値  
 外接する四角形に含まれているアイテムが表示される場合は&0; 以外`lpRect`します。 それ以外の場合、0 を`lpRect`初期化されていません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&17;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_19.cpp)]  
  
##  <a name="getitemstate"></a>CTreeCtrl::GetItemState  
 指定した項目の状態を返す`hItem`します。  
  
```  
UINT GetItemState(
    HTREEITEM hItem,  
    UINT nStateMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 状態を取得するアイテムのハンドル。  
  
 `nStateMask`  
 1 つまたは複数の状態を取得するかを示すマスク。 詳細に指定できる値について`nStateMask`の説明を参照してください、**状態**と**対象**のメンバー、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 A **UINT**取得で指定された値のビットごとの OR を保持しています。 使用可能な値については、次を参照してください。 [CTreeCtrl::GetItem](#getitem)します。 特定の状態の値を検索するには、次の例で示すように、状態の値と戻り値のビットごとの AND 演算を実行します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#18;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_20.cpp)]  
  
##  <a name="getitemstateex"></a>CTreeCtrl::GetItemStateEx  
 現在のツリー ビュー コントロール内の指定した項目の拡張の状態を取得します。  
  
```  
UINT GetItemStateEx(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|ツリー ビュー コントロールの項目へのハンドルします。|  
  
### <a name="return-value"></a>戻り値  
 項目の拡張の状態。 詳細については、次を参照してください。、`uStateEx`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 返します。 メッセージを、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)ツリー ビュー コントロールの項目、このメソッドを記述する構造体を取得、`uStateEx`構造体のメンバーです。  
  
##  <a name="getitemtext"></a>CTreeCtrl::GetItemText  
 指定した項目のテキストを返します`hItem`します。  
  
```  
CString GetItemText(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 テキストを取得するアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 A`CString`項目のテキストを含むオブジェクト。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetNextItem](#getnextitem)します。  
  
##  <a name="getlastvisibleitem"></a>CTreeCtrl::GetLastVisibleItem  
 現在のツリー ビュー コントロール内の最後のノードが展開されていない項目を取得します。  
  
```  
HTREEITEM GetLastVisibleItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、最後のノードが展開されていない項目を識別するハンドルそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_GETNEXTITEM](http://msdn.microsoft.com/library/windows/desktop/bb773622)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。、`TVGN_LASTVISIBLE`フラグ、`flag`そのメッセージのパラメーターです。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 1 つ以上のこれらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例では、最後の展開されていないツリー ビュー ノードのアイテムを識別するハンドルを取得し、そのアイテムの周囲の 3D の四角形を描画します。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_21.cpp)]  
  
##  <a name="getlinecolor"></a>CTreeCtrl::GetLineColor  
 このメンバー関数は、win32 メッセージの動作を実装して[TVM_GETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773619)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetLineColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の線の色。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#19;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_22.cpp)]  
  
##  <a name="getnextitem"></a>CTreeCtrl::GetNextItem  
 この関数はツリーを取得するアイテムの表示の呼び出しによって示される、指定されたリレーションシップでは、`nCode`パラメーターを`hItem`します。  
  
```  
HTREEITEM GetNextItem(
    HTREEITEM hItem,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
 `nCode`  
 リレーションシップの種類を示すフラグ`hItem`します。 このフラグは、次の値のいずれかになります。  
  
- `TVGN_CARET`現在選択されている項目を取得します。  
  
- `TVGN_CHILD`指定した項目の最初の子アイテムを取得、`hItem`パラメーター。  
  
- `TVGN_DROPHILITE`ドラッグ アンド ドロップ操作の対象である項目を取得します。  
  
- `TVGN_FIRSTVISIBLE`最初に表示される項目を取得します。  
  
- `TVGN_LASTVISIBLE`ツリーの最後の展開項目を取得します。 これは、ツリー ビュー ウィンドウに表示されている最後の項目を取得しません。  
  
- `TVGN_NEXT`次の兄弟アイテムを取得します。  
  
- `TVGN_NEXTVISIBLE`次に、指定した項目に依存して表示される項目を取得します。  
  
- `TVGN_PARENT`指定した項目の親を取得します。  
  
- `TVGN_PREVIOUS`前の兄弟の項目を取得します。  
  
- `TVGN_PREVIOUSVISIBLE`最初に指定した項目の前に表示される項目を取得します。  
  
- `TVGN_ROOT`指定した項目が一部を元のルート項目の最初の子項目を取得します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、次のアイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この関数は**NULL**取得する項目が、ツリーのルート ノードである場合。 たとえば、このメッセージで使用する場合、`TVGN_PARENT`にフラグを設定、ツリー ビューのルート ノードの直下の子では、メッセージを返します**NULL**します。  
  
### <a name="example"></a>例  
 使用する例については`GetNextItem`ループで、次を参照してください。 [CTreeCtrl::DeleteItem](#deleteitem)します。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#20;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_23.cpp)]  
  
##  <a name="getnextsiblingitem"></a>CTreeCtrl::GetNextSiblingItem  
 次の兄弟を取得するには、この関数を呼び出す`hItem`します。  
  
```  
HTREEITEM GetNextSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 次の兄弟アイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&21;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_24.cpp)]  
  
##  <a name="getnextvisibleitem"></a>CTreeCtrl::GetNextVisibleItem  
 次に表示される項目を取得するには、この関数を呼び出す`hItem`します。  
  
```  
HTREEITEM GetNextVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 次に表示される項目のハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetCheck](#setcheck)します。  
  
##  <a name="getparentitem"></a>CTreeCtrl::GetParentItem  
 親を取得するには、この関数を呼び出す`hItem`します。  
  
```  
HTREEITEM GetParentItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 親項目でのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この関数は**NULL**指定した項目の親が、ツリーのルート ノードである場合。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::EnsureVisible](#ensurevisible)します。  
  
##  <a name="getprevsiblingitem"></a>CTreeCtrl::GetPrevSiblingItem  
 前の兄弟を取得するには、この関数を呼び出す`hItem`します。  
  
```  
HTREEITEM GetPrevSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 前の兄弟のハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&22;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_25.cpp)]  
  
##  <a name="getprevvisibleitem"></a>CTreeCtrl::GetPrevVisibleItem  
 前に表示される項目を取得するには、この関数を呼び出す`hItem`します。  
  
```  
HTREEITEM GetPrevVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 前に表示される項目のハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl 第&23;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_26.cpp)]  
  
##  <a name="getrootitem"></a>CTreeCtrl::GetRootItem  
 ツリー ビュー コントロールのルート項目を取得するには、この関数を呼び出します。  
  
```  
HTREEITEM GetRootItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ルート アイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::EditLabel](#editlabel)します。  
  
##  <a name="getscrolltime"></a>CTreeCtrl::GetScrollTime  
 ツリー ビュー コントロールのスクロールの最大の時刻を取得するには、このメンバー関数を呼び出します。  
  
```  
UINT GetScrollTime() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最長のスクロールの時間 (ミリ秒)。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、win32 メッセージの動作を実装して[TVM_GETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773625)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getselectedcount"></a>CTreeCtrl::GetSelectedCount  
 現在のツリー ビュー コントロールで選択したアイテムの数を取得します。  
  
```  
UINT GetSelectedCount();
```  
  
### <a name="return-value"></a>戻り値  
 選択した項目の数。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_GETSELECTEDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb773629)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getselecteditem"></a>CTreeCtrl::GetSelectedItem  
 ツリー ビュー コントロールの現在選択されている項目を取得するには、この関数を呼び出します。  
  
```  
HTREEITEM GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したアイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&24;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_27.cpp)]  
  
##  <a name="gettextcolor"></a>CTreeCtrl::GetTextColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773633)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**を現在のテキストの色を表す値。 この値が-1 の場合は、コントロールがテキストの色のシステム カラーが使用します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetTextColor](#settextcolor)します。  
  
##  <a name="gettooltips"></a>CTreeCtrl::GetToolTips  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773729)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)ツリー コントロールで使用するオブジェクト。 場合、[作成](#create)メンバー関数は、スタイルを使用して**TVS_NOTOOLTIPS**、ツールヒントを使用しないと**NULL**が返されます。  
  
### <a name="remarks"></a>コメント  
 MFC 実装の`GetToolTips`返します、`CToolTipCtrl`ツールヒント コントロールへのハンドルではなく、ツリー コントロールで使用されるオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#25;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_28.cpp)]  
  
##  <a name="getvisiblecount"></a>CTreeCtrl::GetVisibleCount  
 この関数では、ツリー ビュー コントロールに表示される項目の数を取得します。  
  
```  
UINT GetVisibleCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツリー ビュー コントロールに表示される項目の数それ以外の場合 – 1 です。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetCheck](#setcheck)します。  
  
##  <a name="hittest"></a>CTreeCtrl::HitTest  
 この関数では、ツリー ビュー コントロールのクライアント領域を基準と、指定したポイントの場所を特定します。  
  
```  
HTREEITEM HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
  
HTREEITEM HitTest(TVHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 クライアントをテストするには、点の座標。  
  
 `pFlags`  
 ヒット テストの結果に関する情報を受け取る整数へのポインター。 いずれかまたは値の下に一覧表示、**フラグ**「解説」セクション内のメンバーです。  
  
 `pHitTestInfo`  
 アドレス、 [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448)ヒット テストする位置を含む構造体は、ヒット テストの結果に関する情報を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 指定した点を占めているツリー ビューのアイテムのハンドルまたは**NULL**場合、項目は、ポイントを使用しません。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出されると、`pt`をテストする点の座標を指定します。 指定された位置にアイテムのハンドルを返しますまたは**NULL**場合、項目は、ポイントを使用しません。 さらに、`pFlags`パラメーターには指定したポイントの場所を示す値が含まれています。 指定できる値は次のとおりです。  
  
|||  
|-|-|  
|値|説明|  
|TVHT_ABOVE|クライアント領域の上にします。|  
|TVHT_BELOW|クライアント領域の下。|  
|TVHT_NOWHERE|クライアント領域で、最後の項目の下です。|  
|TVHT_ONITEM|ビットマップの項目に関連付けられているラベルにします。|  
|TVHT_ONITEMBUTTON|上の項目に関連付けられているボタンをクリックします。|  
|TVHT_ONITEMICON|上の項目に関連付けられているビットマップです。|  
|TVHT_ONITEMINDENT|内の項目に関連付けられているインデントします。|  
|TVHT_ONITEMLABEL|上の項目に関連付けられているラベル (文字列) です。|  
|TVHT_ONITEMRIGHT|アイテムの右側に領域です。|  
|TVHT_ONITEMSTATEICON|ユーザー定義の状態にあるツリー ビューの項目の状態アイコン。|  
|TVHT_TOLEFT|クライアント領域の左側のです。|  
|TVHT_TORIGHT|クライアント領域の桁数。|  
|||  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="insertitem"></a>CTreeCtrl::InsertItem  
 ツリー ビュー コントロールに新しい項目を挿入するには、この関数を呼び出します。  
  
```  
HTREEITEM InsertItem(LPTVINSERTSTRUCT lpInsertStruct);

 
HTREEITEM InsertItem(
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    HTREEITEM hParent,  
    HTREEITEM hInsertAfter);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpInsertStruct*  
 ポインター、`TVINSERTSTRUCT`挿入するツリー ビューの項目の属性を指定します。  
  
 `nMask`  
 設定する属性を指定する整数。 参照してください、`TVITEM`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpszItem`  
 項目のテキストを含む文字列のアドレスです。  
  
 `nImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目のイメージのインデックス。  
  
 `nSelectedImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目の選択したイメージのインデックス。  
  
 `nState`  
 項目の状態の値を指定します。 「ツリー ビュー コントロール項目の状態で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の適切な状態の一覧です。  
  
 `nStateMask`  
 どの状態では、設定を指定します。 参照してください、`TVITEM`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lParam`  
 アイテムに関連付けられている 32 ビット アプリケーションに固有の値。  
  
 `hParent`  
 挿入された項目の親のハンドル。  
  
 *hInsertAfter*  
 その後、新しい項目を挿入するアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、新しいアイテムのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この例では、ツリー コントロール項目を挿入するときに、関数の各バージョンを使用する状況を示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&27;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_30.cpp)]  
  
##  <a name="itemhaschildren"></a>CTreeCtrl::ItemHasChildren  
 ツリー項目がで指定されたかどうかを判断するこの関数を使用して`hItem`子項目があります。  
  
```  
BOOL ItemHasChildren(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 ツリー項目で指定する場合は 0 以外`hItem`子項目がそうでない場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 そのため、使用できる場合、 [CTreeCtrl::GetChildItem](#getchilditem)をそれらの子項目を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetSelectedItem](#getselecteditem)します。  
  
##  <a name="mapaccidtoitem"></a>CTreeCtrl::MapAccIdToItem  
 現在のツリー ビュー コントロール内のツリー ビュー アイテムのハンドルに指定されたアクセシビリティ識別子にマップします。  
  
```  
HTREEITEM MapAccIdToItem(UINT uAccId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uAccId`|ツリー ビューの項目内の要素に対してユーザー補助機能の識別子です。|  
  
### <a name="return-value"></a>戻り値  
 ツリー ビューの項目を識別するハンドル ( `HTREEITEM`) に対応する、`uAccId`パラメーター。 詳細については、次を参照してください。、`hItem`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造体。  
  
### <a name="remarks"></a>コメント  
 ユーザー補助機能は、障碍を持つユーザーを支援するアプリケーションがコンピューターを使用します。 ユーザー補助識別子を使用して、`IAccessible`インターフェイスのウィンドウで要素を一意に指定します。 ユーザー補助機能の識別子の詳細についてで「に関する Active Accessibility のサポート」トピックを検索[Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)します。  
  
 このメソッドは、送信、 [TVM_MAPACCIDTOHTREEITEM](http://msdn.microsoft.com/library/windows/desktop/bb773734)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例は、ユーザー補助識別子を使用して、 [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)ルート ツリー ビューの項目を識別するハンドルを取得します。 例では、ハンドルを使用して、 [CTreeCtrl::GetItemPartRect](#getitempartrect)そのアイテムの周囲の 3D の四角形を描画するメソッドです。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 使用して、 [CTreeCtrl::MapItemToAccID](#mapitemtoaccid)アクセシビリティ識別子にルート ツリー ビューの項目を関連付けるメソッド。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="mapitemtoaccid"></a>CTreeCtrl::MapItemToAccID  
 アクセシビリティ識別子には、現在のツリー ビュー コントロール内のツリー ビュー アイテムの指定したハンドルを割り当てます。  
  
```  
UINT MapItemToAccID(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|コントロール内のツリー ビュー アイテムのハンドル。 詳細については、次を参照してください。、`hItem`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造体。|  
  
### <a name="return-value"></a>戻り値  
 ユーザー補助機能の識別子に対応する、`hItem`パラメーター。  
  
### <a name="remarks"></a>コメント  
 ユーザー補助機能は、障碍を持つユーザーを支援するアプリケーションがコンピューターを使用します。 ユーザー補助識別子を使用して、`IAccessible`インターフェイスのウィンドウで要素を一意に指定します。 ユーザー補助機能の識別子の詳細についてで「に関する Active Accessibility のサポート」トピックを検索[Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)します。  
  
 このメソッドは、送信、 [TVM_MAPHTREEITEMTOACCID](http://msdn.microsoft.com/library/windows/desktop/bb773735)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例では、ツリー ビュー コントロールの項目の識別番号を取得します。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 このコード例では、ルートの国/地域のノードの一意な識別番号を取得します。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctreectrl-class_31.cpp)]  
  
##  <a name="select"></a>CTreeCtrl::Select  
 指定されたツリー ビューのアイテムを選択し、ビューにアイテムをスクロールするか、アイテムをドラッグ アンド ドロップ操作の対象を示すために使用するスタイルに再描画するには、この関数を呼び出します。  
  
```  
BOOL Select(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
 `nCode`  
 実行するアクションの種類。 このパラメーターは、次の値のいずれかになります。  
  
- `TVGN_CARET`選択範囲を指定したアイテムに設定します。  
  
- `TVGN_DROPHILITE`ドラッグ アンド ドロップ操作の対象を示すために使用するスタイルで指定したアイテムを再描画します。  
  
- `TVGN_FIRSTVISIBLE`ツリー ビューを垂直方向にスクロールできるように、指定された項目が最初に表示される項目。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`nCode`値を含む`TVGN_CARET`、親ウィンドウは、 **TVN_SELCHANGING**と**TVN_SELCHANGED**通知メッセージです。 さらに、指定した項目が折りたたまれた親アイテムの子である場合は、子項目の親のリストを展開すると、指定した項目を表示することがします。 この場合、親ウィンドウを受け取る、 **TVN_ITEMEXPANDING**と**TVN_ITEMEXPANDED**通知メッセージです。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::HitTest](#hittest)します。  
  
##  <a name="selectdroptarget"></a>CTreeCtrl::SelectDropTarget  
 この関数では、アイテムをドラッグ アンド ドロップ操作の対象を示すために使用するスタイルに再描画します。  
  
```  
BOOL SelectDropTarget(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="selectitem"></a>CTreeCtrl::SelectItem  
 この関数では、指定されたツリー ビューのアイテムを選択します。  
  
```  
BOOL SelectItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 ツリー ビューのアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`hItem`は**NULL**、この関数を使用しないため、項目を選択し、します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="selectsetfirstvisible"></a>CTreeCtrl::SelectSetFirstVisible  
 この関数では、指定したアイテムが最初に表示される項目をされるように、ツリー ビューを垂直方向にスクロールします。  
  
```  
BOOL SelectSetFirstVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 最初に表示される項目として設定するアイテムのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、ウィンドウにメッセージを送信、`TVM_SELECTITEM`と`TVGN_FIRSTVISIBLE`メッセージのパラメーターです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&28;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_32.cpp)]  
  
##  <a name="setautoscrollinfo"></a>CTreeCtrl::SetAutoscrollInfo  
 現在のツリー ビュー コントロールの自動スクロール速度を設定します。  
  
```  
BOOL SetAutoscrollInfo(
    UINT uPixelsPerSec,   
    UINT uUpdateTime);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uPixelsPerSec`|スクロールする&1; 秒あたりのピクセル数。|  
|[入力] `uUpdateTime`|コントロールの更新の間隔の時間間隔。|  
  
### <a name="return-value"></a>戻り値  
 常に `true` を返します。  
  
### <a name="remarks"></a>コメント  
 自動スクロール パラメーターは、現在表示されていない項目をスクロールして表示に使用されます。 ツリー ビュー コントロールが必要、`TVS_EX_AUTOHSCROLL`拡張で説明されているスタイル[ツリー ビュー コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb759981)します。  
  
 このメソッドは、送信、 [TVM_SETAUTOSCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb773738)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在のツリー ビュー コントロールの自動スクロール動作を設定します。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 意図的に行ったツリー ビュー コントロール幅の狭いが自動的にフォーカスがツリー項目を表示するスクロールできるようにします。 コード例では、ツリーの項目がビューに表示されるまで、5 秒ごとに 1 秒あたり 30 ピクセルを自動的にスクロールするツリー ビュー コントロールを設定します。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_33.cpp)]  
  
##  <a name="setbkcolor"></a>CTreeCtrl::SetBkColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773741)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 A **COLORREF**新しい背景色を表す値。 この値が-1 の場合は、コントロールは、背景色のシステム カラーを使用するように戻ります。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**を現在のテキストの色を表す値。 この値が-1 の場合は、コントロールがテキストの色のシステム カラーが使用します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::SetTextColor](#settextcolor)します。  
  
##  <a name="setcheck"></a>CTreeCtrl::SetCheck  
 ツリー コントロール項目のチェック状態を設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetCheck(
    HTREEITEM hItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 **HTREEITEM**チェック状態の変更を受信します。  
  
 `fCheck`  
 ツリー コントロール項目をオンまたはオフにするかどうかを示します。 既定では、`SetCheck`チェックする項目を設定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ツリー コントロール項目をチェックするとき (`fCheck`に設定**TRUE**)、アイテムが隣にチェック マークが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&29;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_34.cpp)]  
  
### <a name="example"></a>例  
 チェック ボックスを使用するには、ツリー コントロールを設定する前に TVS_CHECKBOXES を設定します。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #&30;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_35.cpp)]  
  
##  <a name="setextendedstyle"></a>CTreeCtrl::SetExtendedStyle  
 現在のツリー ビュー コントロールの拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,   
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwExMask`|このメソッドによって、現在のツリー ビュー コントロールのスタイルを指定するビットマスクです。 このパラメーターが&0; の場合は無視されますの値、`dwExStyles`パラメーターがツリー ビュー コントロールに割り当てられます。<br /><br /> 0 またはで説明されているスタイルのビットごとの組み合わせ (OR) を指定[ツリー ビュー コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb759981)します。|  
|[入力] `dwExStyles`|現在のツリー ビューのスタイルを設定または解除に制御を指定するビットマスク。<br /><br /> スタイルの組み合わせを設定するには、「スタイルのビットごとの組み合わせ (OR) を指定[ツリー ビュー コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb759981)します。 一連のスタイルをクリアするには、0 を指定します。|  
  
### <a name="return-value"></a>戻り値  
 以前の値では、コントロールのスタイルを拡張します。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定したスタイルのクリア、`dwExMask`パラメーターで指定されたスタイルを設定し、`dwExStyles`パラメーター。 内のビットに対応する拡張スタイル`dwExMask`を変更します。  
  
 このメソッドは、送信、 [TVM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773744)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例では追加、`TVS_EX_AUTOHSCROLL`スタイルを現在のツリー ビュー コントロールを拡張します。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 意図的に行ったツリー ビュー コントロール幅の狭いが自動的にフォーカスがツリー項目を表示するスクロールできるようにします。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctreectrl-class_36.cpp)]  
  
##  <a name="setimagelist"></a>CTreeCtrl::SetImageList  
 法線を設定するには、この関数を呼び出すか、ツリーの状態のイメージ リスト コントロールを表示し、新しいイメージを使用してコントロールを再描画します。  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 割り当てるイメージ リストへのポインター。 場合`pImageList`は**NULL**、すべてのイメージがツリー ビュー コントロールから削除されます。  
  
 `nImageListType`  
 設定するイメージ リストの種類です。 イメージ リストには、次の値のいずれかを指定できます。  
  
- `TVSIL_NORMAL`ツリー ビューのアイテムを選択し、選択されていないイメージを含む通常のイメージの一覧を設定します。 イメージのオーバーレイには、この状態を使用する必要があります。  
  
- `TVSIL_STATE`ユーザー定義の状態にあるツリー ビューのアイテムのイメージを含んでいる状態のイメージ一覧を設定します。  
  
### <a name="return-value"></a>戻り値  
 存在する場合です。 は前のイメージ リストへのポインターそれ以外の場合**NULL**します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetImageList](#getimagelist)します。  
  
##  <a name="setindent"></a>CTreeCtrl::SetIndent  
 ツリー ビュー コントロールのインデントの幅を設定して、新しい幅をリフレクションするコントロールを再描画するには、この関数を呼び出します。  
  
```  
void SetIndent(UINT nIndent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndent`  
 (ピクセル単位)、インデントの幅。 場合`nIndent`が小さいシステム定義の最小幅よりも新しい幅がシステム定義の最小値に設定します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetIndent](#getindent)します。  
  
##  <a name="setinsertmark"></a>CTreeCtrl::SetInsertMark  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb773753)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL SetInsertMark(
    HTREEITEM hItem,  
    BOOL fAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 **HTREEITEM**挿入マークの配置先アイテムを指定します。 この引数は場合**NULL**、挿入マークを削除します。  
  
 *fAfter*  
 **BOOL**指定した項目の前後に挿入マークは、配置を指定する値。 この引数が&0; 以外の場合、挿入マークは、アイテムの後に配置されます。 この引数がゼロの場合は、挿入マークは、項目の前に配置されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&31;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_37.cpp)]  
  
##  <a name="setinsertmarkcolor"></a>CTreeCtrl::SetInsertMarkColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773755)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrNew`  
 A **COLORREF**新しい挿入マークの色を表す値。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**前の挿入マークの色を表す値。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)します。  
  
##  <a name="setitem"></a>CTreeCtrl::SetItem  
 指定されたツリー ビューのアイテムの属性を設定するには、この関数を呼び出します。  
  
```  
BOOL SetItem(TVITEM* pItem);

 
BOOL SetItem(
    HTREEITEM hItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 」の説明に従って、新しいアイテムを含む構造体の属性、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `hItem`  
 属性を設定するアイテムのハンドル。 参照してください、 **hItem**のメンバー、`TVITEM`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `nMask`  
 設定する属性を指定する整数。 参照してください、**マスク**のメンバー、`TVITEM`構造体。  
  
 `lpszItem`  
 項目のテキストを含む文字列のアドレスです。  
  
 `nImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目のイメージのインデックス。 参照してください、`iImage`のメンバー、`TVITEM`構造体。  
  
 `nSelectedImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目の選択したイメージのインデックス。 参照してください、 **iSelectedImage**のメンバー、`TVITEM`構造体。  
  
 `nState`  
 項目の状態の値を指定します。 参照してください、**状態**のメンバー、`TVITEM`構造体。  
  
 `nStateMask`  
 どの状態では、設定を指定します。 参照してください、**対象**のメンバー、`TVITEM`構造体。  
  
 `lParam`  
 アイテムに関連付けられている 32 ビット アプリケーションに固有の値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `TVITEM`構造体、 **hItem**メンバーは、項目を識別して、**マスク**メンバーが設定される属性を指定します。  
  
 場合、**マスク**メンバーまたは`nMask`パラメーターを指定、`TVIF_TEXT`値、 **pszText**メンバー、または`lpszItem`null で終わる文字列のアドレスは、および**cchTextMax**メンバーは無視されます。 場合**マスク**(または`nMask`) を指定、`TVIF_STATE`値、**対象**メンバーまたは`nStateMask`パラメーターを指定する項目の状態を変更して、**状態**メンバーまたは`nState`パラメーターには、これらの状態の値が含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#32;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_38.cpp)]  
  
##  <a name="setitemdata"></a>CTreeCtrl::SetItemData  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有の値を設定するには、この関数を呼び出します。  
  
```  
BOOL SetItemData(
    HTREEITEM hItem,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 データを取得するアイテムのハンドル。  
  
 `dwData`  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有値`hItem`です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&33;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_39.cpp)]  
  
##  <a name="setitemexpandedimageindex"></a>CTreeCtrl::SetItemExpandedImageIndex  
 現在のツリー ビュー コントロールの指定した項目が展開された状態を表示するイメージのインデックスを設定します。  
  
```  
BOOL SetItemExpandedImageIndex(
    HTREEITEM hItem,   
    int iExpandedImage);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|ツリー ビュー コントロールの項目へのハンドルします。|  
|[入力] `iExpandedImage`|指定した項目が展開された状態を表示するイメージのインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドは割り当てます、`iExpandedImage`パラメーターを`iExpandedImage`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造、および、そのメッセージの構造体を使用しています。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例は、単純なテストを判断するかどうか、 [CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)メソッドで設定値を返す、 [CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)メソッドです。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;8](../../mfc/reference/codesnippet/cpp/ctreectrl-class_40.cpp)]  
  
##  <a name="setitemheight"></a>CTreeCtrl::SetItemHeight  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773761)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
SHORT SetItemHeight(SHORT cyHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `cyHeight`  
 ピクセル単位で、ツリー ビューでは、すべての項目の新しい高さを指定します。 この引数がイメージの高さよりも小さい場合は、イメージの高さに設定されます。 この引数があってもがない場合に切り捨てられますが、最も近い偶数値。 この引数が-1 の場合は、コントロールは、既定の項目の高さを使用してに戻ります。  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位での項目の前の高さ。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetItemHeight](#getitemheight)します。  
  
##  <a name="setitemimage"></a>CTreeCtrl::SetItemImage  
 イメージを項目に関連付けます。  
  
```  
BOOL SetItemImage(
    HTREEITEM hItem,  
    int nImage,  
    int nSelectedImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 イメージを設定するアイテムのハンドル。  
  
 `nImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目のイメージのインデックス。  
  
 `nSelectedImage`  
 ツリー ビュー コントロールのイメージ リスト内の項目の選択したイメージのインデックス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ツリー ビュー コントロール内の各項目には、2 つのビットマップのイメージが関連付けられていることができます。 項目のラベルの左側にある、画像が表示されます。 項目が選択されているし、項目が選択されていないときに、もう一方が表示されたら、1 つのイメージが表示されます。 たとえば、項目が選択されていない時に、開いているフォルダーを選択すると閉じたフォルダーを表示可能性があります。  
  
 項目のイメージ、およびツリー ビュー コントロールのイメージ リスト内で選択したイメージのインデックスを設定するには、この関数を呼び出します。  
  
 イメージの詳細については、次を参照してください。 [CImageList](../../mfc/reference/cimagelist-class.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetItemImage](#getitemimage)します。  
  
##  <a name="setitemstate"></a>CTreeCtrl::SetItemState  
 指定した項目の状態を設定`hItem`します。  
  
```  
BOOL SetItemState(
    HTREEITEM hItem,  
    UINT nState,  
    UINT nStateMask);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 状態を設定するアイテムのハンドル。  
  
 `nState`  
 項目の新しい状態を指定します。  
  
 `nStateMask`  
 どの状態が変更するかを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、状態は、次を参照してください。 [CTreeCtrl::GetItem](#getitem)します。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetItemState](#getitemstate)します。  
  
##  <a name="setitemstateex"></a>CTreeCtrl::SetItemStateEx  
 現在のツリー ビュー コントロールの指定した項目の拡張の状態を設定します。  
  
```  
BOOL SetItemStateEx(
    HTREEITEM hItem,   
    UINT uStateEx);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|ツリー ビュー コントロールの項目へのハンドルします。|  
|[入力] `uStateEx`|項目の拡張の状態。 詳細については、次を参照してください。、`uStateEx`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドは割り当てます、`uStateEx`パラメーターを`uStateEx`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造、および、そのメッセージの構造体を使用しています。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_treeCtrl`つまり、現在のツリー ビュー コントロールにアクセスするために使用します。 このコード例は、符号なし整数といくつかの HTREEITEM 変数にも定義します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>例  
 次のコード例は、ツリー ビューの項目を無効の状態に設定します。 コード例は、示されていませんが、前のセクションでは、米国のルート国/地域ノード、ペンシルバニア州とワシントン州の状態を表すサブノードおよびこれらの州の都市を対象としてツリー項目で構成されるツリー ビューを作成しました。 このコード例では、ペンシルベニア ノードを無効になっている状態に設定します。  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctreectrl-class_41.cpp)]  
  
##  <a name="setitemtext"></a>CTreeCtrl::SetItemText  
 指定した項目のテキストを設定`hItem`します。  
  
```  
BOOL SetItemText(
    HTREEITEM hItem,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 テキストを設定するアイテムのハンドル。  
  
 `lpszItem`  
 新しい項目のテキストを含む文字列のアドレス  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&34;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_42.cpp)]  
  
##  <a name="setlinecolor"></a>CTreeCtrl::SetLineColor  
 ツリー ビュー コントロールの現在の線の色を設定するには、このメンバー関数を呼び出します。  
  
```  
COLORREF SetLineColor(COLORREF clrNew = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrNew`  
 新しい行の色。  
  
### <a name="return-value"></a>戻り値  
 前の線の色。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、win32 メッセージの動作を実装して[TVM_SETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773764)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#35;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_43.cpp)]  
  
##  <a name="setscrolltime"></a>CTreeCtrl::SetScrollTime  
 ツリー ビュー コントロールのスクロールの最大時間を設定するには、このメンバー関数を呼び出します。  
  
```  
UINT SetScrollTime(UINT uScrollTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *uScrollTime*  
 新しいスクロールの最大時間 (ミリ秒)。 この値が 100 未満の場合は、ことが 100 に切り上げします。  
  
### <a name="return-value"></a>戻り値  
 前のスクロールの最大時間 (ミリ秒)。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、win32 メッセージの動作を実装して[TVM_SETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773767)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="settextcolor"></a>CTreeCtrl::SetTextColor  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773769)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 A **COLORREF**新しいテキストの色を表す値。 この引数が-1 の場合は、コントロールはテキストの色のシステム カラーを使用してに戻ります。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**を以前のテキストの色を表す値。 この値が-1 の場合は、コントロールは、テキストの色のシステム カラーを使用していました。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl&#36;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_44.cpp)]  
  
##  <a name="settooltips"></a>CTreeCtrl::SetToolTips  
 このメンバー関数は、Win32 メッセージの動作を実装して[TVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773772)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndTip`  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)ツリー コントロールで使用するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 、コントロールによって使用されていたツール ヒントを格納するオブジェクトまたは**NULL**ツールヒントが以前に使用しない場合。  
  
### <a name="remarks"></a>コメント  
 ツール ヒントを使用するには、 **TVS_NOTOOLTIPS**スタイルを作成するとき、`CTreeCtrl`オブジェクトです。  
  
### <a name="example"></a>例  
  例を参照してください[CTreeCtrl::GetToolTips](#gettooltips)します。  
  
##  <a name="showinfotip"></a>CTreeCtrl::ShowInfoTip  
 現在のツリー ビュー コントロール内の指定した項目のヒントを表示します。  
  
```  
void ShowInfoTip(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hItem`|コントロール内のツリー ビューの項目へのハンドル。 詳細については、次を参照してください。、`hItem`のメンバー、 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459)構造体。|  
  
### <a name="remarks"></a>コメント  
 ヒントの違いについての詳細については、「ツールヒントとヒント」トピックを検索[Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)します。  
  
 このメソッドは、送信、 [TVM_SHOWINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb773779)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="sortchildren"></a>CTreeCtrl::SortChildren  
 この関数では、ツリー ビュー コントロール内の指定した親アイテムの子アイテムをアルファベット順に並べ替えます。  
  
```  
BOOL SortChildren(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `hItem`  
 子項目が並べ替えられますが、親アイテムのハンドル。 場合`hItem`は**NULL**、並べ替えは、ツリーのルートから続行します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `SortChildren`ツリーを再帰的に参照しません。直下の子のみ`hItem`が並べ替えられます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&37;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_45.cpp)]  
  
##  <a name="sortchildrencb"></a>CTreeCtrl::SortChildrenCB  
 アイテムを比較するアプリケーション定義のコールバック関数を使用してツリー ビューの項目を並べ替えるには、この関数を呼び出します。  
  
```  
BOOL SortChildrenCB(LPTVSORTCB pSort);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSort*  
 ポインター、 [TVSORTCB](http://msdn.microsoft.com/library/windows/desktop/bb773462)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構造体の比較関数、 **lpfnCompare**、負の値を返す必要があります最初の項目が、2 番目に従う必要がありますか場合は&0;、2 つの項目が等しい場合、正の値の最初の項目は、2 つ目の前に記述場合、。  
  
 `lParam1`と`lParam2`パラメーターに対応、 **lParam**のメンバー、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456)の比較対象となる&2; つの項目を構成します。 `lParamSort`パラメーターに対応して、 **lParam**のメンバー、`TV_SORTCB`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CTreeCtrl #&38;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_46.cpp)]  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#39;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_47.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CImageList クラス](../../mfc/reference/cimagelist-class.md)

