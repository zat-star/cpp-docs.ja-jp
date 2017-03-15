---
title: "CButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CButton
dev_langs:
- C++
helpviewer_keywords:
- CButton class
- checkbox buttons
- pushbuttons
- button control [MFC]
- check boxes, button controls
- button objects (CButton)
- radio buttons, CButton class
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
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
ms.openlocfilehash: 751d4aee2c734acd455734ca694eb88bb149fc09
ms.lasthandoff: 02/24/2017

---
# <a name="cbutton-class"></a>CButton クラス
Windows のボタン コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|`CButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CButton::Create](#create)|Windows のボタン コントロールを作成し、それにアタッチ、`CButton`オブジェクトです。|  
|[CButton::DrawItem](#drawitem)|オーナー描画を描画する上書き`CButton`オブジェクトです。|  
|[CButton::GetBitmap](#getbitmap)|以前、ビットマップのハンドルを取得[SetBitmap](#setbitmap)します。|  
|[CButton::GetButtonStyle](#getbuttonstyle)|ボタン コントロールのスタイルに関する情報を取得します。|  
|[CButton::GetCheck](#getcheck)|ボタン コントロールのチェックの状態を取得します。|  
|[CButton::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)します。|  
|[CButton::GetIcon](#geticon)|既に設定アイコンのハンドルを取得[SetIcon](#seticon)します。|  
|[CButton::GetIdealSize](#getidealsize)|ボタン コントロールの適切なサイズを取得します。|  
|[CButton::GetImageList](#getimagelist)|ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetNote](#getnote)|現在のコマンド リンク コントロールの注釈のコンポーネントを取得します。|  
|[CButton::GetNoteLength](#getnotelength)|現在のコマンド リンク コントロールのメモのテキストの長さを取得します。|  
|[CButton::GetSplitGlyph](#getsplitglyph)|現在の分割ボタン コントロールに関連付けられたグリフを取得します。|  
|[CButton::GetSplitImageList](#getsplitimagelist)|現在の分割ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetSplitInfo](#getsplitinfo)|現在の分割ボタン コントロールを定義する情報を取得します。|  
|[CButton::GetSplitSize](#getsplitsize)|現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を取得します。|  
|[CButton::GetSplitStyle](#getsplitstyle)|現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。|  
|[CButton::GetState](#getstate)|状態の確認、強調表示状態、および button コントロールのフォーカス状態を取得します。|  
|[CButton::GetTextMargin](#gettextmargin)|ボタン コントロールのテキストの余白を取得します。|  
|[CButton::SetBitmap](#setbitmap)|ボタンに表示されるビットマップを指定します。|  
|[CButton::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを変更します。|  
|[CButton::SetCheck](#setcheck)|ボタン コントロールのチェックの状態を設定します。|  
|[CButton::SetCursor](#setcursor)|ボタンに表示されるカーソルのイメージを指定します。|  
|[CButton::SetDropDownState](#setdropdownstate)|現在の分割ボタン コントロールのドロップ ダウン状態に設定します。|  
|[CButton::SetIcon](#seticon)|ボタンに表示されるアイコンを指定します。|  
|[CButton::SetImageList](#setimagelist)|ボタン コントロールのイメージ リストを設定します。|  
|[CButton::SetNote](#setnote)|現在のコマンド リンク コントロールの注釈を設定します。|  
|[CButton::SetSplitGlyph](#setsplitglyph)|指定されたグリフを現在の分割ボタン コントロールに関連付けます。|  
|[CButton::SetSplitImageList](#setsplitimagelist)|イメージ リストを現在の分割ボタン コントロールに関連付けます。|  
|[CButton::SetSplitInfo](#setsplitinfo)|現在の分割ボタン コントロールを定義する情報を指定します。|  
|[CButton::SetSplitSize](#setsplitsize)|現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を設定します。|  
|[CButton::SetSplitStyle](#setsplitstyle)|現在の分割ボタン コントロールのスタイルを設定します。|  
|[CButton::SetState](#setstate)|ボタン コントロールの強調表示の状態を設定します。|  
|[CButton::SetTextMargin](#settextmargin)|ボタン コントロールのテキストの余白を設定します。|  
  
## <a name="remarks"></a>コメント  
 ボタン コントロールは、オンとオフのクリックして可能な小さな四角形の子ウィンドウです。 ボタンは、単独またはグループに使用できますとラベルを設定することができますか、またはテキストなしで表示されます。 ボタンは、ユーザーがクリックしたときに通常の外観を変更します。  
  
 代表的なボタンは、チェック ボックスをオン ラジオ ボタンをプッシュします。 A`CButton`オブジェクトは、次のいずれかになることができます」の手順に従って、[ボタンのスタイル](../../mfc/reference/button-styles.md)によって初期化時に指定されている、[作成](#create)メンバー関数。  
  
 さらに、 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)から派生したクラス`CButton`ラベルがテキストではなくビットマップ イメージでボタン コントロールの作成をサポートします。 A`CBitmapButton`ボタンの下、重点を置いて、および状態を無効になっている別のビットマップことができます。  
  
 ダイアログ テンプレートから、またはコードで直接、ボタン コントロールを作成できます。 どちらの場合も、コンス トラクターを呼び出す最初`CButton`を構築する、`CButton`オブジェクト。 まず、**作成**、ウィンドウを作成するメンバー関数は、コントロールのボタンをクリックし、添付、`CButton`オブジェクトです。  
  
 構築から派生したクラスにワンステップ プロセス`CButton`します。 呼び出しと派生クラスのコンス トラクターを記述**作成**からコンス トラクター内です。  
  
 ボタン コントロールからその親に送信される Windows の通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップ エントリは、次の形式をとります。  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 ここで`id`通知を送信するコントロールの子ウィンドウの ID を指定し、`memberFxn`通知を処理する記述した親メンバー関数の名前を指定します。  
  
 親の関数のプロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 潜在的なメッセージ マップ エントリは次のとおりです。  
  
|マップ エントリ|親のときに送信しています.|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|ユーザーがボタンをクリックします。|  
|**ON_BN_DOUBLECLICKED**|ボタンをダブルクリックします。|  
  
 作成する場合、`CButton`ダイアログ リソースからのオブジェクト、`CButton`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CButton`ウィンドウ内でオブジェクトを破棄する必要があります。 作成する場合、`CButton`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**ボタン コントロールをユーザーがウィンドウを閉じたときに破棄するオブジェクト。 作成する場合、`CButton`またはスタック上のオブジェクトが親ダイアログ オブジェクトに埋め込まれているは自動的に破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecbuttona--cbuttoncbutton"></a><a name="cbutton"></a>CButton::CButton  
 `CButton` オブジェクトを構築します。  
  
```  
CButton();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#1;](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="a-namecreatea--cbuttoncreate"></a><a name="create"></a>CButton::Create  
 Windows のボタン コントロールを作成し、それにアタッチ、`CButton`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszCaption`  
 ボタン コントロールのテキストを指定します。  
  
 `dwStyle`  
 ボタン コントロールのスタイルを指定します。 任意の組み合わせを適用[ボタン スタイル](../../mfc/reference/button-styles.md)ボタンをクリックします。  
  
 `rect`  
 ボタン コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `pParentWnd`  
 通常、ボタン コントロールの親ウィンドウを指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `nID`  
 ボタン コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CButton`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず**作成**、Windows の button コントロールを作成およびそれにアタッチする、`CButton`オブジェクトです。  
  
 場合、 **WS_VISIBLE**スタイルが与えられると、Windows は、ボタン コントロールをアクティブ化し、ボタンを表示するために必要なすべてのメッセージを送信します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)ボタン コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ オーダーにボタンを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#2;](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="a-namedrawitema--cbuttondrawitem"></a><a name="drawitem"></a>CButton::DrawItem  
 オーナー描画ボタンの外観が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体。 構造体には、描画される項目と必要な図面の種類に関する情報が含まれています。  
  
### <a name="remarks"></a>コメント  
 オーナー描画ボタンは、 **BS_OWNERDRAW**一連のスタイルを設定します。 オーナー描画の描画を実装するには、この関数をオーバーライド`CButton`オブジェクトです。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はメンバーの前に終了します。  
  
 参照してください、[うち](../../mfc/reference/button-styles.md)値のスタイルを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#3;](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="a-namegetbitmapa--cbuttongetbitmap"></a><a name="getbitmap"></a>CButton::GetBitmap  
 以前、ビットマップのハンドルを取得するには、このメンバー関数を呼び出す[SetBitmap](#setbitmap)つまり、ボタンに関連付けられています。  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップへのハンドル。 **NULL**ビットマップが既に指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="a-namegetbuttonstylea--cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>CButton::GetButtonStyle  
 ボタン コントロールのスタイルに関する情報を取得します。  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このボタンのスタイルを返します`CButton`オブジェクトです。 この関数だけを返す、[うち](../../mfc/reference/button-styles.md)スタイル値は、任意の他のウィンドウ スタイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="a-namegetchecka--cbuttongetcheck"></a><a name="getcheck"></a>CButton::GetCheck  
 オプション ボタンまたはチェック ボックスのチェックの状態を取得します。  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>戻り値  
 作成されたボタン コントロールからの戻り値、 **BS_AUTOCHECKBOX**、 **BS_AUTORADIOBUTTON**、 **BS_AUTO3STATE**、 **BS_CHECKBOX**、 **BS_RADIOBUTTON**、または**BS_3STATE**スタイルは、次の値のいずれか。  
  
|値|説明|  
|-----------|-------------|  
|**設定されています。**|ボタンの状態がオフになっています。|  
|**BST_CHECKED**|ボタンの状態がチェックされます。|  
|**BST_INDETERMINATE**|ボタンの状態が不定になります (ボタンには、場合にのみ、 **BS_3STATE**または**BS_AUTO3STATE**スタイル)。|  
  
 その他のスタイルをボタンには場合、戻り値は**設定されている**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="a-namegetcursora--cbuttongetcursor"></a><a name="getcursor"></a>CButton::GetCursor  
 以前、カーソルのハンドルを取得するには、このメンバー関数を呼び出す[以前](#setcursor)つまり、ボタンに関連付けられています。  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>戻り値  
 カーソルのイメージへのハンドル。 **NULL**以前にカーソルが指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="a-namegeticona--cbuttongeticon"></a><a name="geticon"></a>CButton::GetIcon  
 以前、アイコンのハンドルを取得するには、このメンバー関数を呼び出す[SetIcon](#seticon)つまり、ボタンに関連付けられています。  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイコンのハンドル。 **NULL**以前にアイコンが指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cbuttongetidealsize"></a><a name="getidealsize"></a>CButton::GetIdealSize  
 ボタン コントロールの適切なサイズを取得します。  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>パラメーター  
 *psize*  
 ボタンの現在のサイズへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETIDEALSIZE** 」の説明に従って、メッセージ、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)のセクションで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetimagelista--cbuttongetimagelist"></a><a name="getimagelist"></a>CButton::GetImageList  
 ボタン コントロールからのイメージの一覧を取得するには、このメソッドを呼び出します。  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbuttonImagelist`  
 イメージ リストへのポインター、`CButton`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETIMAGELIST** 」の説明に従って、メッセージ、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)のセクションで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetnotea--cbuttongetnote"></a><a name="getnote"></a>CButton::GetNote  
 現在のコマンド リンク コントロールに関連付けられているメモのテキストを取得します。  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpszNote`|呼び出し元が割り当てと解放を担当するバッファーへのポインター。 戻り値が場合`true`バッファーには、現在のコマンド リンク コントロールに関連付けられている以外の場合は、メモのテキストが含まれている、バッファーは変更されません。|  
|[入力、出力] `cchNote`|符号なし整数型の変数へのポインター。<br /><br /> 指定したバッファーのサイズが、変数にこのメソッドが呼び出されると、`lpszNote`パラメーター。<br /><br /> このメソッドが返す場合、戻り値が場合`true`変数には、現在のコマンド リンク コントロールに関連付けられている注釈のサイズが含まれています。 戻り値が場合`false`変数には、メモの格納に必要なバッファー サイズが含まれています。|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードで、 [CString](../../atl-mfc-shared/using-cstring.md)を現在のコマンド リンク コントロールに関連付けられているメモのテキストを含むオブジェクト。  
  
 または  
  
 2 番目のオーバー ロードで`true`場合、このメソッドは正常でない場合は`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetnotelengtha--cbuttongetnotelength"></a><a name="getnotelength"></a>CButton::GetNoteLength  
 現在のコマンド リンク コントロールのメモのテキストの長さを取得します。  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のコマンド リンク コントロールの 16 ビット Unicode 文字のメモのテキストの長さ。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetsplitglypha--cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>CButton::GetSplitGlyph  
 現在の分割ボタン コントロールに関連付けられたグリフを取得します。  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の分割ボタン コントロールに関連付けられたグリフの文字。  
  
### <a name="remarks"></a>コメント  
 グリフとは、特定のフォントの文字の物理的に表したものです。 たとえば、分割ボタン コントロールは、チェック マークの Unicode 文字のグリフで装飾できます可能性があります (u+2713)。  
  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_GLYPH`フラグ、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)メッセージに記載されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドがからグリフを取得するメッセージの関数から制御が戻るとき、`himlGlyph`構造体のメンバーです。  
  
##  <a name="a-namegetsplitimagelista--cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>CButton::GetSplitImageList  
 取得、[イメージ リスト](../../mfc/reference/cimagelist-class.md)の現在の分割ボタン コントロールです。  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_IMAGE`フラグ、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)メッセージに記載されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドは、イメージの一覧から取得メッセージ関数から制御が戻るとき、`himlGlyph`構造体のメンバーです。  
  
##  <a name="a-namegetsplitinfoa--cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>CButton::GetSplitInfo  
 現在の分割ボタン コントロールの描画方法を決定するパラメーターを取得します。  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pInfo`|ポインター、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)現在の分割ボタン コントロールに関する情報を受け取る構造体。 呼び出し元は、構造体の割り当てをします。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetsplitsizea--cbuttongetsplitsize"></a><a name="getsplitsize"></a>CButton::GetSplitSize  
 現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を取得します。  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pSize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)四角形の名前を受け取る構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタン コントロールを展開すると、ページャー コントロールまたはリスト コントロールのようなドロップダウン コンポーネントを表示できます。 このメソッドは、ボックスの一覧のコンポーネントを含む外接する四角形を取得します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_SIZE`フラグ、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)メッセージに記載されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドがから外接する四角形を取得するメッセージの関数から制御が戻るとき、`size`構造体のメンバーです。  
  
##  <a name="a-namegetsplitstylea--cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>CButton::GetSplitStyle  
 現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ボタン スタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタンのスタイルは、配置、縦横比、および Windows で分割ボタンのアイコンを描画するため、グラフィカルな形式を指定します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_STYLE`フラグ、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)メッセージに記載されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 このメソッドがから分割ボタンのスタイルを取得するメッセージの関数から制御が戻るとき、`uSplitStyle`構造体のメンバーです。  
  
##  <a name="a-namegetstatea--cbuttongetstate"></a><a name="getstate"></a>CButton::GetState  
 ボタン コントロールの状態を取得します。  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタン コントロールの現在の状態を示す値の組み合わせを含むビット フィールドです。 次の表は、指定できる値を示します。  
  
|ボタンの状態|値|説明|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|初期状態です。|  
|`BST_CHECKED`|0x0001|ボタン コントロールがチェックされます。|  
|`BST_INDETERMINATE`|0x0002|不確定な (のみ可能なボタン コントロールに&3; つの状態がある場合) です。|  
|`BST_PUSHED`|0x0004|ボタン コントロールをクリックします。|  
|`BST_FOCUS`|0x0008|ボタン コントロールにフォーカスが移動するとします。|  
  
### <a name="remarks"></a>コメント  
 ボタン コントロール、`BS_3STATE`または`BS_AUTO3STATE`ボタン スタイルは、中間の状態という&3; つ目の状態にあるチェック ボックスを作成します。 不確定な状態は、チェック ボックスがオンでもオンになっていないことを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="a-namegettextmargina--cbuttongettextmargin"></a><a name="gettextmargin"></a>CButton::GetTextMargin  
 テキストの余白を取得するには、このメソッドを呼び出して、`CButton`オブジェクトです。  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>パラメーター  
 `pmargin`  
 テキストの右側部分へのポインター、`CButton`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 テキストの余白を返します。  
  
### <a name="remarks"></a>コメント  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETTEXTMARGIN** 」の説明に従って、メッセージ、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)のセクションで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetbitmapa--cbuttonsetbitmap"></a><a name="setbitmap"></a>CButton::SetBitmap  
 新しいビットマップをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 ビットマップのハンドル。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているビットマップのハンドル。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、既定で中央揃え ボタンの表面に自動的に配置されます。 ビットマップが大きすぎるボタンのいずれかの側クリップされます。 次のような配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用して`SetBitmap`ボタンあたり&1; つだけのビットマップを使用します。 ボタンが押されたときにシフトし、右下に、ビットマップが表示されます。  
  
 関連付けが済んだら、ビットマップの解放を担当しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="a-namesetbuttonstylea--cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>CButton::SetButtonStyle  
 ボタンのスタイルを変更します。  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyle`  
 指定、[ボタンのスタイル](../../mfc/reference/button-styles.md)します。  
  
 `bRedraw`  
 ボタンを再描画されるかどうかを指定します。 0 以外の値には、ボタンが再描画します。 値が 0 に、ボタンが再描画されません。 ボタンは既定で再描画されます。  
  
### <a name="remarks"></a>コメント  
 使用して、`GetButtonStyle`ボタン スタイルを取得します。 完了ボタン スタイルの下位ワードは、特定のボタンのスタイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="a-namesetchecka--cbuttonsetcheck"></a><a name="setcheck"></a>CButton::SetCheck  
 設定またはオプション ボタンまたはチェック ボックスのチェックの状態をリセットします。  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCheck`  
 チェックの状態を指定します。 このパラメーターは、次のいずれかになります。  
  
|値|説明|  
|-----------|-------------|  
|**設定されています。**|ボタンの状態をオフに設定します。|  
|**BST_CHECKED**|チェック ボタンの状態を設定します。|  
|**BST_INDETERMINATE**|中間に、ボタンの状態を設定します。 ボタンがある場合のみ、この値を使用できる、 **BS_3STATE**または**BS_AUTO3STATE**スタイル。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、プッシュ ボタンに影響を与えません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="a-namesetcursora--cbuttonsetcursor"></a><a name="setcursor"></a>CButton::SetCursor  
 新しいカーソルをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>パラメーター  
 `hCursor`  
 カーソルのハンドル。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているカーソルのハンドル。  
  
### <a name="remarks"></a>コメント  
 カーソルは既定で中央揃え ボタンの表面に自動的に配置されます。 カーソルが大きすぎるボタンのいずれかの側クリップされます。 次のような配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用して`SetCursor`ボタンごとに&1; つだけのカーソルを使用します。 ボタンが押されたときに移動し、右下にカーソルが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="a-namesetdropdownstatea--cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>CButton::SetDropDownState  
 現在の分割ボタン コントロールのドロップ ダウン状態に設定します。  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fDropDown`|`true`設定する`BST_DROPDOWNPUSHED`状態以外の場合、`false`です。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 分割ボタン コントロールのスタイルを持つ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`ボタンと右側の下向きの矢印で構成されます。 詳細については、次を参照してください。[ボタン スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775951)します。 通常は、ドロップ ダウン状態では、ドロップダウン矢印をクリックするには設定されます。 コントロールのドロップダウンの状態をプログラムで設定するのにには、このメソッドを使用します。 下向きの矢印は、状態を示す網掛けが描画されます。  
  
 このメソッドは、送信、 [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`つまり、分割ボタン コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、ドロップダウン矢印を送ることを示すために、分割ボタン コントロールの状態を設定します。  
  
 [!code-cpp[NVC_MFC_CButton_s1&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="a-namesetelevationrequireda--cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>CButton::SetElevationRequired  
 現在のボタン コントロールの状態を設定`elevation required`、これは、管理者特権で [セキュリティ] アイコンを表示するコントロールのために必要なです。  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fElevationRequired`|`true`設定する`elevation required`状態以外の場合、`false`です。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタンやコマンドのリンク コントロールには、アクションの実行に管理者特権でのセキュリティ アクセス許可が必要とする場合は、コントロールを設定`elevation required`状態です。 その後、Windows では、コントロールにユーザー アカウント制御 (UAC) 盾のアイコンが表示されます。 詳細についてにある「ユーザー アカウント制御」を参照してください。 [MSDN](http://go.microsoft.com/fwlink/linkid=18507)します。  
  
 このメソッドは、送信、[した BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameseticona--cbuttonseticon"></a><a name="seticon"></a>CButton::SetIcon  
 新しいアイコンをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 アイコンのハンドル。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているアイコンのハンドル。  
  
### <a name="remarks"></a>コメント  
 アイコンは、既定で中央揃え ボタンの表面に自動的に配置されます。 ボタンのアイコンが大きすぎる、または左側クリップされます。 次のような配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用して`SetIcon`ボタンあたり&1; つだけのアイコンを使用します。 ボタンが押されたときに、シフトし、右下に、アイコンが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="a-namesetimagelista--cbuttonsetimagelist"></a><a name="setimagelist"></a>CButton::SetImageList  
 イメージ リストを設定するには、このメソッドを呼び出して、`CButton`オブジェクトです。  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbuttonImagelist`  
 新しいイメージ リストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_SETIMAGELIST** 」の説明に従って、メッセージ、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)のセクションで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetnotea--cbuttonsetnote"></a><a name="setnote"></a>CButton::SetNote  
 現在のコマンド リンク コントロールのメモのテキストを設定します。  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `lpszNote`|コマンド リンク コントロールのメモのテキストとして設定されている Unicode 文字列へのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_cmdLink`、つまりコマンド リンク コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、コマンド リンク コントロールのメモのテキストを設定します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="a-namesetsplitglypha--cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>CButton::SetSplitGlyph  
 指定されたグリフを現在の分割ボタン コントロールに関連付けます。  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `chGlyph`|分割ボタンのドロップダウン矢印として使用するグリフを指定する文字。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルのコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 グリフとは、特定のフォントの文字の物理的に表したものです。 `chGlyph`パラメーターは、グリフには使用されませんが、代わりにシステム定義のグリフのセットからのグリフの選択に使用します。 既定の下向き矢印グリフでは、文字 '6' で指定され、Unicode 文字 (U +&25;BC) 黒ダウン右向き三角形のようになります。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_GLYPH`フラグと`himlGlyph`を持つメンバー、`chGlyph`パラメーター、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)に記載されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetsplitimagelista--cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>CButton::SetSplitImageList  
 関連付けます、[イメージ リスト](../../mfc/reference/cimagelist-class.md)現在の分割ボタン コントロールにします。  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pSplitImageList`|ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトを現在の分割ボタン コントロールに代入します。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_IMAGE`フラグと`himlGlyph`を持つメンバー、`pSplitImageList`パラメーター、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)に記載されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetsplitinfoa--cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>CButton::SetSplitInfo  
 現在の分割ボタン コントロールの描画方法を決定するパラメーターを指定します。  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pInfo`|ポインター、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)を現在の分割ボタン コントロールを定義します。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、送信、 [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`つまり、分割ボタン コントロールをプログラムでアクセスするために使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、分割ボタンのドロップダウン矢印に使用するグリフを変更します。 上向き三角形のグリフ既定下向きの三角形のグリフの例に置換されます。 指定した文字に表示されるグリフの依存、`himlGlyph`のメンバー、`BUTTON_SPLITINFO`構造体。 下向きの三角形のグリフが文字 '6 で指定された' と '5 文字で、上向き三角形のグリフが指定された' です。 比較については、便利なメソッドを参照してください。 [CButton::SetSplitGlyph](#setsplitglyph)します。  
  
 [!code-cpp[NVC_MFC_CButton_s1&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="a-namesetsplitsizea--cbuttonsetsplitsize"></a><a name="setsplitsize"></a>CButton::SetSplitSize  
 現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を設定します。  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pSize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)外接する四角形を表す構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタン コントロールを展開すると、ページャー コントロールまたはリスト コントロールのようなドロップダウン コンポーネントを表示できます。 このメソッドは、ボックスの一覧のコンポーネントを含む外接する四角形のサイズを指定します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_SIZE`フラグと`size`を持つメンバー、`pSize`パラメーター、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)に記載されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`つまり、分割ボタン コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例には、分割ボタンのドロップダウン矢印のサイズが&2; 倍にします。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="a-namesetsplitstylea--cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>CButton::SetSplitStyle  
 現在の分割ボタン コントロールのスタイルを設定します。  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uSplitStyle`|分割ボタン スタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタン スタイルがコントロールでのみ`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタンのスタイルは、配置、縦横比、および Windows で分割ボタンのアイコンを描画するため、グラフィカルな形式を指定します。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_STYLE`フラグと`uSplitStyle`を持つメンバー、`uSplitStyle`パラメーター、および、構造体の送信、[したり](http://msdn.microsoft.com/library/windows/desktop/bb775969)に記載されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`つまり、分割ボタン コントロールをプログラムでアクセスするために使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、分割ボタンのドロップダウン矢印のスタイルを設定します。 `BCSS_ALIGNLEFT`スタイルは、ボタンの左側にある矢印を表示し、`BCSS_STRETCH`スタイルは、ボタンのサイズを変更するときにドロップダウン矢印の比率を保持します。  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="a-namesetstatea--cbuttonsetstate"></a><a name="setstate"></a>CButton::SetState  
 ボタン コントロールを強調表示すると、かどうかを設定します。  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>パラメーター  
 *bHighlight*  
 ボタンが強調表示されるかどうかを指定します。 0 以外の値には、ボタンが強調表示します。値 0 は、任意の強調表示を削除します。  
  
### <a name="remarks"></a>コメント  
 ボタン コントロールの外観に影響を強調表示します。 オプション ボタンまたはチェック ボックスのチェックの状態に影響を与えません。  
  
 ユーザーがクリックするし、マウスの左ボタンを保持して、ボタン コントロールは自動的に強調表示されます。 ユーザーがマウス ボタンを離すと、強調表示は削除されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton&#9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="a-namesettextmargina--cbuttonsettextmargin"></a><a name="settextmargin"></a>CButton::SetTextMargin  
 テキストの余白を設定するには、このメソッドを呼び出して、`CButton`オブジェクトです。  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>パラメーター  
 `pmargin`  
 新しいテキスト マージンへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_SETTEXTMARGIN** 」の説明に従って、メッセージ、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)のセクションで、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton クラス](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

