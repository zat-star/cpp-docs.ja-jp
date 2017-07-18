---
title: "Visual C++ の紹介 (UNIX ユーザー向け) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7c75629d56e6d8e5291b7d1f7cca9995ab9a50da
ms.openlocfilehash: d8515fc613f95ae5d6395e33b49482488bcc488d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="introduction-to-visual-c-for-unix-users"></a>Visual C++ の紹介 (UNIX ユーザー向け)
このトピックでは、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を初めて使用し、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] で生産性を向上したい UNIX ユーザー向けの情報を提供します。  
  
## <a name="getting-started-on-the-command-line"></a>コマンドラインに関する概要  
 UNIX のコマンドライン環境を使用するのと同様の方法で、コマンドラインから [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を使用できます。 Microsoft バージョンの UNIX make ユーティリティである NMAKE.EXE を含むコマンド ラインの C と C++ コンパイラ (CL.EXE) およびツールを使用して、コマンド プロンプトからコンパイルします。  
  
 UNIX では、コマンドは /usr/bin などの共通のフォルダーにインストールされます。 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では、コマンドライン ツールはインストール ディレクトリの VC\bin (標準インストールでは Program Files\Microsoft Visual Studio 8\VC\bin) にインストールされます。 コマンドライン ツールを使用するには、Common7\Tools のインストール ディレクトリにある、vsvars32.bat を実行します。 これは、bin ディレクトリをパスに追加し、コマンド ラインから Visual C++ プログラムをコンパイルするために必要なその他のパスを設定します。 詳細については、「[コマンド ラインでのビルド](../build/building-on-the-command-line.md)」および「[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。  
  
> [!NOTE]
>  **[スタート]** メニューの **[Visual Studio のコマンド ライン プロンプト]** を使用してコマンド プロンプトを開く場合、vsvars32.bat が実行されます。  
  
 Visual Studio デバッガー、ステートメント入力候補などのより強力な機能を活用するには、開発環境を使用する必要があります。  
  
## <a name="debugging-your-code"></a>コードのデバッグ  
 コマンドラインを使用して開発用ワークステーションでアプリケーションを実行する場合、コードでメモリ アクセス違反、ハンドルされない例外や、その他の回復不能なエラーが発生したときに、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] デバッガーを実行するダイアログ ボックスが表示されます。 **[OK]** をクリックすると、Visual Studio の開発環境が起動し、障害発生時点でデバッガーが開きます。 この方法でアプリケーションをデバッグすることができますが、このケースでは、[/Z7、/Zi、/ZI (デバッグ情報の形式)](../build/reference/z7-zi-zi-debug-information-format.md) スイッチを使用してコンパイルした場合にのみ、ソースを利用できます。 詳細については、「[ネイティブ コードのデバッグ](/visualstudio/debugger/debugging-native-code)」および「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。  
  
## <a name="using-the-development-environment"></a>開発環境を使用する  
 開発環境を使用すると、*プロジェクト*でソース コードを編集してビルドしやすくなります。 プロジェクトは、ライブラリまたは実行可能ファイルなどの 1 つの単位にコンパイルされる、ソースと関連ファイルのコレクションです。 プロジェクトには、ファイルをビルドする方法に関する情報も含まれます。 プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。  
  
 それぞれが別のセットのコンパイラ オプションや別の言語でビルドされている可能性がある複数のライブラリおよび実行可能ファイルから構成されるアプリケーションは、1 つの*ソリューション*の一部である複数のプロジェクトに格納されます。 ソリューションは、複数のプロジェクトをグループ化するためのコンテナーの抽象化です。 プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。 詳細については、「[Visual Studio のソリューションおよびプロジェクト](/visualstudio/ide/solutions-and-projects-in-visual-studio)」および「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。  
  
## <a name="importing-your-existing-code"></a>既存のコードをインポートする  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を使用して、メイクファイルを使用または使用せずにコンパイルするよう設定される既存のコードを使用し、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] プロジェクトに配置できます。 詳細については、「**既存コード ファイルからの新しいプロジェクトの作成ウィザード**」を参照してください。 詳細については、「[方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。  
  
## <a name="creating-a-new-project"></a>新規プロジェクトの作成  
 開発環境では、新しいプロジェクトを作成できます。 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] はさまざまな共通プロジェクトの標準的なコードを提供する多数のテンプレートを提供します。 アプリケーション ウィザードを使用して、様々な種類のアプリケーション用のコードのアウトラインを持つプロジェクトを生成することができます。  
  
 まず、**コンソール アプリケーション (Win32) ウィザード**を使用して、空のプロジェクトを作成できます。 **[空のプロジェクト]** チェック ボックスをオンにします。 これで、新規および既存のファイルをプロジェクトに後で追加できます。  
  
 プロジェクトを作成するときに、プロジェクトの名前を付けてください。 既定では、プロジェクト名は、ダイナミック リンク ライブラリ (DLL) の名前またはプロジェクトからビルドされる実行可能ファイルと等しくなります。 詳細については、「[ソリューションとプロジェクトの作成](/visualstudio/ide/creating-solutions-and-projects)」を参照してください。  
  
## <a name="microsoft-specific-modifiers"></a>Microsoft 固有の修飾子  
 Visual C++ には、標準の c++ プログラミング言語のいくつかの拡張機能が含まれています。 これらの拡張機能は、ストレージ クラス属性、関数の呼び出し規約、ベース アドレス指定などを指定するために使用されます。 すべての Visual C++ の拡張機能の完全な一覧については、「[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)」を参照してください。  
  
 **/Za** コンパイラ オプションを使用して、C++ へのすべての Microsoft 固有の拡張機能を無効にすることができます。 複数のプラットフォームで実行するコードを記述する場合、このオプションが推奨されます。 **/Za** コンパイラ オプションの詳細については、「[/Za、/Ze (言語拡張機能の無効化)](../build/reference/za-ze-disable-language-extensions.md)」を参照してください。 Visual C++ の準拠の詳細については、「[非標準動作](../cpp/nonstandard-behavior.md)」を参照してください。  
  
## <a name="precompiled-headers"></a>プリコンパイル済みヘッダー  
 Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。  
  
 既定では、プリコンパイル済みのすべてのコードは、ファイル **stdafx.h** と **stdafx.cpp** で指定されます。 **[プリコンパイル済みヘッダー]** オプションをオフにしない限り、**[新しいプロジェクト]** ウィザードは自動的にこれらのファイルを作成します。 プリコンパイルされたヘッダーの詳細については、「[プリコンパイル済みヘッダー ファイルの作成](../build/reference/creating-precompiled-header-files.md)」を参照してください。  
  
## <a name="related-sections"></a>関連項目  
 詳細については、「[UNIX から Win32 への移植](../porting/porting-from-unix-to-win32.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ ガイド ツアー](http://msdn.microsoft.com/en-us/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)
