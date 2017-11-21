---
title: "Visual Studio での Visual C++ の新機能 | Microsoft Docs"
ms.custom: 
ms.date: 8/2/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: b90891be2ca726bb6cdd28d024cda68494e69af4
ms.openlocfilehash: 9103da7fb4e10553d2558b15a24bc6a894dd1eff
ms.contentlocale: ja-jp
ms.lasthandoff: 08/15/2017

---

# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] での Visual C++ の新機能

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] には、Visual C++ 環境に対する多くの更新プログラムと修正プログラムが導入されています。 250 以上のバグを修正し、コンパイラおよびツールの問題をレポートしてきました。その多くは [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect") を通じてお客様から寄せられたものです。 バグ レポートをお寄せいただきありがとうございました。  Visual Studio 全体の新機能の詳細については、「[[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] の新機能](https://go.microsoft.com/fwlink/?linkid=834481)」を参照してください。

<!--The compiler and tools version number in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] is 14.10.24629. -->


## <a name="c-compiler"></a>C++ コンパイラ

### <a name="c-conformance-improvements"></a>C++ 準拠の強化
このリリースでは、C++ コンパイラと標準ライブラリを更新して C++11 と C++14 機能のサポートを強化し、C++17 標準に組み込まれると予想される特定の機能について予備的なサポートを追加しました。 詳しくは、「[C++ Conformance Improvements in Visual Studio 2017](cpp-conformance-improvements-2017.md)」(Visual Studio 2017 での C++ 準拠の強化) をご覧ください。

### <a name="new-compiler-switches"></a>新しいコンパイラ スイッチ  

 -**/std:c++14** と **/std:c++latest**: これらのコンパイラ スイッチを使うと、プロジェクトで ISO C++ プログラミング言語の特定のバージョンにオプトインできます。 詳細については、「[-std (言語標準バージョンの指定)](build/reference/std-specify-language-standard-version.md)」をご覧ください。 ほとんどの新しいドラフト標準機能は、/std:c++latest スイッチによって保護されています。 

**Visual Studio 2017 バージョン 15.3**: **/std:c++17** オプションを使用すると、Visual C++ コンパイラによって実装された C++17 機能セットが有効になります。 このオプションによって、C++ 標準のワーキング ドラフトと不具合の更新の最新バージョンで変更または更新された機能に対するコンパイラと標準ライブラリのサポートが無効になります。

-[/permissive-](build/reference/permissive-standards-conformance.md): すべての厳密な標準準拠コンパイラ オプションを有効にして、ほとんどの Microsoft 固有コンパイラ拡張機能 (ただし、たとえば __declspec(dllimport) は除きます) を無効にします (現在は既定でオフですが、将来のある時点において既定でオンになります)。

-[/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): 診断エラーまたは警告が検出された場所の、行番号、行番号と列、または行番号、列、コード行の下のカレットを表示できるようにします。

-[/debug:fastlink](build/reference/debug-generate-debug-info.md):  
すべてのデバッグ情報を PDB ファイルにコピーしないことで、インクリメンタル リンク時間を最大で 30% 高速化します (Visual Studio 2015 と比較した場合)。 代わりに、PDB ファイルは実行可能ファイルの作成に使われたオブジェクトとライブラリ ファイルのデバッグ情報を参照します。 「[Faster C++ build cycle in VS “15” with /Debug:fastlink](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/)」 (VS "15" での /Debug:fastlink による C++ ビルド サイクルの高速化) および「[Recommendations to speed C++ builds in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/)」(Visual Studio で C++ のビルドを高速化するための推奨事項) をご覧ください。

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] では、/sdl を /await と一緒に使うことができます。 コルーチンでの /RTC の制限がなくなりました。 

### <a name="codegen-security-diagnostics-and-versioning"></a>コード生成、セキュリティ、診断、バージョン管理
このリリースでは、最適化、コード生成、ツールセットのバージョン管理、診断に関して、いくつかの機能強化が行われています。 主な改良点は次のとおりです。  

- ループのコード生成の向上: 定数整数の除算の自動ベクター化がサポートされるようになりました。また、memset パターンの識別機能が向上しています。
- コード セキュリティの向上: バッファー オーバーラン コンパイラ診断の出力が向上し、/guard:cf によりジャンプ テーブルを生成する switch ステートメントが保護されるようになりました。
- バージョン管理: 組み込みプリプロセッサ マクロ _MSC_VER の値が、Visual C++ ツールセットの更新のたびに単調に更新されるようになりました。 詳しくは、「[Visual C++ Compiler Version](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/)」(Visual C++ コンパイラのバージョン) をご覧ください。
- 新しいツールセット レイアウト: 開発用コンピューターでのコンパイラおよび関連するビルド ツールの場所とディレクトリ構造が新しくなりました。 新しいレイアウトでは、複数のバージョンのコンパイラのサイド バイ サイド インストールが可能です。 詳細については、「[Compiler Tools Layout in Visual Studio "15" (Visual Studio "15" でのコンパイラ ツール レイアウト) ](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/)」をご覧ください。
- 診断の強化: 出力ウィンドウにエラーが発生した列が表示されるようになりました。 詳細については、「[C++ compiler diagnostics improvements in VS "15" Preview 5 (VS "15" Preview 5 での C++ コンパイラの診断の機能強化)](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/)」をご覧ください。
- コルーチンを使用する場合、試験的キーワード "yield" (/await スイッチによって使用可能) は削除されています。 代わりにコードを書き直し、`co_yield` を使用する必要があります。 詳細については、「[Visual C++ チーム ブログ](https://blogs.msdn.microsoft.com/vcblog/)」を参照してください。 

**Visual Studio 2017 バージョン 15.3**: コンパイラでの診断の機能をさらに強化。 詳細については、「[Diagnostic Improvements in Visual Studio 2017 15.3.0 (Visual Studio 2017 15.3.0 での診断機能の強化)](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/)」をご覧ください。

## <a name="c-libraries"></a>C++ ライブラリ

### <a name="standard-library-improvements"></a>標準ライブラリの機能強化:

* basic_string_ITERATOR_DEBUG_LEVEL!= 0 の診断は若干改良されました。 文字列構造の IDL チェックが失敗すると、その失敗の原因となった特定の動作が報告されるようになりました。 たとえば、"string iterator not dereferencable (文字列反復子を逆参照できません)" の代わりに、"cannot dereference string iterator because it is out of range (e.g. an end iterator) (範囲外のため文字列反復子を逆参照できません (例: 終了反復子))" が報告されます。
* パフォーマンスの向上: basic_string::find(char) オーバーロードで traits::find が 1 回だけ呼び出されるようになりました。 これまで、この操作は、長さ 1 の文字列の一般的な文字列検索として実装されていました。
* パフォーマンスの向上: basic_string::operator== は、文字列の内容を比較する前に文字列のサイズをチェックするようになりました。
* パフォーマンスの向上: コンパイラ オプティマイザーによる分析が困難であった basic_string でのコントロールの結合が削除されました。 VSO# 262848 "\<string\>: reserve() が過剰な処理をする" が解決されました。 短い文字列では、reserve を呼び出すと、処理は何も行われませんがコストは 0 ではないことに注意してください。
* \<any\>、\<string_view\>、apply()、make_from_tuple() が追加されました。
* 正確性とパフォーマンスについて std::vector が徹底的に見直されました。挿入/配置操作中のエイリアシングが標準に従って適切に処理されるようになりました。強固な例外保証が、標準で求められるときに move_if_noexcept() およびその他のロジックを介して提供されるようになりました。挿入/配置に伴う要素の操作が少なくなりました。
* C++ 標準ライブラリでは、手の込んだ null ポインターの逆参照が回避されるようになりました。
* \<optional\>、\<variant\>、shared_ptr::weak_type、および \<cstdalign\> が追加されました。
* min/max/minmax(initializer_list) および min_element/max_element/minmax_element() で C++14 constexpr が有効になりました。
* weak_ptr::lock() パフォーマンスが向上しました。
* 以前はコードが永続的にブロックされていた std::promise の移動代入演算子が修正されました。
* atomic\<T \*\> の T \* への暗黙の変換でコンパイラのエラーが修正されました。
* pointer_traits\<Ptr\> で Ptr::rebind\<U\> が適切に検出されるようになりました。
* move_iterator の減算演算子に不足した const 修飾子が修正されました。
* propagate_on_container_copy_assignment および propagate_on_container_move_assignment を要求するステートフルなユーザー定義アロケーターのサイレントかつ不適切な codegen が修正されました。
* atomic\<T\> でオーバーロードされた operator&() が許容されるようになりました。
* コンパイラのスループットを上げるため、C++ 標準ライブラリ ヘッダーで不要なコンパイラ組み込みの宣言を含むことが回避されるようになりました。
* 間違った bind() 呼び出しのコンパイラ診断が若干向上しています。
* std::string/std::wstring の移動コンストラクターのパフォーマンスが 3 倍以上に向上しました。
* 標準ライブラリの改善に関する完全な一覧については、「[Standard Library Fixes In VS 2017 RTM (Visual Studio 2017 RTM での標準ライブラリの修正)](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/)」をご覧ください。

#### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

##### <a name="c17-features"></a>C++17 の機能 
C++17 の追加機能がいくつか実装されました。 詳細については、「[Visual C++ 言語への準拠](visual-cpp-language-conformance.md)」をご覧ください。

##### <a name="other-new-features"></a>その他の新機能
* P0602R0 "variant と optional は自明的にコピー/移動を伝達する必要がある" を実装しました。
* 標準ライブラリが、/GR- で無効にされた動的 RTTI を正式に許容するようになりました。 dynamic_pointer_cast() と rethrow_if_nested() には本質的に dynamic_cast が必要なため、標準ライブラリでは /GR- の指定時にこれらの関数が =delete としてマークされるようになりました。
* 動的 RTTI が /GR- で無効にされた場合でも、"static RTTI" (typeid(SomeType) の形式) は引き続き使用可能で、標準ライブラリの一部のコンポーネントを強化します。 標準ライブラリでは、/D_HAS_STATIC_RTTI=0 でこの無効化もサポートするようになりました。 *これによって、std::any、std::function の target() と target_type()、shared_ptr の get_deleter() も無効になることに注意してください。*

##### <a name="correctness-fixes"></a>正確性の修正
* 標準ライブラリのコンテナーでは、max_size() を size_type の最大値ではなく、numeric_limits\<difference_type\>::max() にクランプするようになりました。これにより、そのコンテナーからの反復子における distance() の結果が、distance() の戻り値の型で表現できるようになります。
* 特殊化 auto_ptr\<void\> が欠落する不具合を修正しました。
* 以前は、length 引数が整数型ではない場合、meow_n() アルゴリズムはコンパイルに失敗していました。現在は、整数型ではない length 引数から反復子の difference_type に変換するようになりました。
* normal_distribution\<float\> では、double から float への縮小について、標準ライブラリ内で警告を出力しないようになりました。
* 最大サイズのオーバーフローをチェックするときに、max_size() ではなく npos と比較していた一部の basic_string 操作を修正しました。
* condition_variable::wait_for(lock, relative_time, predicate) は、疑似ウェイクが発生した場合、相対時間の全体で待機していました。 現在は、相対時間の単一間隔の間のみ待機します。
* 標準での必要性に応じて、future::get() は future を無効化するようになりました。
* iterator_traits\<void \*\> は void&; を形成しようとするため、ハード エラーとして使用されていましたが、これが明確に空の構造体となり、"is iterator" SFINAE 条件で iterator_traits が使用できるようになりました。
* Clang -Wsystem-headers によって報告される警告の一部を修正しました。
* Clang -Wmicrosoft-exception-spec によって報告された "宣言での例外指定が以前の宣言と一致しない" 問題も修正しました。
* Clang と C1XX によって報告された mem-initializer-list 順序付けの警告も修正しました。
* 順序なしのコンテナーは、コンテナー自体がスワップされるときに hasher や述語のスワップを行っていませんでした。 現在は行うようになりました。
* 多くのコンテナー スワップ操作は、マークされた noexcept となりました (標準ライブラリが non-propagate_on_container_swap non-equal-allocator の未定義の動作条件を検出したときに、例外をスローすることがないため)。
* 多くの vector\<bool\> 操作が、マークされた noexcept になりました。
* 標準ライブラリは、アロケーター value_types (C++17 モードで) の照合をオプトアウト エスケープ ハッチで強制するようになりました。
* basic_strings への self-range-insert が文字列の内容をスクランブルする場合の条件の一部を修正しました。 (注: ベクターへの self-range-insert は、標準によって引き続き禁止されています。)
* basic_string::shrink_to_fit() は、アロケーターの propagate_on_container_swap によって影響を受けることがなくなりました。
* std::decay は、煩雑な関数の型 (cv-qualified や ref-qualified などの関数型) を処理するようになりました。
* include ディレクティブを変更した結果、正しい大文字小文字の区別とスラッシュの使用が可能となり、移植性が向上させました。
* 警告 C4061 "列挙型 'Kitten' の switch 文内の列挙子 'Meow' は、case ラベルによって明示的に扱われていません" を修正しました。 この警告は既定ではオフになっており、標準ライブラリの警告の全般的なポリシーに対する例外として修正されました。 (標準ライブラリは /W4 クリーンですが、/Wall クリーンにしようとはしません。 既定でオフである警告の多くは、非常にノイズが多く、日常的に使用するためのものではありません。)
* std::list のデバッグ チェックが強化されました。 リストの反復子は演算子 ->() をチェックし、list::unique() では反復子を無効としてマークするようになりました。
* タプル内の uses-allocator メタプログラミングを修正しました。

##### <a name="performancethroughput-fixes"></a>パフォーマンスやスループットの修正
* 構造化例外処理 (SEH) を使用する関数に std::atomic の実装をインライン展開することを防ぐ noexcept との相互作用を回避しました。
* 標準ライブラリの internal _Deallocate() 関数を変更してより小さなコードに最適化し、より多くの場所にインライン化できるようにしました。
* std::try_lock() を変更し、再帰の代わりにパック展開を使用するようにしました。
* std::lock() のデッドロック回避アルゴリズムを改善し、すべてのロックで try_lock() を使用するのではなく、lock() 操作を使用するようにしました。
* system_category::message() で名前付きの戻り値の最適化を有効にしました。
* 結合および論理和演算が、2N + 2 型ではなく、N + 1 型をインスタンス化するようになりました。
* std::function が各々の型消去呼び出しのアロケーター サポート メカニズムをインスタンス化しなくなり、多くの異なるラムダを std::function に渡すプログラムでスループットが向上し、.obj サイズが縮小しました。
* allocator_traits\<std::allocator\> に手動でインライン化された std::allocator 操作が含まれたことにより、allocator_traits のみで std::allocator と対話するコード (つまりほとんどのコード) のコード サイズが縮小されます。
* C++ 11 の最小アロケーター インターフェイスは、内部クラス _Wrap_alloc 内のアロケーターをラップするのでなく、直接 allocator_traits を呼び出す標準ライブラリによって処理されるようになりました。 これにより、アロケーター サポートに対して生成されるコード サイズが小さくなり、オプティマイザーの機能が向上して標準ライブラリのコンテナーを推測できる場合があり、デバッグ エクスペリエンスが向上します (デバッガ―で _Wrap_alloc\< アロケーター型 \>ではなくアロケーター型を表示するようになりました)。
* カスタマイズされた allocator::reference のメタプログラミングを削除しました。実際にアロケーターをカスタマイズすることは許可されていないものです。 (アロケーターは、コンテナーが手の込んだポインターを使用するようにできますが、手の込んだ参照を使用するようにはできません。)
* コンパイラのフロントエンドが、範囲ベースの for ループでデバッグ反復子のラップを解除するようにしてあり、デバッグ ビルドのパフォーマンスを向上させます。
* shrink_to_fit() と reserve() への basic_string の内部圧縮パスは再割り当て操作のパスではなくなったため、変化を伴うすべてのメンバーのコード サイズが減少します。
* basic_string の内部拡張パスが、shrink_to_fit() のパスからなくなりました。
* basic_string の変更操作が、非割り当て高速パスと割り当て低速パスの関数に含まれるようになり、一般的な非割り当てのケースが呼び出し元にインライン化されやすくなりました。
* basic_string の変化を伴う操作が、インプレースでサイズ変更するのではなく、目的の状態で、再割り当てバッファーを構築するようになりました。 たとえば、文字列の先頭への挿入は、再割り当ての場合に 2 回 (新しく割り当てられたバッファーへ、そして下へ) 移動するのではなく、一度 (下へ、または新しく割り当てられたバッファーへ) 完全に挿入した後にコンテンツを移動させます。
* \<string\> 内の C 標準ライブラリを呼び出す操作では、errno のアドレスをキャッシュに格納することで、TLS でのやりとりを繰り返さないようになりました。
* Is_pointer の実装を簡素化しました。
* 関数ベースの SFINAE 式から struct/void_t ベースへの変更が完了しました。
* 標準ライブラリのアルゴリズムで、ポスト インクリメントの反復子を使用しないようになりました。
* 64 ビット システムで 32 ビットのアロケーターを使用した場合の切り捨ての警告を修正しました。
* non-POCMA non-equal-allocator の場合に、バッファーが使用可能な場合は再利用することによって、std::vector 移動割り当てがより効率的になるようになりました。

##### <a name="readability-and-other-improvements"></a>読みやすさとその他の改善
* 標準ライブラリでは、条件付きで定義されたマクロではなく、無条件で C++14 constexpr を使用するようになりました。
* 標準ライブラリでは、エイリアス テンプレートを内部で使用するようになりました。
* 標準ライブラリでは、nullptr_t {} ではなく、nullptr を内部で使用するようになりました。 (NULL は内部で使用できなくなりました。 0 を null として内部で使用している箇所は、徐々に削除されています。)
* 標準ライブラリでは、様式上 std::forward() を誤用するのではなく、std::move() を内部で使用するようになりました。
* static_assert(false, "message") を #error メッセージに変更しました。 これにより、#error がコンパイルを即時に中止するため、コンパイラによる診断が向上します。
* 標準ライブラリでは、関数を __declspec(dllimport) としてマークしなくなりました。 最新のリンカー テクノロジでは、これが不要になりました。
* SFINAE を既定のテンプレート引数に抽出するため、戻り値型と関数引数型に比べて、煩雑さが軽減されました。
* \<random\> のデバッグ チェックでは、fputs() を stderr に呼び出す内部関数 _Rng_abort() ではなく、標準ライブラリの通常のメカニズムが使用されるようになりました。 この関数の実装は、バイナリ互換性のために保持されているものの、標準ライブラリの次のバイナリ非互換バージョンでは削除されています。 

### <a name="open-source-library-support"></a>オープン ソース ライブラリのサポート  
Vcpkg は、Visual Studio でオープン ソースの C++ スタティック ライブラリと DLL を取得してビルドするプロセスを大幅に単純化するオープン ソースのコマンド ライン ツールです。 詳細については、「[vcpkg: C++ 用のパッケージ マネージャー](vcpkg.md)」を参照してください。

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0  
C++ 用のクロスプラットフォーム Web API である CPPRestSDK が、バージョン 2.9.0 に更新されました。 詳しくは、「[CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/)」(CppRestSDK 2.9.0 が GitHub で入手可能) をご覧ください。

### <a name="atl"></a>ATL
* もう 1 つの名前検索の適合性が解決しました
* 既存の移動コンストラクターと移動代入演算子が非スローとして正しくマークされるようになりました。
* atlstr.h のローカルな静的変数のスレッド セーフな init に関する有効な警告 (C4640) の抑制が解除されました。
* XP ツールセットで、ローカルな静的変数のスレッド セーフな初期化が自動的に無効になっていました (ATL を使用し DLL をビルドするとき)。 現在のバージョンには該当しません。 スレッド セーフな初期化をオフにすることを希望する場合は、プロジェクト設定で /Zc:threadSafeInit- を追加することができます。 

### <a name="visual-c-runtime"></a>Visual C++ ランタイム
* コントロール フロー ガード シンボルに新しいヘッダー "cfguard.h" が追加されました。 

## <a name="c-ide"></a>C++ IDE

* C++ ネイティブ プロジェクトの構成変更が簡単になりました。C++/CLI プロジェクトの場合、さらに簡単です。 ソリューション構成を初めて有効にするとき、そのプロセスが以前より速やかに進行し、そのソリューション構成の後続のアクティベーションがすべて即座に完了します。

**Visual Studio 2017 バージョン 15.3**:
* プロジェクトとコードのいくつかのウィザードを署名ダイアログのスタイルで書き直しました。
* **[クラスの追加]** でクラス追加ウィザードが直接起動されるようになりました。 以前ここにあったその他の項目はすべて、**[追加] > [新しい項目]** に移動しています。
* **[新しいプロジェクト]** ダイアログで、Win32 プロジェクトが [Windows デスクトップ] カテゴリに表示されるようになりました。
* Windows コンソールのテンプレートと Windows デスクトップ アプリケーションのテンプレートで、ウィザードなしでプロジェクトを作成するようになりました。 以前と同じオプションを表示する同じカテゴリに新しい Windows デスクトップ ウィザードが追加されました。

### <a name="intellisense"></a>Intellisense  
* SQLite ベースの新しいデータベース エンジンが、既定で使用されるようになりました。 これにより、[定義に移動] や [すべての参照を検索] などのデータベース操作が高速化され、ソリューションの初期解析時間も大幅に短縮されます。 設定は、[ツール] > [オプション] > [テキスト エディター] > [C/C++] > [詳細設定] に移動しました (以前は、... [C/C++] > [試験的] の下)。

* プリコンパイル済みヘッダーを使用していないプロジェクトやファイルでの IntelliSense のパフォーマンスが向上しました。現在のファイルのヘッダーに対して自動プリコンパイル済みヘッダーが作成されます。

* エラー一覧の IntelliSense エラーに対するフィルター処理とヘルプが追加されました。 エラー列をクリックするとフィルター処理を実行できます。 また、特定のエラーをクリックするか F1 キーを押すと、エラー メッセージのオンライン検索が開始します。

  ![エラー一覧](media/ErrorList1.png "Error List")

  ![フィルター処理されたエラー一覧](media/ErrorList2.png "Error List Filtered")

* メンバー リストの項目を種類別にフィルターする機能が追加されました。

  ![メンバー リストのフィルター処理](media/mlfiltering.png "Member List Filtering")

* メンバー リストの表示項目のコンテキストに応じたフィルター処理を提供する新しい実験的な予測 IntelliSense 機能が追加されました。 「[C++ IntelliSense Improvements - Predictive IntelliSense & Filtering](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)」 (C++ IntelliSense の機能改善 - 予測 IntelliSense とフィルター処理) を参照してください。

* [すべての参照の検索]\(Shift + F12) を使って、複雑なコードベースでも簡単に参照できるようになりました。 高度なグループ化、フィルター処理、並べ替え、結果内の検索と色づけ (一部の言語) が提供され、参照を明確に理解できます。 C++ では、新しい UI に、変数から読み取っているのか、または変数に書き込んでいるのかに関する情報が含まれます。

* Dot-to-Arrow IntelliSense 機能が試験段階から進んだ段階に移り、既定で有効になっています。 エディターの [Expand Scopes (スコープの展開)] および [Expand Precedence (優先順位の展開)] 機能が試験段階から進んだ段階に移ります。

* 試験的なリファクタリング機能である "署名の変更" および "関数の抽出" が既定で使用可能になりました。

* C++ プロジェクトの "迅速なプロジェクトの読み込み" の試験的機能。 C++ プロジェクトを次回に開いた際に、読み込みが速くなり、またそれ以降、読み込みが非常に速くなります。

他の言語と共通の機能と、C++ に固有の機能があります。 これらの新機能について詳しくは、「[Announcing Visual Studio “15”](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/)」(Visual Studio "15" のご案内) をご覧ください。 


### <a name="support-for-non-msbuild-projects-with-open-folder"></a>[フォルダーを開く] での非 MSBuild プロジェクトのサポート
Visual Studio 2017 で導入された [フォルダーを開く] 機能を使うと、ソリューションまたはプロジェクトを作成することなく、ソース コードを含むフォルダーでコーディング、ビルド、デバッグを行うことができます。 これにより、プロジェクトが MSBuild ベースではない場合でも、Visual Studio を簡単に使い始めることができます。 [フォルダーを開く] では、Visual Studio で MSBuild プロジェクトに対して既に提供されている、強力なコード理解、編集、ビルド、デバッグの機能にアクセスできます。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](ide/non-msbuild-projects.md)」をご覧ください。

* [フォルダーを開く] のエクスペリエンスが改善されました。 以下の json ファイルを使って、エクスペリエンスをカスタマイズできます。
  - CppProperties.json: IntelliSense および参照エクスペリエンスをカスタマイズします。
  - Tasks.json: ビルド ステップをカスタマイズします。 
  - Launch.json: デバッグ エクスペリエンスをカスタマイズします。

**Visual Studio 2017 バージョン 15.3**: 
* MinGW や Cygwin といった、別のコンパイラとビルド環境のサポートを強化しました。 詳細については、「[Using MinGW and Cygwin with Visual C++ and Open Folder (Visual C++ と [フォルダーを開く] で MinGW と Cygwin を使用する)](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/)」をご覧ください。
* "CppProperties.json" と "CMakeSettings.json" でグローバル環境変数と構成固有の環境変数を定義するためのサポートが追加されました。 この環境変数は、"launch.vs.json" に定義されているデバッグ構成と "tasks.vs.json" のタスクで利用されます。
* 簡単に 64 ビット プラットフォームを対象とする機能など、CMake の Ninja generator のサポートを強化しました。

### <a name="cmake-support-via-open-folder"></a>[フォルダーを開く] での CMake のサポート
Visual Studio 2017 では、MSBuild プロジェクト ファイル (.vcxproj) を変換しなくても、CMake プロジェクトを使用できるようになりました。 詳細については、「[CMake projects in Visual C++ (Visual C++ の CMake プロジェクト)](ide/cmake-tools-for-visual-cpp.md)」をご覧ください。 [フォルダーを開く] で CMake プロジェクトを開くと、C++ の編集、ビルド、およびデバッグ用の環境が自動的に構成されます。

* C++ の IntelliSense は、ルート フォルダーに CppProperties.json ファイルを作成しなくても動作します。 これに加えて、CMake に用意された構成と CppProperties.json ファイルをユーザーが簡単に切り替えることができるように新しいドロップダウンが追加されました。

* CMakeLists.txt ファイルと同じフォルダーに配置される CMakeSettings.json ファイルにより、追加の構成がサポートされます。

  ![Cmake の [フォルダーを開く]](media/cmake_cpp.png "CMake Open Folder")

**Visual Studio 2017 バージョン 15.3**: CMake Ninja generator のサポートが追加されました。 詳しくは、「[CMake support in Visual Studio – what’s new in 2017 15.3 Preview 2 (Visual Studio での CMake のサポート – 2017 15.3 プレビュー 2 の新機能)](https://blogs.msdn.microsoft.com/vcblog/2017/06/14/cmake-support-in-visual-studio-whats-new-in-2017-15-3-preview-2/)」をご覧ください。 

## <a name="c-installation-workloads"></a>C++ インストール ワークロード 

### <a name="windows-desktop-development-with-c"></a>C++ による Windows デスクトップ開発:  
元の C++ ワークロードのインストールに対して、より詳細なインストール エクスペリエンスを提供します。 必要なツールだけをインストールできる選択可能なコンポーネントが追加されました。  インストーラーの UI のコンポーネント一覧で示されるインストール サイズは正確ではなく、合計サイズが少なめに表示されることに注意してください。

C++ デスクトップ ワークロードで Win32 プロジェクトを作成するには、ツールセットと Windows SDK の両方をインストールする必要があります。 推奨される (選択されている) コンポーネント "VC++ 2017 v141 toolset (x86, x64)" と "Windows 10 SDK (10.0.14393)" をインストールすれば、確実に実行できます。 必要なツールがインストールされていない場合、プロジェクトは正常に作成されず、ウィザードがハングします。

### <a name="linux-development-with-c"></a>C++ による Linux 開発:  
よく利用される拡張機能である [Visual C++ for Linux Development](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) が Visual Studio に組み込まれます。 このインストールでは、Linux 環境で実行する C++ アプリケーションの開発とデバッグに必要なすべてのものが提供されます。  

**Visual Studio 2017 バージョン 15.2**: クロスプラットフォームのコード共有と型の視覚化の機能強化。 詳細については、「[Linux C++ improvements for cross-platform code sharing and type visualization (Linux C++ の、クロスプラットフォームのコード共有と型の視覚化の機能強化)](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/)」をご覧ください。

### <a name="game-development-with-c"></a>C++ によるゲーム開発:  
C++ を最大限に活用して DirectX または Cocos2d で駆動するプロフェッショナルなゲームを構築します。  

### <a name="mobile-development-with-c-android-and-ios"></a>C++ によるモバイル開発 (Android および iOS):  
Android および iOS を対象とするモバイル アプリを、Visual Studio を使用して作成およびデバッグできるようになりました。  

### <a name="universal-windows-apps"></a>ユニバーサル Windows アプリ:  
ユニバーサル Windows アプリ ワークロードのオプション コンポーネントとして、C++ が提供されます。  C++ プロジェクトのアップグレードは、現在のところ、手動で行う必要があります。 v140 をターゲットとする UWP プロジェクトを Visual Studio 2017 で開くときに、Visual Studio 2015 がインストールされていない場合はプロジェクト プロパティ ページで v141 プラットフォーム ツールセットを選択する必要があります。

## <a name="new-options-for-c-on-universal-windows-platform"></a>ユニバーサル Windows プラットフォームでの C++ の新しいオプション
ユニバーサル Windows プラットフォームおよび Windows ストア用の C++ アプリケーションを記述およびパッケージ化するための新しいオプションが追加されました。Desktop App Converter を使うと、Windows ストアを通してデプロイできるように既存のデスクトップ アプリケーションをパッケージ化できます。 詳しくは、「[Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/)」(Centennial プロジェクトでの Visual C++ ランタイムの使用) および「[Bring your desktop app to the Universal Windows Platform (UWP) with the Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)」(Desktop Bridge でデスクトップ アプリをユニバーサル Windows プラットフォーム (UWP) 対応にする) をご覧ください。

新しいコードを作成するときに、ヘッダー ファイルだけに実装される Windows ランタイム向けの標準 C++ 言語プロジェクションである C++/WinRT を使うことができるようになりました。 これにより、標準準拠の任意の C++ コンパイラを使って、Windows ランタイム API を作成および使用できます。 C++/WinRT は、C++ の開発者が最新の Windows API に最適にアクセスできるように設計されています。 詳しくは、「[C++/WinRT Available on GitHub](https://moderncpp.com/)」 (C++/WinRT が GitHub で入手可能) をご覧ください。


## <a name="clangc2-platform-toolset"></a>Clang/C2 プラットフォーム ツールセット
[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] に付属する Clang/C2 ツールセットが、/bigobj スイッチをサポートするようになりました。これは、大規模なプロジェクトを構築する際に重要です。 また、コンパイラのフロントエンドとバックエンドの両方について、いくつかの重要なバグ修正が組み込まれました。

## <a name="c-code-analysis"></a>C++ コードの分析

[C++ コア ガイドライン](https://github.com/isocpp/CppCoreGuidelines)を適用するための C++ コア チェッカーが Visual Studio で配布されています。 プロジェクトのプロパティ ページの [Code Analysis Extensions]\(コード分析の拡張機能) ダイアログでチェックを有効にするだけで、拡張機能がコード分析の実行時に含まれます。 

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck properties page") 

**Visual Studio 2017 バージョン 15.3**: リソース管理に関連するルールのサポートが追加されました。 詳細については、「[Using the C++ Core Guidelines checkers (C++ Core ガイドラインのチェッカーを使用する)](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers)」をご覧ください。

## <a name="unit-testing"></a>単体テスト

新しい Visual Studio 拡張機能を使用すると、Google Test と Boost.Test に基づく単体テストをVisual Studio で直接実行できます。 詳細については、「[C++ Unit Testing Updates: Announcing Boost.Test Adapter and Improved Google Test Support (C++ 単体テストの更新: Boost.Test Adapter と、Google Test のサポートの強化を発表)](https://blogs.msdn.microsoft.com/vcblog/2017/08/04/c-unit-testing-updates-announcing-boost-test-adapter-and-improved-google-test-support/)」をご覧ください。

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio グラフィックス診断

Visual Studio のグラフィックス診断は、Direct3D アプリのレンダリングとパフォーマンスを記録し、問題を分析するためのツール セットです。 グラフィックス診断機能は、Windows PC でローカルに実行されているアプリ、Windows デバイス エミュレーターで実行されているアプリ、あるいはリモート PC またはデバイスで実行されているアプリに対して使用できます。

* **頂点シェーダーとジオメトリ シェーダーの入力と出力:** 頂点シェーダーとジオメトリ シェーダーの入力と出力を表示する機能は、最も要求の多かった機能の 1 つであり、ツールでサポートされるようになりました。 パイプライン ステージ ビューで VS または GS ステージを選ぶだけで、次の表の入力と出力を調べることができます。

  ![シェーダーの入力/出力](media/io-shaders.png)

* **オブジェクト テーブルでの検索とフィルター:** 探しているリソースを検索する迅速かつ簡単な手段を提供します。

  ![[検索]](media/search.png)
   
* **リソース履歴:** この新しいビューは、キャプチャされたフレームのレンダリング時に使われたリソースの全体の変更履歴を表示する簡単な手段を提供します。 リソースの履歴を呼び出すには、リソースのハイパーリンクの横にある時計のアイコンをクリックします。

  ![リソース履歴](media/resource-history.png)

  新しいリソース履歴ツール ウィンドウに、リソースの変更履歴が表示されます。

  ![リソース履歴の変更](media/resource-history-change.png)

  完全な呼び出し履歴のキャプチャを有効にしてフレームをキャプチャした場合 (**[Visual Studio] > [ツール] > [オプション] > [グラフィックス診断]**)、Visual Studio プロジェクト内の各変更イベントのコンテキストを簡単に推測および検査できます。  

* **API 統計情報:** フレームでの API の使用の概要を表示します。 行っていることにまったく気付いていない呼び出しまたは多すぎる呼び出しを発見するのに便利です。 このウィンドウは、Visual Studio Graphics Analyzer の **[表示] > [API 統計情報]** から表示できます。

  ![API 統計情報](media/api-stats.png)

* **メモリ統計情報:** フレームで作成されたリソースにドライバーが割り当てているメモリの量を表示します。 このウィンドウは、Visual Studio Graphics Analyzer の [表示] > [メモリ統計情報] から表示できます。 右クリックして [すべてコピー] を選ぶことで、データを CSV ファイルにコピーしてスプレッドシートで表示できます。

  ![メモリ統計情報](media/memory-stats.png)
 
* **フレームの検証:** 新しいエラーと警告の一覧は、Direct3D デバッグ レイヤーで検出された潜在的な問題を基に、イベント リストを移動する簡単な方法を提供します。 ウィンドウを開くには、Visual Studio Graphics Analyzer で [表示] > [フレームの検証] をクリックします。 次に、[検証の実行] をクリックして分析を開始します。 フレームの複雑さによっては、完了するまでに数分かかることがあります。

  ![フレームの検証](media/frame-validation.png)
 
* **D3D12 のフレーム分析:** フレーム分析を使って、指示された "what-if" 実験で描画呼び出しのパフォーマンスを分析します。 [フレーム分析] タブに切り替え、分析を実行してレポートを表示します。 詳しくは、「[GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool)」(GoingNative 25: Visual Studio のグラフィックス フレーム分析) のビデオをご覧ください。

  ![フレーム分析](media/frame-analysis.png)

* **GPU 使用率の改善:** GPU ビューまたは Windows パフォーマンス アナライザー (WPA) ツールを使って Visual Studio の GPU 使用率プロファイラーで取得されたトレースを開き、詳細な分析を行います。 Windows パフォーマンス ツールキットがインストールされている場合、セッション概要の右下に WPA と GPU ビューの 2 つのハイパーリンクが表示されます。

  ![GPU 使用率](media/gpu-usage.png)
 
  このリンクから GPU ビューで開かれるトレースは、VS と GPU ビューの間で同期されたタイムラインのズームとパンをサポートします。 VS 内のチェック ボックスは、同期の有効/無効を制御するために使われます。 

  ![GPU ビュー](media/gpu-view.png) 


 

