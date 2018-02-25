---
title: "-Z7、-zi、ZI (デバッグ情報の形式) |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs:
- C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6e3de89c5336cda98960b67b80932df8f67d183
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7、/Zi、/ZI (デバッグ情報の形式)

オブジェクト ファイルまたはプログラム データベース (PDB) ファイルにこの情報を保持するかどうか、プログラム用に作成されたデバッグ情報の種類を指定します。

## <a name="syntax"></a>構文

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>コメント

デバッグ情報の形式オプションは、次のセクションで説明します。  
  
### <a name="none"></a>なし

既定では、デバッグ情報の形式のオプションが指定されていない場合、コンパイラありませんデバッグ情報を生成、コンパイルが高速なためです。  
  
### <a name="z7"></a>/Z7

**/Z7**生成のオプション、*オブジェクト ファイル*デバッガーでは、使用するための詳細なシンボリック デバッグ情報を含む .obj 拡張子を持つファイルです。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。 いいえ*PDB ファイル*、.pdb 拡張子が付いたファイルが生成されます。

サードパーティ製のライブラリのディストリビューターの場合、PDB ファイルを持たないことによる利点があります。 ただし、プリコンパイル済みヘッダーのオブジェクト ファイルは、リンク フェーズおよびデバッグするために必要です。 がある場合のみ .pch オブジェクト ファイルに情報 (およびコードなし) を入力する必要がありますを使用するも、 [/Yl (挿入 PCH 参照デバッグ ライブラリの)](../../build/reference/yl-inject-pch-reference-for-debug-library.md)オプションは、既定で有効にします。

### <a name="zi"></a>/ZI

**/Zi**オプションは、型情報と、デバッガーで使用するためのシンボリック デバッグ情報を含む PDB ファイルを生成します。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。

使用**/Zi**の最適化には影響しません。 ただし、 **/Zi**わけでは**/debug**; を参照してください[/DEBUG (デバッグ情報の生成)](../../build/reference/debug-generate-debug-info.md)詳細についてはします。

ときに**/Zi**が指定されている PDB ファイルとオブジェクト ファイルではなく、型情報を配置します。

使用することができます[/Gm (簡易リビルドの有効)](../../build/reference/gm-enable-minimal-rebuild.md)と共に**/Zi**が**/gm 化**場合は使用できません**/Z7**を指定します。

両方を指定すると**/Zi**と**/clr**、<xref:System.Diagnostics.DebuggableAttribute>属性がアセンブリのメタデータに保存されていません。 場合は、ソース コードで指定する必要があります。 この属性は、アプリケーションの実行時パフォーマンスに影響します。 方法の詳細については**Debuggable**属性がパフォーマンスに影響し、パフォーマンスに与える影響を変更する方法を参照してください[デバッグするイメージの簡略化を行う](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)です。

### <a name="zi"></a>/ZI

**/ZI**オプションをサポートする形式に PDB ファイルを生成する、[エディット コンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp)機能します。 エディット コンティニュのデバッグを使用する場合は、必ずこのオプションを使用してください。 エディット コンティニュ機能は開発者の生産性、便利ですが、コンパイラ準拠、コードのサイズとパフォーマンスの問題が発生することができます。 ほとんどの最適化にエディット コンティニュと互換性がないために使用**/ZI**も無効になります`#pragma optimize`コードのステートメント。 **/ZI**オプションも互換性がありませんを使用した、 [&#95; &#95;です。行 &#95; #95定義済みマクロ](../../preprocessor/predefined-macros.md)です。 コードでコンパイルされた**/ZI**は使用できません**&#95; &#95;です。行 &#95; #95**非型テンプレート引数としてが**&#95; &#95;です。行 &#95; #95**マクロの展開で使用できます。

**/ZI**オプションを指定する両方、 [/Gy (関数レベルのリンクを有効にする)](../../build/reference/gy-enable-function-level-linking.md)と[/FC (完全パスのソース コード ファイルで診断)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)コンパイル時に使用するオプションです。

**/ZI**と互換性がありません[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。

> [!NOTE]
> **/ZI**オプションは、x86 および x64 プロセッサを対象とすると、コンパイラで使用できるのみです。 このコンパイラ オプションは ARM プロセッサを対象とするコンパイラでは使用されません。

PDB ファイルの名前、コンパイラ*プロジェクト*.pdb です。 プロジェクトの外側でファイルをコンパイルする場合、コンパイラが VC をという名前の PDB ファイルを作成*x*0. pdb、場所*x*使用中で Visual Studio のバージョンのメジャー バージョン番号です。 このオプションを指定して生成した各 .obj ファイルには、PDB の名前が埋め込まれ、シンボル情報と行番号情報の場所がデバッガーに通知されます。 このオプションを使用する場合、.obj ファイルの値が .obj ファイル内ではなく .pdb ファイルにデバッグ情報が格納されているため、小さい。

このオプションを使って生成したオブジェクトからライブラリを作成する場合は、ライブラリをプログラムにリンクするときに該当する .pdb ファイルが必要になります。 したがって、ライブラリを配布する場合は、その PDB も併せて配布する必要があります。

.Pdb ファイルを使用せずにデバッグ情報を含むライブラリを作成するには、コンパイラの C 7.0 互換を選択する必要があります (**/Z7**) オプション。 プリコンパイル済みヘッダー オプションを使用する場合、PDB ファイルには、プリコンパイル済みヘッダーと、ソース コードの残りの部分の両方のデバッグ情報が配置されます。 **/Yd への取り込み**プログラム データベース オプションを指定するオプションは無視されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 開く、**構成プロパティ** > **C/C++** > **全般**プロパティ ページ。

1. 変更、**デバッグ情報の形式**プロパティです。 選択**OK**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  

