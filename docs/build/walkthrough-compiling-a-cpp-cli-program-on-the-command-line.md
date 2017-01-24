---
title: "チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共通言語ランタイム \(CLR\) を対象とし、.NET Framework を使用する Visual C\+\+ プログラムを作成して、コマンド ラインでビルドできます。  Visual C\+\+ では C\+\+\/CLI プログラミング言語がサポートされます。このプログラミング言語には、.NET プログラミング モデルを対象とする追加の型と演算子があります。  C\+\+\/CLI 言語の概要については、「[Pure C\+\+: Hello, C\+\+\/CLI](http://msdn.microsoft.com/magazine/cc163681.aspx)」を参照してください。  一般情報については、「[C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。  
  
 このチュートリアルでは、テキスト エディターを使って基本的な C\+\+\/CLI プログラムを作成し、コマンド ラインでコンパイルします。  \(表示されているプログラムをタイプするのではなく、自分の C\+\+\/CLI プログラムを使用するか、別のヘルプ記事の C\+\+\/CLI コード サンプルを使用できます。  この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です。\)  
  
> [!NOTE]
>  Visual Studio IDE を使用して C\+\+\/CLI プログラムをコンパイルすることもできます。  詳細については、「[チュートリアル: Visual Studio で CLR をターゲットにした C\+\+ プログラムのコンパイル](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)」を参照してください。  
  
## 必須コンポーネント  
 C\+\+ 言語の基本を理解している必要があります。  
  
## C\+\+\/CLI プログラムのコンパイル  
 次の手順は、.NET Framework クラスを使用する C\+\+\/CLI コンソール アプリケーションをコンパイルする方法を示します。  
  
 C\+\+\/CLI のコンパイルを有効にするには、[\/clr](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを使用する必要があります。  Visual C\+\+ コンパイラは、MSIL コードまたは MSIL とネイティブ コードの混合を含む .exe ファイルを生成し、必要な .NET Framework ライブラリにリンクします。  
  
#### C\+\+\/CLI アプリケーションをコマンド ラインでコンパイルするには  
  
1.  **\[開発者コマンド プロンプト\]** ウィンドウを開きます。  \(**\[スタート\]** ウィンドウで、**\[アプリ\]** を開きます。  使用しているバージョンの [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] の **\[Visual Studio ツール\]** フォルダーを開き、**\[開発者コマンド プロンプト\]** ショートカットを選択します\)。コマンド プロンプト ウィンドウを開く方法の詳細については、「[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。  
  
     コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。  管理者としてコマンド プロンプト ウィンドウを実行するには、**\[開発者コマンド プロンプト\]** のショートカット メニューを開いて **\[管理者として実行\]** を選択します。  
  
2.  コマンド プロンプトで、「**notepad basicclr.cpp**」と入力します。  
  
     ファイルを作成するかどうかを確認するメッセージが表示されたら、**\[はい\]** を選択します。  
  
3.  メモ帳で、次の行を入力します。  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  メニュー バーで、**\[ファイル\]**、**\[保存\]** の順に選択します。  
  
     <xref:System> 名前空間にある、.NET Framework クラス \(<xref:System.Console>\) を使用する Visual C\+\+ ソース ファイルを作成しました。  
  
5.  コマンド プロンプトで、「**cl \/clr basicclr.cpp**」と入力します。  cl.exe コンパイラによって、ソース コードは MSIL を含む .obj ファイルにコンパイルされ、リンカーが実行されて basicclr.exe という名前の実行可能プログラムが生成されます。  
  
6.  basicclr.exe プログラムを実行するには、コマンド プロンプトで「**basicclr**」と入力します。  
  
     プログラムは、次のテキストを表示して終了します。  
  
  **This is a C\+\+\/CLI program.**  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)