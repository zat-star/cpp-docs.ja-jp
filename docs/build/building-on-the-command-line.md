---
title: "コマンドラインで C/C++ コードをビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f613c20e0cab45a8eaa802c4c7ba0c6ac391357
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="build-cc-code-on-the-command-line"></a>コマンドラインで C/C++ コードをビルドします。

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に含まれているツールを使用して、コマンド ラインで C および C++ アプリケーションをビルドできます。

C++ のワークロードのいずれかを選択すると、 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] C/C++ コンパイラ、リンカーが含まれているツールセットをインストールし、他のツールをビルドします。 これらのツールを使用して、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]の IDE であるとすることもできます、コマンドラインでします。 X86 ホストおよび x64 がホストする個別のコンパイラと x86、x64、および ARM を対象のコードを構築するためのツールがあります。 特定のホストとターゲットのビルド アーキテクチャ用のツールの各セットは、独自のディレクトリに格納されます。 正常に機能するこれらのツールのいくつか必要な特定の環境変数設定して、パスに追加するにはには、ファイル、ライブラリ ファイル、および SDK の場所が含まれます。 やすくこれらの環境変数を設定するには、インストーラーは、インストール中にカスタマイズされたコマンド ファイルでは、バッチ ファイルとも呼ばれるを作成します。 特定のビルドのアーキテクチャを設定するコマンド プロンプト ウィンドウでは、これらのコマンド ファイルのいずれかを実行できます。 便宜上、インストーラーもショートカットを作成、[スタート] メニュー (または Windows のスタート ページ 8.x) すべての必要な環境変数が設定され、準備ができて、使用するようにこれらのコマンド ファイルを使用して開発者コマンド プロンプト ウィンドウを起動します。 

必要な環境変数は、インストールして、ビルドのアーキテクチャを選択し、製品の更新プログラムやアップグレードによって変更される可能性に固有です。 そのため、インストールされているコマンド プロンプト ショートカットまたはコマンド ファイルのいずれかを自分で windows 環境変数を設定する代わりに使用することを強くお勧めします。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。  

コマンド ライン ツールセット、コマンド ファイルは、およびインストールされているコマンド プロンプト ショートカットは、コンピューターのプロセッサとのインストール時に選択したオプションによって異なります。 少なくとも 32 ビット x86 ネイティブ コードをビルドし、64 ビット x64 ネイティブ コードのビルド ツールに交差している 32 ビット x86 ホスト ツールがインストールされます。 64 ビットの Windows がある場合は、64 ビットのネイティブ コードをビルドし、32 ビットのネイティブ コードのビルド ツールに交差している 64 ビット x64 でホストされたツールもインストールされます。 省略可能な C++ ユニバーサル Windows プラットフォーム ツールをインストールする場合は、ARM コードをビルドする 32 ビットおよび 64 ビット ネイティブ ツールがインストールされます。 その他のワークロードでは、その他のツールをインストールできます。

<a name="developer_command_prompt_shortcuts"></a>
## <a name="developer-command-prompt-shortcuts"></a>開発者コマンド プロンプト ショートカット

バージョン固有のコマンド プロンプトのショートカットがインストールされている[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)][スタート] メニューのフォルダーです。 基本のコマンド プロンプトのショートカットとサポートするビルド アーキテクチャの一覧を次に示します。

- **開発者コマンド プロンプト**を 32 ビット x86 ネイティブ ツールを使用して、32 ビット、x86 ネイティブ コードをビルドする環境を設定します。  
- **x86 native Tools コマンド プロンプト**を 32 ビット x86 ネイティブ ツールを使用して、32 ビット、x86 ネイティブ コードをビルドする環境を設定します。  
- **x64 native Tools コマンド プロンプト**を 64 ビット、x64 ネイティブ ツールを使用して、64 ビット、x64 ネイティブ コードをビルドする環境を設定します。  
- **x86_x64 Cross Tools コマンド プロンプト**を 32 ビット x86 ネイティブ ツールを使用して、64 ビット、x64 ネイティブ コードをビルドする環境を設定します。  
- **x64_x86 Cross Tools コマンド プロンプト**を 64 ビット、x64 ネイティブ ツールを使用して、32 ビット、x86 ネイティブ コードをビルドする環境を設定します。  

実際のスタート メニュー フォルダーとショートカット名前のバージョンによって異なります[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]をインストールして、インストールのいずれかに設定した場合のニックネームです。 たとえば、インストールされている場合、Visual Studio 2017 があり、15.3 のニックネーム インストールを許可した場合、開発者コマンド プロンプト ショートカットがという名前の**VS 2017 (15.3) 用開発者コマンド プロンプト**、という名前のフォルダーで**Visual Studio 2017**です。 

インストールしている場合、[構築ツールを Visual Studio 2017 の](https://go.microsoft.com/fwlink/p/?linkid=840931)または[Visual C 2015 のビルド ツール](http://landinghub.visualstudio.com/visual-cpp-build-tools)edition、ある可能性がありますのみ特定のネイティブまたはクロス ツールの 開発者コマンド プロンプト オプション。 

<a name="developer_command_prompt"></a>
## <a name="to-open-a-developer-command-prompt-window"></a>開発者コマンド プロンプト ウィンドウを開く  
  
1.  デスクトップで、ウィンドウを開く**開始**メニューのおよびを見つけてなど、Visual Studio のバージョンのフォルダーを開き、スクロール**Visual Studio 2017**です。 以前のバージョンの Visual Studio でのショートカットは、というサブフォルダーに**Visual Studio Tools**です。  
  
2.  フォルダーで、選択、**開発者コマンド プロンプト**Visual Studio のバージョンにします。 このショートカットは、アーキテクチャを使用する、既定ビルド ツールの 32 ビット、x86 ネイティブの 32 ビット、x86 ネイティブ コードをビルドする開発者コマンド プロンプト ウィンドウを起動します。 既定ではないビルド アーキテクチャを使用する場合は、ネイティブのいずれかを選択またはクロス ツール コマンド プロンプトをホストとターゲット アーキテクチャを指定します。 

開発者コマンド プロンプト ウィンドウを開くに高速の方法は、入力する*開発者コマンド プロンプト*デスクトップ検索 ボックスで、目的の結果を選択し、します。

<a name="developer_command_files"></a>
## <a name="developer-command-files-and-locations"></a>開発者コマンド ファイルと場所

既存のコマンド プロンプト ウィンドウで、アーキテクチャのビルド環境を設定する場合は、インストーラーによって作成されたコマンド ファイルのいずれかを行うこともできます。 これらのファイルの場所は、のバージョンによって異なります。[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]をインストールしていると、インストール中に行われた場所と名前の選択肢にします。 Visual Studio 2017、64 ビット コンピューター上の標準的なインストール場所は \Program Files (x86) \Microsoft Visual Studio\2017 で\\*エディション*ここで、*エディション*コミュニティがあります。Professional、Enterprise、BuildTools、または別の名前を入力します。 Visual Studio 2015 では、標準的なインストール場所は \Program Files (x86) \Microsoft Visual Studio 14.0 です。 

プライマリの開発者コマンド プロンプト コマンドのファイル、VsDevCmd.bat、は、common7 \tools のインストール ディレクトリのサブディレクトリにあります。 32 ビット x86 を構築する 32 ビット x86 ネイティブ ツールを使用する環境とビルド アーキテクチャ設定パラメーターが指定されていないときにコード。

追加のコマンド ファイルは、プロセッサのアーキテクチャに応じて、特定のビルドのアーキテクチャを設定して、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]ワークロードとインストールされているオプションです。 Visual Studio 2017 での VC\Auxiliary\Build サブディレクトリにあるこれらは、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]インストール ディレクトリです。 Visual Studio 2015 では、これらに VC、vc \bin、または vc \bin\\*アーキテクチャ*インストール ディレクトリのサブディレクトリ場所*アーキテクチャ*は 1 つのネイティブまたはクロスコンパイラ オプション。 これらのコマンド ファイルは、パラメーターを設定し、指定したビルド アーキテクチャ環境をセットアップする VsDevCmd.bat を呼び出します。 標準的なインストールには、これらのコマンド ファイルが含まれます。

- **vcvars32.bat**ツールを使用して、32 ビット x86 ネイティブ 32 ビット x86 をビルドするコードです。  
- **vcvars64.bat**ツールを使用して、64 ビット x64 ネイティブ 64 ビット x64 をビルドするコードです。  
- **vcvarsx86_amd64.bat** 32 ビット x86 ネイティブ クロス ツールを使用して、64 ビット x64 をビルドするコードです。  
- **vcvarsamd64_x86.bat** 64 ビット x64 ネイティブ クロス ツールを使用して、32 ビット x86 をビルドするコードです。  
- **vcvarsx86_arm.bat** ARM コードをビルドする 32 ビット x86 ネイティブ クロス ツールを使用します。  
- **vcvarsamd64_arm.bat** ARM コードをビルドする 64 ビット x64 ネイティブ クロス ツールを使用します。  
- **vcvarsall.bat**パラメーターを使用して、ホストとターゲット アーキテクチャに加え、SDK とプラットフォームのオプションを指定します。 使用して呼び出し、`/help`オプションの一覧のパラメーターです。  

> [!CAUTION]
>  Vcvarsall.bat ファイルとその他のコマンド ファイルには、コンピューターが異なります。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 再実行してください、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]インストーラーが不足しているファイルを置き換えます。  
>   
> vcvarsall.bat ファイルは、バージョンによっても異なります。 Visual C の現在のバージョンが Visual C の以前のバージョンは、コンピューターにインストールされている場合は実行されません vcvarsall.bat または別のコマンド ファイルから別のバージョンの同じコマンド プロンプト ウィンドウ。  
 
既存のコマンド ウィンドウで、特定のビルドのアーキテクチャを指定する最も簡単な方法では、vcvarsall.bat ファイルを使用します。 Vcvarsall.bat を使用してネイティブの 32 ビットまたは 64 ビット コンパイル用または x86、x64、または ARM プロセッサ; にクロス コンパイルのコマンドラインを構成する環境変数を設定することができます。Microsoft Store、ユニバーサル Windows プラットフォーム、または Windows デスクトップ プラットフォームを対象とする使用するには、どの Windows SDK の指定プラットフォーム ツールセットのバージョンを指定します。 Vcvarsall.bat が x86 の現在の 32 ビット ネイティブ コンパイラを使用するための環境変数を構成する引数が指定されていない場合 Windows デスクトップのターゲットです。 ただし、ネイティブのまたはクロス コンパイラ ツールを構成するのには使用できます。 コンパイラ構成がインストールされていないまたはビルド コンピューターのアーキテクチャ上で利用できることを指定すると、エラー メッセージが表示されます。 次の表は、サポートするアーキテクチャの引数を示します。  
  
|Vcvarsall.bat アーキテクチャ引数|コンパイラ|ホスト コンピューターのアーキテクチャ|ビルド出力のアーキテクチャ|  
|----------------------------|--------------|----------------------------------|-------------------------------|  
|x86|x86 32 ビット ネイティブ|x86、x64|x86|  
|x86\_amd64 または x86\_x64|on x86 クロス x64|x86、x64|X64|  
|x86_arm|ARM on x86 クロス|x86、x64|ARM|  
|amd64 または x64|x64 64 ビット ネイティブ|X64|X64|  
|amd64\_x86 または x64\_x86|x64 で x86 クロスします。|X64|x86|  
|amd64\_arm または x64\_arm|ARM on x64 クロス|X64|ARM|  
  
使用することができます、**格納**または**uwp**プラットフォームの種類、またはどちらも、デスクトップ アプリを指定するを指定するオプションです。 Windows SDK のバージョンを指定するには 10.0.10240.0 などのすべての Windows 10 SDK 数字を使用したり 8.1、Windows 8.1 SDK を使用するを指定できます。 14.0 を使用して、Visual Studio 2015 コンパイラ ツールセットです。既定では、Visual Studio 2017 コンパイラ ツールセットを使用する環境が設定されます。

<a name="vcvarsall"></a>
## <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>既存のコマンド プロンプト ウィンドウで、ビルド環境をセットアップするには  
  
1.  コマンド プロンプトで、Visual Studio インストール ディレクトリに変更する CD コマンドを使用します。 次に、構成に固有のコマンド ファイルを含むサブディレクトリに変更する CD をもう一度使用します。 Visual Studio 2017、これは VC\Auxiliary\Build サブディレクトリです。 Visual Studio 2015 では、VC サブディレクトリを使用します。  
  
1.  ツールを使用する 32 ビット x86 用のコードをビルドするには、このコマンド プロンプト ウィンドウを構成するのにはプラットフォームでは、コマンド プロンプトで入力してください。  
  
     `vcvarsall`  

1.  32 ビット ツールを使用して x64 用のコードをビルドするには、このコマンド プロンプト ウィンドウを構成するのにはプラットフォームでは、コマンド プロンプトを入力します。  
  
     `vcvarsall x86_amd64`  
  
1.  32 ビット ツールを使用して、ARM プラットフォームでは、コマンド プロンプトでのコードを構築するには、このコマンド プロンプト ウィンドウを構成するには、次のように入力します。  
  
     `vcvarsall x86_arm`  
  
1.  ツールを使用して 64 ビット x64 用のコードをビルドするには、このコマンド プロンプト ウィンドウを構成するのにはプラットフォームでは、コマンド プロンプトで入力してください。  
  
     `vcvarsall amd64`  
  
1.  ツールを使用して 64 ビット x86 用のコードをビルドするには、このコマンド プロンプト ウィンドウを構成するのにはプラットフォームでは、コマンド プロンプトで入力してください。  
  
     `vcvarsall amd64_x86`  
  
1.  64 ビット ツールを使用して、ARM プラットフォームでは、コマンド プロンプトでのコードを構築するには、このコマンド プロンプト ウィンドウを構成するには、次のように入力します。  
  
     `vcvarsall amd64_arm`  

コマンド ファイルは、ビルド ツール、ライブラリ、およびヘッダーをパスの必要な環境変数を設定します。 このコマンド プロンプト ウィンドウを使用して、コマンド ライン コンパイラおよびツールを実行することができますようになりました。  
  
使用している場合[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)コマンド ライン ビルドの場合は、vcvarsall.bat またはその他のコマンド ファイルで設定した環境には影響しません、ビルドにも指定しない限り、 **/useenv**オプション。  

## <a name="command-line-tools"></a>コマンド ライン ツール
  
コマンドラインで C/C++ プロジェクトをビルドするには、これら Visual C のコマンド ライン ツールを使用できます。  
  
[CL](../build/reference/compiling-a-c-cpp-program.md)  
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。  
  
[リンク](../build/reference/linking.md)  
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
MSBuild (msbuild.exe) を使用して Visual C プロジェクトをビルドおよび[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]ソリューションです。 これは、実行中に、**ビルド**プロジェクトまたは**ソリューションのビルド**コマンドを[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]IDE です。  
  
[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)  
コマンド ライン スイッチと組み合わせて使用 DEVENV (devenv.exe) を使用する — たとえば、 **/build**または**/clean**— を実行する特定ビルド コマンドを表示せず、 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE です。  
  
[(NMAKE の)](../build/nmake-reference.md)  
NMAKE (nmake.exe) を使用すると、従来のメイクファイルを使用して Visual C プロジェクトをビルドするタスクを自動化できます。  
  
コマンドラインでビルドする場合は、警告、エラー、およびメッセージに関する情報を取得できます。 開始[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]し、メニュー バーで、次のように選択します。**ヘルプ**、**検索**です。  
  
## <a name="in-this-section"></a>このセクションの内容  

ドキュメントのこのセクションの記事では、コマンド ラインでアプリをビルドする方法を示し、64 ビット ツールセットを使用して x86、x64、および ARM プラットフォームを対象とするように、コマンド ライン ビルド環境をカスタマイズする方法について説明し、コマンド ライン ビルド ツール MSBuild および NMAKE を使用する方法を示します。  
  
[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
コマンド ラインで単純な C++ プログラムを作成およびコンパイルする方法を示す例があります。  
  
[チュートリアル: コマンドラインでの C プログラムをコンパイルします。](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
C プログラミング言語で書かれたプログラムをコンパイルする方法について説明します。  
  
[チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
.NET Framework を使用する C++/CLI プログラムを作成およびコンパイルする方法について説明します。  
  
[チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
Windows ランタイムを使用する C++/CX プログラムを作成およびコンパイルする方法について説明します。  
  
[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
ターゲットとする x86、x64、コマンド ライン ビルドの設定および ARM プラットフォームを 32 ビットまたは 64 ビット ツールセットを使用して必要な環境変数を持つコマンド プロンプト ウィンドウを起動する方法について説明します。  
  
[NMAKE リファレンス](../build/nmake-reference.md)  
NMAKE.EXE (Microsoft Program Maintenance Utility) について説明する記事へのリンクがあります。  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
MSBuild.EXE の使用方法について説明する記事へのリンクがあります。  
  
## <a name="related-sections"></a>関連項目  

[/MD、/MT、/LD (ランタイム ライブラリの使用)](../build/reference/md-mt-ld-use-run-time-library.md)  
デバッグ バージョンまたはリリース バージョンのランタイム ライブラリを使用するための、コンパイラ オプションの使用方法について説明します。  
  
[C/C++ コンパイラ オプション](../build/reference/compiler-options.md)  
C と C++ のコンパイラ オプションおよび CL.exe に関する記事へのリンクがあります。  
  
[リンカー オプション](../build/reference/linker-options.md)  
リンカー オプションおよび LINK.exe に関する記事へのリンクがあります。  
  
[C/C++ のビルド ツール](../build/reference/c-cpp-build-tools.md)  
[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に含まれている C/C++ ビルド ツールへのリンクがあります。  
  
## <a name="see-also"></a>参照  

[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)