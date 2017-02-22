---
title: "/LTCG (リンク時のコード生成) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LinkTimeCodeGeneration"
  - "VC.Project.VCConfiguration.WholeProgramOptimization"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
  - "/ltcg"
  - "VC.Project.VCCLCompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LTCG リンカー オプション"
  - "リンク時コード生成 (C++ リンカーの)"
  - "LTCG リンカー オプション"
  - "-LTCG リンカー オプション"
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# /LTCG (リンク時のコード生成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## 解説  
 :INCREMENTAL \(省略可能\)  
 プロジェクト全体ではなく、編集によって影響を受けたファイル セットにのみ、リンカーがプログラム全体の最適化またはリンク時のコード生成 \(LTCG\) を適用することを指定します。既定では、\/LTCG が指定されている場合にこのフラグは設定されません。つまり、プロジェクト全体がプログラム全体の最適化を使用してリンクされます。  
  
 :NOSTATUS &#124; STATUS \(省略可能\)  
 リンカーが、リンクの完了パーセントを示す進行状況のインジケーターを表示するかどうかを指定します。既定では、この状態情報は表示されません。  
  
 :OFF \(省略可能\)  
 リンク時のコード生成を無効にします。この動作は、コマンド ラインに \/LTCG を指定しない場合と同じです。  
  
 :PGINSTRUMENT \(省略可能\)  
 このオプションは推奨されなくなりました。ガイド付き最適化のプロファイルのためにインストルメントされたビルドを生成するには、代わりに、**\/LTCG** と **\/GENPROFILE** または **\/FASTGENPROFILE** を使用してください。  
  
 インストルメントされた実行から収集したデータは、最適化されたイメージを作成するために使用されます。詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。このオプションの短い形式は \/LTCG:PGI です。  
  
 :PGOPTIMIZE \(省略可能\)  
 このオプションは推奨されなくなりました。最適化されたイメージを作成するには、代わりに **\/LTCG** と **\/USEPROFILE** を使用してください。詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。このオプションの短い形式は \/LTCG:PGO です。  
  
 :PGUPDATE \(省略可能\)  
 このオプションは推奨されなくなりました。最適化されたイメージを作成するには、代わりに **\/LTCG** と **\/USEPROFILE** を使用してください。詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。このオプションの短い形式は \/LTCG:PGU です。  
  
 \/LTCG オプションは、コンパイラを呼び出してプログラム全体の最適化を実行するようにリンカーに指示します。または、ガイド付きプロファイルの最適化を実行することもできます。詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。  
  
 \/LTCG オプションと \/GENPROFILE オプションを組み合わせた前回の PGO 初期化で指定しなかったリンカー オプションを \/LTCG と \/USEPROFILE の組み合わせに対して追加することはできません。ただし、次に挙げるオプションは例外です。  
  
-   [\/BASE](../../build/reference/base-base-address.md)  
  
-   [\/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   \/LTCG  
  
-   [\/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [\/OUT](../../build/reference/out-output-file-name.md)  
  
-   [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [\/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 \/LTCG オプションおよび \/GENPROFILE オプションと一緒に指定した PGO を初期化するリンカー オプションは、\/LTCG および \/USEPROFILE を使用してビルドするときに指定する必要はありません。それらのオプションは暗黙的に指定されます。  
  
 このトピックの残りの部分では、リンク時のコード生成の観点から \/LTCG について説明します。  
  
 \/LTCG を指定すると、暗黙的に [\/GL](../../build/reference/gl-whole-program-optimization.md) も指定されます。  
  
 **\/GL** を使用してコンパイルされたモジュール、または MSIL モジュールをリンカーに渡すと、リンカーはリンク時コード生成を呼び出します \(「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」を参照してください\)。明示的に **\/LTCG** を指定せずに **\/GL** モジュールまたは MSIL モジュールをリンカーに渡すと、最終的にリンカーはこれを検出し、**\/LTCG** を使用してリンクを再実行します。明示的に **\/LTCG** を指定した上で **\/GL** モジュールや MSIL モジュールをリンカーに渡すと、可能な最大限のパフォーマンスでビルドが実行されます。  
  
 パフォーマンスをさらに高速にするには、**\/LTCG:INCREMENTAL** を使用します。このオプションを指定すると、リンカーは、プロジェクト全体ではなく、ソース ファイルの変更によって影響を受ける一連のファイルのみを再び最適化します。これにより、リンクに必要な時間を大幅に削減できます。これは、インクリメンタル リンクと同じオプションではありません。  
  
 **\/LTCG** を [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) と一緒に指定することはできません。  
  
 [\/Og](../../build/reference/og-global-optimizations.md)、[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、または [\/Ox](../../build/reference/ox-full-optimization.md) を使用してコンパイルしたモジュールをリンクするために **\/LTCG** を使用すると、次に示す最適化が実行されます。  
  
-   モジュールをまたいだインライン展開  
  
-   プロシージャを越えたレジストリの割り当て \(64 ビット オペレーティング システムのみ\)  
  
-   カスタム呼び出し規則 \(x86 のみ\)  
  
-   小さい TLS 変位 \(x86 のみ\)  
  
-   スタックの二重配置 \(x86 のみ\)  
  
-   メモリの一義化 \(グローバル変数および入力パラメーターの干渉情報\) の改善  
  
> [!NOTE]
>  リンカーは、コンパイル時に関数ごとにどの最適化が使用されたかを検出し、リンク時に同じ最適化を適用します。  
  
 **\/LTCG** と **\/Ogt** を使用すると、二重配置の最適化が適用されます。  
  
 **\/LTCG** と **\/Ogs** を指定すると、二重配置は実行されません。アプリケーションで大部分の関数を速度優先でコンパイルし、サイズ優先でコンパイルする関数はごく少数であるとすると \(たとえば、[optimize](../../preprocessor/optimize.md) プラグマを使用する\)、サイズ優先で最適化された関数が二重配置される必要のある関数を呼び出す場合、コンパイラはサイズ優先で最適化された関数を二重配置します。  
  
 コンパイラが関数のすべての呼び出しサイトを識別できる場合、コンパイラは、関数に対する明示的な呼び出し規則修飾子を無視し、次に示す方法で関数の呼び出し規則を最適化しようとします。  
  
-   パラメーターをレジスタに入れて渡す  
  
-   アラインメント優先でパラメーターの順序を変更する  
  
-   未使用のパラメーターを削除する  
  
 関数が関数ポインターを介して呼び出されている場合、または **\/GL** を使用してコンパイルされたモジュールの外側から関数が呼び出されている場合は、コンパイラは関数の呼び出し規則を最適化しようとしません。  
  
> [!NOTE]
>  **\/LTCG** を使用して mainCRTStartup を再定義する場合、アプリケーションには、グローバル オブジェクトの初期化前に実行されるユーザー コードに関連して予測不可能な動作が存在することがあります。この問題に対処するには次の 3 つの方法があります。mainCRTStartup を再定義しないこと、mainCRTStartup が含まれているファイルを **\/LTCG** を使用してコンパイルしないこと、グローバル変数とグローバル オブジェクトは静的に初期化すること。  
  
## \/LTCG モジュールと MSIL モジュール  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) と [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を使用してコンパイルされたモジュールは、**\/LTCG** が指定されている場合にリンカーへの入力として使用できます。  
  
-   **\/LTCG** は、ネイティブ オブジェクト ファイル、ネイティブ\/マネージが混合しているオブジェクト ファイル \(**\/clr** を使用してコンパイルしたもの\)、純粋オブジェクト ファイル \(**\/clr:pure** を使用してコンパイルしたもの\)、安全なオブジェクト ファイル \(**\/clr:safe** を使用してコンパイルしたもの\) を受け入れることができます  
  
-   **\/LTCG** は、安全な .netmodule を受け入れることができます。これは、Visual C\+\+ で **\/clr:safe \/LN** を使用して作成したもの、またはその他の Visual Studio コンパイラで **\/target:module** を指定して作成できます。**\/clr** または **\/clr:pure** を使用して生成した .netmodule は、**\/LTCG** で受け入れることができません。  
  
-   \/LTCG:PGI は、**\/GL** や **\/clr** を使用してコンパイルしたネイティブ モジュール、または純粋モジュール \(**\/clr:pure** を使用して生成した\) を受け付けません  
  
#### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** フォルダーを選択します。  
  
3.  **\[全般\]** プロパティ ページをクリックします。  
  
4.  **\[プログラム全体の最適化\]** プロパティを変更します。  
  
 または、**\/LTCG** を特定のビルドに適用するために、メニュー バーで **\[ビルド\]**、**\[ガイド付き最適化のプロファイル\]** を選択する、あるいは、プロジェクトのショートカット メニューから \[ガイド付き最適化のプロファイル\] のいずれかのオプションを選択するという方法もあります。  
  
#### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)