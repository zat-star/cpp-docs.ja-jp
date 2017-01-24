---
title: "Visual C++ における MBCS のサポート | Microsoft Docs"
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
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アジアの言語 [C++]"
  - "文字セット [C++], マルチバイト"
  - "中国語の文字 [C++]"
  - "コード エディター [C++], MBCS サポート"
  - "デバッガー [C++], MBCS サポート"
  - "2 バイト文字セット [C++]"
  - "IME [C++]"
  - "IME [C++], MBCS"
  - "Input Method Editor [C++]"
  - "Input Method Editor [C++], MBCS"
  - "日本語の文字 [C++]"
  - "漢字のサポート [C++]"
  - "MBCS [C++], 有効化"
  - "マルチバイト文字 [C++]"
  - "NMAKE プログラム, MBCS サポート"
  - "リソース エディター [C++], MBCS サポート"
  - "ツール [C++], MBCS サポート"
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Visual C++ における MBCS のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MBCS をサポートしている Windows 2000 オペレーティング システムまたは Windows XP オペレーティング システム上で Visual C\+\+ 開発システムを実行すると、メモリ ウィンドウを除いて、システム内の統合ソース コード エディター、デバッガー、コマンド ライン ツールなどのすべてが MBCS をサポートします。  
  
 メモリ ウィンドウは、MBCS 文字として ANSI 文字または Unicode 文字として解釈できる場合でも、データのバイトを解釈されません。  ANSI 文字のサイズは常に 1 バイトで、Unicode 文字は 2 バイトです。  MBCS を使うと、文字が 1 である場合も、コード ページによって使用されているまたは 2 バイトと解釈が異なります。  このため、メモリ ウィンドウが確実に MBCS の文字を表示することは困難です。  メモリ ウィンドウは、文字の開始はどのバイトを特定することはできません。  開発者は、メモリ ウィンドウのバイト値を参照し、その値をテーブルで検索して文字表現を判断できます。  これは、開発者がソース コードに基づいて文字列の開始アドレスを理解しているためです。  
  
 Visual C\+\+ では、該当する部分で 2 バイト文字を入力できます。  つまり、ダイアログ ボックスではパス名およびファイル名に、Visual C\+\+ リソース エディターではテキスト入力に、2 バイト文字を使用できます。たとえば、ダイアログ エディターでは静的テキストとして、アイコン エディターでは静的テキストとして入力できます。  また、プリプロセッサも一部の 2 バイト ディレクティブを認識するようになります。たとえば、`#include` ステートメントのファイル名、**code\_seg** プラグマおよび **data\_seg** プラグマの as 引数などを認識します。  ソース コード エディターでは、コメントおよびリテラル文字列に 2 バイト文字を使用できますが、C\/C\+\+ 言語の要素 \(変数名など\) には使用できません。  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> IME \(Input Method Editor\) のサポート  
 MBCS を使用する日本などの東アジア市場向けに記述されたアプリケーションでは、通常、Windows IME をサポートして、1 バイト文字と 2 バイト文字の両方を入力できるようにしています。  Visual C\+\+ の開発環境では、IME を全面的にサポートしています。  詳細については、「[IME サンプル : IME モードの制御方法と IME レベル 3 の実装方法](http://msdn.microsoft.com/ja-jp/87ebdf65-cef0-451d-a6fc-d5fb64178b14)」を参照してください。  
  
 日本語のキーボードは、漢字を直接サポートしていません。  日本語のアルファベット \(ローマ字、カタカナ、またはひらがな\) のいずれかで入力された音節文字列は、IME によって該当する漢字表記に変換されます。  あいまいなときは、いくつかの選択肢から選択できます。  目的の漢字を選択すると、IME は 2 つの `WM_CHAR` メッセージを制御アプリケーションに渡します。  
  
 IME は Alt \+ \` キーでアクティブにします。アクティブになると、一連のボタン \(インジケーター\) と変換ウィンドウが表示されます。  アプリケーションでは、このウィンドウをテキスト挿入位置に移動します。  つまり、`WM_MOVE` メッセージと `WM_SIZE` メッセージの処理として、変換ウィンドウを新しい位置に再配置するか、ターゲット ウィンドウのサイズに合わせる必要があります。  
  
 アプリケーションのユーザーが漢字入力できるようにするには、アプリケーションで Windows IME メッセージを処理する必要があります。  IME プログラミングの詳細については、「[Input Method Editor](https://msdn.microsoft.com/en-us/library/ms776145.aspx)」を参照してください。  
  
## Visual C\+\+ デバッガー  
 Visual C\+\+ デバッガーでは、IME メッセージにブレークポイントを設定できます。  メモリ ウィンドウに 2 バイト文字を表示させることもできます。  
  
## コマンド ライン ツール  
 Visual C\+\+ のコマンド ライン ツールには、コンパイラ、NMAKE、リソース コンパイラ \(RC.EXE\) などがありますが、すべて MBCS をサポートしています。  アプリケーションのリソースをコンパイルするときにリソース コンパイラの \/c オプションを使うと、既定のコード ページを変更できます。  
  
 ソース コードのコンパイル時に既定のロケールを変更するには、[\#pragma setlocale](../preprocessor/setlocale.md) を使います。  
  
## グラフィカル ツール  
 Spy\+\+ やリソース編集ツールなどの Visual C\+\+ Windows ベースのツールは、IME 文字列を全面的にサポートしています。  
  
## 参照  
 [マルチバイト文字セット \(MBCS\) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)