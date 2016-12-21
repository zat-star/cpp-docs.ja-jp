---
title: "テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ リフレクション"
  - "通知メッセージ"
  - "ON_CONTROL_REFLECT マクロ"
  - "ON_CONTROL_REFLECT_EX マクロ"
  - "ON_NOTIFY メッセージ"
  - "ON_NOTIFY_REFLECT メッセージ"
  - "ON_NOTIFY_REFLECT_EX メッセージ"
  - "ON_UPDATE_COMMAND_UI_REFLECT マクロ"
  - "ON_WM_CHARTOITEM_REFLECT マクロ"
  - "ON_WM_COMPAREITEM_REFLECT マクロ"
  - "ON_WM_CTLCOLOR_REFLECT マクロ"
  - "ON_WM_DELETEITEM_REFLECT マクロ"
  - "ON_WM_DRAWITEM_REFLECT マクロ"
  - "ON_WM_HSCROLL_REFLECT マクロ"
  - "ON_WM_MEASUREITEM_REFLECT マクロ"
  - "ON_WM_PARENTNOTIFY_REFLECT マクロ"
  - "ON_WM_VKEYTOITEM_REFLECT マクロ"
  - "ON_WM_VSCROLL_REFLECT マクロ"
  - "TN062"
  - "WM_COMMAND"
  - "WM_CTLCOLOR メッセージ"
  - "WM_NOTIFY メッセージ"
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートはメッセージ リフレクション、MFC 4.0 の新機能について説明します。  また、メッセージ リフレクションを使用する簡単な再利用可能なコントロールを作成する手順を示します。  
  
 このテクニカル ノートは ActiveX コントロールに適用するときにメッセージ リフレクションについては説明しません \(以前の OLE コントロールとも呼ばれます\)。  [ActiveX コントロール: Windows のコントロールをサブクラス化する。](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)記事を参照してください。  
  
 **メッセージ リフレクションは何ですか。**  
  
 Windows のコントロールが親ウィンドウに頻繁に通知メッセージを送信します。  たとえば、多くのコントロールには親コントロールの親の背景を描画するためのブラシを指定できるように、コントロールの色の通知メッセージ \(バリアントの`WM_CTLCOLOR` または 1\) します。  
  
 Windows とバージョン 4.0 以前の MFC、親ウィンドウ、ダイアログ ボックスで次のメッセージを処理する必要があります。  これにより、メッセージを親ウィンドウ クラスになる必要があることを、そのメッセージを処理する必要があるすべてのクラスで重複している処理のためのコードを示します。  上記のときにカスタムの背景の望まれたコントロールがコントロールのカラー通知メッセージが処理しなければならない場合は、必ずダイアログ ボックス。  独自の背景色を処理するコントロール クラスを記述しているが、コードの再利用が簡単です。  
  
 MFC 4.0 で、古い機能は引き続き動作しますが、親ウィンドウに通知メッセージを処理できます。  また、MFC 4.0 は「メッセージ リフレクション」と呼ばれる機能を提供して再利用を割り当てと子コントロールのウィンドウまたは親ウィンドウ、またはその両方で処理される必要も通知メッセージしやすくなります。  コントロールの背景色の例で、`WM_CTLCOLOR` 反映されたメッセージの—親に依存しないですべて処理して独自の背景色を設定するコントロール クラスを記述できます。\(メッセージ リフレクションが Windows による MFC ではなく、親ウィンドウのクラス実装されるため、メッセージ リフレクションの `CWnd` から始めるに派生されなければならないください。\)  
  
 MFC の古いバージョンがオーナー描画のリスト ボックス`WM_DRAWITEM` \(提供してメッセージ リフレクションに似たものなど\) のメッセージなどの一部のメッセージに仮想関数が、しました。  新しいメッセージ リフレクションの機能は、汎化され、一貫性があります。  
  
 メッセージ リフレクションは、MFC 4.0 以前のバージョン用に記述されたコードと下位互換性があります。  
  
 特定のメッセージ、またはメッセージの範囲のハンドラーを、親ウィンドウのクラスで渡す場合、同じメッセージのリフレクション メッセージ ハンドラーを提供しました呼び出しません独自のハンドラーの基本クラスのハンドラー関数をオーバーライドします。  たとえば、ダイアログ ボックス クラスで `WM_CTLCOLOR` を処理すれば、処理はリフレクション メッセージ ハンドラーをオーバーライドします。  
  
 、親ウィンドウのクラスでは、**WM\_NOTIFY** メッセージの **WM\_NOTIFY** 特定のメッセージまたは範囲のハンドラーを指定した場合、ハンドラーはメッセージを送信する子コントロールが **ON\_NOTIFY\_REFLECT\(\)**でリフレクション メッセージ ハンドラーがない場合にのみ呼び出されます。  メッセージ マップで **ON\_NOTIFY\_REFLECT\_EX\(\)** を使用して親ウィンドウがメッセージを処理するようにことなく、メッセージ ハンドラーがされたり、そうでない場合があります。  ハンドラーが **FALSE**を返した場合、メッセージは親によって **TRUE** を返す呼び出しは親を処理しないようにようにしていても、同様に処理されます。  リフレクション メッセージが通知メッセージの前に処理されることに注意してください。  
  
 **WM\_NOTIFY** メッセージが送信されると、コントロールはそれを処理する最初の可能性が提供されます。  そのほかのリフレクション メッセージ、つまり、親ウィンドウに処理する最初の可能性があり、コントロールはリフレクション メッセージを受け取ります。  そのためには、コントロールのクラスのメッセージ マップでハンドラー関数と適切なエントリが必要です。  
  
 リフレクション メッセージのメッセージ マップ マクロは通常の通知とは少し異なります: これは、通常の名前が付けられている **\_REFLECT** があります。  たとえば、親の **WM\_NOTIFY** メッセージを処理するために、親のメッセージ マップで `ON_NOTIFY` マクロを使用します。  子コントロールのリフレクション メッセージを処理するには、子コントロールのメッセージ マップで **ON\_NOTIFY\_REFLECT** マクロを使用します。  場合によっては、パラメーターが異なる場合は、同様に。  ClassWizard は通常、に対するメッセージ マップ エントリを追加し、適切なパラメーターをスケルトン関数の実装に付与できることに注意してください。  
  
 **WM\_NOTIFY** 新しいメッセージについては、" [TN061: ON\_NOTIFY と WM\_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md) を参照してください。  
  
 **リフレクション メッセージに対するメッセージ マップ エントリとハンドラー関数プロトタイプ**  
  
 反射したコントロール通知メッセージを処理するには、次の表に示すメッセージ マップ マクロや関数プロトタイプを使用します。  
  
 ClassWizard は通常、これらのメッセージ マップ エントリを追加して、スケルトン関数の実装を提供します。  リフレクション メッセージ ハンドラーを定義する方法の詳細については、" [リフレクション メッセージのメッセージ ハンドラーを定義する](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) を参照してください。  
  
 メッセージの名前が反映されたマクロ名に変換するには、**ON\_** をアタッチし、**\_REFLECT**を追加します。  たとえば、`WM_CTLCOLOR` は **ON\_WM\_CTLCOLOR\_REFLECT**になります。\(メッセージが反映できるかを参照するには次の表のマクロ エントリの逆変換を\)。  
  
 上記の規則の 3 点は次のとおりです。:  
  
-   **WM\_COMMAND** 通知のマクロは **ON\_CONTROL\_REFLECT**です。  
  
-   **WM\_NOTIFY** のリフレクションのマクロは **ON\_NOTIFY\_REFLECT**です。  
  
-   `ON_UPDATE_COMMAND_UI` のリフレクションのマクロは **ON\_UPDATE\_COMMAND\_UI\_REFLECT**です。  
  
 上記の特殊なケースにはそれぞれ、ハンドラー メンバー関数の名前を指定する必要があります。  そのほかの場合は、ハンドラー関数には標準の名前を使用する必要があります。  
  
 関数のパラメーターと戻り値の意味は関数名で参照してまたは **オン** 関数名を結合します。  たとえば、**CtlColor** は `OnCtlColor`"で説明しています。  一部のリフレクション メッセージ ハンドラーが親ウィンドウに似たハンドラーよりも少ないパラメーターが必要です。  、ドキュメントの仮パラメーターの名前に次の表の名前と一致します。  
  
|マップ エントリ|関数プロトタイプ|  
|--------------|--------------|  
|**ON\_CONTROL\_REFLECT\(**  `wNotifyCode`\#\#\#，`memberFxn` **\)**|**afx\_msg void**  `memberFxn`  **\( \);**|  
|**ON\_NOTIFY\_REFLECT\(**  `wNotifyCode`\#\#\#，`memberFxn` **\)**|**afx\_msg void**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\*** の*結果* **\);**|  
|**ON\_UPDATE\_COMMAND\_UI\_REFLECT\(**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( CCmdUI\***  `pCmdUI`  **\);**|  
|**ON\_WM\_CTLCOLOR\_REFLECT \(\)**|**afx\_msg HBRUSH CtlColor \( CDC\***  `pDC` **, UINT**  `nCtlColor`  **\);**|  
|**ON\_WM\_DRAWITEM\_REFLECT \(\)**|**afx\_msg void DrawItem \( LPDRAWITEMSTRUCT**  `lpDrawItemStruct`  **\);**|  
|**ON\_WM\_MEASUREITEM\_REFLECT \(\)**|**afx\_msg void MeasureItem \( LPMEASUREITEMSTRUCT**  `lpMeasureItemStruct`  **\);**|  
|**ON\_WM\_DELETEITEM\_REFLECT \(\)**|**afx\_msg void DeleteItem \( LPDELETEITEMSTRUCT**  `lpDeleteItemStruct`  **\);**|  
|**ON\_WM\_COMPAREITEM\_REFLECT \(\)**|**afx\_msg int CompareItem \( LPCOMPAREITEMSTRUCT**  `lpCompareItemStruct`  **\);**|  
|**ON\_WM\_CHARTOITEM\_REFLECT \(\)**|**afx\_msg int CharToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_VKEYTOITEM\_REFLECT \(\)**|**afx\_msg int VKeyToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_HSCROLL\_REFLECT \(\)**|**afx\_msg void HScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_VSCROLL\_REFLECT \(\)**|**afx\_msg void VScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_PARENTNOTIFY\_REFLECT \(\)**|**afx\_msg void ParentNotify \( UINT**  `message` **, LPARAM**  `lParam`  **\);**|  
  
 **ON\_NOTIFY\_REFLECT** と **ON\_CONTROL\_REFLECT** マクロに複数のオブジェクト \(コントロールや親などの特定のメッセージを処理するようにようなバリエーションがあります。  
  
|マップ エントリ|関数プロトタイプ|  
|--------------|--------------|  
|**ON\_NOTIFY\_REFLECT\_EX\(**  `wNotifyCode`\#\#\#，`memberFxn` **\)**|**afx\_msg BOOL**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\*** の*結果* **\);**|  
|**ON\_CONTROL\_REFLECT\_EX\(**  `wNotifyCode`\#\#\#，`memberFxn` **\)**|**afx\_msg BOOL**  `memberFxn`  **\( \);**|  
  
## 処理のリフレクション メッセージ: 再利用可能なコントロールの例  
 この簡単な例を `CYellowEdit`という再利用可能なコントロールを作成します。  コントロールは標準エディット コントロールと同じように動作しますが、黄色い背景に黒のテキストが表示されます。  `CYellowEdit` のコントロールが異なる色が表示されるようにするメンバー関数を追加したりできます。  
  
#### 再利用可能なコントロールを作成する例があります。  
  
1.  既存のアプリケーションの新しいダイアログ ボックスを作成します。  詳細については、[ダイアログ エディター](../mfc/dialog-editor.md) "を参照します。  
  
     再利用可能なコントロールを開発するアプリケーションが必要です。  使用する既存のアプリケーションがない場合は、AppWizard を使用してダイアログ ベースのアプリケーションを作成します。  
  
2.  Visual C\+\+ でプロジェクトが読み込まれて `CEdit`に基づいて `CYellowEdit` という名前の新しいクラスを作成するために ClassWizard を使用します。  
  
3.  `CYellowEdit` クラスに 3 個の変数を追加します。  最初の 2 つがテキストの色と背景色を保持する **COLORREF** の変数です。  番目には背景を描画するためのブラシを保持する `CBrush` オブジェクトです。  `CBrush` オブジェクトは `CYellowEdit` のコントロールを破棄すると、ブラシを使用して、その後は一度だけ作成し、ブラシを参照して自動的に破棄することができます。  
  
4.  コンストラクターを記述してメンバー変数を初期化して、次のような:  
  
    ```  
    CYellowEdit::CYellowEdit()  
    {  
       m_clrText = RGB( 0, 0, 0 );  
       m_clrBkgnd = RGB( 255, 255, 0 );  
       m_brBkgnd.CreateSolidBrush( m_clrBkgnd );  
    }  
    ```  
  
5.  ClassWizard を使用して、`CYellowEdit` クラスに `WM_CTLCOLOR` 反映されたメッセージのハンドラーを追加します。  メッセージが反映されるように、処理できるメッセージ ボックスの一覧でメッセージの名前の前に等号を示すことに注意してください。  これは [リフレクション メッセージのメッセージ ハンドラーを定義する](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)で説明します。  
  
     ClassWizard では以下のメッセージ マップ マクロとスケルトン関数を追加する:  
  
    ```  
    ON_WM_CTLCOLOR_REFLECT()  
  
    // Note: other code will be in between....  
  
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
    {  
       // TODO: Change any attributes of the DC here  
  
       // TODO: Return a non-NULL brush if the  
       //   parent's handler should not be called  
       return NULL;  
    }  
    ```  
  
6.  次のコードでは、関数の本体を置き換えます。  コードでは、コントロール内のテキストの色、テキストの背景色と背景色を指定します。  
  
    ```  
    pDC->SetTextColor( m_clrText );   // text  
    pDC->SetBkColor( m_clrBkgnd );   // text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
    ```  
  
7.  エディット コントロールをダイアログ ボックスで作成し、メンバー変数にエディット コントロールをダブルクリックして接続して、Ctrl キーを押したまま中。  メンバー変数の追加ダイアログ ボックスで、変数名を終了し、カテゴリの「コントロール」、および変数の型の「CYellowEdit」選択します。  ダイアログ ボックスのタブ オーダーを設定するのを忘れないしないでください。  このダイアログ ボックスのヘッダー ファイルに `CYellowEdit` のコントロールのヘッダー ファイルをインクルードするようにしてください。  
  
8.  アプリケーションをビルドして実行します。  エディット コントロールは、黄色い背景があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)