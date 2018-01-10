---
title: "IDE と Visual C 開発用ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e503c3ecbf0cd7245aadeb231030a91577e1e865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE と Visual C++ 開発用ツール
Visual Studio 統合開発環境 (IDE) に属する Visual C++ では、多くの他の言語と共通のウィンドウやツールを使用します。 などの多く**ソリューション エクスプ ローラー**、コード エディターと、デバッガーが下に記載されている[Visual Studio IDE](/visualstudio/ide/visual-studio-ide)です。 共有ツールやウィンドウの機能は C++ と、.NET 言語や Javascript とで若干異なることがよくあります。 一部のウィンドウやツールは、Visual Studio Pro または Visual Studio Enterprise でのみ使用できます。   
  
 Visual Studio IDE の共有ツールに加えて、Visual C++ には、ネイティブ コード開発に特化したいくつかのツールがあります。 この記事には、これらのツールの一覧も掲載します。 そのうちツールは Visual Studio の各エディションで利用可能な一覧は、次を参照してください。 [Visual c ツールおよび Visual Studio のエディションで機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)します。  
## <a name="creating-a-solution-and-projects"></a>ソリューションとプロジェクトの作成  

「プロジェクト」は、基本的に、ソース コード ファイルとイメージまたは実行可能ファイルに組み込まれているデータ ファイルなどのリソースのセットです。 Visual Studio 2017 には、すべてのビルド システムまたは使用し、Intellisense、閲覧とデバッグを完全にサポートするカスタム ビルド ツールをサポートできます。
 - MSBuild は Visual Studio の「ネイティブ」ビルド システムであり、UWP アプリまたは MFC または ATL を使用する従来の Windows デスクトップ アプリケーションに最適な選択肢では多くの場合 MSBuild ベースの C++ プロジェクトの詳細については、次を参照してください。[の作成とプロジェクトの MSBuild ベースの管理](creating-and-managing-visual-cpp-projects.md)です。
 - CMake は、クロス プラットフォーム ビルドは、デスクトップ C++ のワークロードをインストールするときに、Visual Studio IDE に統合されているシステムです。 詳細については、「[CMake projects in Visual C++ (Visual C++ の CMake プロジェクト)](cmake-tools-for-visual-cpp.md)」をご覧ください。
 - フォルダーを開く機能を使用してその他の C++ ビルド システム、ファイルの厳密でないコレクションを含むがサポートされています。 ビルドのプログラムを起動し、デバッグ セッションを構成する単純な JSON ファイルを作成します。 詳細については、次を参照してください。 [、C++ コードを Visual Studio に取り込む](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/)です。
 
 
 **プロジェクト テンプレート (MSBuild)**  
  
 Visual C プロジェクトの MSBuild ベース; のいくつかのテンプレートが付属します。このテンプレートには、スタート コードは、さまざまな種類の基本的なプログラムに必要な設定が含まれています。 通常は、まずを選択して**ファイル &#124;です。新しいプロジェクト**プロジェクト テンプレートからプロジェクトを作成するにし、そのプロジェクトに新しいソース コード ファイルを追加または提供されているファイルでコーディングを開始します。 C++ プロジェクトやプロジェクト ウィザードに固有の情報を参照してください。 [Visual c プロジェクトの管理の作成と](../ide/creating-and-managing-visual-cpp-projects.md)です。  
  
 **アプリケーション ウィザード (MSBuild)**  
  
 Visual C では、ウィザードによって MSBuild プロジェクトの種類を選択すると**ファイル &#124;です。新しいプロジェクト**です。 このウィザードの手順に従って、新しいプロジェクトの作成プロセスを実行します。 これは、オプションや設定が多いプロジェクトの種類の場合に便利です。 詳細については、次を参照してください。[作成デスクトップ プロジェクトでアプリケーション ウィザードを使用した](../ide/creating-desktop-projects-by-using-application-wizards.md)です。  
  
## <a name="creating-user-interfaces-with-designers-msbuild"></a>デザイナー (MSBuild) によるユーザー インターフェイスの作成 
 プログラムにユーザー インターフェイスがある場合、まずそのインターフェイスにボタン、リスト ボックスなどのコントロールを設定します。 Visual Studio には、C++ アプリケーションの種類ごとに、ビジュアル デザイン領域とツールボックスが含まれています。 どの種類のアプリを作成している場合であっても、[ツールボックス] ウィンドウからコントロールをドラッグして、目的の場所にあるデザイン領域にドロップするという基本的な概念は同じです。 Visual Studio は、バック グラウンドで、リソースとそれらすべてを正常に動作させるために必要なコードを生成します。 コントロールにデータを表示したり、外観と動作をカスタマイズするコードを記述します。
  
 ユニバーサル Windows プラットフォーム アプリのユーザー インターフェイスの設計の詳細については、次を参照してください。[デザインと UI](https://developer.microsoft.com/en-us/windows/design)です。  
  
 MFC アプリケーションのユーザー インターフェイスの作成の詳細については、次を参照してください。 [MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)です。 Win32 Windows プログラムについては、次を参照してください。 [Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)です。  
  
 C + を使用して Windows フォーム アプリケーションについては +/CLI を参照してください[を作成する、Windows フォーム アプリケーションを使用して .NET Framework (C++)](http://msdn.microsoft.com/en-us/8e007885-6c8b-4fb2-a41d-91febd114a9b)です。  
  
## <a name="writing-and-editing-code"></a>作成とコードの編集  
 **セマンティクスの色づけ**  
  
 プロジェクトを作成すると、すべてのプロジェクト ファイルが表示される、**ソリューション エクスプ ローラー**ウィンドウです。 .H または .cpp ファイルをクリックすると**ソリューション エクスプ ローラー**、コード エディターでファイルを開きます。 コード エディターは、C++ ソース コード専用のワード プロセッサです。 このエディターでは、コードを読みやすく理解しやすいものにするために、言語のキーワード、メソッド名と変数名、およびその他のコードの要素が色分けされます。  
  
 **Intellisense**  
  
 コード エディターでは、Intellisense と呼ばれるいくつかの機能もサポートしています。 メソッドの上にポインターを合わせると、そのメソッドに関するいくつかの基本的な情報を参照できます。 クラスの変数名と . または -> を入力すると、 そのクラスのインスタンス メンバーの一覧が表示されます。 クラス名に続けて :: と入力すると、静的メンバーの一覧が表示されます。 クラスやメソッドの名前を入力し始めると、コード エディターが完全なステートメントの候補を表示します。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。  
  
 **コード スニペット**  
  
 Intellisense コード スニペットを使用すると、ショートカット キーを入力して、一般的に使用されるコード構造や複雑なコード構造を生成できます。 詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。  
  
## <a name="navigating-code"></a>コード間の移動  
 **ビュー**メニューは、コード ファイル内をナビゲートするためのさまざまなウィンドウやツールへのアクセスを提供します。 これらのウィンドウの詳細については、次を参照してください。[コードの構造を表示する](/visualstudio/ide/viewing-the-structure-of-code)です。  
  
 **ソリューション エクスプローラー**  
  
 Visual Studio のすべてのエディションでは、[ソリューション エクスプローラー] ウィンドウを使用して、プロジェクト内のファイル間を移動します。 .H または .cpp ファイルのアイコンを展開するとファイル内のクラスが表示されます。 クラスを展開するとそのメンバーが表示されます。 メンバーをダブルクリックするとファイル内のそのメンバーの定義や実装に移動します。  
  
 **クラス ビューおよびコード定義ウィンドウ**  
  
 使用して、**クラス ビュー**ペインを部分クラスを含むすべてのファイル名前空間とクラスを参照してください。 それぞれの名前空間またはクラスを展開するとそのメンバーが表示され、メンバーをダブルクリックするとソース ファイル内のそのメンバーの場所に移動します。 コード定義ウィンドウを開いている場合、[クラス ビュー] で種類を選択すると、その種類の定義や実装を表示できます。  
  
 **オブジェクト ブラウザー**  
  
 使用して**オブジェクト ブラウザー**を Windows ランタイム コンポーネント (.winmd ファイル) の型情報を探索するには、.NET アセンブリおよび COM タイプ ライブラリ。 これは、Win32 の DLL では使用されません。  
  
 **定義/宣言へ移動します。**  
  
 API 名またはメンバー変数の上で F12 キーを押して、その定義に移動します。 定義が ([!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリの) .winmd ファイル内にある場合、オブジェクト ブラウザーに種類の情報が表示されます。 選択することもできます**定義へ移動**または**宣言へ移動**変数または型の名前を右クリックし、コンテキスト メニューからオプションを選択します。  
  
 **すべての参照の検索**  
  
 ソース コード ファイルでは、型メソッド、または変数の名前の上にマウス カーソルを右クリックし、選択**すべての参照の検索**に型が使用されているファイル、プロジェクトまたはソリューション内のすべての場所の一覧を返します。 **すべての参照の検索**はインテリジェントな機能と他の変数の別のスコープで同じ名前である場合でも、同じ変数のインスタンスをのみを返します。  
  
 **アーキテクチャ エクスプ ローラーと依存関係グラフ (Ultimate)**  
  
 使用して**アーキテクチャ エクスプ ローラー**コード内のさまざまな要素間の関係を表示します。 詳細については、次を参照してください。[アーキテクチャ エクスプ ローラーでコードを検索](http://msdn.microsoft.com/en-us/b1707926-ef73-47f9-92cd-e00d0fac7e76)です。 依存関係グラフを使用すると、依存関係を表示できます。 詳細については、次を参照してください。[する方法: C および C++ コードの依存関係グラフを生成する](http://msdn.microsoft.com/en-us/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c)です。  
  
## <a name="adding-and-editing-resources--msbuild"></a>追加するリソースと編集 (MSBuild)
 Visual Studio デスクトップ プロジェクトのコンテキストにおける「リソース」という用語には、ダイアログ ボックス、アイコン、ローカライズ可能な文字列、スプラッシュ画面、データベースの接続文字列、または実行可能ファイルに含める任意のデータなどが含まれます。  
  
 追加して、ネイティブ デスクトップ C++ プロジェクトにリソースの編集の詳細については、次を参照してください。[リソース ファイルの操作](../windows/working-with-resource-files.md)です。  
  
## <a name="building-compiling-and-linking"></a>ビルド (コンパイルとリンク)  
 **[Ctrl + Shift + B]** を押して、プロジェクトをコンパイルし、リンクします。 実行可能コードを作成するための Visual Studio の使用[MSBuild](/visualstudio/msbuild/msbuild1)経由でセットアップする CMake または任意のビルド環境または**フォルダーを開く**です。 MSBuild プロジェクトの下で [全般] ビルド オプションを設定する**ツール &#124;です。オプション &#124;です。プロジェクトおよびソリューション**下にある特定のプロジェクトのプロパティを設定して**プロジェクト &#124;です。プロパティ**です。 エラー一覧で、ビルド エラーと警告が報告される (**Ctrl +\\、E**)。 非 MSBuild プロジェクトは、ソリューション エクスプ ローラーで作成する JSON ファイルで構成されます。 任意のビルド システムを使用して、出力ウィンドウ (**alt キーを押しながら 2**)、ビルド プロセスに関する情報を表示します。 MSBuild の構成の詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)と[Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)です。  
  
 Visual C++ コンパイラ (cl.exe) や、その他多くのビルド関連のスタンドアロン ツール (コマンド ラインから直接入力するNMAKE や LIB など) も使用できます。 詳細については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../build/building-on-the-command-line.md)と[c/c++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)です。  
  
## <a name="testing"></a>テスト中  
 Visual Studio には、ネイティブ C++ の単体テスト フレームワークと C++/CLI の単体テスト フレームワークの両方が含まれています。 詳細については、次を参照してください[単体テストを使用したコードの検証](/visualstudio/test/unit-test-your-code)と[単体テストの記述した C++ 用の Microsoft 単体テスト フレームワーク c++。](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)  
  
## <a name="debugging"></a>デバッグ  
 キーを押してプログラムをデバッグできます**f5 キーを押して**デバッグに、プロジェクトの構成を設定するとします。 キーを押してブレークポイントを設定するデバッグ中に**F9**、キーを押してコードをステップ**F10**、指定された変数やレジスタの値を表示およびも場合によってはコードでの変更を行うし、続行再コンパイルせずにデバッグします。 詳しくは、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」をご覧ください。  
  
## <a name="deploying-completed-applications"></a>完成したアプリケーションの配置  
 展開する、 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 、Windows ストアを通じて顧客向けに、**プロジェクト &#124;です。ストア**メニュー オプション。 CRT の配置は、水面下で自動的に処理されます。 詳細については、「 [アプリの販売](http://go.microsoft.com/fwlink/p/?LinkId=262280)」を参照してください。  
  
 ネイティブ C++ デスクトップ アプリケーションを別のコンピューターに配置する場合、アプリケーション自体と、そのアプリケーションが依存するすべてのライブラリ ファイルをインストールする必要があります。 アプリケーションと共に Visual C++ ランタイムを配置する方法として、集中配置、ローカル配置、または静的リンクの 3 とおりの方法があります。 詳細については、次を参照してください。[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)です。  
  
 C + の展開の詳細については +/CLI プログラムを参照してください[開発者向けの展開ガイド](/dotnet/framework/deployment/deployment-guide-for-developers)、  

## <a name="related-articles"></a>関連トピック  
  
|||  
|-|-|  
|[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Visual Studio の各種エディションで使用可能な機能が表示されます。|  
|[作成して、プロジェクトの MSBuild ベースの管理](../ide/creating-and-managing-visual-cpp-projects.md)|C++ MSBuild ベース Visual Studio プロジェクトを作成し、それらを管理する方法を説明する他の記事へのリンクの概要を示します。|  
|[Visual C で CMake プロジェクト](cmake-tools-for-visual-cpp.md)です。|CMake または Visual C では、他の非 MSBuild プロジェクトをビルドする方法について説明します。|
|[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)|C++ プロジェクトの作成方法について説明します。|  
|[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ アプリケーションの配置の概要と、配置について詳しく説明する他の記事へのリンクが示されます。|  
|[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法と、Visual Studio の以前のバージョンで作成された C++ アプリケーションをアップグレードする方法の詳細についてはします。|  
|[Visual C++](../top/visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|
