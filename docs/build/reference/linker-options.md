---
title: "リンカー オプション | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ライブラリ [C++], リンク (COFF に)"
  - "LINK ツール [C++], リンカー オプション"
  - "リンカー [C++]"
  - "リンカー [C++], オプション一覧"
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
caps.latest.revision: 37
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# リンカー オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK.exe は、COFF \(Common Object File Format\) オブジェクト ファイルとライブラリをリンクし、実行可能ファイル \(.exe\) やダイナミック リンク ライブラリ \(DLL: Dynamic\-Link Library\) を生成します。  
  
 LINK.exe のオプションの一覧を次の表に示します。 LINK の詳細については、下記を参照してください。  
  
-   [コンパイラで制御される LINK オプション](../../build/reference/compiler-controlled-link-options.md)  
  
-   [LINK の入力ファイル](../../build/reference/link-input-files.md)  
  
-   [LINK からの出力](../../build/reference/link-output.md)  
  
-   [予約語](../../build/reference/reserved-words.md)  
  
 コマンド ラインでは、リンカー オプションの大文字と小文字は区別されません。たとえば、\/base と \/BASE は、同じ指定を意味します。 コマンド ラインまたは Visual Studio で各オプションを指定する方法の詳細については、そのオプションのドキュメントを参照してください。  
  
 [comment](../../preprocessor/comment-c-cpp.md) プラグマを使用して、一部のリンカー オプションを指定できます。  
  
|オプション|目的|  
|-----------|--------|  
|[@](../../build/reference/at-specify-a-linker-response-file.md)|応答ファイルを指定します。|  
|[\/ALIGN](../../build/reference/align-section-alignment.md)|各セクションのアラインメントを指定します。|  
|[\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|DLL をバインディングできないことを指定します。|  
|[\/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|マニフェスト検索の動作を指定します。|  
|[\/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|アプリケーションが appcontainer プロセス環境内で実行される必要があるかどうかを指定します。|  
|[\/ASSEMBLYDEBUG](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)|<xref:System.Diagnostics.DebuggableAttribute> をマネージ イメージに追加します。|  
|[\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|マネージ リソースへのリンクを作成します。|  
|[\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|MSIL \(Microsoft Intermediate Language\) モジュールをアセンブリにインポートする必要があることを指定します。|  
|[\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|マネージ リソース ファイルをアセンブリに埋め込みます。|  
|[\/BASE](../../build/reference/base-base-address.md)|プログラムのベース アドレスを設定します。|  
|[\/CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|リンク時のコード生成を指定するときに、最適化およびコード生成に使用する cl.exe スレッド数を設定します。|  
|[\/CLRIMAGETYPE](../Topic/-CLRIMAGETYPE%20\(Specify%20Type%20of%20CLR%20Image\).md)|CLR イメージの種類 \(IJW、純粋、または安全\) を設定します。|  
|[\/CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P\/Invoke 機構を通じて呼び出された関数の最終エラー コードを保持します。|  
|[\/CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|CLR プログラムのエントリ ポイントに適用するスレッド処理属性を指定します。|  
|[\/CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute.md)|マネージ コードからネイティブ DLL への呼び出しを行う、リンカーによって生成された PInvoke スタブに、SuppressUnmanagedCodeSecurity 属性を適用するかどうかを指定します。|  
|[\/DEBUG](../../build/reference/debug-generate-debug-info.md)|デバッグ情報を作成します。|  
|[\/DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|デバッグ情報に含めるデータを指定します。|  
|[\/DEF](../../build/reference/def-specify-module-definition-file.md)|モジュール定義 \(.def\) ファイルをリンカーに渡します。|  
|[\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|外部参照を解決するときに、指定したライブラリを検索します。|  
|[\/DELAY](../../build/reference/delay-delay-load-import-settings.md)|DLL の遅延読み込みを制御します。|  
|[\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|指定した DLL に遅延読み込みを発生させます。|  
|[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|アセンブリに部分署名します。|  
|[\/DLL](../../build/reference/dll-build-a-dll.md)|DLL をビルドします。|  
|[\/DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|カーネル モード ドライバーを作成します。|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|ASLR \(Address Space Layout Randomization\) 機能を使用してロード時にランダムに再ベースできる実行可能イメージを生成するかどうかを指定します。|  
|[\/ENTRY](../../build/reference/entry-entry-point-symbol.md)|開始アドレスを設定します。|  
|[\/errorReport](../Topic/-ERRORREPORT%20\(Report%20Internal%20Linker%20Errors\).md)|内部リンカー エラーを Microsoft に報告します。|  
|[\/EXPORT](../../build/reference/export-exports-a-function.md)|関数をエクスポートします。|  
|[\/FIXED](../../build/reference/fixed-fixed-base-address.md)|指定のベース アドレスだけに読み込まれるプログラムを作成します。|  
|[\/FORCE](../../build/reference/force-force-file-output.md)|未解決のシンボルまたは複数定義のシンボルがある場合でも、リンクを強制的に終了します。|  
|[\/FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|ホット パッチ可能なイメージを作成します。|  
|[\/GENPROFILE、\/FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|これらのオプションは、ガイド付き最適化のプロファイル \(PGO\) をサポートするために、どちらもリンカーによる .pgd ファイルの生成を指定します。 \/GENPROFILE と \/FASTGENPROFILE は、それぞれに異なる既定のパラメーターを使用します。|  
|[\/GUARD](../../build/reference/guard-enable-guard-checks.md)|制御フロー ガードによる保護を有効にします。|  
|[\/HEAP](../../build/reference/heap-set-heap-size.md)|ヒープ サイズをバイト単位で設定します。|  
|[\/HIGHENTROPYVA](../Topic/-HIGHENTROPYVA%20\(Support%2064-Bit%20ASLR\).md)|高エントロピの 64 ビット ASLR \(Address Space Layout Randomization\) のサポートを指定します。|  
|[\/IDLOUT](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)|.idl ファイル名およびその他の MIDL の出力ファイル名を指定します。|  
|[\/IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|指定されたリンカー警告の出力を抑制します。|  
|[\/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|.idl ファイル内に属性情報を挿入しません。|  
|[\/IMPLIB](../Topic/-IMPLIB%20\(Name%20Import%20Library\).md)|既定のインポート ライブラリ名をオーバーライドします。|  
|[\/INCLUDE](../../build/reference/include-force-symbol-references.md)|シンボルを明示的に参照します。|  
|[\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|インクリメンタル リンクの処理方法を制御します。|  
|[\/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|モジュールが読み込み時に署名の確認を要求することを指定します。|  
|[\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|アセンブリに署名するためのキー コンテナーを指定します。|  
|[\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|アセンブリに署名するキーまたはキー ペアを指定します。|  
|[\/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|アプリケーションが 2 GB を超えるアドレスをサポートしていることをコンパイラに指定します。|  
|[\/LIBPATH](../../build/reference/libpath-additional-libpath.md)|環境ライブラリ パスの前に検索するパスを指定します。|  
|[\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|リンク時のコード生成を指定します。|  
|[\/MACHINE](../../build/reference/machine-specify-target-platform.md)|ターゲット プラットフォームを指定します。|  
|[\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|side\-by\-side マニフェスト ファイルを作成し、バイナリに埋め込むことができるようにします。|  
|[\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|マニフェスト ファイルの \<dependentAssembly\> セクションを指定します。|  
|[\/MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|マニフェスト ファイルの既定の名前を変更します。|  
|[\/MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|リンカーが処理を行い、バイナリに埋め込むための、マニフェスト入力ファイルを指定します。 このオプションを複数回使用して、複数のマニフェストの入力ファイルを指定できます。|  
|[\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|ユーザー アカウント制御 \(UAC\) 情報をプログラム マニフェストに組み込むかどうかを指定します。|  
|[\/MAP](../../build/reference/map-generate-mapfile.md)|マップファイルを作成します。|  
|[\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|指定した情報をマップ ファイルに格納します。|  
|[\/MERGE](../../build/reference/merge-combine-sections.md)|セクションを結合します。|  
|[\/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|MIDL コマンド ライン オプションを指定します。|  
|[\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|.NET Framework アセンブリを作成しません。|  
|[\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|外部参照を解決するときに、すべてのまたは指定した既定のライブラリを無視します。|  
|[\/NOENTRY](../../build/reference/noentry-no-entry-point.md)|リソースだけの DLL を作成します。|  
|[\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|開始メッセージを表示しません。|  
|[\/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Windows データ実行防止機能との互換性が確認済みとして実行可能ファイルをマークします。|  
|[\/OPT](../../build/reference/opt-optimizations.md)|LINK の最適化を制御します。|  
|[\/ORDER](../../build/reference/order-put-functions-in-order.md)|指定された順序で COMDAT をイメージに取り込みます。|  
|[\/OUT](../../build/reference/out-output-file-name.md)|出力ファイル名を指定します。|  
|[\/PDB](../../build/reference/pdb-use-program-database.md)|プログラム データベース \(PDB\) ファイルを作成します。|  
|[\/PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|別の場所を使用して PDB ファイルを保存します。|  
|[\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|プログラム データベース \(PDB\) ファイルの作成時にプライベート シンボルを含めません。|  
|[\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|ガイド付き最適化のプロファイル用の .pgd ファイルを指定します。|  
|[\/PROFILE](../../build/reference/profile-performance-tools-profiler.md)|パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。|  
|[\/RELEASE](../../build/reference/release-set-the-checksum.md)|.exe ヘッダーにチェックサムを設定します。|  
|[\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md)|安全な例外ハンドラーのテーブルがイメージに含まれるように指定します。|  
|[\/SECTION](../../build/reference/section-specify-section-attributes.md)|セクションの属性をオーバーライドします。|  
|[\/STACK](../../build/reference/stack-stack-allocations.md)|スタック サイズをバイト単位で設定します。|  
|[\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|MS\-DOS スタブ プログラムを Win32 プログラムにアタッチします。|  
|[\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|オペレーティング システムに対して、.exe ファイルの実行方法を指定します。|  
|[\/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|リンカー出力をスワップ ファイルにコピーしてから実行します。|  
|[\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|リンカーによって生成されたタイプ ライブラリのリソース ID を指定します。|  
|[\/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|.tlb ファイル名およびその他の MIDL の出力ファイル名を指定します。|  
|[\/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|ターミナル サーバーでの実行専用のアプリケーションを作成します。|  
|[\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)|リンカーの進行状況メッセージを出力します。|  
|[\/VERSION](../Topic/-VERSION%20\(Version%20Information\).md)|バージョン番号を割り当てます。|  
|[\/WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Windows ランタイム メタデータ ファイルの生成を有効にします。|  
|[\/WINMDFILE](../Topic/-WINMDFILE%20\(Specify%20winmd%20File\).md)|[\/WINMD](../../build/reference/winmd-generate-windows-metadata.md) のリンカー オプションによって生成される Windows のランタイム メタデータ \(winmd\) の出力ファイルの名前を指定します。|  
|[\/WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Windows ランタイム メタデータに署名するキーまたはキー ペアを指定します。|  
|[\/WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Windows メタデータ ファイルに署名するキー コンテナーを指定します。|  
|[\/WINMDDELAYSIGN](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|winmd ファイルに公開キーを設定して、Windows のランタイム メタデータ \(.winmd\) ファイルに部分的に署名します。|  
|[\/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|リンカー警告をエラーとして扱います。|  
  
 詳細については、「[コンパイラで制御される LINK オプション](../../build/reference/compiler-controlled-link-options.md)」を参照してください。  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [ビルドに関してよく寄せられる質問](http://msdn.microsoft.com/ja-jp/56a3bb8f-0181-4989-bab4-a07ba950ab08)