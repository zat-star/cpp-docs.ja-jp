---
title: "CEdit クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEdit
dev_langs:
- C++
helpviewer_keywords:
- separators, in multiline edit controls
- text editors
- controls [MFC], edit
- text editors, CEdit class
- edit controls, classes
- multiline edit control
- CEdit class
- line separators in multiline edit controls
- edit controls
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: 22
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
ms.openlocfilehash: 9c782e77b1fdb9026ee030238413955ba4d537e9
ms.lasthandoff: 02/24/2017

---
# <a name="cedit-class"></a>CEdit Class
Windows のエディット コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|構築、`CEdit`コントロール オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|エディット コントロールの操作が完了できるかどうかを決定します。|  
|[場合](#charfrompos)|指定した位置に最も近い文字の行や文字のインデックスを取得します。|  
|[CEdit::Clear](#clear)|削除 (クリア) の編集の現在の選択 (存在する場合) を制御します。|  
|[CEdit::Copy](#copy)|現在の選択 (もしあれば) エディット コントロールでクリップボードにコピーで**エディット**形式です。|  
|[CEdit::Create](#create)|Windows のエディット コントロールを作成し、それをアタッチ、`CEdit`オブジェクトです。|  
|[CEdit::Cut](#cut)|(切り取り)、現在の選択項目 (存在する場合)、編集を制御し、削除されたテキストでクリップボードにコピー**エディット**形式です。|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|(クリア) 編集の取り消しのフラグのコントロールをリセットします。|  
|[CEdit::FmtLines](#fmtlines)|複数行のエディット コントロール内でオンまたはオフ ソフト改行文字を含めることを設定します。|  
|[CEdit::GetCueBanner](#getcuebanner)|ヒントのテキストとコントロールが空で、フォーカスがないときに、エディット コントロールでのヒントとして表示されるテキストを取得します。|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|エディット コントロールで表示されている最上位の行を決定します。|  
|[CEdit::GetHandle](#gethandle)|複数行のエディット コントロールに現在割り当てられているメモリを識別するハンドルを取得します。|  
|[CEdit::GetHighlight](#gethighlight)|開始日と終了の現在のエディット コントロールで強調表示されているテキストの範囲の文字のインデックスを取得します。|  
|[CEdit::GetLimitText](#getlimittext)|このテキストの最大量を取得する`CEdit`含めることができます。|  
|[CEdit::GetLine](#getline)|エディット コントロールから、行のテキストを取得します。|  
|[CEdit::GetLineCount](#getlinecount)|複数行のエディット コントロールで行の数を取得します。|  
|[CEdit::GetMargins](#getmargins)|このため、左右の余白を取得`CEdit`します。|  
|[CEdit::GetModify](#getmodify)|エディット コントロールの内容が変更されたかどうかを決定します。|  
|[CEdit::GetPasswordChar](#getpasswordchar)|テキストを入力したときに、エディット コントロールで表示されるパスワード文字を取得します。|  
|[CEdit::GetRect](#getrect)|エディット コントロールの書式設定の四角形を取得します。|  
|[CEdit::GetSel](#getsel)|エディット コントロールで現在の選択範囲の最初と最後の文字位置を取得します。|  
|[CEdit::HideBalloonTip](#hideballoontip)|現在のエディット コントロールに関連付けられているすべてのバルーン ヒントを非表示にします。|  
|[CEdit::LimitText](#limittext)|エディット コントロールに入力できるテキストの長さを制限します。|  
|[CEdit::LineFromChar](#linefromchar)|指定した文字のインデックスを含む行の行番号を取得します。|  
|[CEdit::LineIndex](#lineindex)|複数行のエディット コントロール内の行の文字インデックスを取得します。|  
|[CEdit::LineLength](#linelength)|エディット コントロールで行の長さを取得します。|  
|[CEdit::LineScroll](#linescroll)|複数行のエディット コントロールのテキストをスクロールします。|  
|[CEdit::Paste](#paste)|エディット コントロールの現在のカーソル位置にクリップボードからデータを挿入します。 クリップボードのデータを含んでいる場合のみ、データが挿入される**エディット**形式です。|  
|[CEdit::PosFromChar](#posfromchar)|指定した文字のインデックスの左上隅の座標を取得します。|  
|[CEdit::ReplaceSel](#replacesel)|エディット コントロールで現在の選択範囲を指定したテキストに置き換えます。|  
|[CEdit::SetCueBanner](#setcuebanner)|ヒントのテキストとコントロールが空で、フォーカスがないときに、エディット コントロールでのヒントとして表示されるテキストを設定します。|  
|[CEdit::SetHandle](#sethandle)|複数行のエディット コントロールで使用されるローカル メモリへのハンドルを設定します。|  
|[CEdit::SetHighlight](#sethighlight)|強調表示に現在表示されているテキストの範囲は、コントロールを編集します。|  
|[CEdit::SetLimitText](#setlimittext)|このテキストの最大量を設定する`CEdit`含めることができます。|  
|[CEdit::SetMargins](#setmargins)|左と右の余白を設定してこの`CEdit`します。|  
|[CEdit::SetModify](#setmodify)|設定または編集コントロールの変更フラグをクリアします。|  
|[CEdit::SetPasswordChar](#setpasswordchar)|設定またはテキストを入力したときに、エディット コントロールに表示するパスワード文字を削除します。|  
|[CEdit::SetReadOnly](#setreadonly)|エディット コントロールの読み取り専用の状態を設定します。|  
|[CEdit::SetRect](#setrect)|複数行のエディット コントロールの書式設定の四角形を設定し、コントロールを更新します。|  
|[CEdit::SetRectNP](#setrectnp)|コントロールのウィンドウを再描画せずには、複数行のエディット コントロールの書式設定の四角形を設定します。|  
|[CEdit::SetSel](#setsel)|エディット コントロールでは、文字の範囲を選択します。|  
|[CEdit::SetTabStops](#settabstops)|エディット コントロールを複数行にタブを設定します。|  
|[CEdit::ShowBalloonTip](#showballoontip)|現在のエディット コントロールに関連付けられているバルーン ヒントが表示されます。|  
|[CEdit::Undo](#undo)|最後のエディット コントロールの操作を反転させます。|  
  
## <a name="remarks"></a>コメント  
 エディット コントロールは、テキストを入力できる長方形の子ウィンドウです。  
  
 ダイアログ テンプレートから、またはコードで直接編集コントロールを作成できます。 どちらの場合も、コンス トラクターを呼び出す最初`CEdit`を構築する、`CEdit`オブジェクトを呼び出し、[作成](#create)、ウィンドウを作成するメンバー関数は、コントロールを編集し、添付、`CEdit`オブジェクトです。  
  
 構築から派生したクラスにワンステップ プロセス`CEdit`します。 呼び出しと派生クラスのコンス トラクターを記述**作成**からコンス トラクター内です。  
  
 `CEdit`重要な機能を継承`CWnd`します。 設定してからテキストを取得する、`CEdit`オブジェクトを使用、`CWnd`メンバー関数[SetWindowText](cwnd-class.md#setwindowtext)と[GetWindowText](cwnd-class.md#getwindowtext)、これを設定または複数行のコントロールの場合でも、エディット コントロールの内容全体を取得します。 複数行のコントロールのテキスト行数は、'\r\n' 文字のシーケンスで区切られます。 また、エディット コントロールが複数行の場合は、取得し、呼び出すことによって、コントロールのテキストの一部を設定、`CEdit`メンバー関数[GetLine](#getline)、 [SetSel](#setsel)、 [GetSel](#getsel)、および[ReplaceSel](#replacesel)します。  
  
 Windows のエディット コントロールからその親に送信された通知メッセージを処理する場合 (通常から派生したクラス`CDialog`)、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップ エントリは、次の形式をとります。  
  
 **On _**通知**(** *id、memberFxn***)**  
  
 ここで`id`、通知を送信するエディット コントロールの子ウィンドウの ID を指定し、`memberFxn`通知を処理する記述した親メンバー関数の名前を指定します。  
  
 親の関数のプロトタイプは次のとおりです。  
  
 **afx_msg** void memberFxn **();**  
  
 潜在的なメッセージ マップ エントリと親に送信されるケースの説明の一覧を次に示します。  
  
- **ON_EN_CHANGE**ユーザーがエディット コントロールでテキストが変更された可能性があるアクションを取得します。 異なり、 **EN_UPDATE**通知メッセージを Windows の表示が更新後にこの通知メッセージが送信されます。  
  
- **ON_EN_ERRSPACE**エディット コントロールは、特定の要求を満たすのに十分なメモリを割り当てることができません。  
  
- **ON_EN_HSCROLL**エディット コントロールの水平スクロール バーをクリックします。 親ウィンドウに、画面が更新される前に通知されます。  
  
- **ON_EN_KILLFOCUS**エディット コントロールが入力フォーカスを失った。  
  
- **ON_EN_MAXTEXT**エディット コントロールの文字の指定した数を超えましたの現在の挿入およびが切り捨てられました。 編集コントロールがあるないときにも送信、 **ES_AUTOHSCROLL**スタイルおよび挿入する文字数を超えるエディット コントロールの幅。 編集コントロールがあるないときにも送信、 **ES_AUTOVSCROLL**スタイルおよびテキストの挿入の結果行の合計数を超えるエディット コントロールの高さ。  
  
- **ON_EN_SETFOCUS**エディット コントロールが入力フォーカスを受け取るときに送信します。  
  
- **ON_EN_UPDATE**エディット コントロールが変更されたテキストを表示しようとしています。 コントロールがテキストを書式設定後、そのテキストを表示できるように、ウィンドウのサイズを変更できる、必要に応じて前に送信されます。  
  
- **ON_EN_VSCROLL**エディット コントロールの垂直スクロール バーをクリックします。 親ウィンドウに、画面が更新される前に通知されます。  
  
 作成する場合、 `CEdit`  ダイアログ ボックス内のオブジェクト、`CEdit`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CEdit`ダイアログ エディターを使用して、ダイアログ リソースからのオブジェクト、`CEdit`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CEdit`ウィンドウ内でオブジェクトを破棄しても必要があります。 作成する場合、`CEdit`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CEdit`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**をユーザーが、Windows を終了するときに破棄するオブジェクトにコントロールを編集します。 メモリを割り当てられない場合、`CEdit`オブジェクト、オーバーライド、`CEdit`デストラクターが、割り当てを破棄します。  
  
 エディット コントロールで特定のスタイルを変更する (よう**ES_READONLY**) を使用する代わりに、コントロールに特定のメッセージを送信する必要があります[は](cwnd-class.md#modifystyle)です。 参照してください[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `CEdit` の詳細については、次を参照してください。  
  
- [コントロール](../../mfc/controls-mfc.md)  
  
-   サポート技術情報記事 Q259949: 情報: SetCaretPos() が適切でない CEdit または CRichEditCtrl コントロール  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecanundoa--ceditcanundo"></a><a name="canundo"></a>CEdit::CanUndo  
 この関数では、最後の編集操作を元に戻すことができるかどうかを決定します。  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後の編集操作がへの呼び出しで取り消せる場合は 0 以外、**を元に戻す**メンバー関数は、元に戻すことができない場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::Undo](#undo)します。  
  
##  <a name="a-namecedita--ceditcedit"></a><a name="cedit"></a>CEdit::CEdit  
 `CEdit` オブジェクトを構築します。  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>コメント  
 使用[作成](#create)Windows のエディット コントロールを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#1;](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="a-namecharfromposa--ceditcharfrompos"></a><a name="charfrompos"></a>場合  
 これで、指定したポイントに最も近い文字の文字のインデックス&0; から始まる行を取得するには、この関数を呼び出す`CEdit`コントロール  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 これのクライアント領域内のポイントの座標`CEdit`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 低位の文字インデックス**WORD**、上位の行インデックス**WORD**します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#3;](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="a-namecleara--ceditclear"></a><a name="clear"></a>CEdit::Clear  
 削除する (オフ)、現在の選択 (もしあれば) エディット コントロールでは、この関数を呼び出します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 によって実行される削除**クリア**で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 を現在の選択項目を削除してから、削除した内容をクリップボードに配置する、[切り取り](#cut)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&4;](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="a-namecopya--ceditcopy"></a><a name="copy"></a>CEdit::Copy  
 この関数を呼び出してコピー selection (存在する場合) でクリップボードにエディット コントロールで**エディット**形式です。  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#5;](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="a-namecreatea--ceditcreate"></a><a name="create"></a>CEdit::Create  
 Windows のエディット コントロールを作成し、それをアタッチ、`CEdit`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 エディット コントロールのスタイルを指定します。 任意の組み合わせを適用[エディット スタイル](edit-styles.md)コントロールにします。  
  
 `rect`  
 エディット コントロールのサイズと位置を指定します。 `CRect`オブジェクトまたは`RECT`構造体。  
  
 `pParentWnd`  
 エディット コントロールの親ウィンドウを指定します (通常、 `CDialog`)。 ことはできません**NULL**します。  
  
 `nID`  
 エディット コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CEdit`&2; つのステップ内のオブジェクト。 まずを呼び出して、`CEdit`コンス トラクターと、呼び出し**作成**、Windows のエディット コントロールを作成およびそれにアタッチする、`CEdit`オブジェクトです。  
  
 **作成**実行されると、Windows の送信、 [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635)、 [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634)、 [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619)、および[WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626)エディット コントロールへのメッセージ。  
  
 既定では、これらのメッセージが処理される、 [OnNcCreate](cwnd-class.md#onnccreate)、 [OnNcCalcSize](cwnd-class.md#onnccalcsize)、 [OnCreate](cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo)メンバー関数、`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CEdit`メッセージ マップを新しいクラスに追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](window-styles.md)エディット コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ オーダーにエディット コントロールを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#2;](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="a-namecuta--ceditcut"></a><a name="cut"></a>CEdit::Cut  
 エディット コントロールで現在の選択 (該当する場合) (切り取り) を削除するには、この関数を呼び出すし、削除されたテキストでクリップボードにコピー**エディット**形式です。  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>コメント  
 によって実行される削除**切り取り**で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 を削除したテキストをクリップボードにかけることがなく、現在の選択を削除する、[クリア](#clear)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&6;](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="a-nameemptyundobuffera--ceditemptyundobuffer"></a><a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer  
 エディット コントロールの取り消しのフラグ (クリア) をリセットするには、この関数を呼び出します。  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>コメント  
 エディット コントロールようになりましたことはできません、最後の操作を取り消します。 エディット コントロール内の操作を完了できるときに元に戻すフラグが設定されています。  
  
 取り消しのフラグは、自動的にオフにするたびに、 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)または[SetHandle](#sethandle) `CWnd`メンバー関数が呼び出されます。  
  
 詳細については、次を参照してください。 [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#7;](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="a-namefmtlinesa--ceditfmtlines"></a><a name="fmtlines"></a>CEdit::FmtLines  
 複数行のエディット コントロール内でソフト改行文字を含めることをオンまたはオフに設定するには、この関数を呼び出します。  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAddEOL*  
 ソフト改行文字を挿入するかどうかを指定します。 値**TRUE** ; 文字を挿入します。 値の**FALSE**削除されます。  
  
### <a name="return-value"></a>戻り値  
 存在する場合、0 以外の値の書式設定が発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ソフト改行は、2 つの復帰と改行のワード ラップにより分割された行の末尾に挿入で構成されます。 ハード改行は、1 つの復帰と改行で構成されます。 ハード改行で終わる行に影響されない`FmtLines`します。  
  
 Windows は、場合にのみ応答、`CEdit`オブジェクトが複数行のエディット コントロールです。  
  
 `FmtLines`によって返されるバッファーにのみ影響[GetHandle](#gethandle)とによって返されるテキスト[WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627)します。 影響がないエディット コントロール内のテキストの表示にします。  
  
 詳細については、次を参照してください。 [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#8;](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="a-namegetcuebannera--ceditgetcuebanner"></a><a name="getcuebanner"></a>CEdit::GetCueBanner  
 ヒントのテキストとコントロールが空のときに、エディット コントロールでのヒントとして表示されるテキストを取得します。  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lpszText`  
 キュー テキストを含む文字列へのポインター。  
  
 [入力] `cchText`  
 受信可能な文字数。 この番号には、終端が含まれています。`NULL`文字です。  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードの`true`メソッドが成功した場合`false`します。  
  
 2 番目のオーバー ロードで、 [CString](../../atl-mfc-shared/using-cstring.md)キュー テキストを含む場合は、メソッドが成功した以外の場合、空の文字列 ("") です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。、 [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695)マクロです。  
  
##  <a name="a-namegetfirstvisiblelinea--ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine  
 この関数では、エディット コントロールで表示されている最上位の行を決定します。  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最上位に表示されている行の&0; から始まるインデックス。 単一行のエディット コントロールでは、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#9;](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="a-namegethandlea--ceditgethandle"></a><a name="gethandle"></a>CEdit::GetHandle  
 複数行のエディット コントロールに現在割り当てられているメモリを識別するハンドルを取得するには、この関数を呼び出します。  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 エディット コントロールの内容を保持するバッファーを識別するためのローカル メモリ ハンドルです。 単一行のエディット コントロールに、メッセージの送信などのエラーが発生した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 ハンドルはローカル メモリ ハンドルでありのいずれかで使用できます、**ローカル**ローカル メモリを取得する Windows メモリ関数をパラメーターとして処理します。  
  
 **GetHandle**複数行のエディット コントロールでのみ処理します。  
  
 呼び出す**GetHandle**  ダイアログ ボックスで作成された場合にのみ、ダイアログ ボックスに複数行のエディット コントロールの**DS_LOCALEDIT**スタイルのフラグを設定します。 場合、 **DS_LOCALEDIT**スタイルが設定されていない、0 以外の戻り値が表示されますが、返される値を使用することはできません。  
  
> [!NOTE]
> **GetHandle** Windows 95/98 では動作しません。 呼び出した場合**GetHandle** Windows 95/98 では返します**NULL**します。 **GetHandle**は、Windows NT version 3.51 以降で説明されているように動作します。  
  
 詳細については、次を参照してください。 [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#10;](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="a-namegethighlighta--ceditgethighlight"></a><a name="gethighlight"></a>CEdit::GetHighlight  
 現在のエディット コントロールで強調表示されているテキストの範囲内の最初と最後の文字のインデックスを取得します。  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pichStart`|強調表示されているテキストの範囲の最初の文字の&0; から始まるインデックス。|  
|[出力] `pichEnd`|強調表示されているテキストの範囲の最後の文字の&0; から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetlimittexta--ceditgetlimittext"></a><a name="getlimittext"></a>CEdit::GetLimitText  
 このテキストの制限値を取得するには、このメンバー関数を呼び出す`CEdit`オブジェクトです。  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のテキストの制限 (バイト単位) この`CEdit`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 テキストの制限とは、エディット コントロールが受け入れることのできるバイト数に変換されたテキストの最大サイズです。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#11;](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="a-namegetlinea--ceditgetline"></a><a name="getline"></a>CEdit::GetLine  
 エディット コントロールから、行のテキストを取得するには、この関数を呼び出すしに格納`lpszBuffer`します。  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 エディット コントロールの複数行から取得する行番号を指定します。 行番号が 0 から始まります。値 0 は、最初の行を指定します。 このパラメーターは、単一行のエディット コントロールで無視されます。  
  
 `lpszBuffer`  
 行のコピーを受け取るバッファーへのポインター。 バッファーの最初の単語には、文字バッファーにコピーすることの最大数を指定する必要があります。  
  
 `nMaxLength`  
 バッファーにコピーできるバイトの最大数を指定します。 `GetLine`最初の単語でこの値を配置`lpszBuffer`Windows への呼び出しを行う前にします。  
  
### <a name="return-value"></a>戻り値  
 実際にコピーされたバイト数。 行番号が指定された場合、戻り値は 0`nIndex`エディット コントロール内の行の数よりも大きいです。  
  
### <a name="remarks"></a>コメント  
 コピーした行では、null 終端文字は含まれません。  
  
 詳細については、次を参照してください。 [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::GetLineCount](#getlinecount)します。  
  
##  <a name="a-namegetlinecounta--ceditgetlinecount"></a><a name="getlinecount"></a>CEdit::GetLineCount  
 複数行のエディット コントロール内の行の番号を取得するには、この関数を呼び出します。  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 複数行の行の数を含む整数では、コントロールを編集します。 エディット コントロールにテキストが入力されていない場合、戻り値は 1 です。  
  
### <a name="remarks"></a>コメント  
 `GetLineCount`複数行のエディット コントロールでのみ処理されます。  
  
 詳細については、次を参照してください。 [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#12;](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="a-namegetmarginsa--ceditgetmargins"></a><a name="getmargins"></a>CEdit::GetMargins  
 この編集コントロールの左と右の余白を取得するには、このメンバー関数を呼び出します。  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>戻り値  
 低位の左余白の幅**WORD**高位の右余白の幅と**WORD**します。  
  
### <a name="remarks"></a>コメント  
 余白はピクセル単位で測定されます。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。  
  
##  <a name="a-namegetmodifya--ceditgetmodify"></a><a name="getmodify"></a>CEdit::GetModify  
 この関数では、エディット コントロールの内容が変更されているかどうかを判断します。  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>戻り値  
 エディット コントロールの内容が変更された場合は 0 以外。0 のままである場合は変更されません。  
  
### <a name="remarks"></a>コメント  
 Windows では、エディット コントロールの内容が変更されたかどうかを示す内部フラグを保持します。 エディット コントロールを最初に作成しを呼び出してもクリアが、このフラグがクリアされて、 [SetModify](#setmodify)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#13;](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="a-namegetpasswordchara--ceditgetpasswordchar"></a><a name="getpasswordchar"></a>CEdit::GetPasswordChar  
 この関数では、テキストを入力したときに、エディット コントロールで表示されるパスワード文字を取得します。  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが入力した文字の代わりに表示する文字を指定します。 戻り値は`NULL`パスワード文字が存在しない場合。  
  
### <a name="remarks"></a>コメント  
 編集コントロールを作成する場合、 **ES_PASSWORD**スタイル コントロールをサポートする DLL は、既定のパスワードの文字を決定します。 マニフェストまたは[InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697)メソッドでは、DLL のサポートのどれかを判断エディット コントロールです。 User32.dll には、エディット コントロールがサポートしている、既定のパスワードの文字はアスタリスク ('* '、U +002)。 Comctl32.dll のバージョン 6 では、エディット コントロールをサポートする場合は、黒の丸 ('●' で、U + 25CF) は既定の文字です。 詳細については、DLL とバージョンがサポートするコモン コントロールを参照してください[シェルと共通のコントロール バージョン](http://msdn.microsoft.com/library/windows/desktop/bb776779)です。  
  
 このメソッドは、送信、 [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#14;](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="a-namegetrecta--ceditgetrect"></a><a name="getrect"></a>CEdit::GetRect  
 エディット コントロールの書式設定の四角形を取得するには、この関数を呼び出します。  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`RECT`書式の四角形を受け取る構造体。  
  
### <a name="remarks"></a>コメント  
 書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの外接する四角形です。  
  
 によって複数行のエディット コントロールの書式設定の四角形を変更できる、 [SetRect](#setrect)と[角形](#setrectnp)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::LimitText](#limittext)します。  
  
##  <a name="a-namegetsela--ceditgetsel"></a><a name="getsel"></a>CEdit::GetSel  
 開始日と終了の戻り値またはパラメーターを使用して、エディット コントロールの現在の選択 (存在する場合) の文字位置を取得するには、この関数を呼び出します。  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartChar`  
 現在の選択範囲の最初の文字の位置を受け取る整数への参照。  
  
 `nEndChar`  
 現在の選択範囲の末尾を超える最初の選択されていない文字の位置にお届けする整数への参照。  
  
### <a name="return-value"></a>戻り値  
 バージョンを返す、`DWORD`上位ワードに選択範囲の終了後に下位ワード内の開始位置と最初に選択されていない文字の位置を表す値を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#15;](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="a-namehideballoontipa--cedithideballoontip"></a><a name="hideballoontip"></a>CEdit::HideBalloonTip  
 現在のエディット コントロールに関連付けられているすべてのバルーン ヒントを非表示にします。  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namelimittexta--ceditlimittext"></a><a name="limittext"></a>CEdit::LimitText  
 ユーザーは、エディット コントロールに入力されるテキストの長さを制限するには、この関数を呼び出します。  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChars`  
 ユーザーが入力できるテキストのバイト単位で長さを指定します。 このパラメーターが 0 の場合は、テキストの長さに設定されている**UINT_MAX**バイトです。 これが既定の動作です。  
  
### <a name="remarks"></a>コメント  
 テキストの制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 影響が与えませんされたテキストで既にエディット コントロールでも、エディット コントロールにコピーするテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)のメンバー関数内`CWnd`します。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストを削除します。 ただし、テキストの制限は、ユーザーが新しいテキストに、既存のテキストを置換できないようにを現在の選択項目を削除しない限りは、テキストの制限内に収まるようにテキストを発生します。  
  
> [!NOTE]
>  Win32 では (Windows NT および Windows 95/98) [SetLimitText](#setlimittext)この関数に置き換えられます。  
  
 詳細については、次を参照してください。 [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&17;](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="a-namelinefromchara--ceditlinefromchar"></a><a name="linefromchar"></a>CEdit::LineFromChar  
 指定した文字のインデックスを含む行の行番号を取得するには、この関数を呼び出します。  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 エディット コントロールのテキストで、目的の文字の&0; から始まるインデックス値であるか、–&1; が含まれています。 場合`nIndex`-1 で、現在の行では、キャレットを含む行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定された文字のインデックスを含む行の&0; から始まる行番号`nIndex`です。 場合`nIndex`-1 で、選択範囲の最初の文字を含む行の数が返されます。 選択されていない場合は、現在の行番号が返されます。  
  
### <a name="remarks"></a>コメント  
 文字インデックスでは、エディット コントロールの先頭からの文字数です。  
  
 このメンバー関数は、複数行のエディット コントロールでのみ使用します。  
  
 詳細については、次を参照してください。 [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#18;](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="a-namelineindexa--ceditlineindex"></a><a name="lineindex"></a>CEdit::LineIndex  
 複数行のエディット コントロール内の行の文字のインデックスを取得するには、この関数を呼び出します。  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nLine`  
 エディット コントロールのテキストで目的の行のインデックス値であるか、–&1; が含まれています。 場合`nLine`-1 で、現在の行では、キャレットを含む行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した行の文字インデックス`nLine`指定した行番号がエディット コントロールで行の数より大きい場合は-1 を返します。  
  
### <a name="remarks"></a>コメント  
 文字インデックスでは、エディット コントロールの先頭から指定した行に、文字数です。  
  
 このメンバー関数は、複数行のエディット コントロールでのみ処理します。  
  
 詳細については、次を参照してください。 [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#19;](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="a-namelinelengtha--ceditlinelength"></a><a name="linelength"></a>CEdit::LineLength  
 エディット コントロールで行の長さを取得します。  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nLine`  
 長さを取得する行の文字の&0; から始まるインデックス。 既定値は -1 です。  
  
### <a name="return-value"></a>戻り値  
 単一行のエディット コントロールで、戻り値は、長さ`TCHAR`s、エディット コントロール内のテキスト。  
  
 複数行のエディット コントロールで、戻り値は、長さ`TCHAR`で指定された行の s、`nLine`パラメーター。 [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]テキスト、長さは行のバイト数の場合 Unicode テキスト、長さは行の文字の数。 長さには、行の最後にキャリッジ リターン文字は含まれません。  
  
 場合、`nLine`パラメーターは、コントロール内の文字数よりも多い、戻り値は&0; です。  
  
 場合、`nLine`パラメーターは –&1;、戻り値が選択されていない文字を選択した文字を含む行の数。 たとえば、次の行の末尾からの 8 番目の文字を 1 行の 4 番目の文字から選択範囲の場合、戻り値は 10 です。 つまり、3 つの文字が、最初の行で、次の&7; つです。  
  
 詳細については、`TCHAR`入力を参照してください、`TCHAR`テーブルの行に[Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751)します。  
  
### <a name="remarks"></a>コメント  
 このメソッドはサポート、 [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::LineIndex](#lineindex)します。  
  
##  <a name="a-namelinescrolla--ceditlinescroll"></a><a name="linescroll"></a>CEdit::LineScroll  
 複数行のエディット コントロールのテキストをスクロールするには、この関数を呼び出します。  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLines`  
 垂直方向にスクロールする行数を指定します。  
  
 `nChars`  
 水平方向にスクロールする文字位置の数を指定します。 エディット コントロールにいずれかがある場合、この値は無視されます、 **ES_RIGHT**または**ES_CENTER**スタイル。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、複数行のエディット コントロールでのみ処理されます。  
  
 エディット コントロールは、過去のエディット コントロールでテキストの最後の行は垂直方向にスクロールされません。 現在の行で指定された行の数を加えた場合`nLines`エディット コントロールで行の合計数を超える場合、エディット コントロールの最後の行は、エディット コントロール ウィンドウの上部までスクロールできるように、値を調整します。  
  
 `LineScroll`過去の任意の行の最後の文字、水平方向にスクロールするために使用します。  
  
 詳細については、次を参照してください。 [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::GetFirstVisibleLine](#getfirstvisibleline)します。  
  
##  <a name="a-namepastea--ceditpaste"></a><a name="paste"></a>CEdit::Paste  
 クリップボードからデータを挿入するには、この関数を呼び出して、`CEdit`カーソルの位置にします。  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>コメント  
 クリップボードのデータを含んでいる場合のみ、データが挿入される**エディット**形式です。  
  
 詳細については、次を参照してください。 [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#20;](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="a-nameposfromchara--ceditposfromchar"></a><a name="posfromchar"></a>CEdit::PosFromChar  
 この特定の文字の位置 (左上隅) を取得するには、この関数を呼び出す`CEdit`オブジェクトです。  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 指定した文字の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された文字の左上隅の座標`nChar`します。  
  
### <a name="remarks"></a>コメント  
 文字を指定するには、0 から始まるインデックス値を提供します。 場合`nChar`この最後の文字のインデックスよりも大きい`CEdit`オブジェクトの戻り値は、この最後の文字の直後の文字位置の座標を指定`CEdit`オブジェクトです。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::LineFromChar](#linefromchar)します。  
  
##  <a name="a-namereplacesela--ceditreplacesel"></a><a name="replacesel"></a>CEdit::ReplaceSel  
 エディット コントロールの現在の選択で指定されたテキストに置き換えるには、この関数を呼び出す`lpszNewText`します。  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewText`  
 置換テキストを含む null で終わる文字列へのポインター。  
  
 `bCanUndo`  
 この関数が完了できることを指定するには、このパラメーターの値を設定**TRUE**します。 既定値は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 エディット コントロールでテキストの一部だけを置換します。 すべてのテキストを置換する場合は、使用、[とき](cwnd-class.md#setwindowtext)メンバー関数。  
  
 現在の選択項目がない場合は、置換テキストは、現在のカーソル位置に挿入されます。  
  
 詳細については、次を参照してください。 [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::LineIndex](#lineindex)します。  
  
##  <a name="a-namesetcuebannera--ceditsetcuebanner"></a><a name="setcuebanner"></a>CEdit::SetCueBanner  
 ヒントのテキストとして表示されるか、ヒントは、エディット コントロールとコントロールが空のテキストを設定します。  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszText`  
 エディット コントロールに表示されるヒントを含む文字列へのポインター。  
  
 [入力] `fDrawWhenFocused`  
 場合`false`ユーザーは、エディット コントロールでクリックするし、により、コントロールのフォーカス キュー バナーは描画されません。  
  
 場合`true`コントロールにフォーカスがある場合でも、キュー バナーを描画します。 キュー バナーには、ユーザーがコントロールに入力を開始すると表示されなくなります。  
  
 既定値は `false` です。  
  
### <a name="return-value"></a>戻り値  
 `true`メソッドが成功した場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。、 [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703)マクロです。  
  
### <a name="example"></a>例  
 次の例は、 [CEdit::SetCueBanner](#setcuebanner)メソッドです。  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="a-namesethandlea--ceditsethandle"></a><a name="sethandle"></a>CEdit::SetHandle  
 複数行のエディット コントロールで使用されるローカル メモリにハンドルを設定するには、この関数を呼び出します。  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>パラメーター  
 *hBuffer*  
 ローカル メモリへのハンドルが含まれています。 このハンドルを前回呼び出したときに作成する必要があります、 [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows 関数を使用して、**あらかじめ**フラグ。 メモリは、null で終わる文字列を格納すると見なされます。 そうでない場合、割り当てられたメモリの最初のバイトが 0 に設定する必要があります。  
  
### <a name="remarks"></a>コメント  
 エディット コントロール自体のバッファーを割り当てる代わりに現在表示されているテキストを格納するのにバッファーが使用されます。  
  
 このメンバー関数は、複数行のエディット コントロールでのみ処理されます。  
  
 使用するアプリケーションが新しいメモリ ハンドルを設定する前に、 [GetHandle](#gethandle)現在のメモリ バッファーへのハンドルを取得し、空きメモリを使用してそのメンバー関数を**LocalFree** Windows の機能です。  
  
 `SetHandle`元に戻すバッファーをクリア (、 [CanUndo](#canundo)メンバー関数は、0 を返します)、および内部変更フラグ (、[この](#getmodify)メンバー関数は、0 を返します)。 エディット コントロールのウィンドウが再描画されます。  
  
 ダイアログ ボックスを作成した場合にのみ、ダイアログ ボックスで複数行のエディット コントロールでは、このメンバー関数を使用することができます、 **DS_LOCALEDIT**スタイルのフラグを設定します。  
  
> [!NOTE]
> **GetHandle** Windows 95/98 では動作しません。 呼び出した場合**GetHandle** Windows 95/98 では返します**NULL**します。 **GetHandle**は、Windows NT version 3.51 以降で説明されているように動作します。  
  
 詳細については、次を参照してください。 [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641)、 [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723)、および[LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit #&22;](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="a-namesethighlighta--ceditsethighlight"></a><a name="sethighlight"></a>CEdit::SetHighlight  
 強調表示に現在表示されているテキストの範囲は、コントロールを編集します。  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `ichStart`|強調表示するテキスト範囲の最初の文字の&0; から始まるインデックス。|  
|[入力] `ichEnd`|強調表示するテキスト範囲の最後の文字の&0; から始まるインデックス。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetlimittexta--ceditsetlimittext"></a><a name="setlimittext"></a>CEdit::SetLimitText  
 このテキストの制限を設定するには、このメンバー関数を呼び出す`CEdit`オブジェクトです。  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMax`  
 新しいテキスト制限文字数。  
  
### <a name="remarks"></a>コメント  
 テキストの制限とは、エディット コントロールが受け入れることのできる文字に変換されたテキストの最大サイズです。  
  
 テキストの制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 影響が与えませんされたテキストで既にエディット コントロールでも、エディット コントロールにコピーするテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)のメンバー関数内`CWnd`します。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストを削除します。 ただし、テキストの制限は、ユーザーが新しいテキストに、既存のテキストを置換できないようにを現在の選択項目を削除しない限りは、テキストの制限内に収まるようにテキストを発生します。  
  
 この関数は[LimitText](#limittext) win32 します。  
  
 詳細については、次を参照してください。 [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。  
  
##  <a name="a-namesetmarginsa--ceditsetmargins"></a><a name="setmargins"></a>CEdit::SetMargins  
 この編集コントロールの左と右の余白を設定するには、このメソッドを呼び出します。  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>パラメーター  
 *nLeft*  
 ピクセル単位では、新しい左余白の幅。  
  
 *nRight*  
 ピクセル単位では、新しい右余白の幅。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。  
  
##  <a name="a-namesetmodifya--ceditsetmodify"></a><a name="setmodify"></a>CEdit::SetModify  
 設定または編集コントロールの変更フラグをオフにするには、この関数を呼び出します。  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bModified`  
 値**TRUE**テキストが変更されたことを示す、値を**FALSE**修正されていないことを示します。 既定では、変更のフラグを設定します。  
  
### <a name="remarks"></a>コメント  
 変更のフラグは、エディット コントロール内のテキストが変更されたかどうかを示します。 ユーザーがテキストを変更するたびに自動的に設定されます。 取得できるはその値、[この](#getmodify)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::GetModify](#getmodify)します。  
  
##  <a name="a-namesetpasswordchara--ceditsetpasswordchar"></a><a name="setpasswordchar"></a>CEdit::SetPasswordChar  
 設定またはユーザーがテキストを入力すると、エディット コントロールに表示されるパスワード文字を削除するには、この関数を呼び出します。  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>パラメーター  
 *ch*  
 ユーザーが入力文字の代わりに表示する文字を指定します。 場合*ch*が 0 の場合、ユーザーによって入力された実際の文字が表示されます。  
  
### <a name="remarks"></a>コメント  
 パスワード文字を設定すると、ユーザーの種類の各文字の文字が表示されます。  
  
 このメンバー関数は、エディット コントロールの複数行に影響を与えません。  
  
 ときに、`SetPasswordChar`メンバー関数が呼び出されると、`CEdit`文字の表示で指定された文字を使用して再描画*ch*します。  
  
 エディット コントロールが作成された場合、 [ES_PASSWORD](edit-styles.md)スタイル、既定のパスワードの文字はアスタリスクに設定されて ( ** \* **)。 このスタイルは`SetPasswordChar`で呼び出された*ch*を 0 に設定します。  
  
 詳細については、次を参照してください。 [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#16;](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="a-namesetreadonlya--ceditsetreadonly"></a><a name="setreadonly"></a>CEdit::SetReadOnly  
 エディット コントロールの読み取り専用の状態を設定するには、この関数を呼び出します。  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bReadOnly`  
 設定またはエディット コントロールの読み取り専用の状態を削除するかどうかを指定します。 値**TRUE**状態を設定読み取り専用にする以外の値の**FALSE**を読み取り/書き込みの状態を設定します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、操作が成功すると、または 0 のエラーが発生した場合。  
  
### <a name="remarks"></a>コメント  
 現在の設定は、テストで発見できる、 [ES_READONLY](edit-styles.md)の戻り値のフラグ[状態](cwnd-class.md#getstyle)します。  
  
 詳細については、次を参照してください。 [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit 第&23;](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="a-namesetrecta--ceditsetrect"></a><a name="setrect"></a>CEdit::SetRect  
 この関数では、指定された座標を使用して四角形の寸法を設定します。  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`RECT`構造または`CRect`新しい書式設定の四角形の寸法を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバーは、複数行のエディット コントロールでのみ処理されます。  
  
 使用`SetRect`複数行の四角形は、書式を設定するコントロールを編集します。 書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの外接する四角形です。 エディット コントロールが作成されると、書式設定の四角形の値は、編集コントロール ウィンドウのクライアント領域と同じです。 使用して、`SetRect`メンバー関数をアプリケーションと、書式設定の四角形エディット コントロールのウィンドウよりも大きくします。  
  
 エディット コントロールには、スクロール バーがなければ、テキストが切り取られるでラップされていない書式の四角形が大きすぎてウィンドウに行われた場合です。 エディット コントロールの枠線の場合は、書式設定の四角形が境界線のサイズが減少します。 返す四角形を調整する場合は、`GetRect`メンバー関数の場合に四角形を渡す前に、境界線のサイズを削除する必要があります`SetRect`します。  
  
 `SetRect`が呼び出されたエディット コントロールのテキストも再フォーマットし、再表示されます。  
  
 詳細については、次を参照してください。 [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit #&24;](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="a-namesetrectnpa--ceditsetrectnp"></a><a name="setrectnp"></a>CEdit::SetRectNP  
 この関数では、複数行のエディット コントロールの書式設定の四角形を設定します。  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`RECT`構造または`CRect`新しい四角形の寸法を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの外接する四角形です。  
  
 `SetRectNP`同じですが、`SetRect`のメンバー関数が、エディット コントロールのウィンドウが再描画されません。  
  
 エディット コントロールが作成されると、書式設定の四角形の値は、編集コントロール ウィンドウのクライアント領域と同じです。 呼び出して、`SetRectNP`メンバー関数をアプリケーションと、書式設定の四角形エディット コントロールのウィンドウよりも大きくします。  
  
 エディット コントロールには、スクロール バーがなければ、テキストが切り取られるでラップされていない書式の四角形が大きすぎてウィンドウに行われた場合です。  
  
 このメンバーは、複数行のエディット コントロールでのみ処理されます。  
  
 詳細については、次を参照してください。 [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::SetRect](#setrect)します。  
  
##  <a name="a-namesetsela--ceditsetsel"></a><a name="setsel"></a>CEdit::SetSel  
 この関数では、エディット コントロールでの文字の範囲を選択します。  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwSelection*  
 下位ワード内の開始位置と上位の単語の終了位置を指定します。 下位ワードが 0 で、上位ワードが – 1 の場合は、エディット コントロール内のすべてのテキストが選択されます。 下位ワードが-1 の場合は、現在の選択項目が削除されます。  
  
 *bNoScroll*  
 キャレットをスクロールして表示するかどうかを示します。 場合**FALSE**キャレットをスクロールして表示します。 場合**TRUE**キャレットがスクロールして表示できません。  
  
 `nStartChar`  
 開始位置を指定します。 場合`nStartChar`は 0 と`nEndChar`-1 で、エディット コントロールでテキストが選択されているすべてです。 場合`nStartChar`-1 で、現在の選択項目を削除します。  
  
 `nEndChar`  
 終了位置を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEdit::GetSel](#getsel)します。  
  
##  <a name="a-namesettabstopsa--ceditsettabstops"></a><a name="settabstops"></a>CEdit::SetTabStops  
 この関数では、複数行のエディット コントロールにタブ ストップを設定します。  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>パラメーター  
 `cxEachStop`  
 タブ ストップに設定することを指定すべて`cxEachStop`ダイアログ単位です。  
  
 `nTabStops`  
 含まれているタブ ストップの数を指定`rgTabStops`します。 この番号は、1 より大きくなければなりません。  
  
 `rgTabStops`  
 ダイアログ単位で、タブを指定する符号なし整数の配列へのポインターを停止します。 ダイアログ単位は、水平または垂直距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅の単位の 4 分の 1 と 1 の垂直方向ダイアログ単位は、現在のダイアログ ベースの高さの単位の 8 分の 1 に等しい。 ダイアログの基本単位は、高さ、および現在のシステム フォントの幅に基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します。  
  
### <a name="return-value"></a>戻り値  
 タブが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 複数行のエディット コントロールにテキストをコピーすると、テキスト内の任意のタブ文字を次のタブ ストップまで生成する領域が発生します。  
  
 タブ ストップを 32 ダイアログ単位の既定のサイズに設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブ ストップを 32 以外のサイズを設定するとバージョンを呼び出す、`cxEachStop`パラメーター。 サイズの配列には、タブ ストップを設定するには、2 つのパラメーターを使用してバージョンを使用します。  
  
 このメンバー関数は、複数行のエディット コントロールでのみ処理します。  
  
 `SetTabStops`自動的に再描画されない編集ウィンドウです。 テキスト編集コントロールのタブ ストップを変更する場合に呼び出す[エディット](cwnd-class.md#invalidaterect)編集ウィンドウが再描画します。  
  
 詳細については、次を参照してください。 [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663)と[GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CEditView::SetTabStops](ceditview-class.md#settabstops)します。  
  
##  <a name="a-nameshowballoontipa--ceditshowballoontip"></a><a name="showballoontip"></a>CEdit::ShowBalloonTip  
 現在のエディット コントロールに関連付けられているバルーン ヒントが表示されます。  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pEditBalloonTip`|ポインター、 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466)バルーン ヒントを記述する構造体。|  
|[入力] `lpszTitle`|バルーン ヒントのタイトルを含む Unicode 文字列へのポインター。|  
|[入力] `lpszText`|バルーン ヒントのテキストを含む Unicode 文字列へのポインター。|  
|[入力] `ttiIcon`|`INT`バルーン ヒントに関連付けるアイコンの種類を指定します。 既定値は `TTI_NONE` です。 詳細については、次を参照してください。、`ttiIcon`のメンバー、 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466)構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。、 [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707)マクロです。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_cedit`つまり、現在のエディット コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>例  
 次のコード例では、エディット コントロールのバルーン ヒントが表示されます。 [CEdit::ShowBalloonTip](#showballoontip)メソッドは、タイトルとバルーンのヒント テキストを指定します。  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="a-nameundoa--ceditundo"></a><a name="undo"></a>CEdit::Undo  
 最後のエディット コントロールの操作を元に戻すには、この関数を呼び出します。  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>戻り値  
 単一行のエディット コントロールでは、戻り値は&0; 以外の値では常にします。 複数行のエディット コントロールの場合、戻り値が元に戻す操作が成功した場合、0 以外の値は元に戻す操作が失敗した場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 元に戻す操作が元に戻すことができますもあります。 たとえば、最初の呼び出し、削除した文字列を復元する**を元に戻す**します。 2 番目の呼び出しを使用してテキストを削除するには中間の編集操作がない限り、**を元に戻す**します。  
  
 詳細については、次を参照してください。 [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit&#25;](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](cwnd-class.md)   
 [CButton クラス](cbutton-class.md)   
 [CComboBox クラス](ccombobox-class.md)   
 [CListBox クラス](clistbox-class.md)   
 [CScrollBar クラス](cscrollbar-class.md)   
 [CStatic クラス](cstatic-class.md)   
 [CDialog クラス](cdialog-class.md)

