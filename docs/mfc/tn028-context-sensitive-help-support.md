---
title: "テクニカル ノート 28: 状況依存のヘルプのサポート | Microsoft Docs"
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
  - "vc.help"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "状況依存のヘルプ, MFC アプリケーション"
  - "リソース識別子, 状況依存のヘルプ"
  - "TN028"
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 28: 状況依存のヘルプのサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC のヘルプ コンテキスト ID などを割り当てるための規則をヘルプ問題について説明します。  状況依存のヘルプ サポートは Visual C\+\+ で使用できるヘルプ コンパイラが必要です。  
  
> [!NOTE]
>  WinHelp を使用して状況依存のヘルプの実装に加えて、HTML を使用しても、MFC サポートが役立ちます。  このサポートの詳細についてと HTML ヘルプを使用したプログラミングは、[HTML ヘルプ: プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)を参照します。  
  
## サポートされるヘルプの種類  
 Windows アプリケーションで実装される状況依存のヘルプの 2 種類があります。  1 番目は、現在アクティブなオブジェクトに基づいて適切なコンテキストと、「F1 ヘルプ」として参照される WinHelp を起動する必要があります。  2 番目の単語は「Shift\+ F1」モードです。  このモードでは、オブジェクトをオンにすると、マウス カーソルがヘルプ カーソルとユーザーの順序に変更します。  この時点で、WinHelp は、ユーザーがクリックしたオブジェクトのヘルプを与えるために起動します。  
  
 Microsoft Foundation Class は、ヘルプの両方のフォームを実装します。  また、フレームワークは、2 種類の単純なヘルプ コマンド、ヘルプ索引ヘルプ サポートを使用します。  
  
## ヘルプ ファイル  
 Microsoft Foundation Class は単一のヘルプ ファイルが使用されます。  ヘルプ ファイルは、アプリケーションと同じ名前およびパスが必要です。  たとえば、実行可能ファイルが C:\\MyApplication\\MyHelp.exe のヘルプ ファイルは C:\\MyApplication\\MyHelp.hlp.である必要があります。  [CWinApp クラス](../mfc/reference/cwinapp-class.md)の `m_pszHelpFilePath` のメンバー変数でパスを設定します。  
  
## ヘルプ コンテキストのスコープ  
 MFC の既定の実装は、プログラムがヘルプ コンテキスト ID の割り当てに関する規則に従う必要があります。  これらの規則は、特定のコントロールに割り当てられた ID の範囲です。  さまざまなヘルプ関連のメンバー関数の異なる実装を提供することにより、これらの規則をオーバーライドできます。  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
   0x00010000 + ID_  
   (note: 0x18000-> 0x1FFFF is the practical range since command IDs are >=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
   0x00020000 + IDR_  
   (note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
   0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
   0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
   0x00040000 + IDW_  
```  
  
## 単純な「ヘルプ」コマンド  
 Microsoft Foundation Class によって実装される 2 種類の単純な help コマンドがあります:  
  
-   [CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)によって実装される ID\_HELP\_INDEX  
  
-   [CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)によって実装される ID\_HELP\_USING  
  
 最初のコマンドは、アプリケーションのヘルプ索引を示しています。  2 番目の WinHelp プログラムのユーザー ヘルプを示します。  
  
## コンテキスト ヘルプ \(F1 ヘルプ\)  
 F1 キーは通常、メイン ウィンドウのアクセラレータ テーブルに配置して `ID_HELP` アクセラレータの ID とコマンドに変換されます。  `ID_HELP` コマンドは、メイン ウィンドウまたはダイアログ ボックスに `ID_HELP` の ID を持つボタンが生成されることがあります。  
  
 `ID_HELP` コマンドはどのように関係なくコマンド ハンドラーが見つかるまで、生成されるか、正常なコマンドとしてルーティングされます。  MFC のコマンド ルーティング アーキテクチャの詳細については、[テクニカル ノート 21](../mfc/tn021-command-and-message-routing.md)を示します。  アプリケーションに有効なヘルプがある場合 `ID_HELP` コマンドは [CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)によって処理されます。  Application オブジェクトは、ヘルプ メッセージを受け取り、コマンドを適切にルーティングします。  これは、既定のコマンドのルーティングが特定のコンテキストを確認するには十分ではないためです。  
  
 `CWinApp::OnHelp` は 次の順序で WinHelp を起動しようとしています:  
  
1.  実行中の `AfxMessageBox` のチェックは、ヘルプ ID を呼び出します  メッセージ ボックスで現在アクティブである場合、WinHelp は、メッセージ ボックスに適切なコンテキストに起動されます。  
  
2.  アクティブ ウィンドウに WM\_COMMANDHELP メッセージを送信します。  そのウィンドウに WinHelp を起動して、応答メッセージは、そのウィンドウの先祖にメッセージが処理される場合、または現在のウィンドウがトップレベル ウィンドウになるまで送信されます。  
  
3.  メイン ウィンドウに ID\_DEFAULT\_HELP コマンドを送信します。  これは既定のヘルプを起動します。  このコマンドは `CWinApp::OnHelpIndex`に一般にマップされます。  
  
 全体的に既定の基準値 ID \(ダイアログなどのリソースがコマンドの例 0x10000 と 0x20000\) をオーバーライドする場合、アプリケーションは [CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)をオーバーライドする必要があります。  
  
 この機能は、およびヘルプ コンテキストが決定できる方法をオーバーライドするには、WM\_COMMANDHELP メッセージを処理する必要があります。  現在の MDI 子ウィンドウだけ深さので、フレームワークが提供するよりも多くの特定のルーティングを提供することもできます。  そのオブジェクトの現在の内部状態またはダイアログ内のアクティブなコントロールの特定のヘルプを特定のウィンドウまたはダイアログ ボックスに基づいて、提供する必要があります。  
  
## WM\_COMMANDHELP  
  
```  
  
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
```  
  
 WM\_COMMANDHELP はヘルプが要求されるとアクティブ ウィンドウで受信プライベートな MFC Windows メッセージです。  ウィンドウには、このメッセージを受け取ると、ウィンドウの内部状態に一致するコンテキストの `CWinApp::WinHelp` を呼び出す可能性があります。  
  
 `lParam`  
 現在使用できるヘルプ コンテキストが含まれています。  `lParam` は ヘルプ コンテキストが定められなかったらゼロです。  `OnCommandHelp` の実装は `lParam` で異なるコンテキストを確認するには、コンテキスト ID を使用することも、`CWinApp::WinHelp`だけに渡すことができます。  
  
 `wParam`  
 ゼロ使用されず、です。  
  
 `OnCommandHelp` 関数呼び出し `CWinApp::WinHelp`では、`TRUE`を返します。  `TRUE` を返すと、他のクラスと他のウィンドウに、このコマンドのルーティングを停止します。  
  
## ヘルプ モード \(Shift\+F1 ヘルプ\)  
 これは状況依存のヘルプの 2 番目のフォームです。  通常、このモードは Shift \+ F1 キーを押すか、またはメニューおよびツール バーで Enter キーを押します。  これは、コマンド**ID\_CONTEXT\_HELP** \(\) として実装されます。  モーダル ダイアログ ボックスまたはメニューがアクティブな間、メッセージ フィルター フックでこのコマンドを変換するために使用されるので、アプリケーションのメイン メッセージ ポンプ \(`CWinApp::Run`\) を実行しているときにこのコマンドをユーザーにのみ使用できます。  
  
 このモードになった後、ヘルプ マウス カーソルがアプリケーションのあらゆる領域に関連するアプリケーションは、通常、その区分用のカーソルが表示されても、表示されます \(ウィンドウの周囲のサイズ変更境界など\)。  ユーザーがコマンドを選択するには、マウスまたはキーボードを使用できます。  コマンドを実行する代わりに、そのコマンドのヘルプが表示されます。  また、ユーザーがツール バーのボタンなど、画面に表示されているオブジェクトをクリックし、ヘルプは、そのオブジェクトに表示されます。  ヘルプのこのモードは `CWinApp::OnContextHelp`によって提供されます。  
  
 このループの実行中に、すべてのキーボード入力をメニューにアクセスするキーを除くアクティブでないです。  または、コマンド変換は、`PreTranslateMessage` でユーザーがアクセラレータ キーを押して、そのコマンドのヘルプを表示できるようにします。  
  
 特定の変換が必要な場合、または \+ F1 ヘルプ モードで行う必要な `PreTranslateMessage` で発生するアクションを使用すると、それらのアクションを実行する前に `CWinApp` の `m_bHelpMode` のメンバーを確認する必要があります。  `PreTranslateMessage` の `CDialog` の実装は `IsDialogMessage`を呼び出す前に、たとえばチェックします。  これは \+ F1 モードでモードレス ダイアログの「ダイアログ ナビゲーション」キーを無効にします。  また、`CWinApp::OnIdle` は、ループの間に呼び出されます。  
  
 ユーザーがメニュー コマンドを選択すると、そのコマンドのヘルプとして処理されます \(**WM\_COMMANDHELP**によって、参照してください。  ユーザーがアプリケーション ウィンドウの表示領域をクリックし、判断が非クライアントのクリックやクライアント クリックかについて呼び出されます。  クライアント への非クライアントのクリック`OnContextHelp` ハンドルのマップは自動的にクリックします。  クリック クライアントの場合は、クリックされたウィンドウに、**WM\_HELPHITTEST** を送信します。  そのウィンドウが 0 以外の値を返した場合、その値はヘルプにコンテキストとして使用されます。  これがゼロを返す場合、`OnContextHelp` が親ウィンドウと \(とその親の失敗する場合など\)。  ヘルプ コンテキストを特定できない場合、既定では `CWinApp::OnHelpIndex` \(通常は\) にマップされるメイン ウィンドウへ **ID\_DEFAULT\_HELP** コマンドを送ります。  
  
## WM\_HELPHITTEST  
  
```  
  
afx_msg LRESULT CWnd::OnHelpHitTest(  
WPARAM, LPARAM lParam)  
```  
  
 **WM\_HELPHITTEST** は \+ F1 ヘルプ モードでクリックされたアクティブ ウィンドウで受信 MFC のプライベートなウィンドウ メッセージです。  ウィンドウには、このメッセージを受け取ると、WinHelp で使用する DWORD のヘルプ ID を返します。  
  
 LOWORD \(lParam\)  
 マウスがウィンドウのクライアント領域に対するクリックされた X 軸のデバイス座標が含まれます。  
  
 HIWORD \(lParam\)  
 Y 軸の座標が含まれます。  
  
 `wParam`  
 ゼロ使用されず、です。  戻り値が 0 以外のの場合、WinHelp はそのコンテキストと呼ばれます。  戻り値がゼロの場合、親ウィンドウがヘルプに呼び出されます。  
  
 多くの場合、ユーザーが既に持っている可能性のあるヒット テスト コードを利用できます。  **WM\_HELPHITTEST** メッセージを処理する例については、" **CToolBar::OnHelpHitTest** の実装を参照してください \(コードは `CControlBar`でボタンやツールヒントで使用されるテスト コードを利用します\)。  
  
## MFC アプリケーション ウィザードのサポート、および MAKEHM  
 MFC アプリケーション ウィザードには、ヘルプ ファイルをビルドするために必要なファイルが作成されます \(.cnt および .hpj ファイル\)。  また、Microsoft ヘルプ コンパイラが受け取る一部のプレビルド .rtf ファイルが含まれています。  トピックの多くは完了しますが、一部は特定のアプリケーションに合わせて変更する必要があります。  
  
 「ヘルプ マッピング」ファイルの自動作成は MAKEHM というユーティリティでサポートされます。  MAKEHM ユーティリティは、ヘルプのマッピング ファイルにアプリケーションの RESOURCE.H ファイルを変換できます。  たとえば、次のようになります。  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 に変換されます:  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 この形式はトピック名 \(左側のシンボル\) を持つコンテキストの ID \(右側の数\) をマップするヘルプ コンパイラの機能と互換性があります。  
  
 MAKEHM のソース・コードは MFC プログラミング ユーティリティ [MAKEHM](../top/visual-cpp-samples.md)サンプルで使用できます。  
  
## ヘルプ サポートを MFC アプリケーション ウィザードを実行した後で追加します。  
 アプリケーションにヘルプを追加する最良の方法は、アプリケーションを作成する前に、MFC アプリケーション ウィザードの高度な機能ページでコンテキスト ヘルプ「」オプションを選択します。  この方法は `CWinApp`MFC アプリケーション ウィザードによって必要なメッセージ マップ エントリ\-サポート サービスへの派生クラスを追加します。  
  
## メッセージ ボックスのヘルプ  
 メッセージ ボックスでは、警告 \(とも呼ばれます\) `AfxMessageBox` 関数、`MessageBox` Windows API のラッパーでサポートされます。  
  
 ドキュメントテンプレート文字列 ID 文字列で使用するための `AfxMessageBox`、1 およびポインターで使用するために別の 2 種類のバージョンがあります \(`LPCSTR`\) :  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText, UINT nType, UINT nIDHelp);  
int AFXAPI AfxMessageBox(UINT nIDPrompt, UINT nType, UINT nIDHelp);  
```  
  
 いずれの場合も、省略可能なヘルプ ID があります。  
  
 nIDHelp の最初の場合、既定では、このメッセージ ボックスのヘルプを表示する 0 です。  ユーザーがメッセージ ボックスなど、F1 キーを押すと、アクティブの場合、ユーザーはヘルプを受け取りません \(アプリケーションがサポートするヘルプ\)。  これは好ましくなければ、ヘルプ ID は nIDHelp に指定する必要があります。  
  
 nIDHelp の第 2 レベルでは、既定値はヘルプ ID は nIDPrompt と同じであることを示す \-1 です。  ヘルプは、ヘルプ アプリケーションが有効な場合にのみ、です\)。  メッセージ ボックスは、ヘルプがサポートされていないことを望めば nIDHelp に 0 を指定してください。  あるメッセージに有効なヘルプの場合は nIDPrompt 以外のヘルプを ID は、nIDPrompt の別の nIDHelp に正の値を提供します。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)