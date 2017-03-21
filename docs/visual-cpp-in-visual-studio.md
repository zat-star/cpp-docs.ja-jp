---
title: "Visual Studio の Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- visual c++
- visual c
- vc
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: da3c2e6ce7247d3e8c9a401bc0a133cb8d46a970
ms.openlocfilehash: 81a7d724a4a3b2e5aa7de47461d20cc3385896eb
ms.lasthandoff: 03/15/2017

---
# <a name="visual-c-in-visual-studio"></a>Visual Studio の Visual C++
Visual Studio 2017 プログラミング言語および開発ツールにより、ネイティブのユニバーサル Windows アプリ、ネイティブのデスクトップとサーバー アプリケーション、Windows だけでなく Android や iOS でも実行されるクロスプラットフォーム ライブラリ、および.NET Framework で実行されるマネージ アプリを開発できます。  
  
 **本書の対象読者**  
  
 このコンテンツは、プログラムを記述する C++ 開発者を対象としています。  
  
-   プログラムを実行するために C++ 再頒布可能パッケージとランタイム コンポーネントを探している場合、 [Microsoft ダウンロード センター](http://www.microsoft.com/en-us/download/) にアクセスして検索ボックスに **Visual C++** と入力してください。  
  
-   C++ プログラミングの概念については、そうした内容を記載した Web サイトが多数あるので、そのようなサイトを利用するか、C++ の考案者である Bjarne Stroustrup による「 [プログラミング -- C++ 利用の原理と実践 (第&2; 版)](http://stroustrup.com/Programming/) 」を入手してください。 Visual C++ コンテンツは、C++ の基礎知識を前提として作成されています。  
  
-   Visual C++ コンパイラが必要な場合、 [https://www.visualstudio.com/](https://www.visualstudio.com/)から Visual Studio の有料版または無料版をダウンロードする必要があります。  

## <a name="general-information-about-visual-c"></a>Visual C++ に関する一般情報  
 [Visual C++ の新機能](what-s-new-for-visual-cpp-in-visual-studio.md)  
 Visual C++ の新機能。  

 [Visual Studio 2017 の C++ 準拠の強化](cpp-conformance-improvements-2017.md) 
 Visual Studio 2017 の C++ 準拠の強化について説明します。 

 [Visual C++ 言語への準拠](visual-cpp-language-conformance.md)  
 Visual C++ の各機能の準拠状態を一覧にしています。

 [2003 から 2015 の Visual C++ の履歴の変更](porting/visual-cpp-change-history-2003-2015.md)  
 前のバージョンの互換性に影響する変更点について説明します。  
  
 [C++ へようこそ](cpp/welcome-back-to-cpp-modern-cpp.md)  
 C++11 と C++14 を基盤とする現代的な C++ プログラミング手法にかんする情報。高速で安全なコードを記述し、C スタイルのプログラミングの潜在的な危険を回避できます。  
  
 [Visual C++ ツールセットで問題を報告する方法](how-to-report-a-problem-with-the-visual-cpp-toolset.md)  
 Visual C++ ツールセット (コンパイラ、リンカー、その他のツール) に対して効果的なエラー レポートを作成する方法とレポートの提出方法に関す情報。  
  
 [Visual C++ 移植とアップグレードのガイド](porting/visual-cpp-porting-and-upgrading-guide.md)  
 Windows 10 とユニバーサル Windows プラットフォームに C++ コードを移植するなど、Visual Studio 2017 の Visual C++ へのコードの移植およびプロジェクトのアップグレードのガイダンス。  
  
 [Visual C++ チーム ブログ](http://blogs.msdn.com/b/vcblog/)  
 [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)] の開発者による新機能と最新の情報に関する詳細。  
  
 [Visual Studio のダウンロード](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Visual C++ をダウンロード。  
  
 [さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)  
 さまざまな Visual Studio のエディションに関する情報。  
  
 [サポートされているプラットフォーム](supported-platforms-visual-cpp.md)  
 サポート対象プラットフォームに関する情報。  
  
 [Visual C++ のサンプル](visual-cpp-samples.md)  
 サンプルに関する情報。  
  
 [Visual Studio コミュニティ](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Visual Studio のサポート、バグの報告、提案に関する情報。  
  
## <a name="writing-applications-in-c"></a>C++ でのアプリケーションの作成  
 [ユニバーサル Windows アプリ](windows/universal-windows-apps-cpp.md)  
 Windows Developer Center 内にあるガイドとリファレンス コンテンツを探します。 Windows ストア アプリの開発の詳細については、「 [Visual Studio を使った Windows ストア アプリの開発](http://go.microsoft.com/fwlink/p/?LinkId=248364) 」および「 [C++ を使った Windows ストア アプリのためのロードマップ](http://go.microsoft.com/fwlink/p/?LinkId=244654)」を参照してください。  
  
 [デスクトップ アプリケーション (Visual C++)](windows/desktop-applications-visual-cpp.md)  
 メッセージ ループとコールバックのあるデスクトップ アプリケーションを作成する方法。  
  
 [Visual C++ の DLL](build/dlls-in-visual-cpp.md)  
 Win32、ATL、および MFC を使用して Windows のデスクトップ DLL を作成する方法、さらには DLL をコンパイルおよび登録する方法。  
  
 [並列プログラミング](parallel/parallel-programming-in-visual-cpp.md)  
 並列パターン ライブラリ、C++ AMP、OpenMP、その他 Windows 上でのマルチスレッド化に関連する機能を使用する方法。  
  
 [セキュリティ推奨事項](security/security-best-practices-for-cpp.md)  
 悪意のあるコードや不正使用からアプリケーションを保護する方法。  
  
 [クラウドおよび Web プログラミング](cloud/cloud-and-web-programming-in-visual-cpp.md)  
 C++ では、Web とクラウドに接続するためのいくつかの方法があります。  
  
 [データ アクセス](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b)  
 ODBC およびその他のデータベース アクセス テクノロジを使用してデータベースに接続します。  
  
 [テキストと文字列](text/text-and-strings-in-visual-cpp.md)  
 さまざまなテキスト形式および文字列形式の処理、およびローカルおよび国際対応の開発におけるエンコーディングの処理について説明します。  
  
## <a name="c-development-tools"></a>C++ 開発ツール  
 プロジェクトの作成、ソース コード ファイルの処理、ライブラリへのリンク、コンパイル、デバッグ、プロファイル、配置などの方法については、「[IDE と Visual C++ 開発用ツール](ide/ide-and-tools-for-visual-cpp-development.md)」を参照してください。  
  
## <a name="c-language-reference"></a>C++ 言語リファレンス  
 C++ 言語については、「[C++ 言語リファレンス](cpp/cpp-language-reference.md)」を参照してください。  
  
 C++ プリプロセッサの詳細については、「[C/C++ プリプロセッサ リファレンス](preprocessor/c-cpp-preprocessor-reference.md)」を参照してください。  
  
## <a name="c-libraries-in-visual-studio"></a>Visual Studio での C++ ライブラリ  
 以下のセクションでは、Visual C++ に含まれる様々な C++ ライブラリについて説明します。  
  
 [C ランタイム ライブラリ リファレンス](c-runtime-library/c-run-time-library-reference.md)  
 セキュリティ上の問題が発生することがわかっている関数に対する、セキュリティを強化された代替品が含まれています。  
  
 [C++ 標準ライブラリ](standard-library/cpp-standard-library-reference.md)  
 C++ 標準ライブラリ。  
  
 [Active Template Library (ATL)](atl/atl-com-desktop-components.md)  
 COM コンポーネントとアプリケーションのサポート。  
  
 [Microsoft Foundation Class (MFC) ライブラリ](mfc/mfc-desktop-applications.md)  
 従来型または Office スタイルのユーザー インターフェイスを持つデスクトップ アプリケーションの作成のサポート。  
  
 [並列パターン ライブラリ (PPL)](parallel/concrt/parallel-patterns-library-ppl.md)  
 CPU で実行する非同期および並列アルゴリズム。  
  
 [C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 GPU で実行する膨大な並列アルゴリズム。  
  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 [!INCLUDE[win8_appname_long](build/includes/win8_appname_long_md.md)] のアプリケーションとコンポーネント。  
  
 [C++/CLI (Visual C++) による .NET プログラミング](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 共通言語ランタイム (CLR) のプログラミング。  
  
 「[STL/CLR ライブラリ リファレンス](dotnet/stl-clr-library-reference.md)」および「[C++ のサポート ライブラリ](dotnet/cpp-support-library.md)」のドキュメントも参照してください。  
  
## <a name="other-c-libraries"></a>その他の C++ のライブラリ  
 このセクションには、Visual Studio に含まれてはいないものの、ダウンロードして Visual C++ で使用できるライブラリへのリンクが含まれています。  
  
 [Boost](http://www.boost.org/)  
 一般的で広く使用されているライブラリです。  
  
 [C++ REST SDK](http://casablanca.codeplex.com)。  
 HTTP 経由で Web サービスと通信するための Microsoft ライブラリ。  
  
## <a name="more-resources"></a>その他のリソース  
 [Visual C++ リソース](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 その他の Visual C++ リソース。  
  
 [標準 C++](http://isocpp.org/)  
 C++ について学び、最新の C++ の概要を把握し、書籍、記事、講演、イベントなどへのリンクを探します  
  
 [Visual C++ に関する詳細情報](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 C++ について学び始める。  
  
## <a name="see-also"></a>関連項目  
 [C 言語リファレンス](c-language/c-language-reference.md)   
 [C ランタイム ライブラリ リファレンス](c-runtime-library/c-run-time-library-reference.md)   
 [コンパイラの組み込みとアセンブリ言語](intrinsics/compiler-intrinsics-and-assembly-language.md)

