---
title: "コントロール クラス | Microsoft Docs"
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
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ボタン, MFC コントロール クラス"
  - "コントロール クラス"
  - "コントロール クラス, MFC"
  - "コントロール [C++], MFC コントロール クラス"
  - "コントロール [MFC]"
  - "リスト ボックス, MFC コントロール クラス"
  - "静的表示コントロール"
  - "テキスト, コントロール (入力の)"
  - "ユーザー入力, MFC コントロール クラス"
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コントロール クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロール クラスには、静的テキスト コントロールからのツリー コントロールまで、さまざまな標準の Windows コントロールをカプセル化します。  また、MFC はビットマップとコントロール バー ボタンを含む、新しいコントロールを提供します。  
  
 クラス名が「**Ctrl**」で終わるコントロールは Windows 95 および Windows NT 3.51 で新しかったです。  
  
## 表示コントロール  
 [CStatic](../Topic/CStatic%20Class.md)  
 静的表示ウィンドウ。  スタティック コントロールがダイアログ ボックスまたはウィンドウの他のコントロールを使用して、囲むか、分離されます。  また、よりも、テキストをボックスまたはグラフィカル イメージを表示する場合があります。  
  
## テキスト コントロール  
 [CEdit](../Topic/CEdit%20Class.md)  
 編集できるテキストのコントロール ウィンドウ。  エディット コントロールのテキストをユーザーからの入力を受け入れるために使用されます。  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 インターネット プロトコル \(IP\) のアドレスを処理するためのエディット ボックスをサポートします。  
  
 [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)  
 ユーザーがテキストを入力して編集できるコントロール。  `CEdit`にカプセル化されたコントロールとは異なり、リッチ エディット コントロールは文字や段落書式と OLE オブジェクトをサポートします。  
  
## 数値を表すコントロール  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 値を値または複数選択して、ユーザーが移動できるスライダーを含むコントロール。  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 値をインクリメントするか、デクリメントするためにユーザーがクリックできる矢印ボタンのペア。  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 操作の進行状況を示すために、左から右に塗りつぶされた四角形を表示します。  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 スクロール バー コントロール ウィンドウ。  クラスは、ユーザーが範囲内の位置を指定します。指定できるウィンドウまたはダイアログ ボックスのコントロールとして使用するスクロール バー機能を利用します。  
  
## ボタン  
 [CButton](../mfc/reference/cbutton-class.md)  
 ボタン コントロールのウィンドウ。  クラスは、ダイアログ ボックスまたはウィンドウのプッシュ ボタン、チェック ボックス、オプション ボタンはプログラミング インターフェイスを提供します。  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 キャプション テキストではなくビットマップのボタン。  
  
## 表示内容  
 [CListBox](../Topic/CListBox%20Class.md)  
 リストボックス コントロールのウィンドウ。  ボックスに表示し、ユーザーが選択できるアイテムの一覧が表示されます。  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Windows のリスト ボックスの機能を提供します。; ユーザーがリスト ボックス内の項目を、リスト ボックス内のファイル名とリテラル文字列など、移動できるようにします。  この機能のリスト ボックスがアルファベット以外の順序で項目リストに便利ですなどのプロジェクトのパスまたはファイル名を含めます。  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 コンボ ボックス コントロールのウィンドウ。  コンボ ボックスのリスト ボックスとエディット コントロールから構成されます。  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 各項目の横にあるユーザーがチェック アウトするか、できるチェック ボックスの項目の一覧を表示します。  
  
 [CListCtrl](../Topic/CListCtrl%20Class.md)  
 項目、それぞれファイル エクスプローラーの右ペインに似たアイコンから成るとラベルのコレクションを、では表示されます。  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 ファイル エクスプローラーの左ペインにアイコンとラベルで配置する同様の階層的な一覧が表示されます。  
  
## ツール バーとステータス バー  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ツール バー コモン コントロールの機能が用意されています。  ほとんどの MFC プログラムは、このクラスの代わりに [CToolBar](../mfc/reference/ctoolbar-class.md) を使用します。  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 通常、アプリケーションのステータス情報を表示できるペインに水平方向の分割ウィンドウ。  ほとんどの MFC プログラムは、このクラスの代わりに [CStatusBar](../mfc/reference/cstatusbar-class.md) を使用します。  
  
## そのほかのコントロール  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 単純なビデオ クリップを表示します。  
  
 [CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)  
 アプリケーションでツールの目的を説明する、単一行のテキストを表示する小さなポップアップ ウィンドウ。  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 拡張エディット コントロール、またはユーザーが時刻値を特定の日付を選択できるようにする簡単な暦のインターフェイス コントロールをサポートします。  
  
 [CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)  
 列の表示タイトルまたはラベル。  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 ユーザーが日付を選択できるようにする簡単な暦のインターフェイス コントロールをサポートします。  
  
 [CTabCtrl](../Topic/CTabCtrl%20Class.md)  
 ユーザーがクリックできるメモの区分線のようなタブを持つコントロール。  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 ユーザーが操作を簡単に実行するためにユーザーがクリックできるホット キーの組み合わせを作成できるようにします。  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 ユーザーが埋め込まれたなリンクをクリックしたときに Renders マーク付きのテキストおよび起動の適切なアプリケーション。  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。  
  
## 関連クラス  
 [CImageList](../Topic/CImageList%20Class.md)  
 Windows イメージ リストの機能が用意されています。  イメージ リストはリスト コントロールやツリー コントロールで使われます。  また、同じサイズのビットマップの組の格納や保存にも使用できます。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 すべての基本クラスは、Windows のコントロールには、関連を検索します。  コントロールに基づくビューについて、次に説明します。  
  
 [CEditView](../Topic/CEditView%20Class.md)  
 Windows の標準のエディット コントロールを含むビュー。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Windows のリッチ エディット コントロールを含むビュー。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビュー。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows コモン ツリー コントロールを含むビュー。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)