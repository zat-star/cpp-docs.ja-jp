---
title: "コントロール (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows コモン コントロール [C++]"
  - "コモン コントロール [C++]"
  - "コントロール [MFC]"
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コントロール (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールは、データを入力または操作するときにユーザーが取り扱うオブジェクトです。 通常は、ダイアログ ボックスまたはツール バー上に表示されます。 ここでは、主な 3 種類のコントロールについて説明します。  
  
-   オーナー描画コントロールなどの Windows コモン コントロール  
  
-   ActiveX コントロール  
  
-   MFC \(Microsoft Foundation Class\) ライブラリで提供される、その他のコントロール クラス  
  
## Windows コモン コントロール  
 Windows オペレーティング システムでは、多数の Windows コモン コントロールが提供されています。 これらのコントロール オブジェクトはコードから操作できます。また、Visual C\+\+ ダイアログ エディターを使用して、コントロール オブジェクトをダイアログ ボックスに追加できます。 MFC \(Microsoft Foundation Class\) ライブラリでは、表「[Windows コモン コントロールと MFC クラス](#_core_windows_common_controls_and_mfc_classes)」に記述されているように、各コントロールをカプセル化するためのクラスが提供されています。 \(表内の一部の項目は、詳細を説明するトピックに関連付けられています\)。 トピックに関連付けられていないコントロールについては、MFC クラスに関するドキュメントを参照してください。  
  
 [CWnd](../Topic/CWnd%20Class.md) クラスは、コントロール クラスをすべて含む、すべてのウィンドウ クラスの基底クラスです。 Windows コモン コントロールは以下の環境でサポートされています。  
  
-   Windows 95、Windows 98、および Windows 2000  
  
-   Windows NT Version 3.51 以降  
  
-   Win32s Version 1.3 \(Visual C\+\+ Version 4.2 以降では Win32s をサポートしていません\)  
  
 Windows の旧バージョンでも、古いコモン コントロール \(チェック ボックス、コンボ ボックス、エディット ボックス、リスト ボックス、オプション ボタン、プッシュ ボタン、スクロール バー コントロール、スタティック コントロール\) が使用できます。  
  
## ActiveX コントロール  
 ActiveX コントロールは、以前は OLE コントロールと呼ばれていたもので、Windows アプリケーション、または WWW \(World Wide Web\) の HTML ページで使用できます。 詳細については、「[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)」を参照してください。  
  
## その他の MFC コントロール クラス  
 すべての Windows コモン コントロールをカプセル化するクラスと、ユーザー独自の \(または他のアプリケーションにより提供された\) ActiveX コントロールのプログラミングをサポートするクラスに加えて、MFC では以下のコントロール クラスを独自に提供します。  
  
-   [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
  
-   [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
  
-   [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
  
##  <a name="_core_finding_information_about_windows_common_controls"></a> Windows コモン コントロールに関する情報  
 次の表では、MFC ラッパー クラスを含む Windows コモン コントロールについて簡単に説明します。  
  
### Windows コモン コントロールと MFC クラス  
  
|コントロール|MFC クラス|説明|Windows 95 で追加された機能かどうか|  
|------------|-------------|--------|-----------------------------|  
|[アニメーション](../Topic/Using%20CAnimateCtrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|AVI ビデオ クリップのフレームを連続的に表示します。|はい|  
|ボタン|[CButton](../mfc/reference/cbutton-class.md)|アクションを発生させるプッシュ ボタン。チェック ボックス、オプション ボタン、およびグループ ボックスにも使用します。|いいえ|  
|コンボ ボックス|[CComboBox](../mfc/reference/ccombobox-class.md)|エディット ボックスとリスト ボックスを組み合わせたものです。|いいえ|  
|[日時指定](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|ユーザーが特定の日付または時刻の値を選択できます。|はい|  
|エディット ボックス|[CEdit](../Topic/CEdit%20Class.md)|テキスト入力用のボックスです。|いいえ|  
|[拡張コンボ ボックス](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|イメージを表示できるコンボ ボックス コントロールです。|はい|  
|[ヘッダー](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)|テキストの列の上に表示されるボタンで、テキストの表示幅を制御します。|はい|  
|[ホット キー](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|アクションをすばやく実行するための "ホット キー" を作成できるウィンドウです。|はい|  
|[イメージ リスト。](../mfc/using-cimagelist.md)|[CImageList](../Topic/CImageList%20Class.md)|多数のアイコンまたはビットマップの管理に使用するイメージのコレクションです。イメージ リストは実際にはコントロールではなく、他のコントロールで使用されるリストをサポートします。|はい|  
|[リスト](../Topic/Using%20CListCtrl.md)|[CListCtrl](../Topic/CListCtrl%20Class.md)|アイコンと共にテキストのリストを表示するウィンドウです。|はい|  
|リスト ボックス|[CListBox](../Topic/CListBox%20Class.md)|文字列のリストを格納するボックスです。|いいえ|  
|[月間予定表](../Topic/Using%20CMonthCalCtrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|日付情報を表示するコントロールです。|はい|  
|[progress](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|時間のかかる処理を実行する場合に、その進行状況を示すウィンドウです。|はい|  
|[rebar](../Topic/Using%20CReBarCtrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|子ウィンドウをコントロールとして追加できるツール バーです。|はい|  
|[リッチ エディット](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)|ユーザーが文字書式および段落書式を設定して編集できるウィンドウです \(「[リッチ エディット コントロールに関連するクラス](../mfc/classes-related-to-rich-edit-controls.md)」を参照\)。|はい|  
|スクロール バー|[CScrollBar](../mfc/reference/cscrollbar-class.md)|ウィンドウ上ではなくダイアログ ボックス内のコントロールとして使用されるスクロール バーです。|いいえ|  
|[スライダー](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|オプションで軸目盛りを表示できるスライダー コントロールが配置されたウィンドウです。|はい|  
|[スピン ボタン](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|ユーザーが値の増減をクリック操作で指定できる矢印ボタンです。増加用と減少用がペアになっています。|はい|  
|静的テキスト|[CStatic](../Topic/CStatic%20Class.md)|他のコントロールのラベルに使用するテキストです。|いいえ|  
|[ステータス バー](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|ステータス情報を表示するためのウィンドウです。MFC クラスの `CStatusBar` に似ています。|はい|  
|[タブ](../mfc/using-ctabctrl.md)|[CTabCtrl](../Topic/CTabCtrl%20Class.md)|ノートの仕切りのような役割を果たします。"タブ ダイアログ ボックス" またはプロパティ シートで使用します。|はい|  
|[ツール バー](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|コマンド生成ボタンを持つウィンドウです。MFC クラスの `CToolBar` に似ています。|はい|  
|[ツール ヒント](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)|ツール バー ボタンなどのツールの用途の説明を表示する小さなポップアップ ウィンドウです。|はい|  
|[ツリー](../Topic/Using%20CTreeCtrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|項目を階層化されたリストとして表示するウィンドウです。|はい|  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   各コントロールへのリンクについては、上記の「[Windows コモン コントロールと MFC クラス](#_core_windows_common_controls_and_mfc_classes)」を参照してください。  
  
-   [コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)  
  
-   [ダイアログ エディターを使用したコントロールの追加](../mfc/using-the-dialog-editor-to-add-controls.md)  
  
-   [手動でコントロールを追加する方法](../mfc/adding-controls-by-hand.md)  
  
-   [MFC コントロール クラスからのコントロール クラスの派生](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [子ウィンドウとしてのコモン コントロールの使い方](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [コモン コントロールからの通知の受信](../Topic/Receiving%20Notification%20from%20Common%20Controls.md)  
  
-   ["Add common controls to a dialog box \(ダイアログ ボックスへのコントロールの追加\)"](../mfc/using-common-controls-in-a-dialog-box.md)。  
  
-   [Windows 標準コントロールからのコントロールの派生](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)  
  
-   [コモン コントロールからの通知の受信](../Topic/Receiving%20Notification%20from%20Common%20Controls.md)  
  
-   [サンプル](../mfc/common-control-sample-list.md)  
  
 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] の Windows コモン コントロールについては、「[Common Controls \(コモン コントロール\)](http://msdn.microsoft.com/library/windows/desktop/bb775493)」を参照してください。  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [Dialog Editor](../mfc/dialog-editor.md)