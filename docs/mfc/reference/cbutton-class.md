---
title: "CButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ボタン コントロール [MFC]"
  - "ボタン オブジェクト (CButton)"
  - "CButton クラス"
  - "チェック ボックス, ボタン コントロール"
  - "チェック ボックス ボタン"
  - "プッシュ ボタン"
  - "オプション ボタン, CButton クラス"
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のボタン コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CButton : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CButton::CButton](../Topic/CButton::CButton.md)|`CButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CButton::Create](../Topic/CButton::Create.md)|Windows のボタン コントロールを作成し、`CButton` のオブジェクトにアタッチします。|  
|[CButton::DrawItem](../Topic/CButton::DrawItem.md)|`CButton` のオーナー描画オブジェクトを描画します。|  
|[CButton::GetBitmap](../Topic/CButton::GetBitmap.md)|前に [SetBitmap](../Topic/CButton::SetBitmap.md)に設定されているビットマップのハンドルを取得します。|  
|[CButton::GetButtonStyle](../Topic/CButton::GetButtonStyle.md)|ボタン コントロールのスタイルについての情報を取得します。|  
|[CButton::GetCheck](../Topic/CButton::GetCheck.md)|ボタン コントロールのチェック状態を取得します。|  
|[CButton::GetCursor](../Topic/CButton::GetCursor.md)|前に [SetCursor](../Topic/CButton::SetCursor.md)に設定されているカーソルのイメージのハンドルを取得します。|  
|[CButton::GetIcon](../Topic/CButton::GetIcon.md)|前に [SetIcon](../Topic/CButton::SetIcon.md)で設定されるアイコンのハンドルを取得します。|  
|[CButton::GetIdealSize](../Topic/CButton::GetIdealSize.md)|ボタン コントロールの適切なサイズを取得します。|  
|[CButton::GetImageList](../Topic/CButton::GetImageList.md)|ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetNote](../Topic/CButton::GetNote.md)|現在のコマンド リンクのコントロールのメモのコンポーネントを取得します。|  
|[CButton::GetNoteLength](../Topic/CButton::GetNoteLength.md)|現在のコマンド リンクのコントロールの注釈テキストの長さを取得します。|  
|[CButton::GetSplitGlyph](../Topic/CButton::GetSplitGlyph.md)|現在の分割ボタン コントロールに関連付けられているグリフを取得します。|  
|[CButton::GetSplitImageList](../Topic/CButton::GetSplitImageList.md)|現在の分割ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetSplitInfo](../Topic/CButton::GetSplitInfo.md)|現在の分割ボタン コントロールを定義する情報を取得します。|  
|[CButton::GetSplitSize](../Topic/CButton::GetSplitSize.md)|現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を取得します。|  
|[CButton::GetSplitStyle](../Topic/CButton::GetSplitStyle.md)|現在の分割ボタン コントロールを定義する分割ボタンのスタイルを取得します。|  
|[CButton::GetState](../Topic/CButton::GetState.md)|ボタン コントロールのチェック状態、強調表示状態とフォーカスの状態を取得します。|  
|[CButton::GetTextMargin](../Topic/CButton::GetTextMargin.md)|ボタン コントロールのテキストのマージンを取得します。|  
|[CButton::SetBitmap](../Topic/CButton::SetBitmap.md)|ボタンに表示するビットマップを指定します。|  
|[CButton::SetButtonStyle](../Topic/CButton::SetButtonStyle.md)|ボタンのスタイルを変更します。|  
|[CButton::SetCheck](../Topic/CButton::SetCheck.md)|ボタン コントロールのチェック状態を設定します。|  
|[CButton::SetCursor](../Topic/CButton::SetCursor.md)|ボタンに表示するカーソル イメージを指定します。|  
|[CButton::SetDropDownState](../Topic/CButton::SetDropDownState.md)|現在の分割ボタン コントロールのドロップダウン状態を設定します。|  
|[CButton::SetIcon](../Topic/CButton::SetIcon.md)|ボタンに表示するアイコンを指定します。|  
|[CButton::SetImageList](../Topic/CButton::SetImageList.md)|ボタン コントロールのイメージ リストを設定します。|  
|[CButton::SetNote](../Topic/CButton::SetNote.md)|現在のコマンド リンクのコントロールのメモを設定します。|  
|[CButton::SetSplitGlyph](../Topic/CButton::SetSplitGlyph.md)|現在の分割ボタン コントロールで指定したグリフを関連付けます。|  
|[CButton::SetSplitImageList](../Topic/CButton::SetSplitImageList.md)|現在の分割ボタン コントロールでイメージ リストを関連付けます。|  
|[CButton::SetSplitInfo](../Topic/CButton::SetSplitInfo.md)|現在の分割ボタン コントロールを定義する情報を指定します。|  
|[CButton::SetSplitSize](../Topic/CButton::SetSplitSize.md)|現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を設定します。|  
|[CButton::SetSplitStyle](../Topic/CButton::SetSplitStyle.md)|現在の分割ボタン コントロールのスタイルを設定します。|  
|[CButton::SetState](../Topic/CButton::SetState.md)|ボタン コントロールの強調表示された状態を設定します。|  
|[CButton::SetTextMargin](../Topic/CButton::SetTextMargin.md)|ボタン コントロールのテキストのマージンを設定します。|  
  
## 解説  
 ボタン コントロールはオンとオフをクリックできる、小さい四角形の子ウィンドウです。  ボタンは、一つまたはグループで使用し、ラベル、テキストなしで表示できます。  ボタンは、通常、ユーザーがクリックすると外観を変更します。  
  
 一般的なボタン、チェック ボックス、ラジオ ボタンおよびプッシュ ボタンです。  [&#91;作成&#93;](../Topic/CButton::Create.md) のメンバー関数によって初期化で指定された `CButton` のオブジェクトは、これらの [ボタンのスタイル](../../mfc/reference/button-styles.md) に従って行うことができます。  
  
 また、[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) のクラスはテキストではなく、ビットマップ イメージとラベル ボタン コントロールの `CButton` サポートの作成から書き込みます。  `CBitmapButton` をローカライズするボタン、および無効にされた状態の別のビットマップを持つことができます。  
  
 ダイアログ テンプレートから直接またはコードのボタン コントロールを作成できます。  いずれの場合も、最初の呼び出し `CButton``CButton` のオブジェクトを構築するコンストラクター; 次に、Windows のボタン コントロールを作成し、`CButton` のオブジェクトにアタッチするに **\[作成\]** のメンバー関数を呼び出します。  
  
 構造体は `CButton`から派生したクラスのワンの手順プロセスです。  派生クラスのコンストラクターを書き込み、コンストラクター内で **\[作成\]** を呼び出します。  
  
 親 \(通常は [CDialog](../../mfc/reference/cdialog-class.md)の派生クラス\) にボタン コントロールに送られた Windows の通知メッセージを処理するには、各メッセージの親クラスにメッセージ マップのエントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップのエントリは次の形式を持ちます。  
  
 **ON\_**通知**\(**`id`、`memberFxn`**\)**  
  
 `id` が送信するコントロールの子ウィンドウ ID を指定します。`memberFxn` は、通知と通知を処理する、記述された親メンバー関数の名前です。  
  
 親の関数のプロトタイプは次のようになります。  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 有効なメッセージ マップのエントリは次のとおりです。:  
  
|マップ エントリ|…時拡張するために送信されます。|  
|--------------|----------------------|  
|**ON\_BN\_CLICKED**|ユーザーがボタンをクリックします。|  
|**ON\_BN\_DOUBLECLICKED**|ユーザーがボタンをダブルクリックします。|  
  
 ダイアログ リソースから `CButton` のオブジェクトを作成する場合は、`CButton` のオブジェクトでは、ユーザーがダイアログ ボックスを閉じると、破棄されます。  
  
 ウィンドウ内の `CButton` のオブジェクトを作成する場合は、オブジェクトを破棄する必要があります。  **new** 関数を使ってヒープ領域の `CButton` のオブジェクトを作成し、ユーザーが Windows のボタン コントロールを閉じるときに破棄するオブジェクトの **\[削除\]** を呼び出す必要があります。  スタックの `CButton` のオブジェクトを作成または親ダイアログ オブジェクトに埋め込まれている場合は、自動的に破棄されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CButton`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../Topic/CEdit%20Class.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../Topic/CStatic%20Class.md)   
 [CBitmapButton クラス](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)