---
title: "-LTCG (リンク時コード生成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs: C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8f1abc58f0c36f37307e1d8053e4dd8a4cac06a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (リンク時のコード生成)
```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## <a name="remarks"></a>コメント  
 :INCREMENTAL (省略可能)  
 プロジェクト全体ではなく、編集によって影響を受けるファイルのセット全体プログラム最適化またはリンク時コード生成 (LTCG) をリンカーがのみ適用されることを指定します。 既定では、このフラグは、/LTCG が指定され、プロジェクト全体がプログラム全体の最適化を使用してリンクされている場合に設定されません。  
  
 : NOSTATUS &#124;です。: 状態 (省略可能)  
 リンカーが、リンクの何パーセントが完了を示す進行状況インジケーターを表示するかどうかを指定します。 既定では、この状態情報は表示されません。  
  
 : (省略可能) オフ  
 リンク時コード生成を無効にします。 この動作は、コマンドラインに/LTCG が指定されない場合と同じです。  
  
 ::PGINSTRUMENT (省略可能)  
 このオプションは推奨されません。 代わりに、 **/LTCG**と**/GENPROFILE**または**/FASTGENPROFILE**プロファイル ガイド付き最適化のためにインストルメントされたビルドを生成します。  
  
 インストルメントされた実行から収集されるデータは、最適化されたイメージの作成に使用されます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。 このオプションの短い形式は/LTCG:PGI です。  
  
 ::PGOPTIMIZE (省略可能)  
 このオプションは推奨されません。 代わりに、 **/LTCG**と**/USEPROFILE**最適化されたイメージを作成します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。 このオプションの短い形式は/LTCG:PGO です。  
  
 ::PGUPDATE (省略可能)  
 このオプションは推奨されません。 代わりに、 **/LTCG**と**/USEPROFILE**最適化されたイメージを作成します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。 このオプションの短い形式は/LTCG:PGU です。  
  
 /LTCG オプションは、コンパイラを呼び出すし、プログラム全体の最適化の実行をリンカーに指示します。 または、ガイド付きプロファイルの最適化を実行することもできます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。  
  
 次の例外を除き、PGO とを組み合わせた/LTCG/LTCG および/GENPROFILE オプションの前の PGO 初期化の組み合わせで指定されていない/USEPROFILE にリンカー オプションを追加することはできません。  
  
-   [/BASE](../../build/reference/base-base-address.md)  
  
-   [/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   /LTCG  
  
-   [/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [/OUT](../../build/reference/out-output-file-name.md)  
  
-   [/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 /GENPROFILE オプションにより、PGO を初期化するために、リンカー オプション、/LTCG と共に指定されているは/LTCG および/USEPROFILE; を使用してビルドするときに指定するのにはありません。それらは暗黙的に指定します。  
  
 このトピックの残りの部分では、リンク時コード生成の観点から/LTCG をについて説明します。  
  
 /LTCG を付けずに[/GL](../../build/reference/gl-whole-program-optimization.md)です。  
  
 使用してコンパイルされたモジュールに渡される場合、リンカーがリンク時コード生成を呼び出す**/GL**または MSIL モジュール (を参照してください[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md))。 明示的に指定しない場合**/LTCG**を渡す場合**/GL** MSIL モジュールをリンカー、最終的にリンカーはこれを検出しを使用して、リンクを再起動または**/LTCG**です。 明示的に指定**/LTCG**を渡す場合**/GL** MSIL モジュールをリンカーに最高のパフォーマンスをビルドするとします。  
  
 高速パフォーマンスを得るには、使用**/LTCG: インクリメンタル**です。 このオプションを指定すると、リンカーは、プロジェクト全体ではなく、ソース ファイルの変更によって影響を受ける一連のファイルのみを再び最適化します。 これにより、リンクに必要な時間を大幅に削減できます。 これはインクリメンタル リンクとして同じオプションではありません。  
  
 **/LTCG**で使用するためには不適切な[/incremental](../../build/reference/incremental-link-incrementally.md)です。  
  
 ときに**/LTCG**を使用してコンパイルされたモジュールをリンクするために使用[/Og](../../build/reference/og-global-optimizations.md)、 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、または[/Ox](../../build/reference/ox-full-optimization.md)では、次の最適化が実行されます。  
  
-   モジュール間のインライン展開  
  
-   関数を超えたレジスタの割り当て (64 ビット オペレーティング システムのみ)  
  
-   カスタム呼び出し規約 (x86 のみ)  
  
-   小さい TLS の変位 (x86 のみ)  
  
-   スタックの二重配置 (x86 のみ)  
  
-   強化されたメモリあいまいさを排除 (グローバル変数および入力パラメーターについてより詳細な干渉の情報)  
  
> [!NOTE]
>  リンカーは、各関数のコンパイルに使用する最適化を判断し、リンク時に同じ最適化機能を適用します。  
  
 使用して**/LTCG**と**/Ogt**二重配置の最適化が発生します。  
  
 場合**/LTCG**と**/Ogs**指定すると、二重配置は実行されません。 サイズにコンパイルされたいくつかの関数で、速度のほとんどのアプリケーションで関数がコンパイルされるかどうか (たとえばを使用して、[最適化](../../preprocessor/optimize.md)プラグマ)、コンパイラ倍揃えを呼び出す場合に、サイズの最適化された関数double 型のアラインメントを必要とする関数。  
  
 場合は、コンパイラは、すべての関数の呼び出しサイトを識別できます、コンパイラは関数に明示的な呼び出し規約の修飾子を無視し、関数の呼び出し規約を最適化しようとしています。  
  
-   レジスタにパラメーターを渡す  
  
-   配置のパラメーターの順序を変更します。  
  
-   未使用のパラメーターを削除します。  
  
 関数は、関数ポインターを通じて呼び出された場合、またはを使用してコンパイルされたモジュールの外部から関数を呼び出した場合**/GL**コンパイラが関数の呼び出し規約を最適化しません。  
  
> [!NOTE]
>  使用する場合**/LTCG** mainCRTStartup を再定義して、アプリケーションは、グローバル オブジェクトが初期化される前に実行されるユーザー コードに関連付けられている、予期しない動作を持つことができます。  この問題に対処する 3 つの方法があります。 mainCRTStartup を再定義しない、を使用して、mainCRTStartup を含むファイルをコンパイルしないで**/LTCG**、またはグローバル変数およびオブジェクトを静的に初期化します。  
  
## <a name="ltcg-and-msil-modules"></a>/LTCG モジュールと MSIL モジュール  
 [/GL](../../build/reference/gl-whole-program-optimization.md) と [/clr](../../build/reference/clr-common-language-runtime-compilation.md) を使用してコンパイルされたモジュールは、 **/LTCG** が指定されている場合にリンカーへの入力として使用できます。  
  
-   **/LTCG**ネイティブ オブジェクト ファイル、混合ネイティブ/マネージ オブジェクト ファイルを受け取ることができます (を使用してコンパイル**/clr**)、純粋オブジェクト ファイル (を使用してコンパイル**/clr: 純粋な**)、および安全なオブジェクト ファイル (使用してコンパイル**/clr:safe**)。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
-   **/LTCG**を使用して作成できますが、安全な .netmodule を受け入れることができる**/clr:safe/LN** Visual C でと**/target:module** .NET Visual Studio コンパイラでします。 **/clr** または **/clr:pure** を使用して生成した .netmodule は、 **/LTCG**で受け入れることができません。  
  
-   /LTCG:PGI は、 **/GL** や **/clr**を使用してコンパイルしたネイティブ モジュール、または純粋モジュール ( **/clr:pure**を使用して生成した) を受け付けません  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 参照してください[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[構成プロパティ]** フォルダーを選択します。  
  
3.  **[全般]** プロパティ ページをクリックします。  
  
4.  **[プログラム全体の最適化]** プロパティを変更します。  
  
 または、 **/LTCG** を特定のビルドに適用するために、メニュー バーで **[ビルド]**、 **[ガイド付き最適化のプロファイル]** を選択する、あるいは、プロジェクトのショートカット メニューから [ガイド付き最適化のプロファイル] のいずれかのオプションを選択するという方法もあります。  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)