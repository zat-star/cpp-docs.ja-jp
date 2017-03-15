---
title: "リンカ ツール エラー LNK2001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 3629075e5659cb89ab751b011f3ce2cbf89397cc
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2001"></a>リンカ ツール エラー LNK2001
未解決の外部シンボル"symbol"  
  
 コードは、ライブラリとオブジェクト ファイルでは、リンカーが見つからないもの (関数、変数、ラベルなど) を参照します。  
  
 このエラー メッセージの致命的なエラーが続く[LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)します。  
  
 **考えられる原因**  
  
-   マネージ ライブラリまたは web サービス プロジェクトを Visual C 2003 からアップグレードする場合、 **/Zl**コンパイラ オプションを追加する、**コマンドライン**プロパティ ページです。 これによって LNK2001 が発生します。  
  
     このエラーを解決するのには、msvcrt.lib および msvcmrt.lib をリンカーの追加の依存関係プロパティか追加します。 または、削除**/Zl**から、**コマンドライン**プロパティ ページです。 詳細については、次を参照してください。 [/Zl (既定のライブラリ名の省略)](../../build/reference/zl-omit-default-library-name.md)と[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)します。  
  
-   存在しないため、コードが要求する (シンボルのスペルが間違っているまたは正しくない場合を次に例を使用)。  
  
-   (使用する、ライブラリには、別のバージョンからの他のユーザーと、製品の&1; つのバージョンからいくつかの異なるバージョンが混在) 不正行為のコードが要求します。  
  
 **特定の原因**  
  
 **コーディングの問題**  
  
-   LNK2001 診断用のテキストが報告された場合`__check_commonlanguageruntime_version`は未解決の外部シンボルを参照してください[LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)を解決する方法の詳細。  
  
-   メンバー テンプレートの定義は、クラスの外側です。 Visual C でメンバー テンプレートの完全定義、外側のクラス内で制限があります。 LNK2001 とメンバーのテンプレートの詳細については、サポート技術情報記事 Q239436 を参照してください。  
  
-   大文字と小文字で、コードやモジュール定義 (.def) ファイル LNK2001 が発生することができます。 たとえば、変数の名前を付けた`var1`1 つの C++ のソース ファイルととしてにアクセスしようとしています。`VAR1`別のです。  
  
-   使用するプロジェクト[関数のインライン化](../../error-messages/tool-errors/function-inlining-problems.md)ファイル LNK2001 が原因で、ヘッダーではなく、まだ .cpp ファイルで、関数が定義されます。  
  
-   使用せず、C プログラムから C 関数を呼び出す`extern`"C"(これは、C 名前付け規則を使用するコンパイラで) LNK2001 が発生することができます。 コンパイラ オプション[/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)と[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラがファイル名拡張子に関係なく、C++ または C としてファイルをコンパイルします。 これらのオプションには、関数名が期待と異なる可能性があります。  
  
-   関数または外部リンケージを持たないデータを参照しようと、LNK2001 が発生することができます。 C++ では、インライン関数と`const`として明示的に指定しない限り、データが内部リンケージを持つ`extern`です。  
  
-   A[関数本体または変数がない](../../error-messages/tool-errors/missing-function-body-or-variable.md)LNK2001 が発生することができます。 関数プロトタイプでは単にまたは`extern`宣言、コンパイラはエラーを発生させずに続行できますが、関数のコードまたは予約された変数の領域がないために、リンカーが、アドレスへの呼び出しや変数への参照を解決できません。  
  
-   パラメーターの型と一致しない場合、関数宣言内で関数を呼び出すと、LNK2001 が発生することができます。 [名前の装飾](../../error-messages/tool-errors/name-decoration.md)関数のパラメーターでは、最終の装飾関数名に組み込みます。  
  
-   正しくにより、コンパイラは関数本体が指定されていないことを期待するプロトタイプのインクルードできるしないと、LNK2001。 関数のクラスとクラス以外の両方の実装があれば`F`C++ のスコープ解決ルールに注意してください。  
  
-   C++ を使用する場合は、クラス定義の関数のプロトタイプを含むとして失敗した[実装が含まれて](../../error-messages/tool-errors/missing-function-body-or-variable.md)そのクラスの関数のできます LNK2001 が発生します。  
  
-   コンス トラクターまたは抽象基本クラスのデストラクターから純粋仮想関数を呼び出そうとすると、LNK2001 可能性があります。 純粋仮想関数には、基本クラスの実装はありません。  
  
-   関数内で宣言された変数を使用しようとしています ([ローカル変数](../../error-messages/tool-errors/automatic-function-scope-variables.md)) の外部関数のスコープ LNK2001 が発生することができます。  
  
-   ATL プロジェクトのリリース バージョンを作成するときに、CRT スタートアップ コードが必要であることを示します。 修正を次のいずれかの操作  
  
    -   削除`_ATL_MIN_CRT`プリプロセッサの一覧から CRT スタートアップ コードが含まれるを許可するように定義します。 参照してください[全般構成設定のプロパティ ページ](../../ide/general-property-page-project.md)の詳細。  
  
    -   可能であれば、CRT スタートアップ コードを必要とする CRT 関数の呼び出しを削除します。 代わりに、対応する win32 関数を使用します。 たとえば、使用して`lstrcmp`の代わりに`strcmp`します。 CRT スタートアップ コードを必要とする既知の関数は、文字列および浮動小数点関数の一部を示します。  
  
 **コンパイルとリンクの問題**  
  
-   プロジェクトのライブラリへの参照がありません (します。LIB) またはオブジェクト (します。OBJ) ファイルです。 参照してください[リンカー入力としての .lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)の詳細。  
  
-   使用する場合[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)または[/Zl](../../build/reference/zl-omit-default-library-name.md)、明示的に含めていた場合を除き、必要なコードを含むライブラリは、プロジェクトにリンクされません。 (でコンパイルすると**/clr**または**/clr: 純粋な**、.cctor への参照が表示されます表示[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)の詳細。)。  
  
-   Unicode と MFC を使用している場合未解決の外部が表示されます`_WinMain@16`にエントリ ポイントを作成しない場合は`wWinMainCRTStartup`; を使用して、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)します。 参照してください[Unicode プログラミングの要約](../../text/unicode-programming-summary.md)します。  
  
     詳細については、MSDN ライブラリにある次のサポート技術情報の記事を参照してください。 MSDN ライブラリ をクリックして、**検索** タブで記事 番号または記事のタイトル テキスト ボックスに貼り付けますしてクリックして**トピックを一覧表示**します。 記事の番号で検索する場合は確認、**タイトルのみ検索**オプションはオフです。  
  
    -   Q125750"PRB: エラー LNK2001: '_WinMain@16': 未解決の外部シンボル"  
  
    -   Q131204"PRB: 間違ったプロジェクトの選択されの LNK2001 _WinMain@16"  
  
    -   Q100639"Unicode のサポートでは、Microsoft Foundation Class ライブラリ"  
  
    -   Q291952"PRB: リンク エラー LNK2001: 未解決の外部シンボル _main"  
  
-   LNK2001 ライブラリ LIBC.lib/MT でコンパイルされたコードをリンクと、 `_beginthread`、 `_beginthreadex`、 `_endthread`、および`_endthreadex`です。  
  
-   マルチ スレッド ライブラリを必要とするコードをリンク (MFC コードまたは指定してコンパイルされた[/MT](../../build/reference/md-mt-ld-use-run-time-library.md)) で LNK2001 が発生[_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md)、 `_beginthreadex`、 [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md)、および`_endthreadex`です。 詳細については、次のサポート技術情報記事を参照してください。  
  
    -   Q126646"PRB: エラー メッセージ: __beginthreadex に LNK2001 と\__endthreadex"  
  
    -   Q128641"INFO:/Mx コンパイラ オプションと LIBC、LIBCMT、MSVCRT Libs"  
  
    -   Q166504"PRB: MFC、CRT にデバッグ/リリースおよび静的/動的で一致する必要があります"  
  
-   コンパイルすると**/MD**、ソース内の"func"への参照の参照になります"`__imp__func`"すべてのランタイムが DLL 内で現在保持されているため、オブジェクトにします。 LIBC.lib、LIBCMT.lib または静的ライブラリとリンクしようとする場合 LNK2001 が表示されます`__imp__func`します。 /MD せずにコンパイルするときに、MSVCxx.lib にリンクしようとする場合は常に得られません LNK2001 が、その他の問題が高いでしょう。  
  
-   アプリケーションのデバッグ バージョンを作成するときに、リリース モードのライブラリとリンクと、LNK2001 が発生することができます。 同様を使用して、 **/Mxd**オプション (**/MTd**、または**/MDd**) の定義や`_DEBUG`リリース ライブラリとリンクが提供されます (その他の問題) 間の未解決の外部参照を潜在的なです。 リリース モードのデバッグ ライブラリと一緒にビルドをリンクすると、同様の問題によってもあります。  
  
-   Microsoft ライブラリとコンパイラの製品バージョンの混在は、問題となることができます。 新しいコンパイラ バージョンのライブラリには、以前のバージョンに含まれているライブラリ内にあることはできません新しい記号が含まれて可能性があります。 現在のバージョンを指すディレクトリ検索パス、または変更の順序を変更することがあります。  
  
     ツール |オプション |プロジェクト |Vc++ ディレクトリ ダイアログの ライブラリのファイルの選択 では、検索順序を変更することができます。 プロジェクトのプロパティ ページ ダイアログ ボックスで リンカー フォルダーは、期限切れの可能性があるパスも載っています。  
  
     この問題には、(おそらく、別の場所に) 新しい SDK がインストールされているし、新しい場所を指定する検索順序が更新されない場合があります。 通常、新しい Sdk にパスを記述する必要があります、および lib の Visual C の既定の場所の前にディレクトリ。 また、埋め込みパスを含むプロジェクトが指しているは有効ですが、別の場所にインストールされている新しいバージョンで追加された新機能の期限切れを古いパスにします。  
  
-   現在の標準はありません[C++ の名前付け](../../error-messages/tool-errors/name-decoration.md)コンパイラ販売元間またはコンパイラの異なるバージョン間でさえもです。 そのため、その他のコンパイラでコンパイルされたオブジェクト ファイルをリンク可能性があります、同じ名前付けスキームを作成されず、エラー LNK2001 が発生するためです。  
  
-   [コンパイル オプションのミキシングのインラインと非インライン](../../error-messages/tool-errors/function-inlining-problems.md)モジュールごとに異なることができます LNK2001 が発生します。 関数のインライン化がオンで、C++ のライブラリが作成されたかどうか (**/Ob1**または**/Ob2**)、対応するヘッダー ファイル、機能の説明にはインライン展開を無効になっているが、(ありません`inline`キーワード)、このエラーが表示されます。 この問題を防ぐためには、インライン関数定義で`inline`他のファイルに追加しようとして、ヘッダー ファイルにします。  
  
-   使用している場合、`#pragma inline_depth`コンパイラ ディレクティブは、確認がある場合、 [2 以上のセットの値](../../error-messages/tool-errors/function-inlining-problems.md)を使用しているかどうかを確認し、 [/Ob1](../../build/reference/ob-inline-function-expansion.md)または[/Ob2](../../build/reference/ob-inline-function-expansion.md)コンパイラ オプション。  
  
-   LINK オプションを省略するとリソースのみの DLL を作成するときに/NOENTRY によって LNK2001 が発生します。  
  
-   /SUBSYSTEM または/ENTRY 不適切な設定を使用すると、LNK2001 が発生することができます。 たとえば、文字ベースのアプリケーション (コンソール アプリケーション) を作成し、/SUBSYSTEM:WINDOWS を指定して、表示されます未解決の外部の`WinMain`です。 これらのオプションとエントリ ポイントの詳細については、次を参照してください。、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)と[/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
  
 **エクスポートの問題**  
  
-   32 ビットまたは 64 ビットに 16 からアプリケーションを移植するときに、LNK2001 が発生することができます。 現在のモジュール定義 (.def) ファイルの構文が必要とする`__cdecl`、 `__stdcall`、および`__fastcall`関数がアンダー スコア (装飾されていない) がない EXPORTS セクションに表示されます。 これに対し、16 ビットの構文をアンダー スコア (修飾された) で表示する必要があります。 詳細については、の説明を参照して、[エクスポート](../../build/reference/exports.md)モジュール定義ファイルのセクションです。  
  
-   .Def ファイルに含まれていて存在しない場合の任意のエクスポートには、LNK2001 が発生します。 考えられる原因が存在しない、スペルが間違っている、または、C++ の装飾名 (.def ファイルを取らない装飾名) を使用して  
  
 **出力の解釈**  
  
 シンボルを解決できない場合は、次のガイドラインに従って機能に関する情報を取得できます。  
  
 X86 プラットフォームでは、名前の呼び出し規約による装飾は、C では、コンパイルまたは C++ では、"C"の名前は、extern の。  
  
 `__cdecl`  
 関数には、アンダー スコア (_) プレフィックスを指定します。  
  
 `__stdcall`  
 関数は、アンダー スコア (_) プレフィックスとサフィックス dword 続けて @ スタックのパラメーターのサイズを配置します。  
  
 `__fastcall`  
 関数には、@ プレフィックスとサフィックス dword 続けて @ スタックのパラメーターのサイズを配置します。  
  
 Undname.exe を使用すると、装飾名の装飾されていない形式を取得できます。  
  
 上記の原因のいくつかの詳細については、次を参照してください。[名前装飾](../../error-messages/tool-errors/name-decoration.md)します。
