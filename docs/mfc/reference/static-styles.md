---
title: "静的コントロール スタイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SS_SUNKEN"
  - "SS_CENTER"
  - "SS_ENHMETAFILE"
  - "SS_RIGHT"
  - "SS_BLACKRECT"
  - "SS_LEFTNOWORDWRAP"
  - "SS_GRAYFRAME"
  - "SS_USERITEM"
  - "SS_GRAYRECT"
  - "SS_WHITEFRAME"
  - "SS_ETCHEDFRAME"
  - "SS_ETCHEDVERT"
  - "SS_WHITERECT"
  - "SS_PATHELLIPSIS"
  - "SS_WORDELLIPSIS"
  - "SS_NOPREFIX"
  - "SS_BITMAP"
  - "SS_SIMPLE"
  - "SS_CENTERIMAGE"
  - "SS_BLACKFRAME"
  - "SS_OWNERDRAW"
  - "SS_REALSIZEIMAGE"
  - "SS_RIGHTJUST"
  - "SS_ICON"
  - "SS_NOTIFY"
  - "SS_ETCHEDHORZ"
  - "SS_LEFT"
  - "SS_ENDELLIPSIS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SS_BITMAP 定数"
  - "SS_BLACKFRAME 定数"
  - "SS_BLACKRECT 定数"
  - "SS_CENTER 定数"
  - "SS_CENTERIMAGE 定数"
  - "SS_ENDELLIPSIS 定数"
  - "SS_ENHMETAFILE 定数"
  - "SS_ETCHEDFRAME 定数"
  - "SS_ETCHEDHORZ 定数"
  - "SS_ETCHEDVERT 定数"
  - "SS_GRAYFRAME 定数"
  - "SS_GRAYRECT 定数"
  - "SS_ICON 定数"
  - "SS_LEFT 定数"
  - "SS_LEFTNOWORDWRAP 定数"
  - "SS_NOPREFIX 定数"
  - "SS_NOTIFY 定数"
  - "SS_OWNERDRAW 定数"
  - "SS_PATHELLIPSIS 定数"
  - "SS_REALSIZEIMAGE 定数"
  - "SS_RIGHT 定数"
  - "SS_RIGHTJUST 定数"
  - "SS_SIMPLE 定数"
  - "SS_SUNKEN 定数"
  - "SS_USERITEM 定数"
  - "SS_WHITEFRAME 定数"
  - "SS_WHITERECT 定数"
  - "SS_WORDELLIPSIS 定数"
  - "静的なスタイル"
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 静的コントロール スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SS\_BITMAP**、ビットマップをスタティック コントロールに表示されるように指定します。  指定したテキストは、リソース ファイルの他の場所で定義されたビットマップではなくファイル名\) の名前です。  スタイルは nWidth nHeight とパラメーターを無視します; コントロールが自動的にビットマップを格納するために合わせて自動的に調整されます。  
  
-   **SS\_BLACKFRAME**はフレーム ウィンドウと同じ色で描画フレームのボックスを指定します。  既定値は黒です。  
  
-   **SS\_BLACKRECT**はウィンドウ フレームの描画に使用する色で塗りつぶされた四角形を指定します。  既定値は黒です。  
  
-   **SS\_CENTER**は単純な四角形を指定し、四角形の中央に指定した文字列を表示します。  テキストが表示される前に書式設定されます。  行の末尾を超えて拡張 Word は次にフォーカスした行の先頭に自動的にラップされます。  
  
-   **SS\_CENTERIMAGE**はアイコンまたはビットマップをスタティック コントロールのクライアント領域よりも小さい場合、クライアント領域の他、ビットマップ、アイコンの左上隅のピクセルの色に設定されていることを指定します。  スタティック コントロールは、単一行のテキストが含まれている場合、テキストは、コントロールのクライアント領域の垂直方向に中央揃えします。  
  
-   **SS\_ENDELLIPSIS** または **SS\_PATHELLIPSIS**は省略記号で指定された文字列の一部を、指定された四角形の結果の範囲必要に置き換えます。  
  
     文字列の中にある文字を置き換える文字列の末尾に文字を置き換えるために **SS\_END\_ELLIPSIS** または **SS\_PATHELLIPSIS** を指定できます。  文字列が円記号 \(\\\) 文字が含まれている場合は、最後の有効円記号の後のテキストの **SS\_PATHELLIPSIS** の保存できるだけです。  
  
-   **SS\_ENHMETAFILE**は拡張メタファイルをスタティック コントロールに表示されるように指定します。  指定されたテキストはメタファイルの名前です。  拡張メタファイルのスタティック コントロール サイズは固定です; メタファイルは、スタティック コントロールのクライアント領域に合わせてスケーリングされます。  
  
-   **SS\_ETCHEDFRAME**は  **EDGE\_ETCHED** の末尾のスタイルを使用してスタティック コントロールのフレームを描画します。  
  
-   **SS\_ETCHEDHORZ**は  **EDGE\_ETCHED** の末尾のスタイルを使用してスタティック コントロールの上端と下端を描画します。  
  
-   **SS\_ETCHEDVERT**は EDGE\_ETCHED の末尾のスタイルを使用してスタティック コントロールの左端を描画します。  
  
-   **SS\_GRAYFRAME**は画面の背景 \(デスクトップ\) と同じ色で描画フレームのボックスを指定します。  既定値は灰色です。  
  
-   **SS\_GRAYRECT**は画面の背景を塗りつぶすために使用する色で塗りつぶされた四角形を指定します。  既定値は灰色です。  
  
-   **SS\_ICON**はダイアログ ボックスに表示するアイコンを指定します。  指定したテキストは、リソース ファイルの他の場所で定義されたアイコンではなくファイル名\) の名前です。  `nWidth` と `nHeight` ;パラメーターは無視されます。アイコンが自動的に変更されます。  
  
-   **SS\_LEFT**は四角形で単純な四角形を指定し、指定したテキストを左寄せになります表示されます。  テキストが表示される前に書式設定されます。  行の末尾を超えて拡張 Word は次の先頭に自動的に左寄せにします行をラップされます。  
  
-   **SS\_LEFTNOWORDWRAP**は四角形で単純な四角形を指定し、指定したテキストを左寄せになります表示されます。  タブが展開されますが、Word がラップされません。  テキスト。行の末尾を超えてクリップ拡張。  
  
-   このスタイルが指定されていない場合**SS\_NOPREFIX**、Windows は、アクセラレータの先頭文字になるようにコントロールのテキストにアンパサンド \(&\) 文字を変換します。  この場合、アンパサンドは削除され、文字列の次の文字は下線付きになります。  スタティック コントロールはこの機能は不要であるテキストを含める場合は、**SS\_NOPREFIX** が追加される場合があります。  このスタティック コントロールのスタイルが定義されたスタティック コントロールのいずれかに含まれている場合があります。  他のスタイルとビットごとの OR 演算子を使用して **SS\_NOPREFIX** を結合できます。  これは最も頻繁に使用される時ダイアログ ボックスのスタティック コントロールに表示されるアンパサンドのニーズを含む可能性のある他の文字列またはファイル名。  
  
-   **SS\_NOTIFY**は、ユーザーがコントロールをクリックするか、ダブルクリックすると親ウィンドウ **STN\_CLICKED**、**STN\_DBLCLK**、**STN\_DISABLE**と **STN\_ENABLE** 通知メッセージを送信します。  
  
-   **SS\_OWNERDRAW**はスタティック コントロールの所有者がコントロールの描画を行うことを指定します。  オーナー ウィンドウは `WM_DRAWITEM` メッセージをたびに制御が描画されます。  
  
-   **SS\_REALSIZEIMAGE**は、読み込まれるか、描画されるように **SS\_ICON** または **SS\_BITMAP** のスタイルを持つ静的なアイコンまたはビットマップのコントロール \(スタティック コントロール\) にサイズ変更されるようにします。  アイコンまたはビットマップがコピー先領域よりも大きい場合は、イメージがクリップされます。  
  
-   **SS\_RIGHT**は四角形で単純な四角形を指定し、指定したテキストを右寄せになります表示されます。  テキストが表示される前に書式設定されます。  行の末尾を超えて拡張 Word は次の先頭に自動的に右寄せにします行をラップされます。  
  
-   **SS\_RIGHTJUST**は  **SS\_BITMAP** または **SS\_ICON** のスタイルのスタティック コントロールの右下隅にコントロールのサイズが変更されたときに固定しておくことを指定します。  上端と左側に新しいビットマップまたはアイコンに合わせて調整されます。  
  
-   **SS\_SIMPLE**は四角形で単純な四角形を指定し、単一行のテキストを左寄せになります表示されます。  テキスト行では、短くしたり変更したりすることはできません。\(コントロールの親ウィンドウまたはダイアログ ボックスが `WM_CTLCOLOR` メッセージを処理する必要があります\)。  
  
-   **SS\_SUNKEN**はスタティック コントロールの周囲にくぼんだ境界を描画します。  
  
-   **SS\_USERITEM**はユーザー定義の項目を指定します。  
  
-   **SS\_WHITEFRAME**はウィンドウの背景と同じ色で描画フレームのボックスを指定します。  既定の色は白です。  
  
-   **SS\_WHITERECT**はウィンドウの背景を塗りつぶすために使用する色で塗りつぶされた四角形を指定します。  既定の色は白です。  
  
-   **SS\_WORDELLIPSIS**は収まらない切り捨てて、省略記号をテキストを追加します。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../Topic/CStatic::Create.md)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Static Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb760773)