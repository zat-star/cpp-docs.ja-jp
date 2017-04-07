---
title: "CMFCKeyMapDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCKeyMapDialog class
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
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
ms.openlocfilehash: 6599f5c3cda6eb407f4545d42528c1c68950b94c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog クラス
`CMFCKeyMapDialog`クラスは、コマンド、キーボードのキーを割り当てるコントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|`CMFCKeyMapDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|キーボードのマップ ダイアログ ボックスが表示されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|キーのマッピングを表す文字列を構築するためにフレームワークによって呼び出されます。 既定では、文字列には、コマンド名、ショートカット キー、およびショートカット キーの説明が含まれています。|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|指定されたコマンドに関連付けられているショートカット キーの一覧を含む文字列を取得します。|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|キーボード マップ コントロールをサポートする内部リスト コントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|新しいページのキーボード マップのヘッダーを印刷するために、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|キーボード マップ項目を印刷するためにフレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列のキャプションを設定するためにフレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**印刷** ボタンをクリックします。|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列の幅を設定するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 使用して、`CMFCKeyMapDialog`サイズ変更可能なキーボード マップ ダイアログ ボックスを実装するクラス。 ダイアログ ボックスでは、キーボード ショートカットとそれに関連付けられているコマンドを表示するのにリスト ビュー コントロールを使用します。  
  
 使用する、`CMFCKeyMapDialog`クラスのアプリケーションで、ポインターを渡すメイン フレーム ウィンドウへのパラメーターとして、`CMFCKeyMapDialog`コンス トラクターです。 まず、`DoModal`モーダル ダイアログ ボックスを起動する方法です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxkeymapdialog.h  
  
##  <a name="cmfckeymapdialog"></a>CMFCKeyMapDialog::CMFCKeyMapDialog  
 `CMFCKeyMapDialog` オブジェクトを構築します。  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParentFrame`  
 親ウィンドウへのポインター、`CMFCKeyMapDialog`オブジェクトです。  
  
 [入力] `bEnablePrint`  
 `TRUE`アクセラレータ キーの一覧を印刷する場合それ以外の場合、`FALSE`です。 既定値は、`FALSE` です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCKeyMapDialog`クラスです。 この例は、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&21;](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CMFCKeyMapDialog::DoModal  
 キーボードのマップ ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 符号付き整数など`IDOK`または`IDCANCEL`、つまりに渡される、 [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog)メソッドです。 メソッドは、さらに、ダイアログ ボックスを閉じます。 詳細については、次を参照してください。 [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal)します。  
  
### <a name="remarks"></a>コメント  
 キーボード マップ ダイアログ ボックスを選択し、コマンドのさまざまなカテゴリにアクセラレータ キーを設定できます。 さらに、選択したアクセラレータ キーとその説明をクリップボードにコピーすることができます。  
  
##  <a name="formatitem"></a>CMFCKeyMapDialog::FormatItem  
 キーのマッピングを表す文字列を構築するためにフレームワークによって呼び出されます。 既定では、文字列には、コマンド名、ショートカット キー、およびショートカット キーの説明が含まれています。  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItem`  
 キー マップの内部リストに項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A`CString`を書式設定された項目のテキストを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcommandkeys"></a>CMFCKeyMapDialog::GetCommandKeys  
 文字列値を取得します。 文字列には、指定されたコマンドに関連付けられているショートカット キーの一覧が含まれています。  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 コマンド id。  
  
### <a name="return-value"></a>戻り値  
 セミコロンで区切られた、指定されたコマンドに関連付けられているショートカット キーの (';') の一覧です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oninsertitem"></a>CMFCKeyMapDialog::OnInsertItem  
 キーボード マップ コントロールをサポートする内部リスト コントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 キーボードのキーの組み合わせをコマンドの名前と説明にマップするために使用するツール バー ボタンへのポインター。 キー マップ項目は、内部リスト コントロールに格納されます。  
  
 [入力] `nItem`  
 内部リスト コントロールに新しいキー マップ項目を挿入する場所を指定する&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onprintheader"></a>CMFCKeyMapDialog::OnPrintHeader  
 新しいページのキーボード マップのヘッダーを印刷するために、フレームワークによって呼び出されます。  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dc`  
 プリンター デバイス コンテキスト。  
  
 [入力] `nPage`  
 印刷するページ番号です。  
  
 [入力] `cx`  
 ピクセル単位でヘッダーの横方向のオフセット。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、印刷したテキストの高さ。 詳細については、の戻り値を参照してください[CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、キーボード マップを印刷します。 既定では、このメソッドは、ページ番号、アプリケーション名、およびダイアログ ボックスのタイトルを出力します。  
  
##  <a name="onprintitem"></a>CMFCKeyMapDialog::OnPrintItem  
 キーボード マップ項目を印刷するためにフレームワークによって呼び出されます。  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dc`  
 プリンター デバイス コンテキスト。  
  
 [入力] `nItem`  
 印刷する項目の&0; から始まるインデックス。  
  
 [入力] `y`  
 ページの上部と項目の位置の垂直オフセット。  
  
 [入力] `cx`  
 ページの左側と項目の位置の水平方向のオフセット。  
  
 [入力] `bCalcHeight`  
 `TRUE`最適な印刷項目の高さを計算するには`FALSE`を切り捨てます印刷既定の領域に収まるようにします。  
  
### <a name="return-value"></a>戻り値  
 印刷対象の項目の高さ。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、キー マップ ダイアログ ボックスの項目を印刷するには、このメソッドを呼び出します。 既定では、このメソッドは、項目のコマンド名、ショートカット キー、およびコマンドの説明を出力します。  
  
##  <a name="onsetcolumns"></a>CMFCKeyMapDialog::OnSetColumns  
 キーボード マップ コントロールをサポートする内部リスト コントロール内の列のキャプションを設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは、3 つのリソースから列のキャプションを取得します。 コマンドの列のキャプション IDS_AFXBARRES_COMMAND、IDS_AFXBARRES_KEYS からのキー列のキャプションは、説明列のキャプションは IDS_AFXBARRES_DESCRIPTION から。  
  
##  <a name="printkeymap"></a>CMFCKeyMapDialog::PrintKeyMap  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**印刷** ボタンをクリックします。  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>コメント  
 `PrintKeyMap`メソッドは、キー マップに出力します。 新しい印刷ジョブを開始し、繰り返し呼び出し、 [CMFCKeyMapDialog::OnPrintHeader](#onprintheader)と[CMFCKeyMapDialog::OnPrintItem](#onprintitem)キーのすべてのマッピングが印刷されるまでの方法です。  
  
##  <a name="setcolumnswidth"></a>CMFCKeyMapDialog::SetColumnsWidth  
 キーボード マップ コントロールをサポートする内部リスト コントロール内の列の幅を設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、内部リスト コントロールの列を既定の幅に設定します。 最初に、ショートカット キー列の幅が計算されます。 Command 列に残りの幅の&3; 分の&1; が割り当てられているし、残りの&2;/3 は、[説明] 列に割り当てられます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)

