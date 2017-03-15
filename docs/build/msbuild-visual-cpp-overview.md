---
title: "MSBuild (Visual C++) の概要 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MSBuild の概要"
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MSBuild (Visual C++) の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MSBuild は、Visual C++ プロジェクト用の標準のビルド システムです。 Visual Studio 統合開発環境 (IDE: Integrated Development Environment) でプロジェクトをビルドするときには、msbuild.exe ツール、XML ベースのプロジェクト ファイル、およびオプションの設定ファイルが使用されます。 msbuild.exe とプロジェクト ファイルをコマンド ラインで使用することもできますが、IDE にはユーザー インターフェイスが用意されているため、設定の構成とプロジェクトのビルドをより簡単に行うことができます。 ここでは、Visual C++ で MSBuild システムを使用する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 MSBuild に関する次のドキュメントを参照してください。  
  
 [MSBuild](MSBuild1.md)  
 MSBuild の概念の概要。  
  
 [MSBuild リファレンス](../Topic/MSBuild%20Reference.md)  
 MSBuild システムに関するリファレンス情報。  
  
 [プロジェクト ファイル スキーマ リファレンス](../Topic/MSBuild%20Project%20File%20Schema%20Reference.md)  
 MSBuild XML スキーマ要素の一覧を、それぞれの属性、親要素、および子要素と共に示します。 特に注意してください、 [ItemGroup](../Topic/ItemGroup%20Element%20\(MSBuild\).md), 、[PropertyGroup](../Topic/PropertyGroup%20Element%20\(MSBuild\).md), 、[ターゲット](../Topic/Target%20Element%20\(MSBuild\).md), 、および [タスク](../Topic/Task%20Element%20\(MSBuild\).md) 要素。  
  
 [コマンド ライン リファレンス](../Topic/MSBuild%20Command-Line%20Reference.md)  
 msbuild.exe で使用できるコマンド ライン引数とコマンド ライン オプションについて説明します。  
  
 [タスク リファレンス](../Topic/MSBuild%20Task%20Reference.md)  
 MSBuild タスクについて説明します。 これらのタスクでは、Visual C に固有に特に注意してください: [BscMake タスク](../Topic/BscMake%20Task.md), 、[CL タスク](../Topic/CL%20Task.md), 、[CPPClean タスク](../Topic/CPPClean%20Task.md), 、[LIB タスク](../Topic/LIB%20Task.md), 、[Link タスク](../Topic/Link%20Task.md), 、[MIDL タスク](../Topic/MIDL%20Task.md), 、[MT タスク](../Topic/MT%20Task.md), 、[RC タスク](../Topic/RC%20Task.md), 、[SetEnv タスク](../Topic/SetEnv%20Task.md), 、[VCMessage タスク](../Topic/VCMessage%20Task.md), 、[XDCMake タスク](../Topic/XDCMake%20Task.md), 、[XSD タスク](../Topic/XSD%20Task.md)します。  
  
## <a name="msbuild-on-the-command-line"></a>コマンド ラインでの MSBuild  
 次のステートメント、 [コマンド ライン リファレンス](../Topic/MSBuild%20Command-Line%20Reference.md) ドキュメントは、msbuild.exe ツールが、暗黙的または明示的なを受け取ることを示しています。 `project file` 引数 (Visual c プロジェクトでは .vcxproj ファイル) と 0 個以上のコマンドライン `options`します。  
  
 **msbuild.exe [** `project file` **] [** `options` **]**  
  
 使用して、 **/target** (または **/t**) と **/property** (または **/p**) プロジェクト ファイルで指定されているプロパティおよびターゲットをオーバーライドするコマンド ライン オプションです。  
  
 プロジェクト ファイルの重要な機能を指定するには、 *ターゲット*, 、これは、プロジェクトと、入力とその操作を実行するために必要な出力に適用される特定の操作です。 プロジェクト ファイルでは 1 つ以上のターゲットを指定でき、既定のターゲットを含めることができます。  
  
 各ターゲットが 1 つ以上の一連の構成 *タスク*します。 各タスクは、実行可能なコマンドを 1 つ含む .NET Framework クラスによって表されます。 たとえば、 [CL タスク](../Topic/CL%20Task.md) を含む、 [cl.exe](../build/reference/compiling-a-c-cpp-program.md) コマンドです。  
  
 A *タスク パラメーター* はクラス タスクのプロパティで、通常実行可能なコマンドのコマンド ライン オプションを表します。 たとえば、 `FavorSizeOrSpeed` のパラメーター、 `CL` に対応するタスク、 **/Os** と **/Ot** コンパイラ オプション。  
  
 追加のタスク パラメーターは、MSBuild インフラストラクチャをサポートします。 たとえば、`Sources` タスク パラメーターは、他のタスクで使用できる一連のタスクを指定します。 MSBuild タスクの詳細については、次を参照してください。 [タスク リファレンス](../Topic/MSBuild%20Task%20Reference.md)します。  
  
 ほとんどのタスクには入力と出力が必要です。これには、ファイル名、パス、文字列パラメーター、数値パラメーター、ブール値パラメーターなどがあります。 たとえば、一般的な入力は、コンパイルする .cpp ソース ファイルの名前です。 重要な入力パラメーターは、ビルド構成とプラットフォーム、たとえば、"デバッグ &#124; を指定する文字列Win32"です。 入力と出力は、`Item` 要素に含まれる 1 つ以上のユーザー定義の XML `ItemGroup` 要素で指定します。  
  
 プロジェクト ファイルは、ユーザー定義も指定できます *プロパティ* と *項目定義グループ**項目*します。 プロパティと項目は、ビルドで変数として使用できる名前と値のペアを形成します。 ペアの名前のコンポーネントを定義、 *マクロ*, 、値の構成要素を宣言し、 *マクロの値*です。 $ を使用してプロパティのマクロにアクセス (*名*) 表記法、および、項目マクロは %(を使用してアクセス*名*) 表記します。  
  
 プロジェクト ファイル内の他の XML 要素では、マクロをテストし、条件に従ってマクロの値を設定したり、ビルドの実行を制御したりできます。 マクロ名とリテラル文字列を連結して、パスとファイル名などの構成要素を生成することもできます。 コマンド ラインで、 **/property** オプションを設定またはプロジェクトのプロパティをオーバーライドします。 コマンド ラインで項目を参照することはできません。  
  
 MSBuild システムでは、あるターゲットを、条件に従って別のターゲットの前または後に実行できます。 また、ターゲットで使用されるファイルが出力されるファイルよりも新しいかどうかに基づいて、ターゲットをビルドすることもできます。  
  
## <a name="msbuild-in-the-ide"></a>IDE での MSBuild  
 IDE でプロジェクト プロパティを設定し、プロジェクトを保存すると、Visual C++ によってプロジェクト設定がプロジェクト ファイルに書き込まれます。 プロジェクト ファイルにはプロジェクトに固有の設定が含まれますが、プロジェクトのビルドに必要な設定がすべて含まれているわけではありません。 プロジェクト ファイルには `Import` 、追加のネットワークを含む要素 *ファイルをサポートします。* サポート ファイルには、プロジェクトのビルドに必要なその他のプロパティ、ターゲット、および設定が含まれます。  
  
 サポート ファイル内のほとんどのターゲットとプロパティは、ビルド システムを実装するためだけに用意されています。 次のセクションでは、MSBuild コマンド ラインで指定できる便利なターゲットとプロパティについて説明します。 その他のターゲットおよびプロパティについては、サポート ファイル ディレクトリ内のファイルを参照してください。  
  
### <a name="support-file-directories"></a>サポート ファイル ディレクトリ  
 既定では、Visual C++ の主要なサポート ファイルは、次のディレクトリに配置されています。  
  
|ディレクトリ|説明|  
|---------------|-----------------|  
|*ドライブ*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\|ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。|  
|*ドライブ*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\Platforms\\*プラットフォーム*\|親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリ内のターゲットによって使用されるタスクを定義する .dll ファイルも含まれています。<br /><br />  *プラットフォーム* を表すプレース ホルダー、 `ARM`, 、`Win32`, 、または `x64` サブディレクトリ。|  
|*ドライブ*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\|指定した Visual C アプリケーションを生成するためのビルドを有効にするディレクトリを含む *バージョン* ツールセットのです。<br /><br />  *プラットフォーム* を表すプレース ホルダー、 `ARM`, 、`Win32`, 、または `x64` サブディレクトリ。  *ツールセット* プレース ホルダーは、Windows、Windows XP または Windows Phone アプリを構築するためのツールセット サブディレクトリを表します。|  
|*ドライブ*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\|ビルドで Visual C++ 9.0 アプリケーションまたは Visual C++ 10.0 アプリケーションを生成できるようにするためのディレクトリがあります。<br /><br />  *プラットフォーム* を表すプレース ホルダー、 `Itanium`, 、`Win32`, 、または `x64` サブディレクトリ。  *ツールセット* を表すプレース ホルダー、 `v90` または `v100` ツールセット サブディレクトリ。|  
  
### <a name="support-files"></a>サポート ファイル  
 サポート ファイル ディレクトリには、次の拡張子を持つファイルが含まれます。  
  
|拡張子|説明|  
|---------------|-----------------|  
|.targets|ターゲットによって実行されるタスクを指定する `Target` XML 要素が含まれます。 タスク パラメーターにファイルとコマンド ライン オプションを割り当てるために使用される、`Property Group`、`Item Group`、`Item Definition Group`、およびユーザー定義の `Item` の各要素が含まれることもあります。<br /><br /> 詳細については、次を参照してください。 [Target 要素 (MSBuild)](../Topic/Target%20Element%20\(MSBuild\).md)します。|  
|.props|ビルド時に使用されるファイル設定とパラメーター設定を指定する `Property Group` XML 要素およびユーザー定義の `Property` XML 要素が含まれます。<br /><br /> 追加の設定を指定する `Item Definition Group` XML 要素およびユーザー定義の `Item` XML 要素が含まれることもあります。 項目定義グループに定義されている項目はプロパティに似ていますが、コマンド ラインからはアクセスできません。 Visual C++ プロジェクト ファイルでは、プロパティではなく項目を使用して設定を表すことがよくあります。<br /><br /> 詳細については、次を参照してください。 [ItemGroup 要素 (MSBuild)](../Topic/ItemGroup%20Element%20\(MSBuild\).md), 、[ItemDefinitionGroup 要素 (MSBuild)](../Topic/ItemDefinitionGroup%20Element%20\(MSBuild\).md), 、および [Item 要素 (MSBuild)](../Topic/Item%20Element%20\(MSBuild\).md)します。|  
|.xml|プロパティ シート、プロパティ ページ、テキスト ボックス コントロール、リスト ボックス コントロールなどの IDE ユーザー インターフェイス要素を宣言および初期化する XML 要素が含まれます。<br /><br /> .xml ファイルは、MSBuild ではなく IDE を直接サポートします。 ただし、IDE プロパティの値は、ビルド プロパティおよび項目に割り当てられます。<br /><br /> ほとんどの .xml ファイルは、ロケール固有のサブディレクトリにあります。 たとえば、英語 (米国) 地域のファイルは $(VCTargetsPath) \1033\\します。|  
  
## <a name="user-targets-and-properties"></a>ユーザー ターゲットおよびプロパティ  
 コマンド ラインで MSBuild をより効果的に使用するためには、どのプロパティとターゲットが役に立ち、どれが関係しているかを知っておくと便利です。 ほとんどのプロパティとターゲットは、Visual C++ ビルド システムを実装するために使用されるもので、ユーザーには関係がありません。 ここでは、ユーザー指向の有用なプロパティとターゲットについて説明します。  
  
### <a name="platformtoolset-property"></a>PlatformToolset プロパティ  
 `PlatformToolset` プロパティは、ビルドでどの Visual C++ ツールセットを使用するか決定します。 このプロパティの値はリテラル文字列と連結され、特定のプラットフォームでプロジェクトをビルドするために必要なプロパティ ファイルとターゲット ファイルのあるディレクトリのパスを形成します。  
  
 設定、 `PlatformToolset` プロパティを `v110` を使用する [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] ツールとアプリケーションをビルドするライブラリです。  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v110`  
  
 設定、 `PlatformToolset` プロパティを `v100` を使用する [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] ツールとアプリケーションをビルドするライブラリです。  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v100`  
  
 設定、 `PlatformToolset` プロパティを `v90` を Visual C 2008 ツールとライブラリを使用して、アプリケーションをビルドします。 このプロパティを有効にするには、Visual C++ 2008 のツールセットがコンピューターに既にインストールされている必要があります。  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v90`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture プロパティ  
 `PreferredToolArchitecture` プロパティは、ビルドで使用されているコンパイラとツールが 32 ビットか 64 ビットかを判定します。 このプロパティは、出力プラットフォームのアーキテクチャおよび構成には影響しません。 既定では、MSBuild は、x86 版のコンパイラおよびツールの場合は、このプロパティが設定されていないか、値に設定の他にも `x64`です。  
  
 設定、 `PreferredToolArchitecture` プロパティを `x64` アプリケーションをビルドする 64 ビットのコンパイラおよびツールを使用しています。  
  
 `msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv プロパティ  
 既定では、現在のプロジェクトのプラットフォーム固有の設定によって、PATH、INCLUDE、LIB、LIBPATH、CONFIGURATION、および PLATFORM の各環境変数がオーバーライドされます。 環境変数がオーバーライドされないようにするには、`UseEnv` プロパティを `true` に設定します。  
  
 `msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>ターゲット  
 Visual C++ のサポート ファイル内には、ターゲットが数多く存在します。 ただし、ほとんどはシステム指向のターゲットであり、ユーザーは無視できます。 ほとんどのシステム ターゲットは、先頭にアンダースコア (_) が付くか、"PrepareFor"、"Compute"、"Before"、"After"、"Pre"、または "Post" で始まる名前が付いています。  
  
 ユーザー指向の有用なターゲットを次の表に示します。  
  
|ターゲット|説明|  
|------------|-----------------|  
|BscMake|Microsoft Browse Information Maintenance Utility ツール (bscmake.exe) を実行します。|  
|ビルド|プロジェクトをビルドします。<br /><br /> プロジェクトの既定のターゲットです。|  
|ClCompile|Visual C++ コンパイラ ツール (cl.exe) を実行します。|  
|クリーン|一時ビルド ファイルおよび中間ビルド ファイルを削除します。|  
|Lib|Microsoft 32-Bit Library Manager ツール (lib.exe) を実行します。|  
|Link|Visual C++ リンカー ツール (link.exe) を実行します。|  
|ManifestResourceCompile|マニフェストからリソースの一覧を抽出し、Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|  
|Midl|Microsoft インターフェイス定義言語 (MIDL: Microsoft Interface Definition Language) コンパイラ ツール (midl.exe) を実行します。|  
|リビルド|プロジェクトを消去してからビルドします。|  
|ResourceCompile|Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|  
|XdcMake|XML ドキュメント ツール (xdcmake.exe) を実行します。|  
|Xsd|XML スキーマ定義ツール (Xsd.exe) を実行します。|  
  
## <a name="see-also"></a>関連項目  
 [MSBuild (Visual C)](../Topic/MSBuild%20\(Visual%20C++\).md)