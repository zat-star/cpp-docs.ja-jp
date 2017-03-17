---
title: "CRichEditCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCtrl
- AFXCMN/CRichEditCtrl
- AFXCMN/CRichEditCtrl::CRichEditCtrl
- AFXCMN/CRichEditCtrl::CanPaste
- AFXCMN/CRichEditCtrl::CanRedo
- AFXCMN/CRichEditCtrl::CanUndo
- AFXCMN/CRichEditCtrl::CharFromPos
- AFXCMN/CRichEditCtrl::Clear
- AFXCMN/CRichEditCtrl::Copy
- AFXCMN/CRichEditCtrl::Create
- AFXCMN/CRichEditCtrl::CreateEx
- AFXCMN/CRichEditCtrl::Cut
- AFXCMN/CRichEditCtrl::DisplayBand
- AFXCMN/CRichEditCtrl::EmptyUndoBuffer
- AFXCMN/CRichEditCtrl::FindText
- AFXCMN/CRichEditCtrl::FindWordBreak
- AFXCMN/CRichEditCtrl::FormatRange
- AFXCMN/CRichEditCtrl::GetCharPos
- AFXCMN/CRichEditCtrl::GetDefaultCharFormat
- AFXCMN/CRichEditCtrl::GetEventMask
- AFXCMN/CRichEditCtrl::GetFirstVisibleLine
- AFXCMN/CRichEditCtrl::GetIRichEditOle
- AFXCMN/CRichEditCtrl::GetLimitText
- AFXCMN/CRichEditCtrl::GetLine
- AFXCMN/CRichEditCtrl::GetLineCount
- AFXCMN/CRichEditCtrl::GetModify
- AFXCMN/CRichEditCtrl::GetOptions
- AFXCMN/CRichEditCtrl::GetParaFormat
- AFXCMN/CRichEditCtrl::GetPunctuation
- AFXCMN/CRichEditCtrl::GetRect
- AFXCMN/CRichEditCtrl::GetRedoName
- AFXCMN/CRichEditCtrl::GetSel
- AFXCMN/CRichEditCtrl::GetSelectionCharFormat
- AFXCMN/CRichEditCtrl::GetSelectionType
- AFXCMN/CRichEditCtrl::GetSelText
- AFXCMN/CRichEditCtrl::GetTextLength
- AFXCMN/CRichEditCtrl::GetTextLengthEx
- AFXCMN/CRichEditCtrl::GetTextMode
- AFXCMN/CRichEditCtrl::GetTextRange
- AFXCMN/CRichEditCtrl::GetUndoName
- AFXCMN/CRichEditCtrl::GetWordWrapMode
- AFXCMN/CRichEditCtrl::HideSelection
- AFXCMN/CRichEditCtrl::LimitText
- AFXCMN/CRichEditCtrl::LineFromChar
- AFXCMN/CRichEditCtrl::LineIndex
- AFXCMN/CRichEditCtrl::LineLength
- AFXCMN/CRichEditCtrl::LineScroll
- AFXCMN/CRichEditCtrl::Paste
- AFXCMN/CRichEditCtrl::PasteSpecial
- AFXCMN/CRichEditCtrl::PosFromChar
- AFXCMN/CRichEditCtrl::Redo
- AFXCMN/CRichEditCtrl::ReplaceSel
- AFXCMN/CRichEditCtrl::RequestResize
- AFXCMN/CRichEditCtrl::SetAutoURLDetect
- AFXCMN/CRichEditCtrl::SetBackgroundColor
- AFXCMN/CRichEditCtrl::SetDefaultCharFormat
- AFXCMN/CRichEditCtrl::SetEventMask
- AFXCMN/CRichEditCtrl::SetModify
- AFXCMN/CRichEditCtrl::SetOLECallback
- AFXCMN/CRichEditCtrl::SetOptions
- AFXCMN/CRichEditCtrl::SetParaFormat
- AFXCMN/CRichEditCtrl::SetPunctuation
- AFXCMN/CRichEditCtrl::SetReadOnly
- AFXCMN/CRichEditCtrl::SetRect
- AFXCMN/CRichEditCtrl::SetSel
- AFXCMN/CRichEditCtrl::SetSelectionCharFormat
- AFXCMN/CRichEditCtrl::SetTargetDevice
- AFXCMN/CRichEditCtrl::SetTextMode
- AFXCMN/CRichEditCtrl::SetUndoLimit
- AFXCMN/CRichEditCtrl::SetWordCharFormat
- AFXCMN/CRichEditCtrl::SetWordWrapMode
- AFXCMN/CRichEditCtrl::StopGroupTyping
- AFXCMN/CRichEditCtrl::StreamIn
- AFXCMN/CRichEditCtrl::StreamOut
- AFXCMN/CRichEditCtrl::Undo
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class, common controls
- CRichEditCtrl class
- formatted text [C++]
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
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
ms.openlocfilehash: 77b8dfb6011831f4e4300096a127f70b26bcc603
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditctrl-class"></a>CRichEditCtrl クラス
リッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|`CRichEditCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|リッチ エディット コントロールに、クリップボードの内容が貼り付けられるかどうかを判断します。|  
|[CRichEditCtrl::CanRedo](#canredo)|コントロールの再実行キュー内のすべてのアクションがあるかどうかを決定します。|  
|[CRichEditCtrl::CanUndo](#canundo)|編集操作を元に戻すことができるかどうかを決定します。|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|エディット コントロールのクライアント領域の特定の時点に最も近い文字に関する情報を取得します。|  
|[CRichEditCtrl::Clear](#clear)|現在の選択をクリアします。|  
|[CRichEditCtrl::Copy](#copy)|現在の選択範囲をクリップボードにコピーします。|  
|[CRichEditCtrl::Create](#create)|Windows のリッチ エディット コントロールを作成し、この関連付けます`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::CreateEx](#createex)|拡張ウィンドウ スタイルを指定した Windows リッチ エディット コントロールを作成し、この関連付けます`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::Cut](#cut)|クリップボードに現在の選択項目を切り取ります。|  
|[CRichEditCtrl::DisplayBand](#displayband)|この内容の一部が表示され`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|リセット (クリア) この元に戻すフラグ`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::FindText](#findtext)|このテキストでは、検索`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|指定した文字位置の前後に、次の単語の分割を検索または、その位置の文字に関する情報を取得します。|  
|[CRichEditCtrl::FormatRange](#formatrange)|ターゲットの出力デバイス用のテキストの範囲の書式を設定します。|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|この特定の文字の位置を決める`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|この属性を書式設定現在の既定の文字を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|このイベント マスクを取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|この最上位に表示されている行を決定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|ポインターを取得、`IRichEditOle`このリッチ エディット コントロールのインターフェイスです。|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|このユーザーが入力できるテキストの量に制限を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetLine](#getline)|これから、行のテキストを取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|この行の数を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetModify](#getmodify)|かどうかをこの`CRichEditCtrl`オブジェクトが前回保存以降に変更されました。|  
|[CRichEditCtrl::GetOptions](#getoptions)|リッチ エディット コントロール オプションを取得します。|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|段落のこれの現在の選択で属性を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|リッチ エディット コントロールの現在の区切り文字を取得します。 このメッセージは、オペレーティング システムのアジア言語のバージョンでのみ使用できます。|  
|[CRichEditCtrl::GetRect](#getrect)|この書式指定の四角形を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetRedoName](#getredoname)|再実行キューが存在する、コントロールの場合は、次のアクションの種類を取得します。|  
|[CRichEditCtrl::GetSel](#getsel)|開始と終了この現在の選択項目の位置を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|この現在の選択範囲内の属性を書式設定文字取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|この現在の選択におけるコンテンツの種類を取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::GetSelText](#getseltext)|これで現在の選択項目のテキストを取得`CRichEditCtrl`オブジェクト|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|これで、文字内のテキストの長さを取得`CRichEditCtrl`オブジェクトです。 終端の null 文字は含まれません。|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|文字またはリッチ エディット ビュー内のバイトの数を取得します。 リッチ エディット コントロールでテキストの長さを特定する方法を示すフラグの一覧を受け入れます。|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|リッチ エディット コントロールの現在のテキスト モードと元に戻すレベルを取得します。|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|指定したテキスト範囲を取得します。|  
|[CRichEditCtrl::GetUndoName](#getundoname)|存在する場合は、次の元に戻す操作の種類を取得します。|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|リッチ エディット コントロールのワード区切りオプションの現在のワード ラップを取得します。 このメッセージは、オペレーティング システムのアジア言語のバージョンでのみ使用できます。|  
|[CRichEditCtrl::HideSelection](#hideselection)|現在の選択項目の表示と非表示を切り替えます。|  
|[CRichEditCtrl::LimitText](#limittext)|ユーザーが入力できるテキストの量を制限、`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|特定の文字を含む行を決定します。|  
|[CRichEditCtrl::LineIndex](#lineindex)|この指定された行の文字のインデックスを取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::LineLength](#linelength)|この指定された行の長さを取得`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::LineScroll](#linescroll)|このテキストをスクロール`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::Paste](#paste)|リッチ エディット コントロールには、クリップボードの内容を挿入します。|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|指定したデータ形式でリッチ エディット コントロールには、クリップボードの内容を挿入します。|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|エディット コントロールで指定した文字のクライアント領域の座標を取得します。|  
|[CRichEditCtrl::Redo](#redo)|コントロールの再実行キューでは、次の操作をやり直します。|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|この現在の選択項目を置き換えます`CRichEditCtrl`テキストが指定されたオブジェクト。|  
|[CRichEditCtrl::RequestResize](#requestresize)|これにより`CRichEditCtrl`要求サイズの変更通知を送信するオブジェクト。|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|URL の自動検出は、リッチ エディット コントロールでアクティブなかどうかを示します。|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|この背景色を設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|現在の既定文字がこの属性を書式設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|このイベント マスクを設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetModify](#setmodify)|設定またはこの変更フラグをクリア`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|セット、`IRichEditOleCallback`リッチ エディット コントロールの COM オブジェクト。|  
|[CRichEditCtrl::SetOptions](#setoptions)|このオプションを設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|段落で現在の選択範囲内の属性を書式設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|リッチ エディット コントロールの区切り文字を設定します。 このメッセージは、オペレーティング システムのアジア言語のバージョンでのみ使用できます。|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|この読み取り専用オプションを設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetRect](#setrect)|この書式指定の四角形を設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetSel](#setsel)|これで、選択内容が設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|この現在の選択範囲内の属性を書式設定文字`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|このターゲットの出力デバイスを設定`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetTextMode](#settextmode)|リッチ エディット コントロールのテキスト モードまたは元に戻すレベルを設定します。 コントロールにテキストが含まれている場合、メッセージが失敗します。|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|元に戻すキューに格納できる操作の最大数を設定します。|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|これには、現在の単語内の属性を書式設定文字`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|ワード ラップや単語区切り、豊富なオプションを設定では、コントロールを編集します。 このメッセージは、オペレーティング システムのアジア言語のバージョンでのみ使用できます。|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|収集からに元に戻す操作の現在のアクションを入力するその他のコントロールを停止します。 コントロールは、元に戻すキュー内の新しいアクションに存在する場合に、次の入力のアクションを格納します。|  
|[CRichEditCtrl::StreamIn](#streamin)|これに、入力ストリームからテキストを挿入`CRichEditCtrl`オブジェクトです。|  
|[CRichEditCtrl::StreamOut](#streamout)|これからテキストを格納`CRichEditCtrl`出力ストリームにオブジェクトです。|  
|[CRichEditCtrl::Undo](#undo)|最後の編集操作を反転させます。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ウィンドウで、ユーザーは入力し、テキストの編集です。 テキストは、文字および段落の書式設定に割り当てることができるし、OLE 埋め込みオブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーが使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 この Windows コモン コントロール (つまり、`CRichEditCtrl`クラス) は以降 Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用できます。 `CRichEditCtrl`クラスのバージョン 2.0 および 3.0 のサポート、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]リッチ エディット コントロールです。  
  
> [!CAUTION]
>  ダイアログ ボックスで、リッチ エディット コントロールを使用しているかどうか (アプリケーションが SDI、MDI であるかどうかに関係なくまたはダイアログ ベース)、呼び出す必要があります[AfxInitRichEdit](application-information-and-management.md#afxinitrichedit)ボックスが表示されるダイアログ ボックスの前に一度です。 この関数を呼び出す標準的な場所は、プログラムの`InitInstance`メンバー関数。 初回のみ ダイアログ ボックスを表示するたびに呼び出す必要はありません。 呼び出す必要はありません`AfxInitRichEdit`で作業している場合`CRichEditView`します。  
  
 使用する方法について`CRichEditCtrl`を参照してください。  
  
- [コントロール](../../mfc/controls-mfc.md)  
  
- [CRichEditCtrl の使い方](../../mfc/using-cricheditctrl.md)  
  
-   サポート技術情報記事 Q259949: 情報: SetCaretPos() が適切でない CEdit または CRichEditCtrl コントロール  
  
 MFC アプリケーションでリッチ エディット コントロールの使い方の例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="canpaste"></a>CRichEditCtrl::CanPaste  
 リッチ エディット コントロールが指定のクリップボード形式を貼り付けることができるかどうかを判断します。  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormat`  
 クエリをクリップボード データ形式です。 このパラメーターは、定義済みのクリップボード形式またはによって返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)します。  
  
### <a name="return-value"></a>戻り値  
 クリップボードの形式を貼り付けできる場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`nFormat`は 0、`CanPaste`クリップボードから現在の任意の形式が試行されます。  
  
 詳細については、次を参照してください。 [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993)メッセージと[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#1;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="canredo"></a>CRichEditCtrl::CanRedo  
 すべてのアクションが再実行キューに含まれているかどうかを判断します。  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は再実行キューには、アクション、それ以外の場合に 0 が含まれています。  
  
### <a name="remarks"></a>コメント  
 再実行キューの操作の名前を検出するを呼び出す[CRichEditCtrl::GetRedoName](#getredoname)します。 最新の元に戻す操作をやり直すを呼び出す[やり直し](#redo)します。  
  
 詳細については、次を参照してください。 [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="canundo"></a>CRichEditCtrl::CanUndo  
 最後の編集操作を元に戻すことができるかどうかを決定します。  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後の編集操作がへの呼び出しで取り消せる場合は 0 以外、[を元に戻す](#undo)メンバー関数は、元に戻すことができない場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#2;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 パラメーターに指定された位置の文字に関する情報を取得`pt`します。  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)指定した点の座標を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントに最も近い文字の&0; から始まる文字インデックス。 指定した点がコントロール内の最後の文字を超える場合は、戻り値は、コントロールの最後の文字を示します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、リッチ エディット コントロールでは機能します。 エディット コントロールの情報を取得する[場合](../../mfc/reference/cedit-class.md#charfrompos)します。  
  
 詳細については、次を参照してください。 [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="clear"></a>CRichEditCtrl::Clear  
 削除 (クリア)、リッチで現在の選択 (存在する場合) は、コントロールを編集します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 によって実行される削除**クリア**で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 を現在の選択項目を削除してから削除された内容をクリップボードに配置する、[切り取り](#cut)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#3;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="copy"></a>CRichEditCtrl::Copy  
 現在の選択 (存在する場合) リッチ エディット コントロールでクリップボードにコピーします。  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&4;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
##  <a name="create"></a>CRichEditCtrl::Create  
 Windows のリッチ エディット コントロールを作成し、この関連付けます`CRichEditCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 エディット コントロールのスタイルを指定します。 ウィンドウ スタイルが示されたの組み合わせを適用、**解説**以下のセクションと[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 エディット コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 エディット コントロールの親ウィンドウを指定します (多くの場合、 [CDialog](../../mfc/reference/cdialog-class.md))。 ことはできません**NULL**します。  
  
 `nID`  
 エディット コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CRichEditCtrl`&2; つのステップ内のオブジェクト。 まずを呼び出して、 [CRichEditCtrl](#cricheditctrl)のコンス トラクター物書き**作成**、Windows のエディット コントロールを作成およびそれにアタッチする、`CRichEditCtrl`オブジェクトです。  
  
 この関数で、リッチ エディット コントロールを作成するときに最初に必要なコモン コントロール ライブラリを読み込む必要があります。 ライブラリを読み込むには、グローバル関数を呼び出す[AfxInitRichEdit](application-information-and-management.md#afxinitrichedit)、さらにコモン コントロール ライブラリを初期化します。 呼び出す必要がある`AfxInitRichEdit`プロセスで&1; 回だけです。  
  
 **作成**実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)エディット コントロールへのメッセージ。  
  
 既定では、これらのメッセージが処理される、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数、`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CRichEditCtrl`メッセージ マップを新しいクラスに追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)エディット コントロールにします。  
  
- **WS_CHILD**常にします。  
  
- **WS_VISIBLE**通常です。  
  
- **WS_DISABLED**ことはほとんどありません。  
  
- **WS_GROUP**コントロールをグループ化します。  
  
- **WS_TABSTOP**タブ オーダーにエディット コントロールを含める。  
  
 ウィンドウ スタイルの詳細については、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#5;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="createex"></a>CRichEditCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CRichEditCtrl`オブジェクトです。  
  
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
 エディット コントロールのスタイルを指定します。 示されているウィンドウのスタイルの組み合わせを適用、**解説**の[作成](#create)と[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに**作成**、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 `CRichEditCtrl` オブジェクトを構築します。  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>コメント  
 使用[作成](#create)リッチ エディット コントロールを Windows を構築します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&6;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="cut"></a>CRichEditCtrl::Cut  
 削除 (切り取り)、現在選択 (存在する場合)、リッチ エディット コントロールや、削除されたテキストをクリップボードにコピーします。  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>コメント  
 によって実行される削除**切り取り**で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 を削除したテキストをクリップボードにかけることがなく、現在の選択を削除する、[クリア](#clear)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#7;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="displayband"></a>CRichEditCtrl::DisplayBand  
 リッチ エディット コントロール (テキストと OLE アイテム) の内容の一部を前に書式設定された表示[FormatRange](#formatrange)します。  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisplayRect`  
 ポインター、 [RECT](../../mfc/reference/rect-structure1.md)または[CRect](../../atl-mfc-shared/reference/crect-class.md)テキストを表示するデバイスの領域を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 書式設定されたテキストの表示が成功した場合、それ以外の場合、0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 テキストと OLE アイテムは、ポインターは、指定された領域にクリッピング`pDisplayRect`します。  
  
 詳細については、次を参照してください。 [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditCtrl::FormatRange](#formatrange)します。  
  
##  <a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 リッチ エディット コントロールの取り消しのフラグをリセット (クリア) します。  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>コメント  
 コントロールになりますない最後の編集操作を元に戻すことです。 リッチ エディット コントロール内の操作を完了できるときに元に戻すフラグが設定されています。  
  
 呼び出すたびに取り消しのフラグは自動的に消去、 [CWnd](../../mfc/reference/cwnd-class.md)メンバー関数[SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)します。  
  
 詳細については、次を参照してください。 [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#8;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="findtext"></a>CRichEditCtrl::FindText  
 リッチ エディット コントロール内のテキストを検索します。  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 使用可能な値の一覧は、次を参照してください。`wParam`で[EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *pFindText*  
 ポインター、[指定](http://msdn.microsoft.com/library/windows/desktop/bb787909)構造体の検索のパラメーターを提供および一致が見つかった範囲を取得します。  
  
### <a name="return-value"></a>戻り値  
 次の一致項目の 0 から始まる文字の位置– 1 は一致するものがある場合。  
  
### <a name="remarks"></a>コメント  
 検索単位の上下で適切な範囲のパラメーターを設定して、[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)内で構造体、**指定**構造体。  
  
 詳細については、次を参照してください。 [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011)メッセージと[指定](http://msdn.microsoft.com/library/windows/desktop/bb787909)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#9;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 指定した位置の前後に次の単語分割を検索`nStart`します。  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCode`  
 実行するアクションを示します。 使用可能な値の一覧は、パラメーターの説明を参照してください。`code`で**EM_FINDWORDBREAK**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `nStart`  
 開始する&0; から始まる文字位置。  
  
### <a name="return-value"></a>戻り値  
 パラメーターに基づく`nCode`します。 詳細については、次を参照してください。 [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用すると、指定された位置に文字に関する情報を取得します。  
  
##  <a name="formatrange"></a>CRichEditCtrl::FormatRange  
 特定のデバイスのリッチ エディット コントロール内のテキストの範囲の書式を設定します。  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pfr*  
 ポインター、 [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911)出力デバイスに関する情報を格納する構造体。 **NULL**リッチ エディット コントロール内のキャッシュされた情報を解放できることを示します。  
  
 *bDisplay*  
 テキストを表示するかどうかを示します。 場合**FALSE**テキストが計測されるだけです。  
  
### <a name="return-value"></a>戻り値  
 リージョン&1; を加えた値に適合する最後の文字のインデックス。  
  
### <a name="remarks"></a>コメント  
 通常、この呼び出しはへの呼び出しによって、その後[続いて](#displayband)します。  
  
 詳細については、次を参照してください。[しかし](http://msdn.microsoft.com/library/windows/desktop/bb788020)メッセージと[FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#10;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 この特定の文字の位置 (左上隅) を取得`CRichEditCtrl`オブジェクトです。  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lChar`  
 文字の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された文字の左上隅の位置`lChar`します。  
  
### <a name="remarks"></a>コメント  
 文字を指定するには、0 から始まるインデックス値を提供します。 場合`lChar`この最後の文字のインデックスよりも大きい`CRichEditCtrl`オブジェクトの戻り値は、この最後の文字の直後の文字位置の座標を指定`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 既定の文字の属性の書式を取得`CRichEditCtrl`オブジェクトです。  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a **CHARFORMAT** structure holding the default character formatting attributes.  
  
 In the second version, a pointer to a **CHARFORMAT2** structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure, holding the default character formatting attributes.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specified the default character formatting attributes.  
  
### Remarks  
 For more information, see the **EM_GETCHARFORMAT** message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>  CRichEditCtrl::GetEventMask  
 Gets the event mask for this `CRichEditCtrl` object.  
  
```  
長い GetEventMask() const です。  
```  
  
### Return Value  
 The event mask for this `CRichEditCtrl` object.  
  
### Remarks  
 The event mask specifies which notification messages the `CRichEditCtrl` object sends to its parent window.  
  
 For more information, see [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>  CRichEditCtrl::GetFirstVisibleLine  
 Determines the topmost visible line in this `CRichEditCtrl` object.  
  
```  
int GetFirstVisibleLine() const です。  
```  
  
### Return Value  
 Zero-based index of the uppermost visible line in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>  CRichEditCtrl::GetIRichEditOle  
 Accesses the **IRichEditOle** interface for this `CRichEditCtrl` object.  
  
```  
IRichEditOle * GetIRichEditOle() const です。  
```  
  
### Return Value  
 Pointer to the [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface that can be used to access this `CRichEditCtrl` object's OLE functionality; **NULL** if the interface is not accessible.  
  
### Remarks  
 Use this interface to access this `CRichEditCtrl` object's OLE functionality.  
  
 For more information, see [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) message and [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>  CRichEditCtrl::GetLimitText  
 Gets the text limit for this `CRichEditCtrl` object.  
  
```  
長い GetLimitText() const です。  
```  
  
### Return Value  
 The current text limit, in bytes, for this `CRichEditCtrl` object.  
  
### Remarks  
 The text limit is the maximum amount of text, in bytes, the rich edit control can accept.  
  
 For more information, see [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>  CRichEditCtrl::GetLine  
 Retrieves a line of text from this `CRichEditCtrl` object.  
  
```  
GetLine (int nIndex、int  
    LPTSTR 取り出し) const です。  
  
GetLine (int nIndex、int  
    LPTSTR 取り出し  
    int 型の格納) const です。  
```  
  
### Parameters  
 `nIndex`  
 Zero-based index of the line to retrieve.  
  
 `lpszBuffer`  
 Points to the buffer to receive the text. The first word of the buffer must specify the maximum number of bytes that can be copied into the buffer.  
  
 `nMaxLength`  
 Maximum number of characters that can be copied into `lpszBuffer`. The second form of `GetLine` places this value into the first word of the buffer specified by `lpszBuffer`.  
  
### Return Value  
 The number of characters copied into `lpszBuffer`.  
  
### Remarks  
 The copied line does not contain a terminating null character.  
  
> [!NOTE]
>  Because the first word of the buffer stores the number of characters to be copied, make sure that your buffer is at least 4 bytes long.  
  
 For more information, see [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CRichEditCtrl::GetLineCount  
 Retrieves the number of lines in the `CRichEditCtrl` object.  
  
```  
int GetLineCount() const です。  
```  
  
### Return Value  
 The number of lines in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>  CRichEditCtrl::GetModify  
 Determines if the contents of this `CRichEditCtrl` object have been modified.  
  
```  
BOOL GetModify() const です。  
```  
  
### Return Value  
 Nonzero if the text in this `CRichEditCtrl` object has been modified; otherwise 0.  
  
### Remarks  
 Windows maintains an internal flag indicating whether the contents of the rich edit control have been changed. This flag is cleared when the edit control is first created and can also be cleared by calling the [SetModify](#setmodify) member function.  
  
 For more information, see [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>  CRichEditCtrl::GetOptions  
 Retrieves the options currently set for the rich edit control.  
  
```  
UINT GetOptions() const です。  
```  
  
### Return Value  
 A combination of the current option flag values. For a list of these values, see the *fOptions* parameter in the [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getparaformat"></a>  CRichEditCtrl::GetParaFormat  
 Gets the paragraph formatting attributes of the current selection.  
  
```  
DWORD GetParaFormat(PARAFORMAT& pf) const です。 DWORD GetParaFormat(PARAFORMAT2& pf) const です。 ```  
  
### <a name="parameters"></a>パラメーター  
 `pf`  
 最初のバージョンへのポインターで、 [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940)段落の現在の選択の属性を保持する構造体。  
  
 2 番目のバージョンへのポインターで、 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)リッチ エディット 2.0 拡張機能は、構造体に、 **PARAFORMAT**既定の文字の書式属性を保持します。  
  
### <a name="return-value"></a>戻り値  
 **DwMask**データ メンバーの`pf`です。 段落の現在の選択範囲全体で一貫性のある属性を指定します。  
  
### <a name="remarks"></a>コメント  
 複数の段落を選択すると場合、`pf`最初の選択した段落の属性を受け取る。 戻り値は、選択範囲全体に適用されている属性を指定します。  
  
 詳細については、次を参照してください。、 [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182)メッセージおよび**PARAFORMAT**と**PARAFORMAT2**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditCtrl::SetParaFormat](#setparaformat)します。  
  
##  <a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 リッチ エディット コントロールで現在の区切り文字を取得します。  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `fType`  
 」の説明に従って、区切り型フラグ、`fType`のパラメーター [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpPunc`  
 ポインター、[句読点](http://msdn.microsoft.com/library/windows/desktop/bb787944)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、操作が成功した場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、アジア系言語バージョンのオペレーティング システムのみで使用できます。  
  
##  <a name="getrect"></a>CRichEditCtrl::GetRect  
 この書式指定の四角形を取得`CRichEditCtrl`オブジェクトです。  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md)またはへのポインター、 [RECT](../../mfc/reference/rect-structure1.md)これの書式設定の四角形を受信する`CRichEditCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 書式設定の四角形は、テキストの外接する四角形です。 この値の規模に関係なく、`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。 [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[LimitText](#limittext)します。  
  
##  <a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 存在する場合は、再実行キューに次のアクションの種類を取得します。  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、`GetRedoName`返します、[ある場合](http://msdn.microsoft.com/library/windows/desktop/bb774365)コントロールの再実行キューの次のアクションの種類を示す列挙型。 再実行キューが空である場合、または種類が不明の場合は、キュー内のやり直しアクション`GetRedoName`0 を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻すまたは再実行できるアクションの種類は、入力、削除、ドラッグ アンド ドロップ、切り取り、および貼り付け操作します。 この情報は、アンドゥ操作のドロップダウン リスト ボックスなどの取り消しとやり直し操作の拡張ユーザー インターフェイスを提供するアプリケーションで役立ちます。  
  
##  <a name="getsel"></a>CRichEditCtrl::GetSel  
 この現在の選択範囲の境界を取得`CRichEditCtrl`オブジェクトです。  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 参照、[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)現在の選択範囲の境界を受け取る構造体。  
  
 `nStartChar`  
 現在の選択範囲の最初の文字の&0; から始まるインデックス。  
  
 `nEndChar`  
 現在の選択範囲の最後の文字の&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 この関数の&2; つの形式は、選択範囲の境界を取得する別の方法を提供します。 これらの形式の簡単な説明に従ってください。  
  
- **GetSel (** `cr` **)**このフォームを使用して、**上**構造体の**cpMin**と**cpMax**境界を取得するメンバー。  
  
- **GetSel (** `nStartChar` **、** `nEndChar` **)**このフォームは、パラメーターで境界を返します`nStartChar`と`nEndChar`です。  
  
 選択範囲を含むすべての場合、先頭 ( **cpMin**または`nStartChar`) は 0、末尾 ( **cpMax**または`nEndChar`) が – 1 です。  
  
 詳細については、次を参照してください。 [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001)メッセージと[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#15;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 現在の選択項目の属性を書式設定文字を取得できます。  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure to receive the character formatting attributes of the current selection.  
  
 In the second version, a pointer to a [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure to receive the character formatting attributes of the current selection.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specifies the character formatting attributes that are consistent throughout the current selection.  
  
### Remarks  
 The `cf` parameter receives the attributes of the first character in the current selection. The return value specifies which attributes are consistent throughout the selection.  
  
 For more information, see the [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>  CRichEditCtrl::GetSelectionType  
 Determines the selection type in this `CRichEditCtrl` object.  
  
```  
WORD GetSelectionType() const です。  
```  
  
### Return Value  
 Flags indicating the contents of the current selection. A combination of the following flags:  
  
- `SEL_EMPTY` Indicates that there is no current selection.  
  
- `SEL_TEXT` Indicates that the current selection contains text.  
  
- `SEL_OBJECT` Indicates that the current selection contains at least one OLE item.  
  
- `SEL_MULTICHAR` Indicates that the current selection contains more than one character of text.  
  
- `SEL_MULTIOBJECT` Indicates that the current selection contains more than one OLE object.  
  
### Remarks  
 For more information, see [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>  CRichEditCtrl::GetSelText  
 Retrieves the text from the current selection in this `CRichEditCtrl` object.  
  
```  
長い GetSelText(LPSTR lpBuf) const です。 CString GetSelText() const です。 ```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 現在の選択項目のテキストを受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 フォームに依存します。  
  
- **GetSelText (** `lpBuf` **)**にコピーされた文字数`lpBuf`終端の null は含まない。  
  
- **GetSelText ()**現在の選択項目を含む文字列。  
  
### <a name="remarks"></a>コメント  
 最初の形式を使用する場合**GetSelText (** `lpBuf` **)**バッファーが、テキストを受信するのに十分な大きさであることを確認する必要があります。 呼び出す[GetSel](#getsel)を現在の選択範囲の文字数を決定します。  
  
 詳細については、次を参照してください。 [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditCtrl::GetSelectionType](#getselectiontype)します。  
  
##  <a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 これで、文字内のテキストの長さを取得`CRichEditCtrl`終端の null 文字を含まないオブジェクトです。  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このテキストの長さ`CRichEditCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&17;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 リッチ エディット コントロール内のテキストの長さを計算します。  
  
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
 `GetTextLengthEx`別のテキストの長さを決定する方法を提供します。 リッチ エディット 2.0 の機能がサポートしています。 参照してください[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 リッチ エディット コントロールの現在のテキスト モードと元に戻すレベルを取得します。  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビット フラグのセット、 [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364)列挙型の場合」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 フラグは、現在のテキスト モードを示し、コントロールのレベルを元に戻します。  
  
##  <a name="gettextrange"></a>CRichEditCtrl::GetTextRange  
 指定された文字の範囲を取得します。  
  
```  
int GetTextRange(
    int nFirst,  
    int nLast,  
    CString& refString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFirst`  
 範囲の最初の文字の直前の文字位置を示すインデックス。  
  
 `nLast`  
 範囲の最後の文字の直後の文字位置。  
  
 `refString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)テキストを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を含まないコピーされた文字数。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `GetTextRange`リッチ エディット 2.0 の機能をサポートしています。 参照してください[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 存在する場合は、元に戻すキューに次のアクションの種類を取得します。  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 元に戻す操作がコントロールの元に戻すキューにある場合`GetUndoName`返します、[ある場合](http://msdn.microsoft.com/library/windows/desktop/bb774365)キューでは、次のアクションの種類を示す列挙型。 元に戻すキューが空である場合、またはキュー内の元に戻す操作の種類が不明の場合`GetUndoName`0 を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻すまたは再実行できるアクションの種類は、入力、削除、ドラッグ アンド ドロップ、切り取り、および貼り付け操作します。 この情報は、元に戻す/やり直すなどの操作を取り消すことができるアクションのドロップダウン リスト ボックス拡張ユーザー インターフェイスを提供するアプリケーションに便利です。  
  
##  <a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 リッチ エディット コントロールのワード区切りオプションの現在のワード ラップを取得します。  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のワード ラップし、単語に区切ったりオプション。 これらのオプションの説明を[EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、オペレーティング システムのアジア言語のバージョンでのみ使用できます。  
  
##  <a name="hideselection"></a>CRichEditCtrl::HideSelection  
 選択範囲の表示/非表示を変更します。  
  
```  
void HideSelection(
    BOOL bHide,  
    BOOL bPerm);
```  
  
### <a name="parameters"></a>パラメーター  
 `bHide`  
 選択範囲を表示するか、非表示を示す**TRUE**選択範囲を非表示にします。  
  
 `bPerm`  
 この選択の表示の変更を永続的にするかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 `bPerm`は**TRUE**、変更、`ECO_NOHIDESEL`適しています。 この`CRichEditCtrl`オブジェクトです。 このオプションの簡単な説明を参照してください。 [SetOptions](#setoptions)します。 この関数を使用するにはこのすべてのオプションを設定する`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。 [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#18;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="limittext"></a>CRichEditCtrl::LimitText  
 エディット コントロールに入力できるテキストの長さを制限します。  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChars`  
 ユーザーが入力できるテキストのバイト単位で長さを指定します。 このパラメーターが 0 (既定値) の場合は、テキストの長さは 64 kb に設定されます。  
  
### <a name="remarks"></a>コメント  
 テキストの制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 影響が与えませんされたテキストで既にエディット コントロールでも、エディット コントロールにコピーするテキストの長さに影響は、 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)のメンバー関数内`CWnd`します。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストを削除します。 ただし、テキストの制限は、ユーザーが新しいテキストに、既存のテキストを置換できないようにを現在の選択項目を削除しない限りは、テキストの制限内に収まるようにテキストを発生します。  
  
> [!NOTE]
>  テキストの制限には、各 OLE アイテムは、単一の文字としてカウントされます。  
  
 詳細については、次を参照してください。 [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#19;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 指定した文字のインデックスを含む行の行番号を取得します。  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 エディット コントロールのテキストで、目的の文字の&0; から始まるインデックス値であるか、–&1; が含まれています。 場合`nIndex`-1 で、現在の行では、キャレットを含む行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定された文字のインデックスを含む行の&0; から始まる行番号`nIndex`です。 場合`nIndex`-1 で、選択範囲の最初の文字を含む行の数が返されます。 選択されていない場合は、現在の行番号が返されます。  
  
### <a name="remarks"></a>コメント  
 文字インデックスでは、リッチ エディット コントロールの先頭からの文字数です。 文字をカウントする OLE アイテムが単一の文字としてカウントされます。  
  
 詳細については、次を参照してください。 [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#20;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="lineindex"></a>CRichEditCtrl::LineIndex  
 この行の文字のインデックスを取得`CRichEditCtrl`オブジェクトです。  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nLine`  
 エディット コントロールのテキストで目的の行のインデックス値であるか、–&1; が含まれています。 場合`nLine`-1 で、現在の行では、キャレットを含む行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した行の文字インデックス`nLine`または指定した行番号が大きい場合は –&1;、エディット コントロールで行の数。  
  
### <a name="remarks"></a>コメント  
 文字インデックスでは、リッチ エディット コントロールの先頭から指定した行までの文字数です。  
  
 詳細については、次を参照してください。 [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&21;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="linelength"></a>CRichEditCtrl::LineLength  
 リッチ エディット コントロール内の行の長さを取得します。  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nLine`  
 長さを取得する行で、文字の文字のインデックスを指定します。 このパラメーターが-1 の場合は、現在の行 (行のキャレットを含む) の長さは返されて、行内テキストが選択されている任意の長さは含まれません。 `LineLength`と呼ばれる単一行のエディット コントロールでは、このパラメーターは無視されます。  
  
### <a name="return-value"></a>戻り値  
 `LineLength`と呼ばれる、複数行のエディット コントロールの場合は、戻り値は、長さ (バイト単位) で指定された行の`nLine`です。 `LineLength`と呼ばれる単一行のエディット コントロールの場合、戻り値はエディット コントロールでテキストの長さをバイト単位でします。  
  
### <a name="remarks"></a>コメント  
 使用して、 [LineIndex](#lineindex)この内の特定の行番号の文字インデックスを取得するメンバー関数を`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。 [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[LineIndex](#lineindex)します。  
  
##  <a name="linescroll"></a>CRichEditCtrl::LineScroll  
 複数行のエディット コントロールのテキストをスクロールします。  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLines`  
 垂直方向にスクロールする行数を指定します。  
  
 `nChars`  
 水平方向にスクロールする文字位置の数を指定します。 リッチ エディット コントロールにいずれかがある場合、この値は無視されます、 **ES_RIGHT**または**ES_CENTER**スタイル。 [エディット スタイル](../../mfc/reference/edit-styles.md)で指定された[作成](#create)します。  
  
### <a name="remarks"></a>コメント  
 エディット コントロールは、過去のエディット コントロールでテキストの最後の行は垂直方向にスクロールされません。 現在の行で指定された行の数を加えた場合`nLines`エディット コントロールで行の合計数を超える場合、エディット コントロールの最後の行は、エディット コントロール ウィンドウの上部までスクロールできるように、値を調整します。  
  
 `LineScroll`過去の任意の行の最後の文字、水平方向にスクロールするために使用します。  
  
 詳細については、次を参照してください。 [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[GetFirstVisibleLine](#getfirstvisibleline)します。  
  
##  <a name="paste"></a>CRichEditCtrl::Paste  
 クリップボードからデータを挿入、`CRichEditCtrl`カーソルの位置、カレットの位置にします。  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>コメント  
 クリップボードに認識されている形式のデータが含まれている場合にのみ、データが挿入されます。  
  
 詳細については、次を参照してください。 [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&22;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 これに特定のクリップボード形式でデータを貼り付けます`CRichEditCtrl`オブジェクトです。  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nClipFormat*  
 クリップボードの形式にこれを貼り付ける`CRichEditCtrl`オブジェクトです。  
  
 *型*  
 クリップボードから取得するデータのデバイス アスペクトします。  
  
 *hMF*  
 貼り付けられるオブジェクトのアイコンのビューを含むメタファイルへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 新素材は、カーソルの位置、カレットの位置に挿入されます。  
  
 詳細については、次を参照してください。 [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl 第&23;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 エディット コントロールで指定した文字のクライアント領域の座標を取得します。  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 文字の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 文字、(x, y) の位置。 単一行のエディット コントロールでは、y 座標は常に値が&0; です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="redo"></a>CRichEditCtrl::Redo  
 コントロールの再実行キューでは、次の操作をやり直します。  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 この現在の選択項目を置き換えます`CRichEditCtrl`テキストが指定されたオブジェクト。  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewText`  
 置換テキストを含む null で終わる文字列へのポインター。  
  
 `bCanUndo`  
 この関数が完了できることを指定するには、このパラメーターの値を設定**TRUE**します。 既定値は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 これですべてのテキストを置換する`CRichEditCtrl`オブジェクトを使用[とき](../../mfc/reference/cwnd-class.md#setwindowtext)します。  
  
 現在の選択項目がない場合は、置換テキストはカーソルの位置は、現在のキャレット位置に挿入されます。  
  
 この関数は既存の文字書式の設定に挿入されたテキストをフォーマットできるようになります。 テキストの範囲全体を置換するときに (を呼び出して`SetSel`(0,-1) 呼び出しの前に`ReplaceSel`) を終端に新しく挿入されたテキストに継承される前の段落の書式を保持する段落文字があります。  
  
 詳細については、次を参照してください。 [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[LineIndex](#lineindex)します。  
  
##  <a name="requestresize"></a>CRichEditCtrl::RequestResize  
 これにより`CRichEditCtrl`を送信するオブジェクト**EN_REQUESTRESIZE**通知メッセージを親ウィンドウです。  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>コメント  
 この関数は[、ボトムレス](../../mfc/reference/cwnd-class.md#onsize)処理をボトムレス`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。、 [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220)メッセージおよび**ボトムレス リッチ エディット コントロール**の[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 URL を自動的に検出するリッチ エディット コントロールを設定します。  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 コントロールが自動的に検出する URL に設定されているかどうかを指定します。 場合**TRUE**を有効にします。 場合**FALSE**は無効になります。  
  
### <a name="return-value"></a>戻り値  
 成功しましたが、それ以外の場合は&0; 以外の場合は&0; を返します。 たとえば、メッセージがメモリ不足が原因で失敗します。  
  
### <a name="remarks"></a>コメント  
 有効な場合、リッチ エディット コントロールには、標準の URL 形式が一致するかどうかの判定にテキストがスキャンされます。 これらの URL 形式の一覧は、次を参照してください。 [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
> [!NOTE]
>  設定しない`SetAutoURLDetect`に**TRUE**エディット コントロールで使用する場合、 **CFE_LINK** Url 以外のテキストの効果です。 `SetAutoURLDetect`Url に対してこの効果を有効にし、その他のすべてのテキストを上書きします。 参照してください[EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970)の詳細については、 **CFE_LINK**影響します。  
  
##  <a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 この背景色を設定`CRichEditCtrl`オブジェクトです。  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `bSysColor`  
 背景色をシステムの値を設定する必要があるかどうかを示します。 この値が場合**TRUE**、`cr`は無視されます。  
  
 `cr`  
 要求された背景色。 場合にのみ、使用される`bSysColor`は**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 この前の背景色`CRichEditCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 システムの値または指定した背景色を設定できます[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。  
  
 詳細については、次を参照してください。 [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228)メッセージと[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&24;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 これで新しいテキストの属性を書式設定文字`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 最初のバージョンへのポインターで、 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)新しい既定の文字書式属性を含む構造体。  
  
 2 番目のバージョンへのポインターで、 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)リッチ エディット 2.0 拡張機能は、構造体を**CHARFORMAT**既定の文字の書式属性を持つ。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`cf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。、 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230)メッセージおよび**CHARFORMAT**と**CHARFORMAT2**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#25;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 このイベント マスクを設定`CRichEditCtrl`オブジェクトです。  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwEventMask*  
 この新しいイベント マスク`CRichEditCtrl`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 前のイベント マスクです。  
  
### <a name="remarks"></a>コメント  
 通知メッセージを指定するイベント マスク、`CRichEditCtrl`オブジェクトを親ウィンドウに送信します。  
  
 詳細については、次を参照してください。 [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&26;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="setmodify"></a>CRichEditCtrl::SetModify  
 設定または編集コントロールの変更フラグをクリアします。  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bModified`  
 値**TRUE**テキストが変更されたことを示す、値を**FALSE**修正されていないことを示します。 既定では、変更のフラグを設定します。  
  
### <a name="remarks"></a>コメント  
 変更のフラグは、エディット コントロール内のテキストが変更されたかどうかを示します。 ユーザーがテキストを変更するたびに自動的に設定されます。 その値を取得できる、[この](#getmodify)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[この](#getmodify)します。  
  
##  <a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 これは、`CRichEditCtrl`オブジェクト、 **IRichEditOleCallback** OLE に関連するリソースと情報にアクセスに使用するオブジェクト。  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCallback`  
 ポインター、 [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308)オブジェクトがこの`CRichEditCtrl`OLE に関連するリソースと情報を取得するオブジェクトが使用されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、`CRichEditCtrl`オブジェクトが呼び出す[:addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)で指定された COM オブジェクトの使用率カウントをインクリメントする`pCallback`です。  
  
 詳細については、次を参照してください。 [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252)メッセージと[IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308)インターフェイスで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setoptions"></a>CRichEditCtrl::SetOptions  
 このオプションを設定`CRichEditCtrl`オブジェクトです。  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *wOp*  
 操作の種類を示します。 次のいずれかの値です。  
  
- `ECOOP_SET`によって指定されたオプションを設定`dwFlags`します。  
  
- `ECOOP_OR`指定されたものと現在のオプションを組み合わせる`dwFlags`します。  
  
- `ECOOP_AND`も指定されている現在のオプションのみを保持する`dwFlags`です。  
  
- `ECOOP_XOR`現在のオプションのみを保持する*いない*によって指定された`dwFlags`します。  
  
 `dwFlags`  
 豊富なオプションを編集します。 フラグの値は、「解説」セクションに表示されます。  
  
### <a name="remarks"></a>コメント  
 オプションは、次の値の組み合わせになります。  
  
- `ECO_AUTOWORDSELECTION`単語の自動選択をダブルクリックします。  
  
- `ECO_AUTOVSCROLL`自動的にユーザーが行の末尾に文字を入力したときは、10 文字で右側にあるテキストをスクロールします。 ユーザーは、ENTER キーを押すと、コントロールがゼロの位置にすべてのテキストをスクロールします。  
  
- `ECO_AUTOHSCROLL`最後の行で、ENTER キーを押したときに、1 ページ上のテキストを自動的にスクロールします。  
  
- `ECO_NOHIDESEL`エディット コントロールの既定の動作を無効にします。 既定の動作には、コントロールが入力フォーカスを失い、コントロールが入力フォーカスを受け取ると、選択されて表示と選択範囲が非表示にします。 指定した場合`ECO_NOHIDESEL`コントロールにフォーカスがない場合でも、選択したテキストが反転します。  
  
- `ECO_READONLY`ユーザーが入力するか、エディット コントロールでテキストを編集できなくなります。  
  
- `ECO_WANTRETURN`ダイアログ ボックスで複数行のリッチ エディット コントロールにテキストを入力するときに、ENTER キーを押したときに、キャリッジ リターンを挿入することを指定します。 このスタイルを指定しない場合は、親ウィンドウの既定のボタン (たとえば、ダイアログ ボックスで [ok] ボタン) をクリックするとをまねたリッチ エディット コントロールの親ウィンドウにコマンドを送ります ENTER キーを押します。 このスタイルには、エディット コントロールの単一行への影響がありません。  
  
- `ECO_SAVESEL`コントロールがフォーカスを失ったときに、選択を保存します。 既定では、フォーカスを得たときに、コントロールの内容全体が選択されます。  
  
- `ECO_VERTICAL`垂直方向のテキストおよびオブジェクトを描画します。 アジアの言語でのみ使用できます。  
  
 詳細については、次を参照してください。 [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&27;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 段落の現在の選択の属性を設定`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>パラメーター  
 `pf`  
 最初のバージョンへのポインターで、 [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940)新しい既定の段落書式属性です。  
  
 2 番目のバージョンへのポインターで、 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)リッチ エディット 2.0 拡張機能は、構造体に、 **PARAFORMAT**既定の文字の書式属性を保持します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`pf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。、 [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276)メッセージおよび**PARAFORMAT**と**PARAFORMAT2**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&28;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 リッチ エディット コントロールに区切り記号を設定します。  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>パラメーター  
 `fType`  
 区切り記号のフラグ。 使用可能な値の一覧は、次を参照してください。、`fType`パラメーター [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpPunc`  
 ポインター、[句読点](http://msdn.microsoft.com/library/windows/desktop/bb787944)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、オペレーティング システムのアジア言語バージョンでだけ使用できます。  
  
##  <a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 変更、`ECO_READONLY`適しています。 この`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bReadOnly`  
 示す場合は、この`CRichEditCtrl`オブジェクトが読み取り専用でする必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このオプションの簡単な説明を参照してください。 [SetOptions](#setoptions)します。 この関数を使用するにはこのすべてのオプションを設定する`CRichEditCtrl`オブジェクトです。  
  
 詳細については、次を参照してください。 [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&29;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="setrect"></a>CRichEditCtrl::SetRect  
 この書式指定の四角形を設定`CRichEditCtrl`オブジェクトです。  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md)またはへのポインター、 [RECT](../../mfc/reference/rect-structure1.md)書式の四角形の新しい境界を示します。  
  
### <a name="remarks"></a>コメント  
 書式設定の四角形は、テキストの外接する四角形です。 外接する四角形は、リッチ エディット コントロール ウィンドウのサイズに依存しません。 ときにこの`CRichEditCtrl`オブジェクトが最初に作成された、書式設定の四角形は、ウィンドウのクライアント領域と同じサイズです。 使用`SetRect`書式の四角形の豊富な編集ウィンドウよりも小さいを変更します。  
  
 詳細については、次を参照してください。 [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&30;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="setsel"></a>CRichEditCtrl::SetSel  
 この選択内容が設定`CRichEditCtrl`オブジェクトです。  
  
```  
void SetSel(
    long nStartChar,  
    long nEndChar);  
  
void SetSel(CHARRANGE& cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartChar`  
 選択範囲の最初の文字の&0; から始まるインデックス。  
  
 `nEndChar`  
 選択範囲の最後の文字の&0; から始まるインデックス。  
  
 `cr`  
 [上](http://msdn.microsoft.com/library/windows/desktop/bb787885)現在の選択範囲の境界を保持する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の&2; つの形式は、選択範囲の境界を設定する別の方法を提供します。 これらの形式の簡単な説明に従ってください。  
  
- **SetSel (** `cr` **)**このフォームを使用して、**上**構造体の**cpMin**と**cpMax**のメンバーが、境界を設定します。  
  
- **SetSel (** `nStartChar` **、** `nEndChar` **)**このフォームは、パラメーターを使用して`nStartChar`と`nEndChar`境界を設定します。  
  
 キャレットは最初のうち、長い方によって示される選択範囲の末尾に置かれます ( **cpMin**または`nStartChar`) と終了 ( **cpMax**または`nEndChar`) のインデックス。 この関数の内容をスクロールする、`CRichEditCtrl`キャレットをできるようにします。  
  
 これですべてのテキストを選択する`CRichEditCtrl`を呼び出すオブジェクトを`SetSel`0 と 1 の最後のインデックスの開始インデックスを持つ。  
  
 詳細については、次を参照してください。 [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007)メッセージと[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[GetSel](#getsel)します。  
  
##  <a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 この現在の選択範囲内のテキストの属性を書式設定文字`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 最初のバージョンへのポインターで、 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)新しい文字の書式設定を含む構造体の現在の選択の属性です。  
  
 2 番目のバージョンへのポインターで、 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)リッチ エディット 2.0 拡張機能は、構造体を**CHARFORMAT**書式属性現在の選択項目を新しい文字を含んでいる構造。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`cf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。、 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230)と**CHARFORMAT**と**CHARFORMAT2**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&31;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 WYSIWYG の使用対象デバイスと線の幅を設定 (表示されるは取得する) で書式設定`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetTargetDevice(
    HDC hDC,  
    long lLineWidth);

 
BOOL SetTargetDevice(
    CDC& dc,  
    long lLineWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 新しいターゲット デバイスのデバイス コンテキストへのハンドルします。  
  
 *lLineWidth*  
 書式設定に使用する線の幅。  
  
 `dc`  
 [CDC](../../mfc/reference/cdc-class.md)新しいターゲット デバイス用です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 リッチ エディット コントロールに、デバイスを所有しているこの関数が成功した場合は、コンテキストがパラメーターとして渡されます。 その場合は、呼び出し元の関数は、デバイス コンテキストを破棄しないようにします。  
  
 詳細については、次を参照してください。 [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#32;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 リッチ エディット コントロールのテキスト モードまたは元に戻す/やり直しのレベルを設定します。  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *fMode*  
 コントロールのテキスト モードと元に戻すレベルのパラメーター用の新しい設定を指定します。 使用可能な値の一覧は、モード パラメーターを参照してください。 [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功しましたが、それ以外の場合は&0; 以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 テキスト モードの説明は、次を参照してください。 **EM_SETTEXTMODE**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 このメンバー関数は、コントロールにテキストが含まれている場合に失敗します。 コントロールが空であることを確認するには、送信、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)に空の文字列メッセージ。  
  
##  <a name="setundolimit"></a>CRichEditCtrl::SetUndoLimit  
 元に戻すキューに格納できる操作の最大数を設定します。  
  
```  
UINT SetUndoLimit(UINT nLimit);
```  
  
### <a name="parameters"></a>パラメーター  
 *nLimit*  
 元に戻すキューに格納できる操作の最大数を指定します。 0 に設定を無効にする元に戻します。  
  
### <a name="return-value"></a>戻り値  
 リッチ元に戻す操作の新しいの最大数は、コントロールを編集します。  
  
### <a name="remarks"></a>コメント  
 既定では、元に戻すキュー内のアクションの最大数は 100 です。 この数を増やす場合は、使用可能なメモリ不足のため、新しい番号に対応する必要があります。 パフォーマンス向上のためには、最小有効値に制限を設定します。  
  
##  <a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 これで、現在選択されている単語に対して属性を書式設定文字`CRichEditCtrl`オブジェクトです。  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 最初のバージョンへのポインターで、 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)新しい文字の書式設定を含む構造体は、現在選択されている word の属性です。  
  
 2 番目のバージョンへのポインターで、 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)リッチ エディット 2.0 拡張機能は、構造体を**CHARFORMAT**書式属性、現在選択されている単語を新しい文字を含んでいる構造。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された属性だけ、 **dwMask**のメンバー`cf`は、この関数によって変更します。  
  
 詳細については、次を参照してください。、 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230)メッセージおよび**CHARFORMAT**と**CHARFORMAT2**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&33;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 ワード ラップや単語区切り、豊富なオプションを設定では、コントロールを編集します。  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `uFlags`  
 ワード ラップや単語区切りで設定できるオプションです。 使用可能なオプションの一覧は、次を参照してください。 [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 現在のワード ラップや単語区切りのオプションです。  
  
### <a name="remarks"></a>コメント  
 このメッセージは、オペレーティング システムのアジア言語のバージョンでのみ使用できます。  
  
##  <a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 収集からに元に戻す操作の現在のアクションを入力するその他のコントロールを停止します。  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>コメント  
 コントロールは、元に戻すキュー内の新しいアクションに存在する場合に、次の入力のアクションを格納します。  
  
 詳細については、次を参照してください。 [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="streamin"></a>CRichEditCtrl::StreamIn  
 このテキストを置換`CRichEditCtrl`指定した入力ストリームからテキストを持つオブジェクト。  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormat`  
 入力データの形式を指定するフラグ。 詳細については、「解説」を参照してください。  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)入力ストリームを指定します。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 入力ストリームから読み取られた文字数。  
  
### <a name="remarks"></a>コメント  
 値`nFormat`次のいずれかを指定する必要があります。  
  
- `SF_TEXT`テキストの読み取りのみを示します。  
  
- `SF_RTF`テキストの読み取りと書式設定を示します。  
  
 これらの値のいずれかと組み合わせて使用できます`SFF_SELECTION`します。 場合`SFF_SELECTION`が指定されている`StreamIn`現在の選択範囲を入力ストリームの内容に置き換えます。 指定されていない場合`StreamIn`これの内容全体を置き換える`CRichEditCtrl`オブジェクトです。  
  
 **EDITSTREAM**パラメーター`es`テキストをバッファーするコールバック関数を指定します。 このコールバック関数は、入力ストリームがなくなるまで繰り返し呼び出されます。  
  
 詳細については、次を参照してください。 [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302)メッセージと[EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&34;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#35;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="streamout"></a>CRichEditCtrl::StreamOut  
 このコンテンツを書き出しますが`CRichEditCtrl`を指定した出力ストリーム オブジェクト。  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormat`  
 出力データ形式を指定するフラグ。 詳細については、「解説」を参照してください。  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)出力ストリームを指定します。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 出力ストリームに書き込まれた文字の数。  
  
### <a name="remarks"></a>コメント  
 値`nFormat`次のいずれかを指定する必要があります。  
  
- `SF_TEXT`テキストだけを書き込むことを示します。  
  
- `SF_RTF`手書きのテキストと書式設定を示します。  
  
- `SF_RTFNOOBJS`OLE アイテムをスペースに置き換えて手書きテキストと書式設定を示します。  
  
- `SF_TEXTIZED`テキストの書き込みと書式設定、OLE アイテムのテキスト表現を示します。  
  
 これらの値のいずれかと組み合わせて使用できます`SFF_SELECTION`します。 場合`SFF_SELECTION`が指定されている`StreamOut`出力ストリームに現在の選択範囲を書き込みます。 このオプションを指定しない場合`StreamOut`この全体のコンテンツを書き出しますが`CRichEditCtrl`オブジェクトです。  
  
 **EDITSTREAM**パラメーター`es`テキストをバッファーするコールバック関数を指定します。 このコールバック関数は、出力ストリームがなくなるまで繰り返し呼び出されます。  
  
 詳細については、次を参照してください。 [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304)メッセージと[EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#36;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&37;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="undo"></a>CRichEditCtrl::Undo  
 リッチ エディット コントロールの最後の操作を元に戻します。  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>戻り値  
 元に戻す操作が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻す操作が元に戻すことができますもあります。 たとえば、最初の呼び出し、削除した文字列を復元する**を元に戻す**します。 2 番目の呼び出しを使用してテキストを削除するには中間の編集操作がない限り、**を元に戻す**します。  
  
 詳細については、次を参照してください。 [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CanUndo](#canundo)します。  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)

