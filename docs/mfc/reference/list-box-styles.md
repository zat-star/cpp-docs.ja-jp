---
title: "リスト ボックス スタイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LBS_STANDARD"
  - "LBS_NODATA"
  - "LBS_OWNERDRAWVARIABLE"
  - "LBS_EXTENDEDSEL"
  - "LBS_USETABSTOPS"
  - "LBS_WANTKEYBOARDINPUT"
  - "LBS_NOTIFY"
  - "LBS_DISABLENOSCROLL"
  - "LBS_HASSTRINGS"
  - "LBS_NOREDRAW"
  - "LBS_NOSEL"
  - "LBS_NOINTEGRALHEIGHT"
  - "LBS_MULTICOLUMN"
  - "LBS_SORT"
  - "LBS_MULTIPLESEL"
  - "LBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LBS_DISABLENOSCROLL 定数"
  - "LBS_EXTENDEDSEL 定数"
  - "LBS_HASSTRINGS 定数"
  - "LBS_MULTICOLUMN 定数"
  - "LBS_MULTIPLESEL 定数"
  - "LBS_NODATA 定数"
  - "LBS_NOINTEGRALHEIGHT 定数"
  - "LBS_NOREDRAW 定数"
  - "LBS_NOSEL 定数"
  - "LBS_NOTIFY 定数"
  - "LBS_OWNERDRAWFIXED 定数"
  - "LBS_OWNERDRAWVARIABLE 定数"
  - "LBS_SORT 定数"
  - "LBS_STANDARD 定数"
  - "LBS_USETABSTOPS 定数"
  - "LBS_WANTKEYBOARDINPUT 定数"
  - "リスト ボックス, スタイル"
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# リスト ボックス スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **LBS\_DISABLENOSCROLL**はリスト ボックス リスト ボックスをスクロールするための十分な項目が含まれない場合無効垂直スクロール バーが表示されます。  このスタイルがない場合、スクロール バーはリスト ボックスが十分に項目が含まれていない場合になります。  
  
-   **LBS\_EXTENDEDSEL**は Shift キーとマウスまたは特殊なキーの組み合わせを使用してユーザーが複数の項目を選択できます。  
  
-   **LBS\_HASSTRINGS**は文字列で構成される項目を含むオーナー描画リスト ボックスを指定します。  リスト ボックスには、文字列のメモリおよびポインターを保持します。したがって、特定のアイテムのテキストを取得するために `GetText` メンバー関数を使用できます。  
  
-   **LBS\_MULTICOLUMN**は水平にスクロールされます複数列のリスト ボックスを指定します。  `SetColumnWidth` のメンバー関数は、列の幅を設定します。  
  
-   **LBS\_MULTIPLESEL**の文字列の選択は、ユーザーが文字列をクリックするか、ダブルクリックするたびに通常モードを切り替えます。  文字列はいくつでも選択できます。  
  
-   **LBS\_NODATA**は、データ リスト ボックスを指定します。  リスト ボックスの項目数が数値を超える場合、このスタイルを指定します。  非データ リスト ボックスは、**LBS\_OWNERDRAWFIXED** のスタイルを持つ **LBS\_SORT** または **LBS\_HASSTRINGS** のスタイルを持つことはできません。  
  
     非データ リスト ボックスはオーナー描画のリスト ボックスに似ていますが、項目の文字列やビットマップ データは含まれていません。  項目の追加、挿入、または削除するコマンドは、指定された項目のデータは常に無視します; リスト ボックスが常に失敗する要求内の文字列を返します。  システムは、オーナー ウィンドウに引かれなければ項目がある場合 `WM_DRAWITEM` メッセージを送信します。  `WM_DRAWITEM` メッセージとともに渡された `DRAWITEMSTRUCT` 構造体の itemID のメンバーには、描画される項目の行番号が示されます。  非データ リスト ボックスは `WM_DELETEITEM` メッセージを送信しません。  
  
-   **LBS\_NOINTEGRALHEIGHT**はリスト ボックスのサイズ リスト ボックスを作成したときに、アプリケーションで指定されたサイズです。  通常、Windows、リスト ボックスには部分的な項目を表示しないように、リスト ボックスのサイズを変更します。  
  
-   **LBS\_NOREDRAW**のリスト ボックスには変更が加えられたときに更新されません。  このスタイルは **WM\_SETREDRAW** メッセージを送信すると、いつでも変更できます。  
  
-   **LBS\_NOSEL**はリスト ボックスが表示選択できる項目であることを指定します。  
  
-   **LBS\_NOTIFY**の親ウィンドウはユーザーが文字列をクリックするか、ダブルクリックするたびに、入力メッセージを受け取ります。  
  
-   **LBS\_OWNERDRAWFIXED**はリスト ボックスのオーナー コンテンツを描画する必要があります。; リスト ボックスの項目に揃えます。  
  
-   **LBS\_OWNERDRAWVARIABLE**はリスト ボックスのオーナー コンテンツを描画する必要があります。; リスト ボックスの項目は高さに変化します。  
  
-   リスト ボックスの**LBS\_SORT** の文字列がアルファベット順に並べ替えられます。  
  
-   リスト ボックスの**LBS\_STANDARD** の文字列がアルファベット順に並べ替えられ、ユーザーが文字列をクリックするか、ダブルクリックするたびに、親ウィンドウが入力メッセージを受け取ります。  リスト ボックスが境界をすべての面に含まれています。  
  
-   **LBS\_USETABSTOPS**は文字列を描画するときにリスト ボックスはタブ文字を認識し、展開できます。  既定のタブ位置は 32 ダイアログ単位です。\(最適なダイアログ単位は水平方向または垂直方向の距離です。  1 個の水平ダイアログ単位は現在のダイアログ ベース幅の単位の 4 分の 1 と同じです。  ダイアログの基本単位は現在のシステム フォントの高さと幅に基づいて計算されます。  **GetDialogBaseUnits** の Windows 関数の戻り値はピクセルの現在のダイアログの基本単位\)。このスタイルは **LBS\_OWNERDRAWFIXED**で使用しないでください。  
  
-   **LBS\_WANTKEYBOARDINPUT**はリスト ボックスのオーナー リスト ボックスに入力フォーカスがあるときに、ユーザーがキーを押すたびに `WM_VKEYTOITEM` または `WM_CHARTOITEM` メッセージを受け取ります。  これは、アプリケーションがキーボード入力の特別な処理を実行できます。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../Topic/CListBox::Create.md)   
 [List Box Styles](http://msdn.microsoft.com/library/windows/desktop/bb775149)