---
title: "C++ でプログラミングする Windows の概要 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ でプログラミングする Windows の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ を使用すると、Windows PC \(x86、x64、または ARM\)、Windows サーバー、クラウド、または Xbox で実行される多様なプログラムを記述できます。 適切に記述された C\+\+ プログラムは、高速で効率的であり、電力消費面の経済性に優れています。また、マルチコア デバイスおよびメニーコア デバイス、グラフィックス処理装置 \(GPU\) での一般コンピューティング、その他の最新ハードウェアの利点をフル活用することができます。  
  
 Visual C\+\+ で開発できる Windows アプリにはいくつかの大きなカテゴリがあります。 これらのカテゴリのプログラミング モデルまたはアプリ モデルはさまざまです。つまり、プラットフォームへのアクセスやユーザー インターフェイスの提供のためにさまざまなライブラリや API を使用するということです。  
  
-   [Windows ユニバーサル アプリ](#BK_WindowsUniversal)。 Windows アプリの 3 番目のカテゴリが Windows 8 で導入され、このカテゴリのアプリは Windows 10 でも引き続きサポートされます。 多くの場合、これらのアプリケーションは単に "Windows アプリ" と呼ばれ、さまざまなデバイスを対象とするデスクトップおよびモバイルのアプリがそれに含まれています。 これらのアプリは、C\+\+\/CX \(C\+\+ の方言であり、Windows ランタイム開発のサポートを含む\) で作成することも、Windows ランタイム ライブラリ \(WRL\) を使用して 標準 C\+\+ と COM で作成することもできます。 これらのアプリはもともと全画面表示で実行するよう設計されていましたが、Windows 10 のユーザーにはデスクトップ ウィンドウでこれを実行するオプションがあります。 これらのアプリはタッチ指向ですが、ユーザーがマウスを好む場合や、タッチ スクリーンが利用できない場合はマウスを簡単に使用できます。 これらのアプリは Windows ストアから配布され、"Windows ストア アプリ" と呼ばれています。  
  
-   [デスクトップ、サーバー、およびクラウドのアプリケーションとゲーム](#BK_Native)。 このカテゴリには、Windows デスクトップ アプリケーションが含まれます。これらのアプリケーションは、Windows 8 以前に Win32 APIを使用していたため、Win32 アプリケーションとも呼ばれ、すべての Windows アプリケーションがこのカテゴリに含まれます。 このカテゴリのアプリケーションは、ユーザー インターフェイスに MFC を使用でき、Windows コンポーネント \(通常は COM オブジェクト\) との対話に ATL を使用できます。  
  
     標準の C\+\+ で作成されたアプリケーション、コンポーネント、またはライブラリも、このカテゴリに該当します。  
  
     サーバーおよびクラウド プログラミングのコンテキストにおいて、コア コンポーネントのためや、計算コードのために C\+\+ を使用することも、このカテゴリに含まれます。 場合によっては、サーバーやクラウド アプリケーションのコアとなるパフォーマンス重視のコードを C\+\+ で記述し、パフォーマンスを最適化することもあります。 このようなコードをコンパイルして DLL にし、C\# または Visual Basic から使用することができます。  
  
-   **.NET Framework アプリケーション**。 .NET Framework アプリケーションのほとんどは C\# または Visual Basic で記述されていますが、C\+\+\/CLI でも記述できます \(Visual C\+\+ の\/clr コンパイラ オプション\)。 マネージ コードとネイティブ コードを含む大規模なアプリケーションでは、C\+\+\/CLI は最小限の相互運用層で使用することをお勧めします。  
  
##  <a name="BK_WindowsUniversal"></a> Windows ユニバーサル アプリ  
 Windows 10 では、デスクトップ上だけでなく、タブレットや携帯電話など、すべての Windows 10 デバイスでアプリを実行できます。 デスクトップでは、常に全画面表示で実行しなければならないわけではなく、デスクトップ ウィンドウとして実行することができます。 これらのアプリは Xbox でも動作し、将来のデバイスでも実行できます。  2 種類のアプリのプログラミング モデルは、Win32 デスクトップ アプリケーションとは異なります。 これらの Windows アプリケーションは Windows ランタイム上で動作します。このランタイムは、ユーザー インターフェイス要素、これらのアプリの重要なサービス、およびサポートされている多様なハードウェア デバイスへのインターフェイスを提供します。 これらのアプリはネイティブ コードにコンパイルされ、XAML ユーザー インターフェイスを持つか、DirectX を使用します。 また、他の Windows アプリで使用できる [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] コンポーネントをネイティブ コードで記述することもできます。これには、C\#、Visual Basic、または JavaScript で記述されたアプリが含まれます。 詳細については、「[C\+\+ を使った初めての Windows ストア アプリの作成](http://go.microsoft.com/fwlink/?LinkID=534976)」、「[DirectX を使った初めての Windows ストア アプリの作成](http://go.microsoft.com/fwlink/p/?LinkId=244656)」、および「[C\+\+ での Windows ランタイム コンポーネントの作成](http://go.microsoft.com/fwlink/p/?LinkId=244658)」を参照してください。  
  
 ユニバーサル Windows プラットフォームのサンプルの詳細については、「[GitHub の Windows のユニバーサル サンプル](https://github.com/Microsoft/Windows-universal-samples)」を参照してください。  
  
 既存の Windows 8.1 のプロジェクトがあり、Windows 10 に移植する必要がある場合は、「[ユニバーサル Windows プラットフォームへの移植](../porting/porting-to-the-universal-windows-platform-cpp.md)」を参照してください。 既存の従来の Win32 デスクトップ ライブラリとコードがあり、UWP アプリに統合したい場合には、「[方法: ユニバーサル Windows アプリで既存の C\+\+ コードを使用する](../Topic/How%20to:%20Use%20Existing%20C++%20Code%20in%20a%20Universal%20Windows%20Platform%20App.md)」を参照してください。  
  
 また、[!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) を使用せずに [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) を使用して、ユニバーサルWindows アプリ、ゲーム、およびコンポーネントを作成することもできます。 詳細については、「[Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)」を参照してください。  
  
 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] を使用して、Windows 10 のデスクトップとモバイル デバイスで動作するユニバーサル Windows アプリを開発することができます。 また、Windows 8.1 アプリと Windows Phone 8.1 アプリを [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] で作成することもできますが、それにはまず、同じコンピューターに Visual Studio 2013 をインストールし、**Visual Studio 2013 \(v120\)** ツールセットを使用するようプロジェクトを構成する必要があります。 プロジェクトでこの設定を構成するには、プロジェクトのプロパティを開き、\[**全般**\] セクションで、\[**プラットフォーム ツールセット**\] を \[**Visual Studio 2013 \(v120\)**\] に設定します。  
  
 Visual Studio のセットアップで、Phone 8.0 のツールをインストールする場合は、Windows Phone 8.0 を対象にすることもできます。  
  
 Windows 10 で導入された API コントラクトと呼ばれる新しい概念は、特定のバージョンの Windows を対象とするという従来の慣習を置き換えます。 代わりに、アプリに必要な API コントラクトを選択すると、そのアプリはこれらのコントラクトをサポートするあらゆる Windows デバイスで動作するようになります。 API コントラクトはプラットフォームやデバイスのリソースへのアクセスを提供する安定した API のセットです。 API コントラクトは、プロジェクト システムに参照として含めることができます。 Visual Studio プロジェクトで特定の拡張機能 SDK への参照を追加する場合、Visual Studio は適切な API コントラクトを追加します。  
  
 これらすべての概念の詳細については、「[Windows ユニバーサル アプリに関するガイド](http://go.microsoft.com/fwlink/?LinkId=534605)」を参照してください。  
  
##  <a name="BK_Win32"></a> デスクトップ、サーバー、およびクラウドのアプリとゲーム  
 クラウドでは、C\+\+ で Azure ネイティブ コード アセンブリを作成し、C\# で作成された Web ロールからこれらを呼び出すことができます。 詳細については、「[Azure SDK](http://go.microsoft.com/fwlink/p/?LinkId=256416)」を参照してください。  
  
 デスクトップの Windows クライアント アプリケーションを記述するための基礎を習得するには、「[Developing Windows Applications in C\+\+](http://msdn.microsoft.com/vstudio//hh304489)」 \(C\+\+ での Windows アプリケーションの開発\) および「[Windows C\+\+ プログラミングの概要](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx)」を参照してください。  
  
 Windows 10 では、Visual C\+\+ を使用して多様な種類のプログラムを作成できます。  
  
-   コマンド ライン アプリとユーティリティ。 詳細については、「[コンソール アプリケーション](../Topic/Console%20Applications%20in%20Visual%20C++.md)」を参照してください。  
  
-   PC または Xbox で実行される DirectX ゲーム。 詳細については、[DirectX デベロッパー センター](http://go.microsoft.com/fwlink/p/?LinkId=256418)を参照してください。  
  
-   洗練されたグラフィカル ユーザー インターフェイスを持つコンシューマー向けアプリケーション。 詳細については、「[Hilo: Windows 7 対応 C\+\+ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=256417)」を参照してください。  
  
-   .NET Framework で実行されるか、.NET Framework アプリとネイティブ コードで記述されたアプリまたはコンポーネントとの間のブリッジとなる、エンタープライズ アプリおよび基幹業務アプリ。 詳細については、「[C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。  
  
-   ネイティブ コードで実行される SQL データベース クライアント。 詳細については、「[SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419)」を参照してください。  
  
-   Microsoft Office アプリケーション用アドイン。 詳細については、「[Outlook 2010 の C\+\+ アドインをビルドする](http://go.microsoft.com/fwlink/p/?LinkId=256420)」を参照してください。  
  
-   デバイス ドライバー。 詳細については、「[Windows Driver Kit \(WDK\) について](http://go.microsoft.com/fwlink/p/?LinkId=256421)」を参照してください。  
  
-   Windows サービス 詳細については、「[Windows サービス アプリケーションの概要](../Topic/Introduction%20to%20Windows%20Service%20Applications.md)」を参照してください。  
  
 Visual C\+\+ を使用すると、高性能なカスタム機能をほぼ種類に関係なく Win32 DLL または COM DLL にパッケージ化できます。これらは、C\+\+ アプリまたは C\# や Visual Basic など他の言語で記述されたアプリで使用できます。 WIn32 DLL の詳細については、「[Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)」を参照してください。 COM 開発の詳細については、「[Component Object Model \(COM\)](http://msdn.microsoft.com/ja-jp/375d29a7-a1f3-4bd8-8621-bad7a049b2aa)」を参照してください。  
  
## SDK とヘッダー ファイル  
 Visual C\+\+ には、C および C\+\+ の標準ライブラリ、標準テンプレート ライブラリ \(STL\)、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが格納されるインクルード フォルダーは、Visual Studio のインストール ディレクトリの \\VC\\ フォルダーの下、C ランタイム \(CRT\) ライブラリの場合は Windows SDK のインストール フォルダー \(例: Windows 10 SDK の場合は Program Files フォルダーの Windows Kits\\10\) にあります。  Microsoft ライブラリには、次のものが含まれています。  
  
-   Microsoft Foundation Classes \(MFC\): ボタン、リスト ボックス、ツリー ビュー、および他のコントロールを使用した豊富なユーザー インターフェイスを持つ従来の Windows プログラム \(特にエンタープライズ アプリケーション\) を作成するためのオブジェクト指向フレームワーク。 詳細については、「[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)」を参照してください。  
  
-   Active Template Library \(ATL\): COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「[ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)」を参照してください。  
  
-   C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\): GPU で一般的な計算作業のパフォーマンス向上を可能にするライブラリ。 詳細については、「[C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。  
  
-   同時実行ランタイム: マルチコア デバイスおよびメニーコア デバイス用の並列プログラミングおよび非同期プログラミング作業を簡略化するために役立つライブラリ。 詳細については、「[同時実行ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。  
  
 Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、[!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] のすべてのエディションで Windows SDK がインストールされ 、ユニバーサル Windows アプリの開発が可能になります。 Windows の 10 のユニバーサル Windows アプリを開発するには、Windows 10 バージョンの Windows SDK が必要です。 Windows 10 SDK の詳細については、「[Windows 10 SDK](http://go.microsoft.com/fwlink/p/?LinkId=534603)」を参照してください  \(以前のバージョンの Windows に対応する Windows SDK の詳細については、「[Overview of the Windows SDK](../Topic/Overview%20of%20the%20Windows%20SDK.md)」を参照してください\)。  
  
 Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。  
  
## 開発ツール  
 Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、「[Visual Studio でのアプリケーション開発](http://msdn.microsoft.com/ja-jp/97490c1b-a247-41fb-8f2c-bc4c201eff68)」および「[IDE と開発ツール](../Topic/IDE%20and%20Tools%20for%20Visual%20C++%20Development.md)」を参照してください。  
  
## 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|C\+\+ に関する MSDN ライブラリ コンテンツの親トピック。|