---
title: "HTML の基礎 | Microsoft Docs"
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
  - "HTML, 概要 (HTML の)"
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HTML の基礎
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどのブラウザーでは、表示するページの HTML ソースを確認できます。  ユーザーが複数の HTML \(ハイパーテキストのマークアップ言語\) を参照するソースを表示するとき、テキストが混在している山かっこで \(\<\>\) で囲みます。  
  
 HTML を使用して以下の手順では、簡単な Web ページを作成するためのタグ。  これらの手順では、メモ帳のファイルにプレーンテキストを入力し、数を変更してファイルを保存し、変更を参照するために、ブラウザーのページを再読み込みします。  
  
#### HTML ファイルを作成するには  
  
1.  メモ帳か、プレーンテキスト エディターを開きます。  
  
2.  **ファイル** メニューで、`New`をクリックします。  
  
3.  次の行を入力する:  
  
    ```  
    <HTML>  
    <HEAD>  
    <TITLE>Top HTML Tags</TITLE>  
    </HEAD>  
    </HTML>  
    ```  
  
4.  **ファイル** メニューで、**\[保存\]** をクリックします、c:\\webpages\\First.htm.としてファイルを保存します。  エディターにファイルを開いたままにしておきます。  
  
5.  **ファイル** メニューのブラウザーを選択するか **開く**を入力するブラウザーの URL のエディット ボックスの `file://C:/webpages/first.htm` をに切り替えれば。  ウィンドウ キャプションを持つ空のページが「HTML タグを超えるのを参照する必要があります」。  
  
     タグが山かっこ組み合わせられに格納されていることを確認します。  タグでは大文字と小文字を区別しませんが、タグを際立たせます大文字がよく使用されます。  
  
     タグ \<は HTML\> ドキュメントを起動し、\/HTML\> タグ \<を終了します。  終了タグ \(常に必要\) 開始タグと同じですが、タグの前にはスラッシュ \(\/\) です。  そこに山かっこ \(\<\) と開始タグの間には空白が必要です。  
  
6.  \/HEAD の行、型とメモ帳 \<に戻る\> とと:  
  
    ```  
    <BODY>  
    HTML is swell.  
    Life is good.  
    </BODY>  
    ```  
  
7.  **ファイル** メニューで、**\[保存\]** をクリックします。  
  
8.  ブラウザーに戻り、ページを更新します。  
  
     Word、ブラウザー ウィンドウのクライアント領域に表示されます。  復帰を無視することに注意してください。  改行する場合に、最初の行 `<BR>` タグが必要です。  
  
     ドキュメントの本文に追加する本体\> と \<\/BODY\> まで \<の テキストには続いたり、挿入するすべての手順です。  
  
9. ヘッダーを追加する:  
  
    ```  
    <H3>Here's the big picture</H3>  
    ```  
  
10. ページと同じディレクトリに格納される .gif ファイルを使用してイメージを追加する:  
  
    ```  
    <IMG src="yourfile.gif">  
    ```  
  
11. リストを追加する:  
  
    ```  
    <UL>Make me an unordered list.  
    <LI>One programmer</LI>  
    <LI>Ten SDKs</LI>  
    <LI>Great Internet Apps</LI>  
    </UL>  
    ```  
  
12. リストに番号を追加するには、\/UL の UL\> と \<タグの代わりに、\<OL \<\> と \<\/OL\> タグを\> 使用します。  
  
 これは開始する必要があります。  Web ページの大きい機能を参照すれば、HTML ソースを調べることによってどのように作成されるかを確認できます。  Microsoft の Front Page などの HTML エディターは単純と詳細ページを作成するために使用できます。  
  
 、ビルドしているファイルのすべての HTML ソースを次に示します。:  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 タグの詳細については、"属性と拡張は、Hypertext Markup Language \(HTML\) 仕様を参照します:  
  
 [http:\/\/www.w3.org\/pub\/WWW\/MarkUp\/](http://www.w3.org/pub/WWW/MarkUp/)  
  
## 参照  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)