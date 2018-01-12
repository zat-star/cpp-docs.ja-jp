---
title: "純粋と検証可能なコード (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7bcaabb9f0a696a5eb7b01c4bd78757681e4e6a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>純粋なコードと検証可能なコード (C++/CLI)
.NET プログラミングに対して、Visual C++ は、混在、純粋、検証可能の 3 種類のコンポーネントおよびアプリケーションの作成をサポートしています。 使用可能な 3 つすべて、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。  
  
## <a name="remarks"></a>コメント  
 検証可能なアセンブリの詳細については、以下を参照してください。  
  
-   [混合、純粋、および確認可能の各機能の比較 (C++/CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [方法:/clr:pure に移行: 純粋な (C + + CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [方法: 確認可能な C++ プロジェクトを作成する (C++/CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [方法:/clr:safe に移行 (C + + CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [SQL Server での確認可能なアセンブリの使用 (C++/CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [セキュリティ推奨事項](../security/security-best-practices-for-cpp.md)  
  
-   [混合モードから純粋な中間言語へのプロジェクトの変換](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>混合 (/clr)  
 混在アセンブリ (コンパイルした**/clr**) アンマネージ両方を含めること、および .NET の機能を利用できるようにする、管理対象の部分はアンマネージ コードをまだ保持しています。 このため、プロジェクト全体を書き直すことなく、.NET 機能を使用するようにアプリケーションやコンポーネントを更新できます。 Visual C++ を使用してこのようにマネージ コードとアンマネージ コードを混在させる方法を、C++ Interop と呼びます。 詳細については、次を参照してください。[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)と[ネイティブ モードと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)です。  
  
## <a name="pure-clrpure"></a>純粋 (/clr:pure)  
 純粋なアセンブリ (コンパイルした**/clr: 純粋な**) 両方のネイティブおよびマネージのデータ型を含めることができますが、マネージ関数のみです。 混在アセンブリは、純粋なアセンブリできるようにする P/invoke を通じてネイティブ Dll との相互運用 (を参照してください[C++ (DllImport 属性) で明示的な PInvoke を使用して](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)) が C++ 相互運用機能は使用できません。 さらに、純粋なアセンブリが純粋なアセンブリの使用中のエントリを参照するためにネイティブ関数から呼び出すことができる関数をエクスポートできません、 [_ _clrcall](../cpp/clrcall.md)呼び出し規約です。  
  
### <a name="advantages-of-clrpure"></a>/clr:pure の利点  
  
-   優れたパフォーマンス : 純粋なアセンブリには MSIL だけが含まれ、ネイティブ関数は含まれていないため、マネージとアンマネージ間の遷移は不要です  (ただし、プラットフォーム呼び出しによって行われる関数呼び出しは例外です)。  
  
-   AppDomain 対応 : マネージ関数と CLR データ型は、それらの参照可能範囲やアクセシビリティに影響する `Application Domains` 内に存在しています。 純粋なアセンブリがドメインに対応 (_ _declspec ([appdomain](../cpp/appdomain.md)) が各型の暗黙的) より簡単かつ安全には他の .NET コンポーネントからその種類と機能にアクセスするようにします。 その結果、純粋なアセンブリは混在アセンブリよりも安全に他の .NET コンポーネントとの相互運用が実行できます。  
  
-   ディスクへの読み込みなし : 純粋なアセンブリはメモリに読み込んだりストリームしたりできます。 これは、.NET アセンブリをストアド プロシージャとして使用する場合の基本です。 この点は混在アセンブリとの相違点であり、混在アセンブリは Windows の読み込み機構に依存しているため、実行するにはディスク上に存在している必要があります。  
  
-   リフレクション : 混在実行可能ファイルではリフレクションは使用できませんが、純粋なアセンブリはリフレクションを完全にサポートしています。 詳細については、次を参照してください。[リフレクション (C + + CLI)](../dotnet/reflection-cpp-cli.md)です。  
  
-   ホストの制御性 : 純粋なアセンブリには MSIL だけが含まれるため、CLR をホストしてその既定の動作を変更するアプリケーションで使用する場合、純粋なアセンブリは混在アセンブリよりも予測可能で柔軟な動作をします。  
  
### <a name="limitations-of-clrpure"></a>/clr:pure の制限  
 ここでサポートされていない機能**/clr: 純粋な**します。  
  
-   純粋なアセンブリはアンマネージ関数から呼び出すことができません。 したがって、純粋なアセンブリは COM インターフェイスを実装したりネイティブ コールバックを公開したりできません。 純粋なアセンブリは __declspec(dllexport) または .DEF ファイルを使用して関数をエクスポートすることはできません。 またで宣言された関数、 \__clrcall 規約を使用してインポートすることはできません\__declspec(dllimport) です。 ネイティブ モジュールの関数を純粋なアセンブリから呼び出すことはできますが、純粋なアセンブリはネイティブ呼び出し可能関数を公開できません。そのため、純粋なアセンブリの公開機能は、混在アセンブリでマネージ関数をとおして実行する必要があります。 参照してください[する方法:/clr:pure に移行: 純粋な (C + + CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)詳細についてはします。  
  
-   ATL ライブラリと MFC ライブラリは、Visual C++ の純粋モード コンパイルではサポートされません。  
  
-   純粋な .netmodule は、Visual C++ リンカーの入力として受け付けられません。 ただし、純粋な .obj ファイルはリンカーによって受け付けられ、.obj ファイルには netmodule に含まれる情報のスーパーセットが含まれます。 参照してください[リンカー入力としての .netmodule ファイル](../build/reference/netmodule-files-as-linker-input.md)詳細についてはします。  
  
-   コンパイラ COM サポート (#import) は純粋なアセンブリにアンマネージ命令を導入する可能性があるため、サポートされていません。  
  
-   アラインメントと例外処理の浮動小数点オプションを、純粋なアセンブリに合わせて調整することはできません。 結果的に、__declspec(align) を使用できません。 そのため、fpieee.h などのヘッダー ファイルは /clr:pure と互換性がありません。  
  
-   コンパイルすると、PSDK の GetLastError 関数が未定義の動作を移すことができる**/clr: 純粋な**します。  
  
## <a name="verifiable-clrsafe"></a>検証可能 (/clr:safe)  
 **/Clr:safe**コンパイラ オプションには、Visual Basic および C# の場合、できるように、共通言語ランタイム (CLR) コードが違反していないことを保証するために現在の要件に準拠しているで記述されるものと同様に、検証可能なアセンブリが生成されます。セキュリティ設定。 たとえば、コンポーネントによるディスクへの書き込みがセキュリティ設定で禁止されている場合、CLR は検証可能なコンポーネントがこの条件を満たしているかをコードの実行前に確認できます。 CRT は検証可能なアセンブリをサポートしていません  (CRT のサポートは、C ランタイム ライブラリの純粋 MSIL バージョンを使用して、純粋なアセンブリで利用できます)。  
  
 検証可能なアセンブリには、純粋なアセンブリや混在アセンブリを超える次のような利点があります。  
  
-   セキュリティの向上。  
  
-   これは状況によっては (たとえば SQL コンポーネントで) 必要となります。  
  
-   将来のバージョンの Windows では、検証可能なコンポーネントやアプリケーションが要求される傾向がますます強まります。  
  
 1 つの欠点は、C++ interop 機能を利用できないことです。 検証可能なアセンブリには、マネージ コードによって参照されていない場合でも、アンマネージ関数やネイティブ データ型を含むことはできません。  
  
 単語"safe"の使用に関係なくでアプリケーションをコンパイル**/clr:safe**とは限りませんバグはありません。 CLR が実行時にセキュリティ設定を確認することだけを意味します。  
  
 アセンブリの種類にかかわりなく、プラットフォーム呼び出しによるマネージ アセンブリからネイティブ DLL への呼び出しはコンパイルされますが、セキュリティ設定によっては実行時に失敗することがあります。  
  
> [!NOTE]
>  コンパイラは渡されますが確認不可能なアセンブリとなる 1 つのコーディング例があります。スコープ解決演算子を使用し、オブジェクト インスタンスを通じて仮想関数を呼び出す場合です。  たとえば、`MyObj -> A::VirtualFunction();` のように指定します。  
  
## <a name="see-also"></a>参照  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)