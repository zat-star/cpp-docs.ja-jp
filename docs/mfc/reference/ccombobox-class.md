---
title: "CComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, CComboBox objects
- CComboBox class
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
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
ms.openlocfilehash: 5328c245e0d662c4701042b37c16870d6b1e33c7
ms.lasthandoff: 02/24/2017

---
# <a name="ccombobox-class"></a>CComboBox クラス
Windows のコンボ ボックスの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|`CComboBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Ccombobox::addstring](#addstring)|文字列をコンボ ボックスまたはリスト ボックスでの並べ替えられた位置にあるリスト ボックスの一覧の末尾に追加、 **CBS_SORT**スタイル。|  
|[CComboBox::Clear](#clear)|削除 (クリア) 現在の選択範囲のエディット コントロールである場合。|  
|[CComboBox::CompareItem](#compareitem)|並べ替えられたオーナー描画のコンボ ボックスで新しいリスト アイテムの相対位置を決定するためにフレームワークによって呼び出されます。|  
|[CComboBox::Copy](#copy)|クリップボードに存在する場合は、現在の選択項目をコピー**エディット**形式です。|  
|[CComboBox::Create](#create)|コンボ ボックスを作成し、それにアタッチ、`CComboBox`オブジェクトです。|  
|[CComboBox::Cut](#cut)|(切り取り)、現在選択中のいずれかの編集を制御し、削除されたテキストでクリップボードにコピー**エディット**形式です。|  
|[CComboBox::DeleteItem](#deleteitem)|オーナー描画のコンボ ボックスから、リスト項目が削除されるときに、フレームワークによって呼び出されます。|  
|[オーナー](#deletestring)|コンボ ボックスのリスト ボックスから文字列を削除します。|  
|[CComboBox::Dir](#dir)|コンボ ボックスのリスト ボックスにファイル名の一覧を追加します。|  
|[CComboBox::DrawItem](#drawitem)|オーナー描画のコンボ ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CComboBox::FindString](#findstring)|コンボ ボックスの一覧ボックスで指定されたプレフィックスを含む最初の文字列を検索します。|  
|[CComboBox::FindStringExact](#findstringexact)|リスト ボックスの最初のストリング (コンボ ボックス)、指定した文字列に一致するを検索します。|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|に関する情報を取得、`CComboBox`オブジェクトです。|  
|[CComboBox::GetCount](#getcount)|コンボ ボックスのリスト ボックス内の項目の数を取得します。|  
|[CComboBox::GetCueBanner](#getcuebanner)|コンボ ボックス コントロールに表示されるヒントのテキストを取得します。|  
|[CComboBox::GetCurSel](#getcursel)|コンボ ボックスのリスト ボックスに存在する場合は、現在選択されている項目のインデックスを取得します。|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|ドロップダウン コンボ ボックスの表示 (ドロップ ダウン) リスト ボックスの画面座標を取得します。|  
|[CComboBox::GetDroppedState](#getdroppedstate)|ドロップダウン コンボ ボックスのリスト ボックスを表示するか (ドロップダウン) を決定します。|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックス部分の幅を取得します。|  
|[CComboBox::GetEditSel](#geteditsel)|コンボ ボックスのエディット コントロールで現在の選択範囲の開始と終了文字の位置を取得します。|  
|[CComboBox::GetExtendedUI](#getextendedui)|コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスであるかどうかを決定します。|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|コンボ ボックスの一覧ボックスが水平方向にスクロールするピクセルの幅を返します。|  
|[CComboBox::GetItemData](#getitemdata)|コンボ ボックス内の指定した項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します。|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|コンボ ボックス内の指定した項目に関連付けられているアプリケーションによって提供される 32 ビット ポインターを取得します。|  
|[CComboBox::GetItemHeight](#getitemheight)|コンボ ボックスのリスト項目の高さを取得します。|  
|[CComboBox::GetLBText](#getlbtext)|コンボ ボックスのリスト ボックスから文字列を取得します。|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|コンボ ボックスのリスト ボックスに、文字列の長さを取得します。|  
|[CComboBox::GetLocale](#getlocale)|コンボ ボックスのロケール識別子を取得します。|  
|[CComboBox::GetMinVisible](#getminvisible)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を取得します。|  
|[CComboBox::GetTopIndex](#gettopindex)|コンボ ボックスの一覧ボックス部分には、最初に表示される項目のインデックスを返します。|  
|[CComboBox::InitStorage](#initstorage)|項目と、リスト ボックス、コンボ ボックスの部分で文字列用のメモリ ブロックに事前に割り当てます。|  
|[CComboBox::InsertString](#insertstring)|コンボ ボックスのリスト ボックスに文字列を挿入します。|  
|[CComboBox::LimitText](#limittext)|ユーザーがコンボ ボックスのエディット コントロールに入力できるテキストの長さを制限します。|  
|[CComboBox::MeasureItem](#measureitem)|オーナー描画のコンボ ボックスの作成時に、コンボ ボックスのサイズを調べるためにフレームワークによって呼び出されます。|  
|[CComboBox::Paste](#paste)|エディット コントロールの現在のカーソル位置にクリップボードからデータを挿入します。 クリップボードのデータを含んでいる場合のみ、データが挿入される**エディット**形式です。|  
|[CComboBox::ResetContent](#resetcontent)|すべての項目がリストからボックス、コンボ ボックスのコントロールの編集を削除します。|  
|[CComboBox::SelectString](#selectstring)|コンボ ボックスのリスト ボックスに文字列を検索し、文字列が見つかった場合は、リスト ボックスで、文字列を選択してエディット コントロールに文字列をコピーします。|  
|[CComboBox::SetCueBanner](#setcuebanner)|コンボ ボックス コントロールに表示されるヒントのテキストを設定します。|  
|[CComboBox::SetCurSel](#setcursel)|コンボ ボックスのリスト ボックスに文字列を選択します。|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックス部分の幅を設定します。|  
|[CComboBox::SetEditSel](#seteditsel)|コンボ ボックスのエディット コントロール内の文字を選択します。|  
|[CComboBox::SetExtendedUI](#setextendedui)|既定のユーザー インターフェイスまたはがコンボ ボックスの拡張ユーザー インターフェイスのいずれかを選択する、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|コンボ ボックスの一覧ボックスが水平方向にスクロールするピクセルの幅を設定します。|  
|[CComboBox::SetItemData](#setitemdata)|コンボ ボックスで指定したアイテムに関連付けられている 32 ビット値を設定します。|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|コンボ ボックスで指定された項目に関連付けられている 32 ビット ポインターを設定します。|  
|[CComboBox::SetItemHeight](#setitemheight)|コンボ ボックスまたはコンボ ボックスのエディット コントロール (または静的テキスト) の部分の高さにリスト項目の高さを設定します。|  
|[CComboBox::SetLocale](#setlocale)|コンボ ボックスのロケール識別子を設定します。|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を設定します。|  
|[CComboBox::SetTopIndex](#settopindex)|上部にある指定したインデックスを持つ項目を表示するコンボ ボックスの一覧ボックス部分に指示します。|  
|[CComboBox::ShowDropDown](#showdropdown)|表示またはがコンボ ボックスのリスト ボックスを非表示、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。|  
  
## <a name="remarks"></a>コメント  
 コンボ ボックスは、スタティック コントロールまたはエディット コントロールと組み合わせて、リスト ボックスで構成されます。 コントロールのリスト ボックス部分常に表示される場合がありますまたは可能性がありますのみドロップダウン リスト コントロールの横にあるドロップダウン矢印を選択するとします。  
  
 リスト ボックスで現在選択されているアイテム (存在する場合) は、静的に表示されるまたはコントロールを編集します。 さらに、コンボ ボックスがドロップダウン リストのスタイルは、ユーザーが、ボックスの一覧で、項目のいずれかの先頭の文字を入力し、ボックスの一覧表示されていればをその最初の文字では、次の項目が強調表示します。  
  
 次の表に、次の&3; つのコンボ ボックス[スタイル](../../mfc/reference/combo-box-styles.md)します。  
  
|スタイル|ときにリスト ボックスを表示|コントロールの種類|  
|-----------|-------------------------------|-----------------------------|  
|[シンプル]|Always|編集|  
|Drop-down|下へドロップされたときに|編集|  
|ドロップダウン リスト|下へドロップされたときに|スタティック|  
  
 作成することができます、`CComboBox`ダイアログ テンプレートから、またはコードで直接オブジェクトです。 どちらの場合も、コンス トラクターを呼び出す最初`CComboBox`を構築する、`CComboBox`オブジェクト。 まず、[作成](#create)コントロールを作成し適用するメンバー関数を、`CComboBox`オブジェクトです。  
  
 Windows のコンボ ボックスからその親に送信された通知メッセージを処理する場合 (通常から派生したクラス`CDialog`)、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップ エントリは、次の形式をとります。  
  
 **ON_**Notification **(**`id`**,**`memberFxn`**)**  
  
 ここで`id`通知を送信するコンボ ボックス コントロールの子ウィンドウの ID を指定し、`memberFxn`通知を処理する記述した親メンバー関数の名前を指定します。  
  
 親の関数のプロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 特定の通知を送信する順序を予測することはできません。 具体的には、 **CBN_SELCHANGE**前に、または後に、通知が発生する可能性、 **CBN_CLOSEUP**通知します。  
  
 メッセージ マップ エントリを潜在的な次のとおりです。  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 以降)コンボ ボックスの一覧ボックスが閉じられます。 コンボ ボックスを持つこの通知メッセージは送信されず、 [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md)スタイル。  
  
- **ON_CBN_DBLCLK**ユーザーがコンボ ボックスのリスト ボックスに文字列をダブルクリックします。 コンボ ボックスのこの通知メッセージが送信されるだけ、 **CBS_SIMPLE**スタイル。 コンボ ボックスに、 [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md)または[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイルをダブルクリックを実行できないため、1 回のクリックは、リスト ボックスを非表示にします。  
  
- **ON_CBN_DROPDOWN**コンボ ボックスの一覧ボックスがドロップダウンされようとしています (表示可能にする)。 この通知メッセージは、コンボ ボックスにのみ発生することが、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_EDITCHANGE**ユーザーがコンボ ボックスのエディット コントロールの部分のテキストが変更された可能性があるアクションを取得します。 異なり、 **CBN_EDITUPDATE**メッセージ、画面を更新した後、このメッセージが送信されます。 コンボ ボックスにある場合は送信されません、 **CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_EDITUPDATE**コンボ ボックスのエディット コントロールの部分が変更されたテキストを表示しようとしています。 コントロールがテキストを書式設定後、そのテキストを表示する前に、この通知メッセージが送信されます。 コンボ ボックスにある場合は送信されません、 **CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_ERRSPACE**コンボ ボックスは、特定の要求を満たすのに十分なメモリを割り当てることができません。  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 以降)ユーザーの選択を取り消す必要があることを示します。 ユーザーは、項目をクリックしたし、別のウィンドウまたはコンボ ボックスのリスト ボックスを非表示にするコントロールをクリックします。 この通知メッセージが送信する前に、 **CBN_CLOSEUP**ユーザーの選択を無視するかを示すために通知メッセージです。 **CBN_SELENDCANCEL**または**CBN_SELENDOK**通知メッセージが送信される場合でも、 **CBN_CLOSEUP**通知メッセージは送信されません (コンボ ボックスの場合として、 **CBS_SIMPLE**スタイル)。  
  
- **ON_CBN_SELENDOK**ユーザー項目を選択してし、ENTER キーを押したまたはコンボ ボックスのリスト ボックスを非表示に下方向キーをクリックします。 この通知メッセージが送信する前に、 **CBN_CLOSEUP**こと、ユーザーの選択が有効と見なされるかを示すメッセージ。 **CBN_SELENDCANCEL**または**CBN_SELENDOK**通知メッセージが送信される場合でも、 **CBN_CLOSEUP**通知メッセージは送信されません (コンボ ボックスの場合として、 **CBS_SIMPLE**スタイル)。  
  
- **ON_CBN_KILLFOCUS**コンボ ボックスが入力フォーカスを失うことです。  
  
- **ON_CBN_SELCHANGE**コンボ ボックスのリスト ボックスの選択項目がリスト ボックスでクリックするか、矢印キーを使用して選択を変更するか、ユーザーの結果として変更されます。 このメッセージを処理する場合を使用してコンボ ボックスのエディット コントロールでテキストのみを取得する`GetLBText`または別の同様の関数です。 `GetWindowText`使用できません。  
  
- **ON_CBN_SETFOCUS**コンボ ボックスが入力フォーカスを受け取る。  
  
 作成する場合、 `CComboBox` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、`CComboBox`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 埋め込んだ場合、`CComboBox`別のウィンドウ内のオブジェクトがオブジェクトを破棄する必要はありません。 作成する場合、`CComboBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CComboBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を Windows のコンボ ボックスが破棄されるときに破棄するオブジェクト。  
  
 **注**を処理する場合`WM_KEYDOWN`と`WM_CHAR`、メッセージがあるをサブクラス化、コンボ ボックスの編集しリスト ボックス コントロールからのクラスを派生させることは`CEdit`と`CListBox`、派生クラスに含まれるメッセージのハンドラーを追加します。 詳細については、次を参照してください[http://support.microsoft.com/default.aspxscid=kb;en-us;。Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667)と[CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="addstring"></a>Ccombobox::addstring  
 コンボ ボックスのリスト ボックスに文字列を追加します。  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 追加するのには、null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、リスト ボックス内の文字列の 0 から始まるインデックスを勧めします。 戻り値は**返します**エラーが発生した場合、戻り値は**CB_ERRSPACE**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスで作成されなかった場合、 [CBS_SORT](../../mfc/reference/combo-box-styles.md)スタイル、文字列がリストの末尾に追加します。 それ以外の場合、リストに、文字列を挿入し、リストの並べ替え。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 リスト内の指定位置に文字列を挿入するには、使用、[は](#insertstring)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#3;](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 `CComboBox` オブジェクトを構築します。  
  
```  
CComboBox();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#1;](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 削除 (クリア) 現在の選択範囲のコンボ ボックスのエディット コントロールである場合。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 を現在の選択項目を削除してから削除された内容をクリップボードに配置するには、[切り取り](#cut)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&4;](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 並べ替えられたオーナー描画コンボ ボックスの一覧ボックス部分に新しい項目の相対的な位置を決定するためにフレームワークによって呼び出されます。  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCompareItemStruct`  
 Long ポインター、 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 説明する&2; つのアイテムの相対位置を示す、`COMPAREITEMSTRUCT`構造体。 次の値のいずれかを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|– 1|項目 1 は、項目 2 の前に並べ替えられます。|  
|0|アイテム 1 とアイテム 2 は、同じを並べ替えます。|  
|1|項目 1 は、項目 2 の後に並べ替えられます。|  
  
 参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の詳細については`COMPAREITEMSTRUCT`です。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 オーナー描画のコンボ ボックスを作成するかどうか、 **LBS_SORT**スタイル、リスト ボックスに追加された新しい項目を並べ替え、フレームワークを支援するには、この関数をオーバーライドする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#5;](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 クリップボードにコンボ ボックスのエディット コントロールである場合は、現在の選択項目をコピー**エディット**形式です。  
  
```  
void Copy();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&6;](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 コンボ ボックスを作成し、それにアタッチ、`CComboBox`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 コンボ ボックスのスタイルを指定します。 任意の組み合わせを適用[コンボ ボックス スタイル](../../mfc/reference/combo-box-styles.md)します。  
  
 `rect`  
 コンボ ボックスのサイズと位置を指します。 [RECT 構造体](../../mfc/reference/rect-structure1.md)または`CRect`オブジェクトです。  
  
 `pParentWnd`  
 コンボ ボックスの親ウィンドウを指定します (通常、 `CDialog`)。 ことはできません**NULL**します。  
  
 `nID`  
 コンボ ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CComboBox`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず**作成**、Windows のコンボ ボックスを作成およびそれにアタッチする、`CComboBox`オブジェクトです。  
  
 ときに**作成**実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)コンボ ボックスにメッセージです。  
  
 既定では、これらのメッセージが処理される、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数、`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CComboBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)コンボ ボックス コントロールにします。 :  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**コンボ ボックスで、リスト ボックスに垂直スクロール機能を追加するには  
  
- **WS_HSCROLL**コンボ ボックスで、リスト ボックスに水平スクロール機能を追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ オーダーにコンボ ボックスを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#2;](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 (切り取り) 現在の選択範囲のコンボ ボックスで編集する場合は制御し、削除されたテキストでクリップボードにコピー**エディット**形式です。  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>コメント  
 を削除したテキストをクリップボードをかけることがなく、現在の選択を削除する、[クリア](#clear)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#7;](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 ユーザーは、オーナー描画から項目を削除する場合に、フレームワークによって呼び出されます`CComboBox`オブジェクトまたはコンボ ボックスを破棄します。  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDeleteItemStruct`  
 Windows への long ポインター [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md)削除された項目に関する情報を格納する構造体。 参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)この構造体の詳細についてです。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 必要に応じて、コンボ ボックスを描画するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#8;](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>オーナー  
 位置に項目を削除`nIndex`コンボ ボックスからです。  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスを削除する文字列を指定します。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、リストに残っている文字列の数です。 戻り値は**返します**場合`nIndex`リストの項目の数より大きいインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 次のすべてのアイテム`nIndex`下の&1; つの位置に移動するようになりました。 たとえば、コンボ ボックスに&2; つの項目が含まれている場合の最初の項目を削除するにより最初の位置で今すぐに残りの項目。 `nIndex`=&0; の最初の位置に項目を入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#9;](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 ドライブまたはファイル名の一覧をコンボ ボックスのリスト ボックスに追加します。  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>パラメーター  
 `attr`  
 任意の組み合わせを指定できます、`enum`値」に記載[cfile::getstatus](../../mfc/reference/cfile-class.md#getstatus)または、次の値の任意の組み合わせ。  
  
- **DDL_READWRITE**ファイルの読み取りやに書き込まれることができます。  
  
- **DDL_READONLY**ファイルをから読み取ることができますに書き込まれません。  
  
- **DDL_HIDDEN**ファイルを非表示に、ディレクトリの一覧で表示されません。  
  
- **DDL_SYSTEM**ファイルは、システム ファイルです。  
  
- **DDL_DIRECTORY**により指定された名前`lpszWildCard`ディレクトリを指定します。  
  
- **DDL_ARCHIVE**ファイルはアーカイブされました。  
  
- **含んだ**により指定された名前に一致するすべてのドライブに含める`lpszWildCard`します。  
  
- **DDL_EXCLUSIVE**排他フラグ。 排他フラグが設定されている場合は、指定した種類のファイルのみが表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した型のファイルが一覧表示されます。  
  
 `lpszWildCard`  
 ファイル指定文字列を指します。 文字列にワイルドカードを含めることができます (たとえば、*.\*)。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、最後のファイル名の一覧に追加の 0 から始まるインデックスを勧めします。 戻り値は**返します**エラーが発生した場合、戻り値は**CB_ERRSPACE**新しい文字列を格納する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#10;](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 オーナー描画コンボ ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)この構造体の詳細についてです。  
  
 既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、この関数をオーバーライド`CComboBox`オブジェクトです。 このメンバー関数が終了する前に、アプリケーションがで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#11;](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox::FindString  
 検出されるが、最初の文字列のコンボ ボックスのリスト ボックスで指定したプレフィックスが含まれていますが、選択しません。  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartAfter`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスが含まれています。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nStartAfter`します。 、-1 の場合は、最初からリスト ボックス全体が検索されます。  
  
 `lpszString`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、一致する項目の 0 から始まるインデックス。 **返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#12;](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 呼び出す、 `FindStringExact` 、最初リスト ボックスで指定された文字列と一致する文字列 (コンボ ボックス内を検索するメンバー関数を`lpszFind`します。  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndexStart`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスを指定します。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nIndexStart`します。 場合`nIndexStart`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszFind`  
 検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索は大文字と小文字を区別はないため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 一致する項目の&0; から始まるインデックスまたは**返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 ですが、コンボ ボックスがオーナー描画スタイルで作成された場合、 [CBS_HASSTRINGS](../../mfc/reference/combo-box-styles.md)スタイル、`FindStringExact`の値に対してダブルワード値を一致させようと`lpszFind`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#13;](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 情報を取得、`CComboBox`オブジェクトです。  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pcbi*  
 ポインター、 [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798)構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 コンボ ボックスの一覧ボックス部分内の項目数を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目の数。 返されるカウントは、1 (インデックスは&0; から始まる) の最後の項目のインデックス値よりも大きいです。 **返します**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#14;](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 コンボ ボックス コントロールに表示されるヒントのテキストを取得します。  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpszText`|キュー バナー テキストを受け取るバッファーへのポインター。|  
|[入力] `cchText`|バッファーのサイズを`lpszText`パラメーターをポイントします。|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードで、 [CString](../../atl-mfc-shared/using-cstring.md)存在する場合は、キュー バナー テキストを格納するオブジェクトそれ以外の場合、`CString`長さがゼロを持つオブジェクトです。  
  
 または  
  
 2 番目のオーバー ロードで`true`場合、このメソッドは正常でない場合は`false`です。  
  
### <a name="remarks"></a>コメント  
 ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、キュー テキストが表示されます。  
  
 このメソッドは、送信、 [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 コンボ ボックス内のどのアイテムの選択を判断するには、このメンバー関数を呼び出します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスのリスト ボックスで現在選択されている項目の&0; から始まるインデックスまたは**返します**項目が選択されていない場合。  
  
### <a name="remarks"></a>コメント  
 `GetCurSel`リストにインデックスを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#15;](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 呼び出す、`GetDroppedControlRect`ドロップダウン コンボ ボックスの表示 (ドロップダウン) リスト ボックスの画面座標を取得します。  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lprect*  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)座標を受け取ることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#16;](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 呼び出す、`GetDroppedState`ドロップダウン コンボ ボックスのリスト ボックスを表示するか (ドロップダウン) を調べます。  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスを表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&17;](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 設定できる最小幅は、コンボ ボックスのリスト ボックスのピクセルを取得するには、この関数を呼び出します。  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、最小の使用可能な幅 (ピクセル単位)。それ以外の場合、**返します**します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md)または[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル。  
  
 既定では、ドロップダウン リスト ボックスの使用可能な最小の幅は 0 です。 設定できる最小幅を呼び出すことによって設定できる[SetDroppedWidth](#setdroppedwidth)します。 コンボ ボックスのリスト ボックス部分が表示されるときに、幅が使用可能な幅の最小値またはコンボ ボックスの幅のうち、大きい方。  
  
### <a name="example"></a>例  
  例を参照してください[SetDroppedWidth](#setdroppedwidth)します。  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 コンボ ボックスのエディット コントロールで現在の選択範囲の開始と終了文字の位置を取得します。  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 上位ワードに選択範囲の終了後に下位ワード内の開始位置と最初に選択されていない文字の位置を表す 32 ビット値。 この関数は、編集コントロールを使用しないコンボ ボックスで使用する場合**返します**が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#18;](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 呼び出す、`GetExtendedUI`コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスを持つかどうかを確認します。  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスに、拡張ユーザー インターフェイスがある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 拡張ユーザー インターフェイスは、次の方法で識別できます。  
  
-   静的コントロールをクリックしてコンボ ボックスの場合のみ、リスト ボックスを表示、 [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル。  
  
-   下方向キーを押すことには、(f4 キーは無効) ボックスの一覧ボックスが表示されます。  
  
 項目リストが表示される (矢印キーが無効になっています) ではない場合に、静的コントロールでのスクロールは無効になります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#19;](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 コンボ ボックスから、これによって、リスト ボックス、コンボ ボックスの部分を水平方向にスクロールすることができます (ピクセル単位) の幅を取得します。  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スクロールできる幅をピクセル単位で、コンボ ボックスの一覧ボックス部分です。  
  
### <a name="remarks"></a>コメント  
 これは、コンボ ボックスのリスト ボックス部分に水平スクロール バーがある場合にのみ適用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#20;](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 コンボ ボックス内の指定した項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します。  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 コンボ ボックスのリスト ボックス内の項目の&0; から始まるインデックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている 32 ビット値または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 32 ビット値を設定することができます、`dwItemData`のパラメーター、 [SetItemData](#setitemdata)メンバー関数の呼び出しです。 使用して、`GetItemDataPtr`を取得する 32 ビット値がポインターの場合、メンバー関数 ( **void\***)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&21;](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 ポインターとして指定されたコンボ ボックス アイテムに関連付けられたアプリケーションによって提供される 32 ビット値を取得 ( **void\***)。  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 コンボ ボックスのリスト ボックス内の項目の&0; から始まるインデックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生した場合は、ポインター、または –&1; を取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&22;](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 呼び出す、`GetItemHeight`コンボ ボックスのリスト項目の高さを取得します。  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 高さを取得するコンボ ボックスのコンポーネントを指定します。 場合、`nIndex`パラメーターは –&1;、コンボ ボックスのエディット コントロール (または静的テキスト) の部分の高さを取得します。 コンボ ボックスにある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md)スタイル、`nIndex`の高さを取得するリスト項目の&0; から始まるインデックスを指定します。 それ以外の場合、 `nIndex` 0 に設定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスで指定された項目のピクセル単位の高さ。 エラーが発生した場合は、戻り値は **CB_ERR** です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox 第&23;](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
 コンボ ボックスのリスト ボックスから文字列を取得します。  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 コピーされるリスト ボックスの文字列の&0; から始まるインデックスが含まれています。  
  
 `lpszText`  
 文字列を取得するには、バッファーへのポインター。 バッファーには、文字列と終端の null 文字のための十分な領域が必要です。  
  
 `rString`  
 参照、`CString`です。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を除いた文字列の長さをバイト単位で。 場合`nIndex`有効なインデックスが指定されていない戻り値は**返します**します。  
  
### <a name="remarks"></a>コメント  
 このメンバーの&2; 番目の形式の関数の塗りつぶし、`CString`項目のテキストを持つオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&24;](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 コンボ ボックスのリスト ボックスに、文字列の長さを取得します。  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスの文字列の&0; から始まるインデックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 (バイト)、終端の null 文字を除く文字列の長さ。 場合`nIndex`有効なインデックスが指定されていない戻り値は**返します**します。  
  
### <a name="example"></a>例  
  例を参照してください[CComboBox::GetLBText](#getlbtext)します。  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 コンボ ボックスによって使用されるロケールを取得します。  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックス内の文字列のロケール識別子 (LCID) 値。  
  
### <a name="remarks"></a>コメント  
 ロケールが使用、たとえば、並べ替え後のコンボ ボックス内の文字列の並べ替え順序を決定します。  
  
### <a name="example"></a>例  
  例を参照してください[CComboBox::SetLocale](#setlocale)します。  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 現在のコンボ ボックス コントロールのドロップダウン リストに表示される項目の最小数を取得します。  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のドロップ ダウン リストに表示される項目の最小数。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 コンボ ボックスの一覧ボックス部分に表示される最初の項目の&0; から始まるインデックスを取得します。  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コンボ ボックスの一覧ボックス部分に表示される最初の項目の&0; から始まるインデックス**返します**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 最初に、項目 0、リスト ボックスの上部にあるが場合は、リスト ボックスをスクロールすると、別のアイテムが先頭にある場合があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#25;](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 コンボ ボックスのリスト ボックス部分でリスト ボックス項目を格納するためには、メモリを割り当てます。  
  
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
 かどうかは成功すると、項目の最大数をそれ以外の場合、メモリを再割り当てが必要とせずに、リスト ボックス、コンボ ボックスの部分を格納できます**CB_ERRSPACE**、つまり、十分なメモリがあります。  
  
### <a name="remarks"></a>コメント  
 多くのアイテムをリスト ボックスの部分に追加する前にこの関数を呼び出して、`CComboBox`です。  
  
 Windows 95/98 のみ:`wParam`パラメーターは 16 ビット値に限定します。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数は制限されているが、リスト ボックス内の項目の合計サイズが使用可能なメモリによってのみ制限されます。  
  
 この関数は、多くのアイテム (100 個以上) を持つリスト ボックスの初期化を高速化を使用します。 特定の容量のための後続のメモリを事前に割り当てる[AddString](#addstring)、[は](#insertstring)、および[Dir](#dir)関数は、最短時間を受け取ります。 見積もりは、パラメーターを使用できます。 多くを指定した場合は、余分なメモリが割り当てられます。過小評価する場合は、通常の割り当ては事前に割り当てられた量を超える項目に対して使用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&26;](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 コンボ ボックスのリスト ボックスに文字列を挿入します。  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 文字列を受け取るリスト ボックス内の位置を示す&0; から始まるインデックスです。 このパラメーターが -1 の場合、文字列はリストの末尾に追加されます。  
  
 `lpszString`  
 挿入される null で終わる文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 文字列が挿入された位置の&0; から始まるインデックス。 エラーが発生した場合は、戻り値は **CB_ERR** です。 新しい文字列を保存する空き領域が不足している場合は、戻り値は **CB_ERRSPACE** です。  
  
### <a name="remarks"></a>コメント  
 異なり、 [AddString](#addstring)メンバー関数の場合、`InsertString`メンバー関数では、リストを伴いません、 [CBS_SORT](../../mfc/reference/combo-box-styles.md)並べ替えスタイルです。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&27;](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 ユーザーがコンボ ボックスのエディット コントロールに入力できるテキストの長さ (バイト単位) を制限します。  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxChars`  
 ユーザーが入力できるテキストのバイト単位で長さを指定します。 このパラメーターが 0 の場合、テキストの長さが 65,535 バイトに設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合&0; 以外の値。 コンボ ボックス スタイルを使用して呼び出された場合[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)編集コントロールを使用しないコンボ ボックスでは、戻り値はまたは**返します**します。  
  
### <a name="remarks"></a>コメント  
 コンボ ボックスは、スタイルを持たない場合[CBS_AUTOHSCROLL](../../mfc/reference/combo-box-styles.md)、エディット コントロールのサイズよりもさらに拡大するテキストの制限を設定する効果はありません。  
  
 `LimitText`ユーザーが入力できるテキストを制限するだけです。 影響が与えませんされたテキストで既にエディット コントロールで、メッセージを送信するとき、リスト ボックス内の文字列が選択されているときに、エディット コントロールにコピーするテキストの長さは影響します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&28;](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 オーナー描画スタイルを持つコンボ ボックスが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`コンボ ボックスの一覧の各次元の Windows のボックスに通知する構造体。 コンボ ボックスが作成された場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md)リスト ボックス内の各項目のスタイル、フレームワークと記述します。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
 使用して、 **CBS_OWNERDRAWFIXED**スタイルで作成されたオーナー描画コンボ ボックスで、 [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem)のメンバー関数`CWnd`さらにプログラミングの考慮事項が含まれます。 説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md)します。  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&29;](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 クリップボードから現在のカーソル位置にあるコンボ ボックスのエディット コントロールにデータを挿入します。  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>コメント  
 クリップボードのデータを含んでいる場合のみ、データが挿入される**エディット**形式です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&30;](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 すべての項目がリストからボックス、コンボ ボックスのコントロールの編集を削除します。  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&31;](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 コンボ ボックスのリスト ボックスに文字列を検索し、文字列が見つかった場合、リスト ボックスで、文字列を選択し、エディット コントロールにコピーします。  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartAfter`  
 検索する最初の項目の前に、の項目の&0; から始まるインデックスが含まれています。 検索では、リスト ボックスの下部に達すると、引き続き、リスト ボックスの上部にある戻るで指定した項目`nStartAfter`します。 、-1 の場合は、最初からリスト ボックス全体が検索されます。  
  
 `lpszString`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 文字列が見つかった場合は、選択した項目の&0; から始まるインデックス。 検索が正常に実行されなかった場合、戻り値は**返します**現在の選択は変更されません。  
  
### <a name="remarks"></a>コメント  
 文字列は、(始点) から、先頭の文字がプレフィックス文字列内の文字と一致する場合にのみが選択されます。  
  
 なお、`SelectString`と`FindString`メンバー関数は、文字列を検索が、`SelectString`メンバー関数も、文字列を選択します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#32;](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 コンボ ボックス コントロールに表示されるヒントのテキストを設定します。  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*lpszText*|ヒントのテキストを含む null で終わるバッファーへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は `true`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、キュー テキストが表示されます。  
  
 このメソッドは、送信、 [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_combobox`つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>例  
 次のコード例では、コンボ ボックス コントロールのキュー バナーを設定します。  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 コンボ ボックスのリスト ボックスに文字列を選択します。  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSelect`  
 選択する文字列の&0; から始まるインデックスを指定します。 –&1;、リスト ボックスの現在の選択項目が削除され、編集コントロールをクリアします。  
  
### <a name="return-value"></a>戻り値  
 メッセージが成功した場合に選択した項目の&0; から始まるインデックス。 戻り値は**返します**場合`nSelect`、リスト内の項目数よりも大きい場合、または`nSelect`の選択を解除する –&1; に設定されています。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、リスト ボックスは (リスト ボックスが表示されている場合)、ビューに、文字列をスクロールします。 コンボ ボックスのエディット コントロールのテキストを変更して、新しい選択を反映します。 リスト ボックスで前の選択内容が削除されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&33;](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 この関数では、コンボ ボックスのリスト ボックスのピクセル単位で設定できる最小幅を設定します。  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 ピクセル単位で、コンボ ボックスの一覧ボックス部分の許容される最小の幅。  
  
### <a name="return-value"></a>戻り値  
 成功すると、リストの新しい幅ボックスと、それ以外の場合**返します**します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md)または[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル。  
  
 既定では、ドロップダウン リスト ボックスの使用可能な最小の幅は 0 です。 コンボ ボックスのリスト ボックス部分が表示されるときに、幅が使用可能な幅の最小値またはコンボ ボックスの幅のうち、大きい方。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&34;](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 コンボ ボックスのエディット コントロール内の文字を選択します。  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartChar`  
 開始位置を指定します。 開始位置が-1 の場合、既存の選択項目が削除されます。  
  
 `nEndChar`  
 終了位置を指定します。 最後の終了位置が –&1; を開始位置からすべてのテキストを設定した場合は、エディット コントロール内の文字が選択されます。  
  
### <a name="return-value"></a>戻り値  
 メンバー関数が成功した場合は 0 以外。それ以外の場合 0 を返します。 **返します**場合`CComboBox`が、 [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル プロパティまたはリスト ボックスではありません。  
  
### <a name="remarks"></a>コメント  
 位置は、0 から始まる。 エディット コントロールの最初の文字を選択するには、0 の開始位置を指定します。 終了位置を選択する最後の文字の直後後の文字です。 たとえば、エディット コントロールの最初の 4 つの文字を選択する 0 の開始位置と終了位置に 4 を使用しては。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CComboBox::GetEditSel](#geteditsel)します。  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 呼び出す、`SetExtendedUI`メンバー関数を既定のユーザー インターフェイスまたはがコンボ ボックスの拡張ユーザー インターフェイスのいずれかを選択する、 [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md)または[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル。  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bExtended*  
 拡張ユーザー インターフェイスまたは既定のユーザー インターフェイスにコンボ ボックスを使用する必要があるかどうかを指定します。 値**TRUE**拡張を選択するユーザー インターフェイスは、値は**FALSE**標準のユーザー インターフェイスを選択します。  
  
### <a name="return-value"></a>戻り値  
 **正常**操作が成功した場合または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 拡張ユーザー インターフェイスは、次の方法で識別できます。  
  
-   静的コントロールをクリックしてコンボ ボックスの場合のみ、リスト ボックスを表示、 **CBS_DROPDOWNLIST**スタイル。  
  
-   下方向キーを押すことには、(f4 キーは無効) ボックスの一覧ボックスが表示されます。  
  
 項目リストが表示されていない場合では、スタティック コントロールのスクロールは無効になります (方向キーが無効になります)。  
  
### <a name="example"></a>例  
  例を参照してください[CComboBox::GetExtendedUI](#getextendedui)します。  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 これによって、リスト ボックス、コンボ ボックスの部分を水平方向にスクロールすることができます (ピクセル単位) の幅を設定します。  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *nExtent*  
 これによって、リスト ボックス、コンボ ボックスの部分を水平方向にスクロールすることができます (ピクセル) を指定します。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスの幅がこの値より小さい場合は、水平スクロール バーは水平方向に項目をリスト ボックス内をスクロールします。 水平スクロール バーを非表示に、リスト ボックスの幅がこの値以上の場合は、または、コンボ ボックスにある場合、 [CBS_DISABLENOSCROLL](../../mfc/reference/combo-box-styles.md)スタイル、無効になっています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#35;](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 コンボ ボックスで指定したアイテムに関連付けられている 32 ビット値を設定します。  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 設定する項目の&0; から始まるインデックスが含まれています。  
  
 `dwItemData`  
 項目に関連付ける新しい値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 使用して、`SetItemDataPtr`メンバー関数の場合は 32 ビット値がポインターであることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#36;](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 指定されたポインターであるコンボ ボックスで指定された項目に関連付けられている 32 ビット値の設定 ( **void\***)。  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の&0; から始まるインデックスが含まれています。  
  
 `pData`  
 項目に関連付けるへのポインターが含まれています。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このポインターは項目の追加または削除コンボ ボックス内のアイテムの相対位置を変更することがありますもコンボ ボックスの有効期間に有効です。 そのため、ボックス内の項目のインデックスを変更できますが、ポインターの信頼性を維持します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&37;](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 呼び出す、`SetItemHeight`コンボ ボックスまたはコンボ ボックスのエディット コントロール (または静的テキスト) の部分の高さにリスト項目の高さを設定するメンバー関数。  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト項目の高さまたはコンボ ボックスのエディット コントロール (または静的テキスト) の部分の高さが設定されているかどうかを指定します。  
  
 コンボ ボックスにある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md)スタイル、`nIndex`が高さが設定されている、それ以外の場合に、リスト項目の 0 から始まるインデックスを指定`nIndex`0 と項目が設定されているすべてのリストの高さにする必要があります。  
  
 場合`nIndex`-1 で、エディット コントロールの高さまたはコンボ ボックスの静的テキスト部分を設定します。  
  
 `cyItemHeight`  
 識別されるコンボ ボックス コンポーネントのピクセルで高さを指定`nIndex`します。  
  
### <a name="return-value"></a>戻り値  
 **返します**インデックスまたは高さが無効です。 それ以外の場合 0 の場合。  
  
### <a name="remarks"></a>コメント  
 コンボ ボックスのエディット コントロール (または静的テキスト) の部分の高さは、リスト項目の高さとは無関係に設定されます。 アプリケーションでは、エディット コントロール (または静的テキスト) の部分の高さが特定のリスト ボックスの項目の高さよりも小さいことを確認する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox #&38;](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 このコンボ ボックスのロケール識別子を設定します。  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLocale`  
 コンボ ボックスに設定する新しい値のロケール識別子 (LCID)。  
  
### <a name="return-value"></a>戻り値  
 このコンボ ボックスの以前のロケール識別子 (LCID) 値です。  
  
### <a name="remarks"></a>コメント  
 場合**SetLocale**既定値が呼び出されないシステムからロケールを取得します。 このシステム既定ロケールがコントロール パネルを使用することも可能地域 (または国際) アプリケーションです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox&#39;](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 現在のコンボ ボックスの一覧ボックス コントロールで表示される項目の最小数を設定します。  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iMinVisible`|表示される項目の最小数を指定します。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_combobox`つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>例  
 次のコード例では、コンボ ボックス コントロールのドロップダウン リストに 20 個のアイテムを挿入します。 ドロップダウン矢印を押した場合に、10 個の項目の最小値が表示されることを指定します。  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>CComboBox::SetTopIndex  
 により、特定の項目をコンボ ボックスの一覧ボックス部分に表示されるようにします。  
  
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
 [!code-cpp[NVC_MFC_CComboBox #&40;](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 表示またはがコンボ ボックスのリスト ボックスを非表示、 [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md)または[CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md)スタイル。  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowIt*  
 ドロップダウン リスト ボックスを表示するか非表示にするかどうかを指定します。 値**TRUE**リスト ボックスを表示します。 値**FALSE**リスト ボックスを非表示にします。  
  
### <a name="remarks"></a>コメント  
 既定では、このスタイルのコンボ ボックスは、リスト ボックスを表示します。  
  
 このメンバー関数も何も起こりませんで作成されたコンボ ボックスに、 [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md)スタイル。  
  
### <a name="example"></a>例  
  例を参照してください[CComboBox::GetDroppedState](#getdroppedstate)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

