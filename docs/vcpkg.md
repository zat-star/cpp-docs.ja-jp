---
title: "vcpkg-- Windows 用の C++ パッケージ マネージャー | Microsoft Docs"
description: "vcpkg はコマンド ライン パッケージ マネージャーであり、Windows でのオープン ソースの C++ ライブラリの取得およびインストール作業を大幅に簡素化できます。"
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 05/30/2017
ms.technology:
- cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs:
- C++
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: ed0e4505b68c2ea198e0771b6301e685daa8662e
ms.openlocfilehash: de5825e64abac210561cb8cbe0dc3320a740cbee
ms.contentlocale: ja-jp
ms.lasthandoff: 06/30/2017

---

# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg: Windows 用の C++ パッケージ マネージャー 
vcpkg はコマンド ライン パッケージ マネージャーであり、Windows でのサードパーティ ライブラリの取得とインストール作業を大幅に簡素化できます。 プロジェクトでサードパーティ ライブラリを使用する場合は、vcpkg を使用して、それらをインストールすることをお勧めします。 vcpkg では、オープン ソース ライブラリと専用ライブラリの両方がサポートされています。 vcpkg パブリック カタログ内のすべてのライブラリは、Visual Studio 2015 および Visual Studio 2017 との互換性がテストされています。 2017 年 5 月の時点で、カタログには 238 個を超えるライブラリが存在しており、C++ コミュニティでは継続的にライブラリをさらに追加しています。

## <a name="simple-yet-flexible"></a>簡単かつ柔軟
単一のコマンドで、ソースをダウンロードして、ライブラリをビルドすることができます。 vcpkg はそれ自体がオープン ソース プロジェクトであり、GitHub で入手できます。 プライベート クローン (複数可) を好きなようにカスタマイズできます。その場合、さまざまなライブラリを指定したり、パブリック カタログにあるものとは異なるバージョンのライブラリを指定したりすることができます。 vcpkg の複数のクローンを単一のコンピューターで使用できます。各クローンはライブラリおよび (または) コンパイル スイッチなどのカスタム セットを生成します。各クローンは完全に自己完結型のコピー可能な環境であり、独自の階層でのみ動作する vcpkg.exe の独自のコピーが含まれます。 vcpkg はどの環境変数にも追加されず、Windows レジストリや Visual Studio との依存関係はありません。

## <a name="sources-not-binaries"></a>バイナリではなくソース
パブリック カタログ内のライブラリの場合、vcpkg はバイナリ[1] ではなく、ソースをダウンロードします。 これらのソースは Visual Studio 2017 (2017 がインストールされていない場合は Visual Studio 2015) を使用してコンパイルされます。 C++ では、使用するすべてのライブラリが、リンクされているアプリケーション コードと同じコンパイラ、およびコンパイラ バージョンでコンパイルされることが重要です。 vcpkg を使用すると、一致しないバイナリとそれが原因による問題が発生する可能性がなくなるか、あるいは大幅に減少します。 特定のバージョンの Visual C++ コンパイラで標準化されているチームでは、1 人のチーム メンバーが vcpkg を使用してソースをダウンロードし、一連のバイナリをコンパイルしてからエクスポート コマンドを使用して、他のチーム メンバー用にバイナリとヘッダーを圧縮できます。 詳細については、以下のコンパイルされたバイナリとヘッダーのエクスポートに関する記述を参照してください。 

ポート コレクション内のプライベート ライブラリを使用して vcpkg クローンを作成する場合は、ビルド済みのバイナリとヘッダーをダウンロードするポートを追加し、目的の場所に単にコピーする portfile.cmake ファイルを書き込みます。

[1] *注: 一部の独自のライブラリでは、ソースは入手できません。vcpkg では、このような場合に互換性のあるビルド済みのバイナリをダウンロードします。*

## <a name="installation"></a>インストール
GitHub (https://github.com/Microsoft/vcpkg) から vcpkg リポジトリを複製します。 任意のフォルダー場所にダウンロードすることができます。

ルート フォルダーのブートストラップ (bootstrap-vcpkg.bat) を実行します。

## <a name="basic-tasks"></a>基本的なタスク
  
### <a name="search-the-list-of-available-libraries"></a>入手可能なライブラリのリストを検索する
入手可能なパッケージを確認するには、コマンド プロンプトで `vcpkg search` を入力します。

このコマンドは、vcpkg/ports サブフォルダーにあるコントロール ファイルを列挙します。 リストは以下のようになります。

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. <https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

  `vcpkg search ta` などのパターンでフィルター処理できます。

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library

```

### <a name="install-a-library-on-your-local-machine"></a>ローカル コンピューターにライブラリをインストールする
`vcpkg search` を使用してライブラリの名前を取得したら、`vcpkg install` を使用してライブラリをダウンロードしてからコンパイルします。 vcpkg では、ports ディレクトリのライブラリの portfile を使用します。 トリプレットが指定されていない場合、vcpkg は x86 Windows 用にインストールしてコンパイルします。 portfile で依存関係が指定されている場合、vcpkg はそれもダウンロードしてインストールします。 ダウンロードの後、vcpkg はライブラリで使用される任意のビルド システムを使用して、ライブラリをビルドします。 CMake および MSBuild プロジェクト ファイルが優先されますが、他のビルド システムと共に MAKE がサポートされます。 vcpkg がローカル コンピューターで指定されたビルド システムを見つけられない場合、そのビルド システムがダウンロードされ、インストールされます。

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

### <a name="list-the-libraries-already-installed"></a>既にインストールされているライブラリをリストする
いくつかのライブラリをインストールした後で、`vcpkg list` を使用して、その内容を確認できます。

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

### <a name="integrate-with-visual-studio"></a>Visual Studio と統合する
#### <a name="per-user"></a>ユーザーごと
`vcpkg integrate install` を実行し、VC++ ディレクトリ パスを手動で編集しなくても、ユーザーごとにすべての vcpkg ヘッダー ファイルとバイナリを検索するように Visual Studio を構成します。 複数のクローンがある場合、このコマンドを実行するクローンが新しい既定の場所となります。

これで、フォルダー/ヘッダーを入力するだけでヘッダーを #include でインクルードできるようになりました。オートコンプリートは便利な機能です。 ライブラリにリンクする場合や、プロジェクト参照を追加する場合は、追加の手順が必要になります。 次の図は、Visual Studio が azure-storage-cpp ヘッダーをどのように検索するかを示しています。 vcpkg は、ターゲット プラットフォームでパーティション分割される、\installed サブフォルダーにそのヘッダーを配置します。 以下の図は、ライブラリの `/was` サブフォルダーにあるインクルード ファイルのリストを示しています。

 ![vcpkg Intellisense 統合](media/vcpkg-intellisense.png "vcpkg と Intellisense")  

#### <a name="per-project"></a>プロジェクトごと
アクティブな vcpkg インスタンスのバージョンとは異なる特定のバージョンのライブラリを使用する必要がある場合は、vcpkg の新しいクローンを作成し、必要なバージョンを取得するためにライブラリの portfile を変更してから `vcpkg install <library>` を実行できます。 その後、`vcpkg integrate project` を使用して、プロジェクトごとにそのライブラリを参照する NuGet パッケージを作成できます。

### <a name="export-compiled-binaries-and-headers"></a>コンパイル済みのバイナリとヘッダーをエクスポートする
チームのすべてのメンバーにライブラリをダウンロードしてビルドするよう求めることは非効率な場合があります。 1 人のチーム メンバーがその作業を行ってから、`vcpkg export` を使用して、他のチーム メンバーと簡単に共有できる、バイナリとヘッダーの zip ファイルを作成できます。 

### <a name="update-installed-libraries"></a>インストールされているライブラリを更新する
パブリック カタログは、最新バージョンのライブラリで最新の状態が保たれます。 古いローカル ライブラリを判別するには、`vcpkg update` を使用します。 ポート コレクションをパブリック カタログの最新バージョンに更新する準備ができたら、後は github リポジトリに対して git プル操作を実行するか、新しいクローンを作成して、古いものがまだ必要な場合はそれを保持するだけです。

### <a name="contribute-new-libraries"></a>新しいライブラリを投稿する
プライベート ポート コレクションに好きなライブラリを含めることができます。 パブリック カタログ用の新しいライブラリを提案するには 


### <a name="remove-a-library"></a>ライブラリを削除する
`vcpkg remove` を入力して、インストールされているライブラリを削除します。 他のライブラリがそれに依存している場合は、`--recurse` を指定してコマンドを再実行するよう求められます。実行すると、すべてのダウンストリーム ライブラリが削除されます。

### <a name="customize-vcpkg"></a>vcpkg をカスタマイズする
好きなように vcpkg のクローンを変更することができます。 複数の vcpkg クローンを作成し、それぞれの portfile を変更して、特定のバージョンのライブラリを取得するか、コマンド ライン パラメーターを指定できます。 たとえば、企業では、開発者のあるグループが 1 つの依存関係セットを持つソフトウェアで作業し、別のグループが異なるセットを持つ場合があります。 vcpkg の 2 つのクローンをセットアップし、それぞれを変更して、必要に応じて、該当するバージョンのライブラリやコンパイル スイッチなどをダウンロードできます。 

## <a name="the-vcpkg-folder-hierarchy"></a>vcpkg のフォルダー階層
vcpkg のすべての機能とデータは 1 つのディレクトリ階層にすべて含まれています。これを "インスタンス" といいます。 レジストリの設定や環境変数はありません。 コンピューターで vcpkg の任意の数のインスタンスを使用でき、相互に干渉することはありません。 

vcpkg インスタンスの内容は次のとおりです。 
- buildtrees -- 各ライブラリの作成元となるソースのサブフォルダーが含まれています。
- docs -- ドキュメントと例
- downloads -- ダウンロードしたツールまたはソースのキャッシュ コピー。 vcpkg は、インストール コマンドの実行時に最初にここで検索を行います。
- installed -- インストールされている各ライブラリのヘッダーとバイナリが含まれています。 Visual Studio と統合する場合、基本的にこのフォルダーをその検索パスに追加することを示すことになります。
- packages -- インストール間のステージング用の内部フォルダー。
- ports -- カタログ内の各ライブラリ、そのバージョン、およびダウンロード場所を記述するファイル。 必要に応じて、独自のポートを追加できます。
- scripts -- vcpkg で使用されるスクリプト (cmake、powershell)。
- toolsrc -- vcpkg と関連するコンポーネントの C++ ソース コード
- triplets -- サポート対象のターゲット プラットフォーム (x86 Windows や x64 UWP など) の設定が含まれます。

## <a name="command-line-reference"></a>コマンド ライン リファレンス
- vcpkg search [pat]        入手してビルドできるパッケージを検索します
- vcpkg install <pkg>...  パッケージをインストールします
- vcpkg remove <pkg>...パッケージをアンインストールします
- vcpkg remove --outdated   古いパッケージをアンインストールします
- vcpkg list            インストールされているパッケージをリストします
- vcpkg update          更新対象のパッケージのリストを表示します
- vcpkg hash <file> [alg]       特定のアルゴリズム (既定では SHA512) を使用して、ファイルをハッシュします
- vcpkg integrate install       インストールされているパッケージをユーザー全体で使用できるようにします。 初回使用時は管理特権が必要です
- vcpkg integrate remove        ユーザー全体の統合を削除します
- vcpkg integrate project        個々の VS プロジェクト使用のために参照する nuget パッケージを生成します
- vcpkg export <pkg>... [opt]...  パッケージをエクスポートします
- vcpkg edit <pkg>      編集対象のポートを開きます (既定の 'コード' %EDITOR% を使用)
- vcpkg import <pkg>        ビルド済みのライブラリをインポートします
- vcpkg create <pkg> <url>   [archivename]        新しいパッケージを作成します
- vcpkg owns <pat>      インストールされているパッケージでファイルを検索します
- vcpkg cache           キャッシュされたコンパイル済みのパッケージをリストします
- vcpkg version         バージョン情報を表示します
- vcpkg contact         フィードバックを送信する連絡先の情報を表示します

### <a name="options"></a>オプション:
  **`--triplet <t>`** ターゲット アーキテクチャのトリプレットを指定します。 (既定値: `%VCPKG_DEFAULT_TRIPLET%`。`vcpkg help triplet` も参照してください)

  **`--vcpkg-root <path>`** vcpkg ルート ディレクトリを指定します (既定値: `%VCPKG_ROOT%`)

