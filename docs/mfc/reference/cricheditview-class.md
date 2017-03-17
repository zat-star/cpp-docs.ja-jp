---
title: "CRichEditView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- rich edit controls, OLE container
- CRichEditView class
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
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
ms.openlocfilehash: 9f54ec0c8aae58828607b01973a263e458c30ddb
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditview-class"></a>CRichEditView クラス
[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)と[関数](../../mfc/reference/cricheditcntritem-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキスト内でのリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|`CRichEditView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|現在の選択範囲に重ならないようにダイアログ ボックスに移動します。|  
|[CRichEditView::CanPaste](#canpaste)|リッチ エディット ビューに貼り付けることができるデータがクリップボードに含まれるかどうかを指示します。|  
|[CRichEditView::DoPaste](#dopaste)|OLE アイテムをリッチ エディット ビューに貼り付けます。|  
|[CRichEditView::FindText](#findtext)|待機カーソルを呼び出して、指定したテキストを検索します。|  
|[CRichEditView::FindTextSimple](#findtextsimple)|指定したテキストを検索します。|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|現在の選択項目の属性を書式設定文字を取得します。|  
|[CRichEditView::GetDocument](#getdocument)|関連するへのポインターを取得[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)します。|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|リッチ エディット ビューでの現在の実行中である OLE アイテムを取得します。|  
|[CRichEditView::GetMargins](#getmargins)|リッチ エディット ビューの余白を取得します。|  
|[CRichEditView::GetPageRect](#getpagerect)|リッチ エディット ビューのページの四角形を取得します。|  
|[CRichEditView::GetPaperSize](#getpapersize)|リッチ エディット ビューの用紙サイズを取得します。|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|段落の現在の選択の属性を取得します。|  
|[CRichEditView::GetPrintRect](#getprintrect)|リッチ エディット ビューの印刷の四角形を取得します。|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|リッチ エディット ビューの印刷の幅を取得します。|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|リッチ エディット コントロールを取得します。|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|リッチ エディット ビューから選択した項目を取得します。|  
|[CRichEditView::GetTextLength](#gettextlength)|リッチ エディット ビュー内のテキストの長さを取得します。|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|文字またはリッチ エディット ビュー内のバイトの数を取得します。 長さを決定する方法の拡張フラグの一覧です。|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|OLE アイテムとして、ファイルを挿入します。|  
|[CRichEditView::InsertItem](#insertitem)|OLE アイテムとして、新しい項目を挿入します。|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|リッチ エディットまたはテキスト形式のデータがクリップボードに含まれるかどうかを指示します。|  
|[CRichEditView::OnCharEffect](#onchareffect)|現在の選択範囲の書式設定文字を切り替えます。|  
|[CRichEditView::OnParaAlign](#onparaalign)|段落の配置を変更します。|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|パブリック メンバー関数の文字コマンド UI を更新します。|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|段落のパブリック メンバー関数用のコマンドの UI を更新します。|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|指定した四角形内の指定したテキストの書式を設定します。|  
|[CRichEditView::PrintPage](#printpage)|指定したページ内で指定したテキストの書式を設定します。|  
|[CRichEditView::SetCharFormat](#setcharformat)|現在の選択項目の属性を書式設定文字を設定します。|  
|[CRichEditView::SetMargins](#setmargins)|このリッチ マージンを設定では、ビューを編集します。|  
|[CRichEditView::SetPaperSize](#setpapersize)|リッチ エディット ビューの用紙サイズを設定します。|  
|[CRichEditView::SetParaFormat](#setparaformat)|段落の現在の選択の属性を設定します。|  
|[CRichEditView::TextNotFound](#textnotfound)|コントロールの内部の search の状態をリセットします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|リッチ エディット ビューの範囲でクリップボード オブジェクトを取得します。|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|ダウン右マウス ボタンを使用するコンテキスト メニューを取得します。|  
|[CRichEditView::IsSelected](#isselected)|指定した OLE アイテムが選択されているかを示します。|  
|[CRichEditView::OnFindNext](#onfindnext)|部分文字列の次の出現箇所を検索します。|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|ドキュメントにアタッチする場合は、最初のビューを更新します。|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|OLE アイテムからネイティブのデータを取得します。|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|印刷の特性を特定のデバイスに設定します。|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|新しい文字列に指定された文字列のすべての出現を置換します。|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|現在の選択項目を置き換えます。|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|要求されたテキストが見つからなかったことを示すユーザー通知を処理します。|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|データの参照のクエリ、`IDataObject`です。|  
|[CRichEditView::WrapChanged](#wrapchanged)|このリッチの値に基づいたビューを編集する対象の出力デバイス調整を行う`m_nWordWrap`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|箇条書きのインデント幅の量を示します。|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|ワード ラップを規制を示します。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ウィンドウで、ユーザーは入力し、テキストの編集です。 テキストは、文字および段落の書式設定に割り当てることができるし、OLE 埋め込みオブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーが使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView`テキストとテキストの書式設定特性を保持します。 `CRichEditDoc`ビューに含まれる OLE クライアント アイテムの一覧を保持します。 `CRichEditCntrItem`コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用できます。  
  
 リッチ エディット ビューを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>CRichEditView::AdjustDialogPosition  
 現在の選択項目が見えにくくならないように、指定されたダイアログ ボックスを移動するには、この関数を呼び出します。  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDlg*  
 ポインター、`CDialog`オブジェクトです。  
  
##  <a name="canpaste"></a>CRichEditView::CanPaste  
 この関数では、クリップボードにリッチ エディット ビューに貼り付けることができる情報が含まれるかどうかを判断します。  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リッチ エディット ビューで受け入れられる形式でデータがクリップボードに含まれている場合は 0 以外。それ以外の場合、0 を返します。  
  
##  <a name="cricheditview"></a>CRichEditView::CRichEditView  
 作成するには、この関数を呼び出して、`CRichEditView`オブジェクトです。  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>CRichEditView::DoPaste  
 OLE アイテムを貼り付けるには、この関数を呼び出す`dataobj`リッチ ドキュメント/ビューの編集にします。  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>パラメーター  
 `dataobj`  
 [COleDataObject](../../mfc/reference/coledataobject-class.md)を貼り付けるデータを格納します。  
  
 `cf`  
 目的のクリップボード形式です。  
  
 `hMetaPict`  
 貼り付ける項目を表すメタファイルです。  
  
### <a name="remarks"></a>コメント  
 フレームワークが既定の実装の一部としてこの関数を呼び出す[QueryAcceptData](#queryacceptdata)します。  
  
 この関数は、貼り付け のハンドラーの結果に基づく貼り付けの種類を決定します。 場合`cf`が 0 の場合、新しい項目が現在のアイコン表現を使用します。 場合`cf`は&0; 以外と`hMetaPict`は**NULL**、新しい項目を使用して`hMetaPict`形式のです。  
  
##  <a name="findtext"></a>CRichEditView::FindText  
 指定したテキストを検索し、現在の選択のように設定するには、この関数を呼び出します。  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索する文字列が含まれています。  
  
 `bCase`  
 検索では、大文字小文字を区別かどうかを示します。  
  
 `bWord`  
 検索する単語のみ、単語の一部ではないかどうかを示します。  
  
 `bNext`  
 検索の方向を示します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`lpszFind`テキストが見つかった場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は、検索操作中に待機カーソルを表示します。  
  
### <a name="example"></a>例  
 [!code-cpp[最適な NVC_MFCDocView](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>CRichEditView::FindTextSimple  
 指定したテキストを検索し、現在の選択のように設定するには、この関数を呼び出します。  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索する文字列が含まれています。  
  
 `bCase`  
 検索では、大文字小文字を区別かどうかを示します。  
  
 `bWord`  
 検索する単語のみ、単語の一部ではないかどうかを示します。  
  
 `bNext`  
 検索の方向を示します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`lpszFind`テキストが見つかった場合は 0 です。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection  
 この関数では、現在の選択範囲の書式属性の文字を取得します。  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>戻り値  
 A [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)文字書式の現在の選択項目の属性を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、 [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026)メッセージおよび[CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>CRichEditView::GetClipboardData  
 フレームワークの処理の一環としてこの関数が呼び出さ[IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315)します。  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpchrg`  
 ポインター、[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)の文字 (および OLE アイテム) で指定されたデータ オブジェクトにコピーする範囲を指定する構造体`lplpdataobj`します。  
  
 `dwReco`  
 クリップボードの操作フラグです。 これらの値のいずれかを指定できます。  
  
- **RECO_COPY**をクリップボードにコピーします。  
  
- **RECO_CUT**切り取ってクリップボードにします。  
  
- **RECO_DRAG**操作 (ドラッグ アンド ドロップ) をドラッグします。  
  
- **RECO_DROP**ドロップ操作 (ドラッグ アンド ドロップ) です。  
  
- **RECO_PASTE**クリップボードから貼り付けします。  
  
 `lpRichDataObj`  
 ポインター、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)リッチからクリップボード データを含むオブジェクトを編集できるコントロール ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341))。  
  
 `lplpdataobj`  
 アドレスを受け取るポインター変数へのポインター、`IDataObject`で指定された範囲を表すオブジェクトを`lpchrg`パラメーター。 値`lplpdataobj`エラーが返される場合は無視されます。  
  
### <a name="return-value"></a>戻り値  
 `HRESULT`値の操作の成功を報告します。 詳細については`HRESULT`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 戻り値が成功すると、示されている場合**IRichEditOleCallback::GetClipboardData**を返します、`IDataObject`によってアクセス`lplpdataobj`。 そうしないと、使用した&1; つを返します`lpRichDataObj`します。 クリップボード データを提供するには、この関数をオーバーライドします。 この関数の既定の実装**E_NOTIMPL**します。  
  
 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)、 [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315)、および[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]を参照してくださいと[IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)で、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
##  <a name="getcontextmenu"></a>CRichEditView::GetContextMenu  
 フレームワークの処理の一環としてこの関数が呼び出さ[IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317)します。  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>パラメーター  
 *seltyp*  
 選択の種類。 選択型の値は、「解説」セクションで説明します。  
  
 `lpoleobj`  
 ポインター、 **ole オブジェクト**選択範囲には、1 つまたは複数の OLE アイテムが含まれている場合は、最初に選択した OLE オブジェクトを指定する構造体。 選択範囲に、項目が含まれていない場合`lpoleobj`は**NULL**します。 **Ole オブジェクト**構造が OLE オブジェクト v テーブルへのポインターを保持します。  
  
 `lpchrg`  
 ポインター、[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)現在の選択項目を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 コンテキスト メニューへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 この関数は、処理の速度の右マウス ボタンの標準的な部分です。  
  
 選択の種類は、次のフラグの任意の組み合わせになります。  
  
- `SEL_EMPTY`現在選択されていないことを示します。  
  
- `SEL_TEXT`現在の選択項目にテキストが含まれていることを示します。  
  
- `SEL_OBJECT`現在の選択範囲に少なくとも&1; つの OLE アイテムが含まれていることを示します。  
  
- `SEL_MULTICHAR`現在の選択項目にはテキストの&1; つ以上の文字が含まれていることを示します。  
  
- `SEL_MULTIOBJECT`現在の選択範囲に&1; つ以上のオブジェクトが含まれていることを示します。  
  
 既定の実装**NULL**します。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317)と[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、 **ole オブジェクト**入力で、OLE データ構造体と構造体の割り当てに関する記事を参照してください、 *OLE サポート技術情報*します。  
  
##  <a name="getdocument"></a>CRichEditView::GetDocument  
 ポインターを取得するには、この関数を呼び出して、`CRichEditDoc`このビューに関連付けられています。  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)オブジェクトに関連付けられている、`CRichEditView`オブジェクトです。  
  
##  <a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem  
 この場所に項目を OLE を取得するには、この関数の呼び出しが現在アクティブ`CRichEditView`オブジェクトです。  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ、インプレース アクティブへのポインター[関数](../../mfc/reference/cricheditcntritem-class.md)リッチ エディット ビュー; 内のオブジェクト**NULL**がない場合 OLE アイテム現在インプレース アクティブな状態にします。  
  
##  <a name="getmargins"></a>CRichEditView::GetMargins  
 この関数では、印刷に使用される現在のマージンを取得します。  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>戻り値  
 単位は、印刷に使用される余白`MM_TWIPS`します。  
  
##  <a name="getpagerect"></a>CRichEditView::GetPageRect  
 この関数では、印刷で使用されるページの寸法を取得します。  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 単位は、印刷で使用されるページの境界`MM_TWIPS`します。  
  
### <a name="remarks"></a>コメント  
 この値は、用紙サイズに基づきます。  
  
##  <a name="getpapersize"></a>CRichEditView::GetPaperSize  
 現在の用紙サイズを取得するには、この関数を呼び出します。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷で使用する用紙のサイズの単位で`MM_TWIPS`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&153;](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection  
 段落の現在の選択の属性を取得するには、この関数を呼び出します。  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>戻り値  
 A [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)段落の現在の選択の属性を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182)メッセージと[PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getprintrect"></a>CRichEditView::GetPrintRect  
 この関数では、ページの四角形内の印刷領域の境界を取得します。  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 単位は、印刷に使用されるイメージの領域の境界`MM_TWIPS`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&154;](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>CRichEditView::GetPrintWidth  
 印刷領域の幅を決定するには、この関数を呼び出します。  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷領域の幅を単位で`MM_TWIPS`します。  
  
##  <a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl  
 取得するには、この関数を呼び出して、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)オブジェクトに関連付けられている、`CRichEditView`オブジェクトです。  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CRichEditCtrl`このビューのオブジェクト。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="getselecteditem"></a>CRichEditView::GetSelectedItem  
 OLE アイテムを取得するには、この関数を呼び出します (、`CRichEditCntrItem`オブジェクト) で現在選択されている`CRichEditView`オブジェクトです。  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、[関数](../../mfc/reference/cricheditcntritem-class.md)で選択したオブジェクト、`CRichEditView`オブジェクトです。**NULL**このビューで項目が選択されていない場合。  
  
##  <a name="gettextlength"></a>CRichEditView::GetTextLength  
 このテキストの長さを取得するには、この関数を呼び出す`CRichEditView`オブジェクトです。  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このテキストの長さ`CRichEditView`オブジェクトです。  
  
##  <a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx  
 このテキストの長さを計算するには、このメンバー関数を呼び出す`CRichEditView`オブジェクトです。  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 テキストの長さを決定する際に使用する方法を指定する値。 このメンバーは、いずれかを指定できますまたは以上の値のフラグのメンバーに示されている[GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915)で説明されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `uCodePage`  
 変換 (Unicode の 1200 の ANSI コード ページの CP_ACP) のコード ページです。  
  
### <a name="return-value"></a>戻り値  
 文字またはエディット コントロールでのバイト数。 互換性のないフラグが設定されている場合`dwFlags`、このメンバー関数が返す`E_INVALIDARG`します。  
  
### <a name="remarks"></a>コメント  
 `GetTextLengthEx`別のテキストの長さを決定する方法を提供します。 リッチ エディット 2.0 の機能がサポートしています。 詳細については、次を参照してください。[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject  
 指定したファイルを挿入するには、この関数を呼び出します (として、[関数](../../mfc/reference/cricheditcntritem-class.md)オブジェクト) にリッチなビューを編集します。  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 挿入するファイルの名前を含む文字列です。  
  
##  <a name="insertitem"></a>CRichEditView::InsertItem  
 挿入するには、この関数を呼び出して、[関数](../../mfc/reference/cricheditcntritem-class.md)リッチ エディット ビューへのオブジェクト。  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 挿入する項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `HRESULT`挿入の成功を示す値。  
  
### <a name="remarks"></a>コメント  
 詳細については`HRESULT`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="isricheditformat"></a>CRichEditView::IsRichEditFormat  
 この関数かどうかを`cf`テキスト、リッチ テキストまたはリッチ テキストが OLE アイテムをクリップボードの形式は、です。  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 目的のクリップボードの形式です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`cf`リッチ テキストの編集またはクリップボードの形式です。  
  
##  <a name="isselected"></a>CRichEditView::IsSelected  
 指定された OLE アイテムがこのビューで現在選択されているかどうかを判断するには、この関数を呼び出します。  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocItem`  
 ビュー内のオブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが選択されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 派生ビュー クラスに OLE アイテムの選択範囲を処理するための別の方法がある場合は、この関数をオーバーライドします。  
  
##  <a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent  
 リスト内の項目のインデント既定では、720 単位、1/2 インチであります。  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap  
 リッチ エディット ビューのワード ラップの種類を示します。  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>コメント  
 次のいずれかの値です。  
  
- `WrapNone`自動のワード ラップがないことを示します。  
  
- `WrapToWindow`テキストの折り返し、ウィンドウの幅に基づくことを示します。  
  
- `WrapToTargetDevice`ターゲット デバイスの特性に基づき、ワード ラップを示します。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::WrapChanged](#wrapchanged)します。  
  
##  <a name="onchareffect"></a>CRichEditView::OnCharEffect  
 文字書式の現在の選択の効果を切り替えるには、この関数を呼び出します。  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMask`  
 現在の選択を変更する効果を書式設定文字です。  
  
 `dwEffect`  
 文字書式の効果を切り替えるの目的のリスト。  
  
### <a name="remarks"></a>コメント  
 この関数に対する各呼び出しは、現在の選択に対して指定した書式設定の効果を切り替えます。  
  
 詳細については、`dwMask`と`dwEffect`パラメーターとその潜在的な値の対応するデータ メンバーを参照してください。 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&155;](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>CRichEditView::OnFindNext  
 検索と置換 ダイアログ ボックスからコマンドを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索する文字列。  
  
 `bNext`  
 検索する方向: **TRUE**を示します。**FALSE**, up.  
  
 `bCase`  
 検索では、大文字と小文字を区別するかどうかを示します。  
  
 `bWord`  
 検索を専用か単語全体が一致するかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 内のテキストを検索するには、この関数を呼び出して、`CRichEditView`です。 派生ビュー クラスの検索の特性を変更するには、この関数をオーバーライドします。  
  
##  <a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate  
 ドキュメントにビューを最初にアタッチ後、ビューが最初に表示される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)ヒント情報のないメンバー関数 (つまり、0 に設定する既定値を使用して、`lHint`パラメーターと**NULL**の`pHint`パラメーター)。 ドキュメントに関する情報を必要とする&1; 回限りの初期化を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションに固定サイズのドキュメントがある場合は、ドキュメントのサイズに基づくビューのスクロールの上限を初期化するためにこの関数を使用できます。 アプリケーションでは、可変サイズのドキュメントをサポートする場合に使用して`OnUpdate`スクロールを更新するたびに、ドキュメントにより変更制限します。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::m_nWordWrap](#m_nwordwrap)します。  
  
##  <a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject  
 この関数を使用して、埋め込みアイテムからネイティブ データを読み込みます。  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpStg*  
 ポインター、 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合、0 です。  
  
### <a name="remarks"></a>コメント  
 通常、このタスクは実行を作成して、[関数](../../mfc/reference/colestreamfile-class.md)の周囲、`IStorage`です。 `COleStreamFile`アーカイブに関連付けることが、[指定](../../mfc/reference/cobject-class.md#serialize)データを読み込むために呼び出されます。  
  
 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onparaalign"></a>CRichEditView::OnParaAlign  
 選択した段落の段落の配置を変更するには、この関数を呼び出します。  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 `wAlign`  
 目的の段落の配置。 次のいずれかの値です。  
  
- `PFA_LEFT`左の余白を使用して段落を整列します。  
  
- `PFA_RIGHT`右の余白を使用して段落を整列します。  
  
- `PFA_CENTER`余白を除いた段落を中央揃えです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&156;](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>CRichEditView::OnPrinterChanged  
 プリンターが変更されたときに、リッチ エディット ビューの特性を変更するには、この関数をオーバーライドします。  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>パラメーター  
 `dcPrinter`  
 A [CDC](../../mfc/reference/cdc-class.md)新しいプリンターのオブジェクト。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、物理的な高さと幅出力デバイス (プリンター) 用に、用紙サイズを設定します。 ある場合は、デバイス コンテキスト関連付けられていない`dcPrinter`既定の実装では、用紙サイズを 8.5 で 11 インチに設定します。  
  
##  <a name="onreplaceall"></a>CRichEditView::OnReplaceAll  
 置換 ダイアログ ボックスからすべて置換 コマンドを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 置換するテキストです。  
  
 `lpszReplace`  
 置換する文字列。  
  
 `bCase`  
 検索では、大文字小文字を区別かどうかを示します。  
  
 `bWord`  
 検索に単語全体を選択する必要がありますかかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 別の文字列をすべて指定された文字列に置き換えるには、この関数を呼び出します。 このビューの検索の特性を変更するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="onreplacesel"></a>CRichEditView::OnReplaceSel  
 [置換] ダイアログ ボックス [置換] コマンドを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 置換するテキストです。  
  
 `bNext`  
 検索の方向を示します: **TRUE** 。**FALSE**, up.  
  
 `bCase`  
 検索では、大文字小文字を区別かどうかを示します。  
  
 `bWord`  
 検索に単語全体を選択する必要がありますかかどうかを示します。  
  
 `lpszReplace`  
 置換する文字列。  
  
### <a name="remarks"></a>コメント  
 この関数では、1 つの指定された文字列を別の文字列に置き換えます。 このビューの検索の特性を変更するには、この関数をオーバーライドします。  
  
##  <a name="ontextnotfound"></a>CRichEditView::OnTextNotFound  
 検索が失敗したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 テキストが見つかりませんでした。  
  
### <a name="remarks"></a>コメント  
 出力の通知を変更するには、この関数をオーバーライドして、 [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356)します。  
  
 詳細については、次を参照してください。 [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&157;](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect  
 フレームワークでは、文字効果コマンドのコマンドの UI を更新するには、この関数を呼び出します。  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトです。  
  
 `dwMask`  
 マスクを書式設定文字を示します。  
  
 `dwEffect`  
 文字書式の効果を示します。  
  
### <a name="remarks"></a>コメント  
 マスク`dwMask`書式属性を確認する文字を指定します。 フラグ`dwEffect`文字書式設定/クリアに属性を一覧表示します。  
  
 詳細については、`dwMask`と`dwEffect`パラメーターとその潜在的な値の対応するデータ メンバーを参照してください。 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&158;](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign  
 フレームワークでは、段落効果コマンドのコマンド UI を更新するには、この関数を呼び出します。  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトです。  
  
 `wAlign`  
 段落の配置を確認します。 次のいずれかの値です。  
  
- `PFA_LEFT`左の余白を使用して段落を整列します。  
  
- `PFA_RIGHT`右の余白を使用して段落を整列します。  
  
- `PFA_CENTER`余白を除いた段落を中央揃えです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&159;](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>CRichEditView::PrintInsideRect  
 この関数の範囲に収まるように、リッチ エディット コントロール内のテキストの書式設定*rectLayout*で指定されたデバイスの`pDC`です。  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 出力領域のデバイス コンテキストへのポインター。  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md)または[CRect](../../atl-mfc-shared/reference/crect-class.md)出力領域を定義します。  
  
 `nIndexStart`  
 書式設定する最初の文字の&0; から始まるインデックス。  
  
 `nIndexStop`  
 書式設定する最後の文字の&0; から始まるインデックス。  
  
 *bOutput*  
 テキストを表示するかどうかを示します。 場合**FALSE**テキストが計測されるだけです。  
  
### <a name="return-value"></a>戻り値  
 1 を加えた、出力領域に収まるよう最後の文字のインデックス。  
  
### <a name="remarks"></a>コメント  
 通常、この呼び出しはへの呼び出しによって、その後[CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)出力を生成します。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::GetPaperSize](#getpapersize)します。  
  
##  <a name="printpage"></a>CRichEditView::PrintPage  
 指定された出力デバイスのリッチ エディット コントロール内のテキストの範囲の書式を設定するには、この関数を呼び出す`pDC`します。  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ページ出力のデバイス コンテキストへのポインター。  
  
 `nIndexStart`  
 書式設定する最初の文字の&0; から始まるインデックス。  
  
 `nIndexStop`  
 書式設定する最後の文字の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 1 を加えた、ページに配置できる最後の文字のインデックス。  
  
### <a name="remarks"></a>コメント  
 各ページのレイアウトはによって制御されます[GetPageRect](#getpagerect)と[GetPrintRect](#getprintrect)します。 通常、この呼び出しはへの呼び出しによって、その後[CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)出力を生成します。  
  
 余白は、論理ページではなく、物理ページに注意してください。 このため、多くのプリンターがあるページの一部に印刷できないために、0 の余白はテキストをクリップ多くの場合。 テキストを避けるためを呼び出す必要があります[SetMargins](#setmargins)し、印刷する前に適切なマージンを設定します。  
  
##  <a name="queryacceptdata"></a>CRichEditView::QueryAcceptData  
 リッチ エディットにオブジェクトを貼り付けるために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpdataobj*  
 ポインター、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)を照会します。  
  
 *lpcfFormat*  
 許容可能なデータ形式へのポインター。  
  
 `dwReco`  
 使用しません。  
  
 *bReally*  
 貼り付け操作を続行させるかかどうかを示します。  
  
 `hMetaFile`  
 項目のアイコンを描画するために使われるメタファイルへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `HRESULT`値の操作の成功を報告します。  
  
### <a name="remarks"></a>コメント  
 COM のアイテム、ドキュメントの派生クラスでの別の構成を処理するには、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
 詳細については`HRESULT`と`IDataObject`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)と[IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)をそれぞれに、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&160;](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>CRichEditView::SetCharFormat  
 これで新しいテキストの属性を書式設定文字を設定するには、この関数を呼び出す`CRichEditView`オブジェクトです。  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)新しい既定の文字書式属性を含む構造体。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`cf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230)メッセージと[CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>CRichEditView::SetMargins  
 リッチ エディット ビューの印刷の余白を設定するには、この関数を呼び出します。  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectMargin*  
 単位は、印刷の余白の新しい値`MM_TWIPS`です。  
  
### <a name="remarks"></a>コメント  
 場合[m_nWordWrap](#m_nwordwrap)は`WrapToTargetDevice`、呼び出す必要があります[WrapChanged](#wrapchanged)この関数を使用して、印刷の特性を調整した後です。  
  
 余白設定を使ってメモ[PrintPage](#printpage)は論理ページではなく、物理ページに対する相対パスです。 このため、多くのプリンターがあるページの一部に印刷できないために、0 の余白はテキストをクリップ多くの場合。 テキストを回避するのには、使用するを呼び出す必要があります`SetMargins`を印刷する前に適切なプリンターのマージンを設定します。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::GetPaperSize](#getpapersize)します。  
  
##  <a name="setpapersize"></a>CRichEditView::SetPaperSize  
 リッチ エディット ビューを印刷する用紙サイズを設定するには、この関数を呼び出します。  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizePaper*  
 単位は、印刷の用紙サイズの新しい値`MM_TWIPS`です。  
  
### <a name="remarks"></a>コメント  
 場合[m_nWordWrap](#m_nwordwrap)は`WrapToTargetDevice`、呼び出す必要があります[WrapChanged](#wrapchanged)この関数を使用して、印刷の特性を調整した後です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&161;](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditView::SetParaFormat  
 段落の現在の選択の属性を設定するには、この関数を呼び出す`CRichEditView`オブジェクトです。  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>パラメーター  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)新しい既定の段落書式属性です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`pf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。 [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276)メッセージと[PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&162;](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>CRichEditView::TextNotFound  
 内部的な検索状態をリセットするには、この関数を呼び出して、 [CRichEditView](../../mfc/reference/cricheditview-class.md)に呼び出しが失敗した後の制御[FindText](#findtext)します。  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 見つからなかったテキスト文字列が含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出しの失敗した直後に呼び出すことをお勧め[FindText](#findtext)コントロールの内部の search の状態を適切にリセットできるようにします。  
  
 `lpszFind`パラメーターに指定された文字列と同じ内容を含める必要があります[FindText](#findtext)します。 このメソッドを呼び出す内部検索状態をリセットした後、[見つからなかったとき](#ontextnotfound)メソッドを指定した検索文字列を使用します。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="wrapchanged"></a>CRichEditView::WrapChanged  
 印刷の特性が変化したときに、この関数を呼び出します ( [SetMargins](#setmargins)または[SetPaperSize](#setpapersize))。  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>コメント  
 豊富なビューを編集する方法を変更するには、この関数は、の変化に対応するオーバーライド[m_nWordWrap](#m_nwordwrap)または印刷の特性 ( [OnPrinterChanged](#onprinterchanged))。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&163;](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [関数のクラス](../../mfc/reference/cricheditcntritem-class.md)

