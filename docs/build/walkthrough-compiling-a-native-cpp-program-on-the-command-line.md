---
title: "チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ライン アプリケーション [C++], native"
  - "コンパイル (プログラムを) [C++]"
  - "ネイティブ コード [C++]"
  - "Visual C++, ネイティブ コード"
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
caps.latest.revision: 63
caps.handback.revision: 57
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ に含まれるコマンド ライン C\+\+ コンパイラを使用して、基本的なコンソール アプリからユニバーサル Windows アプリ、Windows ストア アプリおよび .NET コンポーネントまで、あらゆるものを作成できます。  
  
 このチュートリアルでは、テキスト エディターを使用して基本的な Visual C\+\+ コンソール プログラムを作成し、それをコマンド ラインでコンパイルします。  
  
> [!NOTE]
>  Visual Studio 統合開発環境 \(IDE\) を使用して Visual C\+\+ プログラムをコンパイルすることもできます。 詳細については、「[チュートリアル: プロジェクトとソリューションの使用 \(C\+\+\)](../Topic/Walkthrough:%20Working%20with%20Projects%20and%20Solutions%20\(C++\).md)」を参照してください。  
  
 このチュートリアルでは、表示されている Visual C\+\+ プログラムを入力する代わりに独自の Visual C\+\+ プログラムを使用するか、別のヘルプ記事の Visual C\+\+ コード サンプルを使用できます。  
  
## 必須コンポーネント  
 このチュートリアルを完了するには、Visual C\+\+ コンポーネントを含んだバージョンの Visual Studio が必要です。 C\+\+ 言語の基本を理解していると役立ちます。 以下の手順は、Windows 10 と Visual Studio 2015 を使用することを前提としていますが、その他の環境とバージョンでも手順は類似しています。  
  
### Visual C\+\+ ソース ファイルを作成してコマンド ラインでコンパイルするには  
  
1.  最初に、**\[開発者コマンド プロンプト\]** を開きます。 Visual C\+\+ コンパイラは特殊なコマンド環境でなければ実行できないため、このチュートリアルでは通常のコマンド プロンプトを使用できません。  
  
     Windows の **\[スタート\]** メニューで、**\[すべてのアプリ\]** を開きます。 下方にスクロールして、特定のバージョンの [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] の **\[Visual Studio\]** フォルダーを開き、**\[開発者コマンド プロンプト\]** ショートカットを選びます。  
  
2.  プログラムを保持するために、新しいディレクトリを作成します。**\[開発者コマンド プロンプト\]** ウィンドウで、`cd \` コマンドを入力して、ディレクトリをドライブのルートに変更します。`md examples` コマンドを入力して、コード例のためにディレクトリを作成します。`cd examples` コマンドを入力して、このディレクトリを現在の作業ディレクトリにします。 ここに最初のプログラムを入れます。  
  
3.  コマンド プロンプトで、**notepad hello.cpp** と入力します。  
  
     ファイルを作成するかどうかを確認するメッセージが表示されたら、**\[はい\]** を選択します。 これにより、メモ帳の空白ウィンドウが開き、コードを入力する準備が整います。  
  
4.  メモ帳で、次の行を入力します。  
  
    ```cpp  
    #include <iostream> using namespace std; void main() { cout << "Hello, world, from Visual C++!" << endl; }  
    ```  
  
     これは、画面上で 1 行のテキストを書き出して終了する、非常に単純なプログラムです。 エラーを最小限に抑えるには、このコードをコピーし、メモ帳に貼り付けます。  
  
5.  作業内容を保存します。 メモ帳で、**\[ファイル\]** メニューの **\[保存\]** を選びます。  
  
     Visual C\+\+ ソース ファイルが作成されました。  
  
6.  コマンド プロンプトで、`cl /EHsc hello.cpp` と入力してプログラムをコンパイルします。  
  
     cl.exe コンパイラによって、コンパイルされたコードを含む .obj ファイルが生成され、リンカーが実行されて hello.exe という名前の実行可能プログラムが作成されます。 この名前は、コンパイラによって表示される出力情報の行に表示されます。 コンパイラの出力は次のようになります。  
  
    ```Output  
    Microsoft (R) C/C++ Optimizing Compiler Version 19.00.23504 for x86 Copyright (C) Microsoft Corporation.  All rights reserved. hello.cpp Microsoft (R) Incremental Linker Version 14.00.23504.0 Copyright (C) Microsoft Corporation.  All rights reserved. /out:hello.exe hello.obj  
    ```  
  
     エラーがある場合は、メモ帳でコードを確認し、例と一致しているかどうかを調べます。 変更を保存した後で、コンパイラのコマンドをもう一度実行します。  cl コマンドが見つからない場合は、通常コマンド ウィンドウではなく、開発者コマンド プロンプトを使用していることを確認します。 まだインストールされていない場合は、Visual Studio のセットアップで Visual C\+\+ コンポーネントもインストールする必要があります。  
  
7.  hello.exe プログラムを実行するには、コマンド プロンプトで `hello` と入力します。  
  
     プログラムは、次のテキストを表示して終了します。  
  
    ```Output  
    Hello, world, from Visual C++!  
    ```  
  
     これで、コマンド ライン ツールを使用したプログラムの作成とコンパイルが完了しました。  
  
## 次の手順  
 開発者コマンド プロンプト ウィンドウを開いてコマンド ライン ツールを使用する方法について詳しくは、「[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)」をご覧ください。  
  
 コンピューターのオペレーティング システムと構成によっては、このチュートリアルのコードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 管理者として開発者コマンド プロンプト ウィンドウを実行するには、右クリックして **\[開発者コマンド プロンプト\]** のショートカット メニューを開いて **\[管理者として実行\]** を選びます。  
  
 **\/EHsc** は、コンパイラに対して C\+\+ 例外処理を有効化するよう指示するコマンド ライン オプションです。 詳細については、「[\/EH \(例外処理モデル\)](../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ ガイド ツアー](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)