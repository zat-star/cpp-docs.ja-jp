---
title: "C++ での Windows プログラミングの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b204783e3b2c418e5e719ca5c6efcf9c2d31c6df
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

Visual C++ を使用すると、Windows PC (x86、x64、または ARM)、Windows サーバー、クラウド、または Xbox で実行される多様なプログラムを記述できます。 適切に記述された C++ プログラムは、高速で効率的であり、電力消費面の経済性に優れています。また、マルチコア デバイスおよびメニーコア デバイス、グラフィックス処理装置 (GPU) での一般コンピューティング、その他の最新ハードウェアの利点をフル活用することができます。

Visual C++ で開発できる Windows アプリにはいくつかの大きなカテゴリがあります。 これらのカテゴリのプログラミング モデルまたはアプリ モデルはさまざまです。つまり、プラットフォームへのアクセスやユーザー インターフェイスの提供のためにさまざまなライブラリや API を使用するということです。

- [Windows ユニバーサル アプリ](#BK_WindowsUniversal)。 Windows アプリの 3 番目のカテゴリが Windows 8 で導入され、このカテゴリのアプリは Windows 10 でも引き続きサポートされます。 多くの場合、これらのアプリケーションは単に "Windows アプリ" と呼ばれ、さまざまなデバイスを対象とするデスクトップおよびモバイルのアプリがそれに含まれています。 これらのアプリは、C++/CX (C++ の方言であり、Windows ランタイム開発のサポートを含む) で作成することも、Windows ランタイム ライブラリ (WRL) を使用して 標準 C++ と COM で作成することもできます。 これらのアプリはもともと全画面表示で実行するよう設計されていましたが、Windows 10 のユーザーにはデスクトップ ウィンドウでこれを実行するオプションがあります。 これらのアプリはタッチ指向ですが、ユーザーがマウスを好む場合や、タッチ スクリーンが利用できない場合はマウスを簡単に使用できます。 これらのアプリは、Microsoft ストア、アプリの"Store"が呼び出されることに至ったファクトから配布されます。

- [デスクトップ、サーバー、およびクラウドのアプリケーションとゲーム](#BK_Native)。 このカテゴリには、Windows デスクトップ アプリケーションが含まれます。これらのアプリケーションは、Windows 8 以前に Win32 APIを使用していたため、Win32 アプリケーションとも呼ばれ、すべての Windows アプリケーションがこのカテゴリに含まれます。 このカテゴリのアプリケーションは、ユーザー インターフェイスに MFC を使用でき、Windows コンポーネント (通常は COM オブジェクト) との対話に ATL を使用できます。

   標準の C++ で作成されたアプリケーション、コンポーネント、またはライブラリも、このカテゴリに該当します。

   サーバーおよびクラウド プログラミングのコンテキストにおいて、コア コンポーネントのためや、計算コードのために C++ を使用することも、このカテゴリに含まれます。 場合によっては、サーバーやクラウド アプリケーションのコアとなるパフォーマンス重視のコードを C++ で記述し、パフォーマンスを最適化することもあります。 このようなコードをコンパイルして DLL にし、C# または Visual Basic から使用することができます。

- **.NET Framework アプリケーション**。 .NET Framework アプリケーションのほとんどは C# または Visual Basic で記述されていますが、C++/CLI でも記述できます (Visual C++ の/clr コンパイラ オプション)。 マネージ コードとネイティブ コードを含む大規模なアプリケーションでは、C++/CLI は最小限の相互運用層で使用することをお勧めします。

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Windows 10 では、デスクトップ上だけでなく、タブレットや携帯電話など、すべての Windows 10 デバイスでアプリを実行できます。 デスクトップでは、常に全画面表示で実行しなければならないわけではなく、デスクトップ ウィンドウとして実行することができます。 これらのアプリは Xbox でも動作し、将来のデバイスでも実行できます。  2 種類のアプリのプログラミング モデルは、Win32 デスクトップ アプリケーションとは異なります。 これらの Windows アプリケーションは Windows ランタイム上で動作します。このランタイムは、ユーザー インターフェイス要素、これらのアプリの重要なサービス、およびサポートされている多様なハードウェア デバイスへのインターフェイスを提供します。 これらのアプリはネイティブ コードにコンパイルされ、XAML ユーザー インターフェイスを持つか、DirectX を使用します。 その他の Windows アプリで使用できるネイティブ コードで、Windows ランタイム コンポーネントを記述することも、c#、Visual Basic、または JavaScript で記述されたアプリが含まれます。 詳細については、次を参照してください。 [C++ UWP"Hello world"アプリを作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)、 [DirectX で UWP の簡単なゲームを作成する](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game)、および[C++ で作成する Windows ランタイム コンポーネント](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

> [!TIP]
> Windows 10 用 Microsoft ストアを介して展開用の既存のデスクトップ アプリケーションをパッケージ化するのに、デスクトップ アプリを実行するコンバーターを使用できます。 詳しくは、「[Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)」(Centennial プロジェクトでの Visual C++ ランタイムの使用) および「[Bring your desktop app to the Universal Windows Platform (UWP) with the Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)」(Desktop Bridge でデスクトップ アプリをユニバーサル Windows プラットフォーム (UWP) 対応にする) をご覧ください。

ユニバーサル Windows プラットフォームのサンプルの詳細については、「 [GitHub の Windows のユニバーサル サンプル](https://github.com/Microsoft/Windows-universal-samples)」を参照してください。

既存の Windows 8.1 プロジェクトおよび Windows 10 に移植する必要がある場合は、次を参照してください。[ユニバーサル Windows プラットフォームに移植](../porting/porting-to-the-universal-windows-platform-cpp.md)です。 参照してください、UWP アプリに統合する場合、およびコードを既存のクラシック Win32 デスクトップ ライブラリがあります[する方法: ユニバーサル Windows プラットフォーム アプリで既存の C++ コードを使用して](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md)です。

C + を使用せず、ユニバーサル Windows アプリ、ゲーム、およびコンポーネントを記述することも + CX です。代わりに、Windows ランタイム C++ テンプレート ライブラリ (Windows ランタイム C++ テンプレート ライブラリ) を使用することができます。 詳細については、次を参照してください。 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。

[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]を使用して、Windows 10 のデスクトップとモバイル デバイスで動作するユニバーサル Windows アプリを開発することができます。 また、Windows 8.1 アプリと Windows Phone 8.1 アプリを [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]で作成することもできますが、それにはまず、同じコンピューターに Visual Studio 2013 をインストールし、 **Visual Studio 2013 (v120)** ツールセットを使用するようプロジェクトを構成する必要があります。 プロジェクトでこの設定を構成するには、プロジェクトのプロパティを開き、**[全般]** セクションで、**[プラットフォーム ツールセット]** を **[Visual Studio 2013 (v120)]** に設定します。

Visual Studio のセットアップで、Phone 8.0 のツールをインストールする場合は、Windows Phone 8.0 を対象にすることもできます。

Windows 10 で導入された API コントラクトと呼ばれる新しい概念は、特定のバージョンの Windows を対象とするという従来の慣習を置き換えます。 代わりに、アプリに必要な API コントラクトを選択すると、そのアプリはこれらのコントラクトをサポートするあらゆる Windows デバイスで動作するようになります。 API コントラクトはプラットフォームやデバイスのリソースへのアクセスを提供する安定した API のセットです。 API コントラクトは、プロジェクト システムに参照として含めることができます。 Visual Studio プロジェクトで特定の拡張機能 SDK への参照を追加する場合、Visual Studio は適切な API コントラクトを追加します。

これらすべての概念の詳細については、次を参照してください。 [Windows ユニバーサル アプリ ガイド](http://go.microsoft.com/fwlink/p/?linkid=534605)です。

##  <a name="BK_Native"></a> デスクトップ、サーバー、およびクラウドのアプリとゲーム

クラウドでは、C++ で Azure ネイティブ コード アセンブリを作成し、C# で作成された Web ロールからこれらを呼び出すことができます。 詳細については、「 [Azure SDK](http://go.microsoft.com/fwlink/p/?LinkId=256416)」を参照してください。

デスクトップの Windows クライアント アプリケーションを記述するための基礎を習得するには、「 [Developing Windows Applications in C++](http://msdn.microsoft.com/vstudio//hh304489) 」 (C++ での Windows アプリケーションの開発) および「 [Windows C++ プログラミングの概要](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx)」を参照してください。

Windows 10 では、Visual C++ を使用して多様な種類のプログラムを作成できます。

- コマンド ライン アプリとユーティリティ。 詳細については、次を参照してください。[コンソール アプリケーション](../windows/console-applications-in-visual-cpp.md)です。

- PC または Xbox で実行される DirectX ゲーム。 詳細については、 [DirectX デベロッパー センター](http://go.microsoft.com/fwlink/p/?LinkId=256418)を参照してください。

- 洗練されたグラフィカル ユーザー インターフェイスを持つコンシューマー向けアプリケーション。 詳細については、「 [Hilo: Windows 7 対応 C++ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=256417)」を参照してください。

- .NET Framework で実行されるか、.NET Framework アプリとネイティブ コードで記述されたアプリまたはコンポーネントとの間のブリッジとなる、エンタープライズ アプリおよび基幹業務アプリ。 詳細については、次を参照してください。 [C + での .NET プログラミング +/CLI (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)です。

- ネイティブ コードで実行される SQL データベース クライアント。 詳細については、「 [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419)」を参照してください。

- Microsoft Office アプリケーション用アドイン。 詳細については、「 [Outlook 2010 の C++ アドインをビルドする](http://go.microsoft.com/fwlink/p/?LinkId=256420)」を参照してください。

- デバイス ドライバー。 詳細については、「 [Windows Driver Kit (WDK) について](http://go.microsoft.com/fwlink/p/?LinkId=256421)」を参照してください。

- Windows サービス 詳細については、「 [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications)」を参照してください。

Visual C++ を使用すると、高性能なカスタム機能をほぼ種類に関係なく Win32 DLL または COM DLL にパッケージ化できます。これらは、C++ アプリまたは C# や Visual Basic など他の言語で記述されたアプリで使用できます。 WIn32 DLL の詳細については、「 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)」を参照してください。 COM 開発に関する詳細については、次を参照してください。[コンポーネント オブジェクト モデル (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573)です。

## <a name="sdks-and-header-files"></a>SDK とヘッダー ファイル

Visual C には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリでは、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが格納されるインクルード フォルダーは、Visual Studio インストール ディレクトリの \VC\ フォルダーの下にある場合は、CRT、Windows SDK のインストール フォルダー、プログラム ファイルで Windows Kits\10 などにあるいずれかWindows 10 SDK のフォルダーです。  Microsoft ライブラリには、次のとおりです。

- Microsoft Foundation Classes (MFC): ボタン、リスト ボックス、ツリー ビュー、および他のコントロールを使用した豊富なユーザー インターフェイスを持つ従来の Windows プログラム (特にエンタープライズ アプリケーション) を作成するためのオブジェクト指向フレームワーク。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL): COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism): GPU で一般的な計算作業のパフォーマンス向上を可能にするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- 同時実行ランタイム: マルチコア デバイスおよびメニーコア デバイス用の並列プログラミングおよび非同期プログラミング作業を簡略化するために役立つライブラリ。 詳細については、「 [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、ユニバーサル Windows アプリの開発できるようにする Windows SDK をインストールします。 Windows の 10 のユニバーサル Windows アプリを開発するには、Windows 10 バージョンの Windows SDK が必要です。 Windows 10 SDK については、次を参照してください。 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)です。 (Windows の以前のバージョンの Windows Sdk の詳細については、次を参照してください。、 [Windows SDK アーカイブ](https://developer.microsoft.com/windows/downloads/sdk-archive))。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、次を参照してください。 [Visual Studio での開発を開始](/visualstudio/ide/get-started-developing-with-visual-studio)、および[IDE と開発ツール](../ide/ide-and-tools-for-visual-cpp-development.md)です。

## <a name="related-articles"></a>関連トピック

|タイトル|説明|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C 開発者向けのコンテンツの親トピック。|