---
title: "チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル | Microsoft Docs"
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
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows ランタイムをターゲットにする Visual C\+\+ プログラムを作成して、コマンド ライン上に構築できます。  Visual C\+\+ は Visual C\+\+ コンポーネント拡張 \(C\+\+\/CX\) をサポートしており、Windows ランタイム プログラミング モデルをターゲットにするための追加のタイプとオペレーターがあります。  C\+\+\/CX を使って Windows Phone 8.1、Windows Store、および Windows デスクトップのアプリを作成できます。  詳細については、「[C\+\+\/CX のツアー](http://msdn.microsoft.com/magazine/dn166929.aspx)」および「[Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)」を参照してください。  
  
 このチュートリアルでは、テキスト エディターを使って基本的な C\+\+\/CX プログラムを作成し、コマンド ラインでコンパイルします。  \(表示されているプログラムをタイプするのではなく、自分の C\+\+\/CX プログラムを使用するか、別のヘルプ記事の C\+\+\/CX コード サンプルを使用できます。  この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です。\)  
  
> [!NOTE]
>  Visual Studio IDE を使って C\+\+\/CX プログラムをコンパイルすることもできます。  IDE には、コマンド ラインでは利用できない、デザイン、デバッグ、エミュレーション、および配置のサポートが含まれているため、Windows ストア アプリをビルドする場合は IDE を使用することをお勧めします。  詳細については、「[Create a basic C\+\+ Store app](http://msdn.microsoft.com/library/windows/apps/dn263168)」を参照してください。  
  
## 必須コンポーネント  
 C\+\+ 言語の基本を理解している必要があります。  
  
## C\+\+\/CX プログラムのコンパイル  
 C\+\+\/CX のコンパイルを有効にするには、[\/ZW](../build/reference/zw-windows-runtime-compilation.md) コンパイラ オプションを使用する必要があります。  Visual C\+\+ コンパイラは、Windows Runtime をターゲットにする .exe ファイルを生成し、必要なライブラリにリンクします。  
  
#### コマンド ラインで C\+\+\/CX アプリケーションをコンパイルするには:  
  
1.  **\[開発者コマンド プロンプト\]** ウィンドウを開きます。  \(**\[スタート\]** ウィンドウで、**\[アプリ\]** を開きます。  使用しているバージョンの [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] の **\[Visual Studio ツール\]** フォルダーを開き、**\[開発者コマンド プロンプト\]** ショートカットを選択します\)。コマンド プロンプト ウィンドウを開く方法の詳細については、「[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。  
  
     コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。  管理者としてコマンド プロンプト ウィンドウを実行するには、**\[開発者コマンド プロンプト\]** のショートカット メニューを開いて **\[管理者として実行\]** を選択します。  
  
2.  コマンド プロンプトで、「**notepad basiccx.cpp**」と入力します。  
  
     ファイルを作成するかどうかを確認するメッセージが表示されたら、**\[はい\]** を選択します。  
  
3.  メモ帳で、次の行を入力します。  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  メニュー バーで、**\[ファイル\]**、**\[保存\]** の順に選択します。  
  
     Windows Runtime [プラットフォーム名前空間](../Topic/Platform%20namespace%20\(C++-CX\).md) 名前空間を使用する Visual C\+\+ ソース ファイルが作成されました。  
  
5.  コマンド プロンプトで、「**cl \/EHsc \/ZW basiccx.cpp \/link \/SUBSYSTEM:CONSOLE**」と入力します。  cl.exe コンパイラは、ソース コードを .obj ファイルにコンパイルした後、リンカーを実行して basiccx.exe という名前の実行プログラムを生成します。  \([\/EHsc](../build/reference/eh-exception-handling-model.md) コンパイラ オプションは C\+\+ 例外処理モデルを指定し、[\/link](../Topic/-link%20\(Pass%20Options%20to%20Linker\).md) フラグはコンソール アプリケーションを指定します。\)  
  
6.  basiccx.exe プログラムを実行するには、コマンド プロンプトで「**basiccx**」と入力します。  
  
     プログラムは、次のテキストを表示して終了します。  
  
  **これは C\+\+\/CX プログラムです。**  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)