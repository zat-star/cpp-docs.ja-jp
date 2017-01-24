---
title: "ステータス バー ペインのテキストの更新 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar クラス, 更新"
  - "ON_UPDATE_COMMAND_UI マクロ"
  - "ペイン, ステータス バー"
  - "SetText メソッド"
  - "ステータス バー, 更新"
  - "テキスト, ステータス バー"
  - "更新 (ユーザー インターフェイス オブジェクトを)"
  - "ユーザー インターフェイス オブジェクト, 更新"
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ステータス バー ペインのテキストの更新
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC のステータス バー ペインに表示されるテキストを変更する方法について説明します。  ステータス バー—クラス [CStatusBar](../mfc/reference/cstatusbar-class.md) ウィンドウ オブジェクト\) が含まれています。複数の「ペインを」各ペインには、情報を表示するために使用できるステータス バーの四角形領域です。  たとえば、多くのアプリケーションは、右側のペインの CapsLock キー、NumLock キー、およびそのほかのキーの状態を表示します。  アプリケーションは、通常は表示され、「メッセージ ペインは呼び出しの左端のペイン \(0\) ペインのわかりやすいテキストを」、たとえば、既定の MFC ステータス バーは、選択したメニュー項目やツール バー ボタンを現在説明するテキスト文字列を表示するためにメッセージ ペインを使用します。  [ステータス バー](../mfc/status-bar-implementation-in-mfc.md) の図は、アプリケーション ウィザードで作成される MFC アプリケーションのステータス バーを表示します。  
  
 ペインを作成するとき既定で、MFC は `CStatusBar` のペインはできません。  ペインをアクティブにするには、ステータス バーの各ペインに `ON_UPDATE_COMMAND_UI` マクロを使用して、ペインを更新しなければなりません。  ペインが **WM\_COMMAND** メッセージ \(ツール バー ボタンなどではありません\) を送信しないため、コードを手動で入力する必要があります。  
  
 たとえば、1 個のペインにコマンド ID として `ID_INDICATOR_PAGE` があり、そのドキュメントで現在のページ番号があるとします。  次の手順では、ステータス バーに新しいウィンドウを作成する方法について説明します。  
  
### 新しいウィンドウを作成するには  
  
1.  ペインのコマンド ID を定義します。  
  
     **表示** メニュー **リソース ビュー**。  プロジェクト リソースを右クリックし、**リソース シンボル**をクリックします。  リソース シンボル ダイアログ ボックスで、`New`をクリックします。  コマンド ID の名前を入力します。: たとえば、`ID_INDICATOR_PAGE`。  値を ID に指定したり、リソース シンボル ダイアログ ボックスで提示される値を受け入れます。  たとえば、`ID_INDICATOR_PAGE`では、既定値を受け入れます。  リソース シンボル ダイアログ ボックスを閉じます。  
  
2.  ペインに表示する既定の文字列を定義します。  
  
     リソース ビューを開くには、そのウィンドウのダブルクリック **ストリング テーブル** はアプリケーションのリソースの種類について説明します。  開く **ストリング テーブル** のエディターで **挿入** メニューから **新しい文字列** をクリックします。  文字列プロパティ ウィンドウで、ペインのコマンド ID \(たとえば、`ID_INDICATOR_PAGE`\) を選択し、「ページ」など、既定の文字列値を入力します。  ストリング エディターを閉じます。\(既定の文字列がコンパイラ エラーを回避することが必要です。  
  
3.  **インジケーター** の配列に追加します。  
  
     ファイル MAINFRM.CPP で、**インジケーター** の配列を探します。  この配列リストが順番にステータス バー インジケーターのすべての ID は、左から右に表示します。  配列の適切な位置に、`ID_INDICATOR_PAGE`には次に示すように、ペインのコマンド ID を入力する:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 ペインのテキストを表示する方法、ペインの更新ハンドラー関数の `CCmdUI`**SetText** クラスのメンバー関数を呼び出すことです。  たとえば、数の文字列バージョンを、ペインのテキストを設定する、現在のページ番号を使用 **SetText** を含む整数変数 `m_nPage` を設定する場合があります。  
  
> [!NOTE]
>  **SetText** の方法が推奨されます。  `CStatusBar` のメンバー関数 `SetPaneText`を呼び出すことによって若干低レベルでこのタスクを実行することもできます。  それでも、更新ハンドラーが必要です。  ペインのそのようなハンドラーがない場合、MFC は自動的に内容をオフ ペインを無効にします。  
  
 次の手順では、ペインのテキストの表示に更新ハンドラー関数を使用する方法を示します。  
  
#### ペインにテキストを表示する  
  
1.  コマンドのコマンド更新ハンドラーを追加します。  
  
     手動で `ID_INDICATOR_PAGE` には次に示すように、ハンドラーのプロトタイプを追加します \(で MAINFRM.H\) :  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  適切な .cpp ファイルで、`ID_INDICATOR_PAGE` には次に示すように、ハンドラーの定義を追加します。MAINFRM.CPP\) :  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     このハンドラーの最後の 3 行のテキストを表示するコードです。  
  
3.  適切なメッセージ マップでは、`ID_INDICATOR_PAGE` には次に示すように `ON_UPDATE_COMMAND_UI` マクロを追加します。MAINFRM.CPP\) :  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 \(クラス `CMainFrame`\) の `m_nPage` のメンバー変数の値を定義する場合は、この手法の原因と同様に処理するアイドル状態である間にペインに表示されるページ番号とアプリケーションの更新他のインジケーター。  `m_nPage` が変更されると、表示は、次のアイドル ループ中に変更します。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [ユーザー インターフェイス オブジェクトを更新します \(プログラム状態の変更としてツール バー ボタンとメニュー アイテムを更新する方法を\)](../mfc/how-to-update-user-interface-objects.md)  
  
## 参照  
 [MFC でのステータス バーの実装](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar クラス](../mfc/reference/cstatusbar-class.md)