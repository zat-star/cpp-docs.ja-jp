---
title: "テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "通知メッセージ"
  - "ON_NOTIFY メッセージ"
  - "ON_NOTIFY_EX メッセージ"
  - "ON_NOTIFY_EX_RANGE メッセージ"
  - "ON_NOTIFY_RANGE メッセージ"
  - "TN061"
  - "WM_NOTIFY メッセージ"
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートは **WM\_NOTIFY** 新しいメッセージについての背景情報を提供し、MFC アプリケーションで **WM\_NOTIFY** メッセージを処理する推奨 \(および最も一般的な方法について説明します。  
  
 **Windows 3.x 通知メッセージ**  
  
 Windows 3.x では、コントロールは親にメッセージを送信することによって、コンテンツのマウス クリックなどのイベントの親を変更および選択およびコントロールの背景を描画します。  単純な通知は `wParam` にパック通知コード \(**BN\_CLICKED**など\) とコントロール ID と `lParam`のコントロール ハンドルを持つ **WM\_COMMAND** 特別なメッセージとして送信されます。  追加データを渡す方法がないことを `lParam` が完了したことを `wParam` からことに注意し、これらのメッセージは、単純な通知のみです。  たとえば、**BN\_CLICKED** 通知に、ボタンがクリックされたときのマウス カーソルの位置に関する情報を送信する方法はありません。  
  
 Windows 3.x のコントロールが追加データを含む通知メッセージを送信する必要がある場合は、さまざまな目的のメッセージを、`WM_CTLCOLOR`が、`WM_VSCROLL`、`WM_HSCROLL`、`WM_DRAWITEM`、`WM_MEASUREITEM`、`WM_COMPAREITEM`、`WM_DELETEITEM`、`WM_CHARTOITEM`、`WM_VKEYTOITEM`などを使用します。  これらのメッセージは、クッキーを送信するコントロールに対して反映できます。  詳細については、「[TN062: Windows のコントロールのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)」を参照してください。  
  
 **Win32 の通知メッセージ**  
  
 Windows 3.1 にあるコントロールについては、Win32 API は、Windows 3.x.で使用された通知メッセージのほとんどを使用します。  ただし、Win32 には、いくつかの高度な Windows 3.x.でサポートされるメソッドへの複雑なコントロールを追加します。  多くの場合、通知メッセージに関する追加データを送信するこれらコントロールが。  追加データを必要とする新しい通知の **WM\_\*** 新しいメッセージを追加するのではなく、Win32 API のデザイナーは、1 種類のメッセージ、標準化された方法の追加データ量を渡すことができる **WM\_NOTIFY**の追加を選択します。  
  
 **WM\_NOTIFY** メッセージが `wParam` に送信するコントロールの ID をメッセージと構造に `lParam`ポインターに含まれています。  この構造は **NMHDR** 構造体または最初のメンバーとして **NMHDR** 構造体が大きい構造です。  使用するための方法によってキャストしたか **NMHDR** のメンバーを 1 なので、この構造体へのポインターが **NMHDR** へのポインター、またはより大きな構造体へのポインターとして使用できることに注意してください。  
  
 ほとんどの場合、ポインターがより大きな構造体をポイントし、それを使用するときにキャストする必要があります。  いくつかの通知のみで、\(名前が **NM\_**で始まる\) に共通の通知とツール ヒント コントロールの **TTN\_SHOW** と **TTN\_POP** 通知など、実際に使用される **NMHDR** 構造体です。  
  
 **NMHDR** 構造体または最初のメンバーは送信コントロール ハンドルと ID をメッセージと通知コードなどがあります \(**TTN\_SHOW**など\)。  **NMHDR** 構造体の形式を次に示します。:  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 **TTN\_SHOW** メッセージについては、**コード** のメンバーは **TTN\_SHOW**に設定されます。  
  
 ほとんどの通知は、メンバーとして **NMHDR** 構造体を含む大きな構造体へのポインターを渡します。  たとえば、構造体をキーが押されたときにリスト ビュー コントロール、リスト ビュー コントロールの **LVN\_KEYDOWN** 通知メッセージとともに使用することを検討してください。  ポインターは、次に示すように定義されている **LV\_KEYDOWN** 構造体を指す場合:  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 **NMHDR** のメンバーがこの構造の 1 番目であるため、通知メッセージに渡されたポインターが **NMHDR** へのポインターまたは **LV\_KEYDOWN**へのポインターにキャストする可能性があることに注意してください。  
  
 **新しいウィンドウのすべてのコントロールに共通する通知**  
  
 ある通知が新しいウィンドウのすべてのコントロールに共通です。  これらの通知は **NMHDR** 構造体へのポインターを渡します。  
  
|通知コード|送信されるためです。|  
|-----------|----------------|  
|**NM\_CLICK**|コントロールのユーザーがマウスの左ボタンでクリックする|  
|**NM\_DBLCLK**|コントロールのユーザーがダブルクリックされたマウスの左ボタン|  
|**NM\_RCLICK**|コントロールのユーザーが右クリックされたボタン|  
|**NM\_RDBLCLK**|コントロールのユーザーがダブルクリックされる右ボタン|  
|**NM\_RETURN**|ユーザーはコントロールに入力フォーカスがあるときに Enter キーが押される|  
|**NM\_SETFOCUS**|指定入力フォーカスを制御します。|  
|**NM\_KILLFOCUS**|コントロールが入力フォーカスを失いました|  
|**NM\_OUTOFMEMORY**|コントロールは、使用できる十分なメモリがないため、操作を完了できませんでした。|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON\_NOTIFY: MFC アプリケーションの WM\_NOTIFY メッセージ処理  
 関数の `CWnd::OnNotify` ハンドルの通知メッセージ。  既定の実装は、通知ハンドラーが呼び出すことができるようにメッセージ マップを確認します。  一般に、`OnNotify`をオーバーライドしません。  代わりに、ハンドラー関数を提供し、オーナー ウィンドウ クラスのメッセージ マップにそのハンドラーに対するメッセージ マップ エントリを追加します。  
  
 ClassWizard は、ClassWizard プロパティ シートで、`ON_NOTIFY` のメッセージ マップのエントリを作成し、スケルトン ハンドラー関数を指定できます。  この操作を簡単に行うために ClassWizard の詳細については [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照します。  
  
 `ON_NOTIFY` のメッセージ マップ マクロに次の構文があります:  
  
```  
  
ON_NOTIFY( wNotifyCode, id, memberFxn )  
```  
  
 斜体のパラメーターは次のとおりのどこに置き換えるか:  
  
 `wNotifyCode`  
 **LVN\_KEYDOWN**など、処理されるよう通知メッセージのコード。  
  
 `id`  
 通知が送信されるコントロールの子識別子。  
  
 `memberFxn`  
 この通知が送信されるときに呼び出すメンバー関数。  
  
 このメンバー関数は、次のプロトタイプを宣言する必要があります:  
  
```  
  
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 解説  
 斜体のパラメーターは次のとおりです。:  
  
 `pNotifyStruct`  
 前のセクションで説明した通知構造体へのポインター。  
  
 *result*  
 返される前に設定した結果コードへのポインター。  
  
## 使用例  
 メンバー関数 `OnKeydownList1` に ID が `IDC_LIST1`である `CListCtrl` から **LVN\_KEYDOWN** メッセージを処理してすることを指定するには、メッセージ マップに追加するために ClassWizard を使用します:  
  
```  
ON_NOTIFY( LVN_KEYDOWN, IDC_LIST1, OnKeydownList1 )  
```  
  
 上の例では、ClassWizard に用意されている関数は、次の操作:  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
   LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;  
   // TODO: Add your control notification handler  
   //       code here  
  
   *pResult = 0;  
}  
```  
  
 ClassWizard を、適切な型のポインターを自動的に提供されることに注意してください。  `pNMHDR` または `pLVKeyDow`から通知の構造にアクセスできます。  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON\_NOTIFY\_RANGE  
 一連のコントロールの **WM\_NOTIFY** 同じメッセージを処理する必要がある `ON_NOTIFY`ではなく **ON\_NOTIFY\_RANGE** を使用できます。  たとえば、特定の通知メッセージの同じ操作を実行する一連のボタンがあることがあります。  
  
 **ON\_NOTIFY\_RANGE**を使用すると、通知メッセージを範囲の開始と終了の子識別子を指定して処理するは子識別子の連続する範囲を指定します。  
  
 ClassWizard は **ON\_NOTIFY\_RANGE**を処理しません; このコマンドを使用するには、独自のメッセージ マップを編集する必要があります。  
  
 次のよう **ON\_NOTIFY\_RANGE** に対するメッセージ マップ エントリと関数プロトタイプがあります:  
  
```  
  
ON_NOTIFY_RANGE(   
wNotifyCode  
,   
id  
,   
idLast  
,   
memberFxn  
 )  
  
```  
  
 斜体のパラメーターは次のとおりのどこに置き換えるか:  
  
 `wNotifyCode`  
 **LVN\_KEYDOWN**など、処理されるよう通知メッセージのコード。  
  
 `id`  
 識別子の連続した範囲の最初の識別子。  
  
 `idLast`  
 識別子の連続した範囲の最後の識別子。  
  
 `memberFxn`  
 この通知が送信されるときに呼び出すメンバー関数。  
  
 このメンバー関数は、次のプロトタイプを宣言する必要があります:  
  
```  
  
afx_msg void memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 解説  
 斜体のパラメーターは次のとおりです。:  
  
 `id`  
 通知を送信コントロールの子識別子。  
  
 `pNotifyStruct`  
 通知構造体へのポインター、上記のようにします。  
  
 *result*  
 返される前に設定した結果コードへのポインター。  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON\_NOTIFY\_EX、ON\_NOTIFY\_EX\_RANGE  
 通知のルーティングの複数のオブジェクトでメッセージを処理して、`ON_NOTIFY` できます。また、**ON\_NOTIFY\_RANGE**\) ではなく **ON\_NOTIFY\_EX** \(または **ON\_NOTIFY\_EX\_RANGE**\) を使用します。  **EX** バージョンと通常バージョンの唯一の違いは、メッセージ処理を続ける必要があるかどうかを示すメンバー関数が **EX** バージョンを **BOOL** に戻り、ことです。  この関数から **FALSE** を返すことは、複数のオブジェクトで同じメッセージを処理できるようにします。  
  
 ClassWizard は **ON\_NOTIFY\_EXON\_NOTIFY\_EX\_RANGE**;を処理しません。これらのいずれかを使用する場合は、独自メッセージ マップを編集する必要があります。  
  
 **ON\_NOTIFY\_EX** に対するメッセージ マップ エントリと関数プロトタイプおよび **ON\_NOTIFY\_EX\_RANGE** は次のとおりです。  パラメーターの意味は**EX** 非バージョンの場合と同じです。  
  
```  
  
ON_NOTIFY_EX( nCode, id, memberFxn ) ON_NOTIFY_EX_RANGE( wNotifyCode, id, idLast, memberFxn )  
```  
  
 上の両方のプロトタイプは同じです:  
  
```  
  
afx_msg BOOL memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 解説  
 いずれの場合も、`id` は通知を送信の子コントロールの ID を保持します。  
  
 関数はコマンド ルーティング オブジェクトにメッセージを処理する可能性がある通知メッセージが完全にまたは **FALSE** 処理されたら **TRUE** を返す必要があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)