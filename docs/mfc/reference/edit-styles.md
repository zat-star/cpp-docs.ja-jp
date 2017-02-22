---
title: "エディット スタイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ES_READONLY"
  - "ES_WANTRETURN"
  - "ES_UPPERCASE"
  - "ES_NUMBER"
  - "ES_AUTOHSCROLL"
  - "ES_LOWERCASE"
  - "ES_RIGHT"
  - "ES_MULTILINE"
  - "ES_PASSWORD"
  - "ES_NOHIDESEL"
  - "ES_OEMCONVERT"
  - "ES_LEFT"
  - "ES_CENTER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エディット スタイル [MFC]"
  - "ES_AUTOHSCROLL 定数"
  - "ES_AUTOVSCROLL 定数"
  - "ES_CENTER 定数"
  - "ES_LEFT 定数"
  - "ES_LOWERCASE 定数"
  - "ES_MULTILINE 定数"
  - "ES_NOHIDESEL 定数"
  - "ES_NUMBER 定数"
  - "ES_OEMCONVERT 定数"
  - "ES_PASSWORD 定数"
  - "ES_READONLY 定数"
  - "ES_RIGHT 定数"
  - "ES_UPPERCASE 定数"
  - "ES_WANTRETURN 定数"
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# エディット スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **ES\_AUTOHSCROLL**は行の最後に 10 文字で右に自動的にテキストを、ユーザー定義型文字スクロールします。  ユーザーが Enter キーを押すと、コントロールは位置 0 にすべてのテキストをスクロールします。  
  
-   **ES\_AUTOVSCROLL**は自動的に、最後の行に Enter キーを押したときの 1 ページ上のテキストをスクロールします。  
  
-   **ES\_CENTER**は、単一行または複数行エディット コントロールのテキストを中央揃えにします。  
  
-   **ES\_LEFT**は、単一行または複数行エディット コントロールのテキストを左寄せにします。  
  
-   **ES\_LOWERCASE**は小文字でユーザーがエディット コントロールに入力されるたびにすべての文字を変換します。  
  
-   **ES\_MULTILINE**は複数行のエディット コントロールを指定します。\(既定では単一行です\)。**ES\_AUTOVSCROLL** のスタイルを指定する場合、エディット コントロールは、ユーザーが Enter キーを押すと、できるだけ多くの行とスクロールを垂直方向に示します。  **ES\_AUTOVSCROLL** を指定しない場合、エディット コントロールはそれ以上行が表示できないときに Enter キーとできるだけ多くの行を示し、ビープ音を出します。  **ES\_AUTOHSCROLL** のスタイルを指定すると、複数行のエディット コントロールは自動的にキャレットがコントロールの右端まで中に水平にスクロールします。  新しい行を開始するには、ユーザーが Enter キーです。  **ES\_AUTOHSCROLL** を指定しない場合、コントロールは次の行の先頭に必要に応じて自動的に単語をラップします; 新しい行または Enter キーと起動します。  ワード ラップの位置はウィンドウのサイズによって決まります。  ウィンドウのサイズが変更されると、ワード ラップの位置が変更され、テキストが再表示されます。  複数行のエディット コントロールはスクロール バーを表示できます。  スクロール バーのあるエディット コントロールは、独自のスクロール バー メッセージを処理します。  スクロール バーのないエディット コントロールは、上記のようにスクロールし、親ウィンドウに送信するスクロール メッセージを処理します。  
  
-   通常は、エディット コントロール**ES\_NOHIDESEL**コントロールが入力フォーカスを受け取ったときにコントロールが入力フォーカスを失った隠し、選択を反転しますと選択を解除します。  **ES\_NOHIDESEL** を指定すると、この既定のアクションを削除します。  
  
-   **ES\_NUMBER**は数字しかエディット コントロールに送信されます。  
  
-   次に、エディット コントロールに入力された**ES\_OEMCONVERT**のテキストは、OEM 文字セットと ANSI への ANSI 文字セットに変換されます。  これは、OEM 文字にエディット コントロールで対象とし、ANSI に変換するようにアプリケーションが `AnsiToOem` の Windows 関数を呼び出すと、適切な文字変換ことを確認します。  このスタイルはファイル名を格納するエディット コントロールに最も役立ちます。  
  
-   **ES\_PASSWORD**は、エディット コントロールに入力できるように、すべての文字をアスタリスク \(\#\#\#\*\) を表示します。  アプリケーションは、表示される文字列を変更するに `SetPasswordChar` メンバー関数を使用できます。  
  
-   **ES\_READONLY**はユーザーがエディット コントロールに入力したり、テキストを編集することはできません。  
  
-   **ES\_RIGHT**は、単一行または複数行エディット コントロールのテキストを右寄せにします。  
  
-   **ES\_UPPERCASE**は大文字にユーザーがエディット コントロールに入力されるたびにすべての文字を変換します。  
  
-   **ES\_WANTRETURN**はテキストをダイアログ ボックスの複数行のエディット コントロールに入力中にユーザーが Enter キーを押したときに復帰を挿入することを指定します。  このスタイルがなくても、Enter キーを押すと押してダイアログ ボックスがプッシュ ボタンを設定するのと同じ効果があります。  このスタイルは単一行エディット コントロールには影響しません。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../Topic/CEdit::Create.md)   
 [Edit Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb775464)