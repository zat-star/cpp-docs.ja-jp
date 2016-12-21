---
title: "アルファベット順のコンパイラ オプション | Microsoft Docs"
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
helpviewer_keywords: 
  - "コンパイラ オプション、C++"
ms.assetid: 98375dad-c9c6-4796-aaa6-fd573269d4ae
caps.latest.revision: 66
caps.handback.revision: 66
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# アルファベット順のコンパイラ オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の表は、コンパイラ オプションをアルファベット順の一覧にしたものです。 カテゴリ別の一覧については、「[カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)」を参照してください。  
  
|オプション|目的|  
|-----------|--------|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|応答ファイルを指定します。|  
|[\/?](../../build/reference/help-compiler-command-line-help.md)|コンパイラ オプションのリストを出力します。|  
|[\/AI](../../build/reference/ai-specify-metadata-directories.md)|[\#using](../../preprocessor/hash-using-directive-cpp.md) ディレクティブに渡されたファイル参照を解決するために検索するディレクトリを指定します。|  
|[\/analyze](../../build/reference/analyze-code-analysis.md)|コード分析を有効にします。|  
|[\/arch](../../build/reference/arch-minimum-cpu-architecture.md)|コード生成のアーキテクチャを指定します。|  
|[\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|.obj ファイル内のアドレス指定可能なセクションの数を増やします。|  
|[\/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|プリプロセス時にコメントを保持します。|  
|[\/c](../../build/reference/c-compile-without-linking.md)|リンクを行わないでコンパイルします。|  
|[\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|最適化およびコード生成に使用する cl.exe スレッド数を指定します。|  
|[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)|共通言語ランタイムで実行する出力ファイルを作成します。|  
|[\/D](../../build/reference/d-preprocessor-definitions.md)|定数とマクロを定義します。|  
|[\/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|ドキュメント コメントを XML ファイルに出力します。|  
|[\/E](../../build/reference/e-preprocess-to-stdout.md)|プリプロセッサ出力を標準出力にコピーします。|  
|[\/EH](../../build/reference/eh-exception-handling-model.md)|例外処理のモデルを指定します。|  
|[\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|プリプロセッサ出力を標準出力にコピーします。|  
|[\/errorReport](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md)|内部コンパイラ エラー \(ICE\) 情報を Visual C\+\+ チームに直接報告できます。|  
|[\/F](../../build/reference/f-set-stack-size.md)|スタック サイズを設定します。|  
|[\/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|特定の [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] アーキテクチャ、または AMD64 アーキテクチャおよび Extended Memory 64 Technology \(EM64T\) アーキテクチャの両方のマイクロアーキテクチャの仕様に合わせて最適化されるコードを作成します。|  
|[\/FA](../../build/reference/fa-fa-listing-file.md)|リスティング ファイルを作成します。|  
|[\/Fa](../../build/reference/fa-fa-listing-file.md)|リスティング ファイル名を設定します。|  
|[\/FC](../Topic/-FC%20\(Full%20Path%20of%20Source%20Code%20File%20in%20Diagnostics\).md)|診断テキストで cl.exe に渡されるソース コード ファイルの完全パスを表示します。|  
|[\/Fd](../../build/reference/fd-program-database-file-name.md)|プログラム データベース ファイルの名前を変更します。|  
|[\/Fe](../../build/reference/fe-name-exe-file.md)|実行可能ファイルの名前を変更します。|  
|[\/FI](../Topic/-FI%20\(Name%20Forced%20Include%20File\).md)|指定したインクルード ファイルをプリプロセスします。|  
|[\/Fi](../../build/reference/fi-preprocess-output-file-name.md)|プリプロセス済みの出力ファイル名を設定します。|  
|[\/Fm](../Topic/-Fm%20\(Name%20Mapfile\).md)|マップファイルを作成します。|  
|[\/Fo](../../build/reference/fo-object-file-name.md)|オブジェクト ファイルを作成します。|  
|[\/fp](../../build/reference/fp-specify-floating-point-behavior.md)|浮動小数点の動作を指定します。|  
|[\/Fp](../Topic/-Fp%20\(Name%20.Pch%20File\).md)|プリコンパイル済みヘッダー ファイルの名前を指定します。|  
|[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)<br /><br /> [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|ブラウザー ファイルを生成します。**\/Fr** は使用されなくなりました。|  
|[\/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|プログラム データベース \(PDB\) ファイルへの書き込みを MSPDBSRV.EXE によりシリアル化します。|  
|[\/FU](../../build/reference/fu-name-forced-hash-using-file.md)|[\#using](../../preprocessor/hash-using-directive-cpp.md) ディレクティブに渡された場合と同じ方法でファイル名の使用を強制します。|  
|[\/Fx](../../build/reference/fx-merge-injected-code.md)|挿入されたコードをソース ファイルとマージします。|  
|[\/GA](../../build/reference/ga-optimize-for-windows-application.md)|Windows アプリケーション用にコードを最適化します。|  
|[\/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|`__cdecl` 呼び出し規約を使用します \(x86 のみ\)。|  
|[\/Ge](../Topic/-Ge%20\(Enable%20Stack%20Probes\).md)|使用しないでください。 スタック プローブをアクティブにします。|  
|[\/GF](../Topic/-GF%20\(Eliminate%20Duplicate%20Strings\).md)|文字列プールを有効にします。|  
|[\/GH](../../build/reference/gh-enable-pexit-hook-function.md)|フック関数 `_pexit` を呼び出します。|  
|[\/Gh](../../build/reference/gh-enable-penter-hook-function.md)|フック関数 `_penter` を呼び出します。|  
|[\/GL](../../build/reference/gl-whole-program-optimization.md)|プログラム全体の最適化を有効にします。|  
|[\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|簡易リビルドを有効にします。|  
|[\/GR](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md)|ランタイム型情報 \(RTTI: Run\-Time Type Information\) を有効にします。|  
|[\/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|`__fastcall` 呼び出し規約を使用します \(x86 のみ\)。|  
|[\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md)|バッファーのセキュリティをチェックします。|  
|[\/Gs](../../build/reference/gs-control-stack-checking-calls.md)|スタック プローブを制御します。|  
|[\/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|静的スレッド ローカル ストレージを使用して割り当てられたデータに対して、ファイバー保護をサポートします。|  
|[\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|制御フロー ガードのセキュリティ チェックを追加します。|  
|[\/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|`__vectorcall` 呼び出し規約を使用します。 \(x86 と x64 のみ\)。|  
|[\/Gw](../../build/reference/gw-optimize-global-data.md)|プログラム全体のグローバル データの最適化を有効にします。|  
|[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)|使用しないでください。 同期例外処理を有効にします。 代わりに [\/EH](../../build/reference/eh-exception-handling-model.md) を使用してください。|  
|[\/Gy](../../build/reference/gy-enable-function-level-linking.md)|関数レベルのリンクを有効にします。|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|使用しないでください。[\/RTC1](../../build/reference/rtc-run-time-error-checks.md) と同じです。|  
|[\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|`__stdcall` 呼び出し規約を使用します \(x86 のみ\)。|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|使用しないでください。 外部名 \(パブリック名\) の長さを制限します。|  
|[\/HELP](../../build/reference/help-compiler-command-line-help.md)|コンパイラ オプションのリストを出力します。|  
|[\/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|関数の実行に入ったときに、レジスタで渡されたパラメーターを、強制的にスタック内のその場所に書き込みます。 これは、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンパイラ \(ネイティブ コンパイルおよびクロス コンパイル\) だけで使用されるコンパイラ オプションです。|  
|[\/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|ホットパッチ可能なイメージを作成します。|  
|[\/I](../../build/reference/i-additional-include-directories.md)|ディレクトリ内でインクルード ファイルを検索します。|  
|[\/J](../../build/reference/j-default-char-type-is-unsigned.md)|既定の `char` 型を変更します。|  
|[\/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|コンパイラとリンカーは、Windows カーネルで実行可能なバイナリを作成します。|  
|[\/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|ダイナミック リンク ライブラリを作成します。|  
|[\/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|デバッグ バージョンのダイナミック リンク ライブラリを作成します。|  
|[\/link](../Topic/-link%20\(Pass%20Options%20to%20Linker\).md)|指定したオプションを LINK に渡します。|  
|[\/LN](../../build/reference/ln-create-msil-module.md)|MSIL モジュールを作成します。|  
|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|MSVCRT.lib を使用して、マルチスレッド DLL を作成します。|  
|[\/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|MSVCRTD.lib を使用して、デバッグ バージョンのマルチスレッド DLL を作成します。|  
|[\/MP](../../build/reference/mp-build-with-multiple-processes.md)|複数のプロセスを使用して、複数のソース ファイルをコンパイルします。|  
|[\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|LIBCMT.lib を使用して、マルチスレッド実行可能ファイルを作成します。|  
|[\/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|LIBCMTD.lib を使用して、デバッグ バージョンのマルチスレッド実行可能ファイルを作成します。|  
|[\/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|著作権情報を表示しません。|  
|[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|コードを最小化します。|  
|[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|コードを最速化します。|  
|[\/Ob](../../build/reference/ob-inline-function-expansion.md)|関数のインライン展開を制御します。|  
|[\/Od](../../build/reference/od-disable-debug.md)|最適化を無効にします。|  
|[\/Og](../../build/reference/og-global-optimizations.md)|使用しないでください。 グローバル最適化を使用します。|  
|[\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)|組み込み関数を生成します。|  
|[\/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|ソース コードで [\#pragma omp](../../preprocessor/omp.md) を有効にします。|  
|[\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|実行可能ファイルで、サイズの小ささを優先させます。|  
|[\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|実行可能ファイルで、実行速度を優先させます。|  
|[\/Ox](../../build/reference/ox-full-optimization.md)|最大限の最適化 \(\/Ob2 ～ \/Gs\) を行います。|  
|[\/Oy](../../build/reference/oy-frame-pointer-omission.md)|フレーム ポインターを省略します \(x86 のみ\)。|  
|[\/P](../../build/reference/p-preprocess-to-a-file.md)|プリプロセッサ出力をファイルに書き込みます。|  
|[\/Qfast\_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|高速超越関数を生成します。|  
|[\/QIfist](../../build/reference/qifist-suppress-ftol.md)|使用しないでください。 浮動小数点型から整数型への変換が必要なときに、`_ftol` を呼び出しません \(x86 のみ\)。|  
|[\/Qimprecise\_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|`fwait` ブロックの中にある `try` コマンドを削除します。|  
|[\/Qpar \(自動並行化\)](../Topic/-Qpar%20\(Auto-Parallelizer\).md)|[\#pragma loop\(\)](../../preprocessor/loop.md) ディレクティブでマークされているループの自動並列化を有効にします。|  
|[\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md)|浮動小数点値の整数移動命令を使用し、特定の浮動小数点読み込み最適化を無効にします。|  
|[\/Qvec\-report \(自動ベクター化レポート作成レベル\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|自動ベクター化のレポート レベルを有効にします。|  
|[\/RTC](../../build/reference/rtc-run-time-error-checks.md)|ランタイム エラー チェックを有効にします。|  
|[\/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|追加のセキュリティ機能と警告を有効にします。|  
|[\/showIncludes](../Topic/-showIncludes%20\(List%20Include%20Files\).md)|コンパイル時にインクルード ファイルの一覧を表示します。|  
|[\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)<br /><br /> [\/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|C ソース ファイルを指定します。|  
|[\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)<br /><br /> [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|C\+\+ ソース ファイルを指定します。|  
|[\/U](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|1 つの定義済みマクロを削除します。|  
|[\/u](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|すべての定義済みマクロを削除します。|  
|[\/V](../../build/reference/v-version-number.md)|使用しないでください。 .obj ファイル バージョン文字列を設定します。|  
|[\/vd](../../build/reference/vd-disable-construction-displacements.md)|隠し vtordisp クラス メンバーの無効と有効を切り替えます。|  
|[\/vmb](../../build/reference/vmb-vmg-representation-method.md)|メンバーへのポインターに対して、最適なクラスを使用します。|  
|[\/vmg](../../build/reference/vmb-vmg-representation-method.md)|メンバーへのポインターに対して、ジェネリック クラスを使用します。|  
|[\/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|多重継承を宣言します。|  
|[\/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|単一継承を宣言します。|  
|[\/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|仮想継承を宣言します。|  
|[\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|volatile キーワードの解釈方法を選択します。|  
|[\/w](../../build/reference/compiler-option-warning-level.md)|すべての警告を無効にします。|  
|[\/W0、\/W1、\/W2、\/W3、\/W4](../../build/reference/compiler-option-warning-level.md)|出力する警告レベルを設定します。|  
|[\/w1、\/w2、\/w3、\/w4](../../build/reference/compiler-option-warning-level.md)|指定した警告の警告レベルを設定します。|  
|[\/Wall](../../build/reference/compiler-option-warning-level.md)|既定で無効にされた警告も含めてすべての警告を有効にします。|  
|[\/wd](../../build/reference/compiler-option-warning-level.md)|指定した警告を無効にします。|  
|[\/we](../../build/reference/compiler-option-warning-level.md)|指定した警告をエラーとして扱います。|  
|[\/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|コマンド ラインから C\+\+ ソース コードをコンパイルするときに、エラー メッセージと警告メッセージの 1 行診断を有効にします。|  
|[\/wo](../../build/reference/compiler-option-warning-level.md)|指定した警告を 1 回だけ表示します。|  
|[\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|互換性のために残されています。 64 ビット移植性の問題を検出します。|  
|[\/Wv](../../build/reference/compiler-option-warning-level.md)|指定したコンパイラ バージョンの後に、導入された警告は表示されません。|  
|[\/WX](../../build/reference/compiler-option-warning-level.md)|すべての警告をエラーとして扱います。|  
|[\/X](../../build/reference/x-ignore-standard-include-paths.md)|標準のインクルード ディレクトリを無視します。|  
|[\/Y\-](../Topic/-Y-%20\(Ignore%20Precompiled%20Header%20Options\).md)|現在のビルドで、他のすべてのプリコンパイル済みヘッダー コンパイラ オプションを無視します。|  
|[\/Yc](../../build/reference/yc-create-precompiled-header-file.md)|プリコンパイル済みヘッダー ファイルを作成します。|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|使用しないでください。 すべてのオブジェクト ファイルに、詳細なデバッグ情報を取り込みます。 代わりに [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) を使用してください。|  
|[\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|デバッグ ライブラリの作成時に PCH の参照を挿入します。|  
|[\/Yu](../../build/reference/yu-use-precompiled-header-file.md)|ビルド時にプリコンパイル済みヘッダー ファイルを使用します。|  
|[\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|C 7.0 互換のデバッグ情報を生成します。|  
|[\/Za](../../build/reference/za-ze-disable-language-extensions.md)|言語拡張機能を無効にします。|  
|[\/Zc](../../build/reference/zc-conformance.md)|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md) [\/Za、\/Ze \(言語拡張機能の無効化\)](../../build/reference/za-ze-disable-language-extensions.md)での標準動作を指定します。|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|使用しないでください。 言語拡張機能を有効にします。|  
|[\/Zg](../../build/reference/zg-generate-function-prototypes.md)|Visual C\+\+ 2015 では削除されています。 関数プロトタイプを生成します。|  
|[\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|エディット コンティニュと互換性のあるプログラム データベースにデバッグ情報を含めます。|  
|[\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|詳細なデバッグ情報を生成します。|  
|[\/Zl](../../build/reference/zl-omit-default-library-name.md)|.obj ファイルから既定のライブラリ名を削除します \(x86 のみ\)。|  
|[\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md)|プリコンパイル済みヘッダーのメモリ割り当て制限を指定します。|  
|[\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)|構造体メンバーをパックします。|  
|[\/Zs](../../build/reference/zs-syntax-check-only.md)|構文だけをチェックします。|  
|[\/ZW](../../build/reference/zw-windows-runtime-compilation.md)|[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行する出力ファイルを生成します。|  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)