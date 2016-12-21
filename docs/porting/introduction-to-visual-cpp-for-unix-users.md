---
title: "Visual C++ の紹介 (UNIX ユーザー向け) | Microsoft Docs"
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
helpviewer_keywords: 
  - "UNIX [C++]"
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ の紹介 (UNIX ユーザー向け)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を初めて使用し、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] で生産性を向上したい UNIX ユーザー向けの情報を提供します。  
  
## コマンドラインに関する概要  
 UNIX のコマンドライン環境を使用するのと同様の方法で、コマンドラインから [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を使用できます。  Microsoft バージョンの UNIX make ユーティリティである NMAKE.EXE を含むコマンド ラインの C と C\+\+ コンパイラ \(CL.EXE\) およびツールを使用して、コマンド プロンプトからコンパイルします。  
  
 UNIX では、コマンドは \/usr\/bin などの共通のフォルダーにインストールされます。  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では、コマンドライン ツールはインストール ディレクトリの VC\\bin \(標準インストールでは Program Files\\Microsoft Visual Studio 8\\VC\\bin\) にインストールされます。  コマンドライン ツールを使用するには、Common7\\Tools のインストール ディレクトリにある、vsvars32.bat を実行します。  これは、bin ディレクトリをパスに追加し、コマンド ラインから Visual C\+\+ プログラムをコンパイルするために必要なその他のパスを設定します。  
  
> [!NOTE]
>  **\[スタート\]** メニューの **\[Visual Studio のコマンド ライン プロンプト\]** を使用してコマンド プロンプトを開く場合、vsvars32.bat が実行されます。  
  
 デバッガー、ステートメント入力候補などのより強力な機能を活用するには、開発環境を使用する必要があります。  詳細については、「[コマンド ラインでのビルド](../Topic/Building%20on%20the%20Command%20Line.md)」および「[チュートリアル: コマンド ラインでのネイティブ C\+\+ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。  
  
## コードのデバッグ  
 コマンドラインを使用して開発用ワークステーションでアプリケーションを実行する場合、コードでメモリ アクセス違反、ハンドルされない例外や、その他の回復不能なエラーが発生したときに、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] デバッガーを実行するダイアログ ボックスが表示されます。  **\[OK\]** をクリックすると、Visual Studio の開発環境が起動し、障害発生時点でデバッガーが開きます。  この方法でアプリケーションをデバッグすることができますが、このケースでは、[\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) スイッチを使用してコンパイルした場合にのみ、ソースを利用できます。  詳細については、「[ネイティブ コードのデバッグ](../Topic/Debugging%20Native%20Code.md)」および「[C\+\+ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。  
  
## 開発環境を使用する  
 開発環境を使用すると、*プロジェクト*でソース コードを編集してビルドしやすくなります。  プロジェクトは、ライブラリまたは実行可能ファイルなどの 1 つの単位にコンパイルされる、ソースと関連ファイルのコレクションです。  プロジェクトには、ファイルをビルドする方法に関する情報も含まれます。  プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。  
  
 それぞれが別のセットのコンパイラ オプションや別の言語でビルドされている可能性がある複数のライブラリおよび実行可能ファイルから構成されるアプリケーションは、1 つの*ソリューション*の一部である複数のプロジェクトに格納されます。  ソリューションは、複数のプロジェクトをグループ化するためのコンテナーの抽象化です。  プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。  詳細については、「[PAVE: Managing Solutions and Projects](http://msdn.microsoft.com/ja-jp/7a50db22-d3cc-46f3-b648-ab7e0528e260)」および「[C\+\+ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。  
  
## 既存のコードをインポートする  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を使用して、メイクファイルを使用または使用せずにコンパイルするよう設定される既存のコードを使用し、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] プロジェクトに配置できます。  詳細については、「**既存コード ファイルからの新しいプロジェクトの作成ウィザード**」を参照してください。  詳細については、「[方法 : 既存のコードから C\+\+ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。  
  
## 新規プロジェクトの作成  
 開発環境では、新しいプロジェクトを作成できます。  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] はさまざまな共通プロジェクトの標準的なコードを提供する多数のテンプレートを提供します。  アプリケーション ウィザードを使用して、様々な種類のアプリケーション用のコードのアウトラインを持つプロジェクトを生成することができます。  
  
 まず、**コンソール アプリケーション \(Win32\) ウィザード**を使用して、空のプロジェクトを作成できます。  **\[空のプロジェクト\]** チェック ボックスをオンにします。  これで、新規および既存のファイルをプロジェクトに後で追加できます。  
  
 プロジェクトを作成するときに、プロジェクトの名前を付けてください。  既定では、プロジェクト名は、ダイナミック リンク ライブラリ \(DLL\) の名前またはプロジェクトからビルドされる実行可能ファイルと等しくなります。  詳細については、「[ソリューションとプロジェクトの作成](../Topic/Creating%20Solutions%20and%20Projects.md)」を参照してください。  
  
## Microsoft 固有の修飾子  
 Visual C\+\+ には、標準の c\+\+ プログラミング言語のいくつかの拡張機能が含まれています。  これらの拡張機能は、ストレージ クラス属性、関数の呼び出し規約、ベース アドレス指定などを指定するために使用されます。  すべての Visual C\+\+ の拡張機能の完全な一覧については、「[Microsoft 固有の修飾子](../Topic/Microsoft-Specific%20Modifiers.md)」」を参照してください。  
  
 **\/Za** コンパイラ オプションを使用して、C\+\+ へのすべての Microsoft 固有の拡張機能を無効にすることができます。  複数のプラットフォームで実行するコードを記述する場合、このオプションが推奨されます。  **\/Za** コンパイラ オプションの詳細については、「[\/Za、\/Ze \(言語拡張機能の無効化\)](../build/reference/za-ze-disable-language-extensions.md)」を参照してください。  Visual C\+\+ の準拠の詳細については、「[Visual C\+\+ での互換性と準拠の問題](../misc/compatibility-and-compliance-issues-in-visual-cpp.md)」を参照してください。  
  
## プリコンパイル済みヘッダー  
 Microsoft C および C\+\+ コンパイラは、インライン コードを含む、C または C\+\+ コードをプリコンパイルするためのオプションを提供します。  このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。  安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。  
  
 既定では、プリコンパイル済みのすべてのコードは、ファイル **stdafx.h** と **stdafx.cpp** で指定されます。  **\[プリコンパイル済みヘッダー\]** オプションをオフにしない限り、**\[新しいプロジェクト\]** ウィザードは自動的にこれらのファイルを作成します。  プリコンパイルされたヘッダーの詳細については、「[プリコンパイル済みヘッダー ファイルの作成](../build/reference/creating-precompiled-header-files.md)」を参照してください。  
  
## 関連項目  
 詳細については、「[UNIX から Win32 への移植](../porting/porting-from-unix-to-win32.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)