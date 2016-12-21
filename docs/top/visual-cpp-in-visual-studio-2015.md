---
title: "Visual Studio 2015 の Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "visual c++"
  - "visual c"
  - "vc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アンマネージ コード、C++"
  - "開発環境、Visual C++"
  - "アンマネージ コード"
  - "Visual C++"
  - "Visual C++、リファレンス"
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
caps.handback.revision: 61
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio 2015 の Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] プログラミング言語および開発ツールにより、ネイティブのユニバーサル Windows アプリ、ネイティブのデスクトップとサーバー アプリケーション、Windows だけでなく Android や iOS でも実行されるクロスプラットフォーム ライブラリ、および.NET Framework で実行されるマネージ アプリを開発できます。  
  
 **本書の対象読者**  
  
 このコンテンツは、プログラムを記述する C\+\+ 開発者を対象としています。  
  
-   プログラムを実行するために C\+\+ 再頒布可能パッケージとランタイム コンポーネントを探している場合、[Microsoft ダウンロード センター](http://www.microsoft.com/en-us/download/)にアクセスして検索ボックスに **Visual C\+\+** と入力してください。  
  
-   C\+\+ プログラミングの概念については、そうした内容を記載した Web サイトが多数あるので、そのようなサイトを利用するか、C\+\+ の考案者である Bjarne Stroustrup による「[プログラミング \-\- C\+\+ 利用の原理と実践 \(第 2 版\)](http://stroustrup.com/Programming/)」を入手してください。 Visual C\+\+ コンテンツは、C\+\+ の基礎知識を前提として作成されています。  
  
-   Visual C\+\+ コンパイラが必要な場合、[https:\/\/www.visualstudio.com\/](https://www.visualstudio.com/) から Visual Studio 2015 の有料版または無料版をダウンロードする必要があります。  
  
> [!WARNING]
>  Visual Studio 2015 では、既定で Visual C\+\+ がインストールされません。 インストール時に、**\[カスタム\]** インストールを選択してから、必要な C\+\+ コンポーネントを選択します。 または、Visual Studio が既にインストールされている状態で、**\[ファイル &#124;新規作成 &#124;プロジェクト &#124;C\+\+\]** を選択すると、必要なコンポーネントをインストールするように求められます。  
  
## Visual C\+\+ に関する一般情報  
 [Visual C\+\+ の新機能](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)  
 Visual C\+\+ の新機能。  
  
 [Visual C\+\+ 2015 での互換性に影響する変更点](../Topic/Visual%20C++%20change%20history%202003%20-%2020151.md)  
 このバージョンの互換性に影響する変更点に関する情報。  
  
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)  
 C\+\+11 と C\+\+14 を基盤とする現代的な C\+\+ プログラミング手法にかんする情報。高速で安全なコードを記述し、C スタイルのプログラミングの潜在的な危険を回避できます。  
  
 [How to Report a Problem with the Visual C\+\+ Toolset](../Topic/How%20to%20Report%20a%20Problem%20with%20the%20Visual%20C++%20Toolset.md)  
 Visual C\+\+ ツールセット \(コンパイラ、リンカー、その他のツール\) に対して効果的なエラー レポートを作成する方法とレポートの提出方法に関す情報。  
  
 [Visual C\+\+  移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)  
 Windows 10 とユニバーサル Windows プラットフォームに C\+\+ コードを移植するなど、[!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] の Visual C\+\+ へのコードの移植およびプロジェクトのアップグレードのガイダンス。  
  
 [C\+\+11\/14\/17 の機能のサポート](../Topic/Support%20For%20C++11-14-17%20Features%20\(Modern%20C++\).md)  
 Visual C\+\+ の C\+\+11 と C\+\+14 機能のサポートに関する情報。  
  
 [Visual C\+\+ チーム ブログ](http://blogs.msdn.com/b/vcblog/)  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] の開発者による新機能と最新の情報に関する詳細。  
  
 [Visual Studio のダウンロード](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Visual C\+\+ をダウンロード。  
  
 [Visual Studio エディションでの Visual C\+\+ ツールおよびテンプレート](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)  
 さまざまな Visual Studio のエディションに関する情報。  
  
 [サポートされるプラットフォーム](../top/supported-platforms-visual-cpp.md)  
 サポート対象プラットフォームに関する情報。  
  
 [Visual C\+\+ のサンプル](../top/visual-cpp-samples.md)  
 サンプルに関する情報。  
  
 [Visual Studio コミュニティ](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Visual Studio のサポート、バグの報告、提案に関する情報。  
  
## C\+\+ でのアプリケーションの作成  
 [ユニバーサル Windows アプリ](../windows/universal-windows-apps-cpp.md)  
 Windows Developer Center 内にあるガイドとリファレンス コンテンツを探します。 Windows ストア アプリの開発の詳細については、「[Visual Studio を使った Windows ストア アプリの開発](http://go.microsoft.com/fwlink/p/?LinkId=248364)」および「[C\+\+ を使った Windows ストア アプリのためのロードマップ](http://go.microsoft.com/fwlink/p/?LinkId=244654)」を参照してください。  
  
 [Windows デスクトップ アプリケーション \(Visual C\+\+\)](../windows/desktop-applications-visual-cpp.md)  
 メッセージ ループとコールバックのあるデスクトップ アプリケーションを作成する方法。  
  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)  
 Win32、ATL、および MFC を使用して Windows のデスクトップ DLL を作成する方法、さらには DLL をコンパイルおよび登録する方法。  
  
 [並列プログラミング](../parallel/parallel-programming-in-visual-cpp.md)  
 並列パターン ライブラリ、C\+\+ AMP、OpenMP、その他 Windows 上でのマルチスレッド化に関連する機能を使用する方法。  
  
 [セキュリティ推奨事項](../top/security-best-practices-for-cpp.md)  
 悪意のあるコードや不正使用からアプリケーションを保護する方法。  
  
 [クラウドおよび Web プログラミング](../Topic/Cloud%20and%20Web%20Programming%20in%20Visual%20C++.md)  
 C\+\+ では、Web とクラウドに接続するためのいくつかの方法があります。  
  
 [データ アクセス](../Topic/Data%20Access%20in%20Visual%20C++.md)  
 ODBC およびその他のデータベース アクセス テクノロジを使用してデータベースに接続します。  
  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)  
 さまざまなテキスト形式および文字列形式の処理、およびローカルおよび国際対応の開発におけるエンコーディングの処理について説明します。  
  
## C\+\+ 開発ツール  
 プロジェクトの作成、ソース コード ファイルの処理、ライブラリへのリンク、コンパイル、デバッグ、プロファイル、配置などの方法については、「[IDE と開発ツール](../Topic/IDE%20and%20Tools%20for%20Visual%20C++%20Development.md)」を参照してください。  
  
## C\+\+ 言語リファレンス  
 C\+\+ 言語については、「[C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)」を参照してください。  
  
 C\+\+ プリプロセッサの詳細については、「[C\/C\+\+ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)」を参照してください。  
  
## Visual Studio での C\+\+ ライブラリ  
 以下のセクションでは、Visual C\+\+ に含まれる様々な C\+\+ ライブラリについて説明します。  
  
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)  
 セキュリティ上の問題が発生することがわかっている関数に対する、セキュリティを強化された代替品が含まれています。  
  
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)  
 標準テンプレート ライブラリ \(STL\)。  
  
 [Active Template Library \(ATL\)](../atl/atl-com-desktop-components.md)  
 COM コンポーネントとアプリケーションのサポート。  
  
 [Microsoft Foundation Class \(MFC\) ライブラリ](../mfc/mfc-desktop-applications.md)  
 従来型または Office スタイルのユーザー インターフェイスを持つデスクトップ アプリケーションの作成のサポート。  
  
 [並列パターン ライブラリ \(PPL\)](../parallel/concrt/parallel-patterns-library-ppl.md)  
 CPU で実行する非同期および並列アルゴリズム。  
  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 GPU で実行する膨大な並列アルゴリズム。  
  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] のアプリケーションとコンポーネント。  
  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 共通言語ランタイム \(CLR\) のプログラミング。  
  
 「[STL\/CLR](../dotnet/stl-clr-library-reference.md)」および「[C\+\+ のサポート ライブラリ](../dotnet/cpp-support-library.md)」のドキュメントも参照してください。  
  
## その他の C\+\+ のライブラリ  
 このセクションには、Visual Studio に含まれてはいないものの、ダウンロードして Visual C\+\+ で使用できるライブラリへのリンクが含まれています。  
  
 [Boost](http://www.boost.org/)  
 一般的で広く使用されているライブラリです。  
  
 [C\+\+ REST SDK](http://casablanca.codeplex.com)。  
 HTTP 経由で Web サービスと通信するための Microsoft ライブラリ。  
  
## その他のリソース  
 [Visual C\+\+ リソース](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 その他の Visual C\+\+ リソース。  
  
 [標準 C\+\+](http://isocpp.org/)  
 C\+\+ について学び、最新の C\+\+ の概要を把握し、書籍、記事、講演、イベントなどへのリンクを探します  
  
 [Visual C\+\+ に関する詳細情報](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 C\+\+ について学び始める。  
  
## 参照  
 [C 言語リファレンス](../Topic/C%20Language%20Reference.md)   
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)   
 [コンパイラの組み込みとアセンブリ言語](../intrinsics/compiler-intrinsics-and-assembly-language.md)