---
title: "既定で無効になっているコンパイラ警告 |Microsoft ドキュメント"
ms.date: 11/04/2016
ms.technology: cpp-tools
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1dec9728679629f25ddbea93956fd25d9b29ef59
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-warnings-that-are-off-by-default"></a>既定で無効になっているコンパイラ警告

コンパイラの一部の警告は既定でオフになっています。ほとんどのユーザーにはそれらの警告の表示が不要なためです。 ただし、次のいずれかのオプションを使用してこのような警告を有効にできます。

`#pragma warning(default : warning_number )`  
指定された警告 (`warning_number`) は既定のレベルで有効になっています。 警告に関するドキュメントには、既定のレベルの警告が記載されています。

`#pragma warning( warning_level : warning_number )`  
指定された警告 (`warning_number`) は指定されたレベル (`warning_level`) で有効になっています。

[/Wall](../build/reference/compiler-option-warning-level.md)  
**/壁**既定で無効になっているすべての警告を有効にします。

既定では、次の警告はオフになっています。

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (レベル 4)|switch 中の 'identifier' ('enumeration' の) は case ラベルに与えられません。|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (レベル 4)|switch 中の 'identifier' ('enumeration' の) は与えられません。|
|C4191 (レベル 3)|'operator/operation': 'type of expression' から 'type required' への安全でない変換|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (レベル 4)|'identifier': 'type1' から 'type2' に変換しました。データが失われている可能性があります。|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (レベル 4)|'operator': 'type1' から 'type2' への変換です。データが失われる可能性があります。|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (レベル 4)|'function': 関数プロトタイプがありません: '()' を '(void)' に変換します。|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (レベル 4)|'function': メンバー関数はどの基底クラスの仮想メンバー関数もオーバーライドしません。|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (レベル 1)|'virtual_function': 仮想メンバー関数用に基底クラス 'class' から使用可能なオーバーライドはありません。関数は隠されます。|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (レベル 3)|'class': クラスは仮想関数を含んでいますが、デストラクターは仮想デストラクターではありません。|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (レベル 4)|'function': 仮想メンバー関数用に基底クラス型 'type' から使用可能なオーバーライドはありません。関数は隠されます。|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (レベル 3)|'operator': 符号なしおよび負の定数が一致していません。|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (レベル 4)|非標準の拡張が使用されています : 'var' : for ループで宣言したループ コントロール変数が for ループ スコープの外側で使用されています。|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (レベル 4)|'operator': 式は常に false です。|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (レベル 4)|'type' : 未定義の型の使用が CLR meta-data で検出されました。この型を使用するとランタイム例外が起きる可能性があります。|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (レベル 1)|動作変更: '関数' が呼び出されましたが、メンバー演算子が前のバージョンで呼び出されました|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (レベル 1)|動作変更: 'member1' が 'member2' の代わりに呼び出されました。|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : ベース メンバー初期化リストで使用されました。|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (レベル 4)|'action': 'type_1' から 'type_2' に変換しました。signed/unsigned が一致しません。|
|C4370 (レベル 3)|パッキングの改善のために、前バージョンのコンパイラからクラスのレイアウトが変更されました。|
|C4371 (レベル 3)|メンバー 'member' のパッキングの改善のために、前バージョンのコンパイラからクラスのレイアウト変更された可能性があります。|
|C4388 (レベル 4)|signed と unsigned の数値を比較しようとしました。|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (レベル 2)|'function': 関数のシグネチャが型 'type' を含んでいます。C++ オブジェクトを、純粋なコードと混合またはネイティブ コードとの間で渡すことは安全ではありません。|
|C4426 (レベル 1)|#pragma optimize() による最適化フラグがヘッダーを含めた後に変更された可能性があります。|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (レベル 4)|'class1': /vd2 下のオブジェクトのレイアウトは仮想ベース 'class2' により変更されます。|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (レベル 4)|仮想ベース 'class1' から 'class2' への dynamic_cast は特定のコンテキストでは失敗する場合があります。|
|C4444 (レベル 3)|トップ レベルの '__unaligned' がこのコンテキストで実装されていません。|
|C4464 (レベル 4)|相対インクルード パスを含む '.. '|
|C4472 (レベル 1)|'identifier' はネイティブの列挙型です。マネージ列挙型を宣言するには、アクセス指定子 (private/public) を追加します。|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (レベル 4)|'function': 参照されていないインライン関数は削除されました。|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (レベル 4)|'type name': 型名がメタデータの限度である 'limit' 文字を超えています。|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (レベル 1)|コンマ前の式は、引数リストのない関数として評価します。|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (レベル 1)|コンマの前の関数呼び出しに引数一覧がありません。|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (レベル 1)|'operator': コンマの前の演算子は無効です。有効な演算子を指定してください。|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (レベル 1)|コンマ前の式は無効です。有効な式を指定してください。|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (レベル 1)|'operator': コンマの前の演算子は無効です。候補 'operator'?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (レベル 1)|式の影響はありません; 式の副作用が必要です。|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (レベル 3)|'__assume' は影響 'effect' を含んでいます。|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (レベル 4)|Visual C 7.1; から変更情報: catch (...) セマンティクス構造化例外 (SEH) はキャッチされません。|
|C4574 (レベル 4)|'identifier' が '0' として定義されています。'#if identifier' を使用しますか?|
|C4582 (レベル 4)|'*型*': コンス トラクターは暗黙的に呼び出されません|
|C4583 (レベル 4)|'*型*': デストラクターは暗黙的に呼び出されません|
|C4587 (レベル 1)|'*anonymous_structure*': 動作変更: コンス トラクターが不要になった暗黙的に呼び出されます|
|C4588 (レベル 1)|'*anonymous_structure*': 動作変更: デストラクターは呼び出されなく|
|C4598 (レベル 1 およびレベル 3)|' #include"*ヘッダー*"': ヘッダー番号*数*プリコンパイル済みヘッダーと一致しませんその位置にある現在のコンパイル|
|C4599 (レベル 3)|'*オプション**パス*': コマンドライン引数の数*数*プリコンパイル済みヘッダーと一致しません|
|C4605 (レベル 1)|'/D*マクロ*' 現在のコマンドラインで指定したが、プリコンパイル済みヘッダーがビルドされたが指定されていません|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (レベル 3)|#pragma warning: 警告番号 'number' がありません。|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (レベル 4)|'derived class': 基底クラスの既定コンストラクターにアクセスできないため、既定のコンストラクターは生成できませんでした。|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (レベル 4)|'derived class': 基底クラスのコピー コンストラクターにアクセスできないため、コピー コンストラクターは生成できませんでした。|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (レベル 4)|'derived class': 基底クラスの代入演算子にアクセスできないため、代入演算子は生成できませんでした。|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (レベル 1)|digraphs は -Ze でサポートされていません。 文字のシーケンス 'digraph' は 'char' の代替トークンとして解釈されません。|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (レベル 3)|'instance': ローカル スタティック オブジェクトの構築がスレッド セーフではありません。|
|C4647 (レベル 3)|動作変更: _ _is_pod (*型*) 別の値が、以前のバージョン|
|C4654 (レベル 4)|プリコンパイル済みヘッダーの前に配置されたコードは、行は無視されます。 コードをプリコンパイル済みヘッダーに追加します。|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (レベル 4)|'*シンボル*'が '0' に置換するプリプロセッサ マクロとして定義されていません'*ディレクティブ*'|
|C4682 警告 (レベル 4)|'*シンボル*': 方向性のあるパラメーター属性がいません指定すると、[入力]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (レベル 3)|'*ユーザー定義型*': 動作の変更可能な UDT の戻り値呼び出し規約|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (レベル 1)|'*関数*': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型 'native_type' を含む|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (レベル 4)|'*関数*': 関数のインライン関数ではありません|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (レベル 3)|メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|揮発性アクセス '*式*' は/volatile:\<iso (& a) #124; ms > 設定; _iso_volatile_load/store 組み込み関数の使用を検討してください|
|C4749 (レベル 4)|条件付きでサポートされる: non standard レイアウトの種類に適用される offsetof '*型*'|
|C4767 (レベル 4)|セクション名 '*シンボル*' が 8 文字より長いと、リンカーによって切り詰められます|
|C4768 (レベル 3)|リンケージ指定する前に _ _declspec 属性は無視されます。|
|C4774 (レベル 4)|'*文字列*': 書式指定文字列の引数で予期されて*数*はない文字列リテラル|
|C4786 (レベル 3)|'*シンボル*': オブジェクト名は 'number' 文字にデバッグ情報で切り詰められました|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (レベル 4)|'バイト' : 'バイト' バイトのパディングを 'コンスラクト' 'member_name' の後に追加しました。|
|C4826 (レベル 2)|変換 '*type1*'to'*type2*' を符号拡張します。 これにより、予期しない実行時の動作が発生する可能性があります。|
|C4837 (レベル 4)|トライグラフが検出されました: ' [概要] タブ*文字*'置き換え'*文字*'|
|C4841 (レベル 4)|使用する標準の拡張機能: offsetof で使用される複合メンバーの指定子|
|C4842 (レベル 4)|コンパイラのリリース間で一致するように 'offsetof' の複数の継承を使用して型に適用の結果は保証されません。|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (レベル 4)|'_ファイル_(*line_number*)' コンパイラは、中かっこで囲んだ初期化リスト内で左から右へ評価順序を強制いない可能性があります|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (レベル 1)|'LPSTR' にキャストされた幅の広いリテラル文字列|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (レベル 1)|'LPWSTR' にキャストされたリテラル文字列|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (レベル 1)|'declarator': GUID はクラス、インターフェイス、または名前空間にのみ関連付けることができます。|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (レベル 1)|コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (レベル 4)|number ビット ポインター用にタイプ ライブラリがビルドされていることを想定します。|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (レベル 1)|reinterpret_cast が関連クラスの間で使用されました : 'class1' と 'class2'|
|C4962|'function': 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (レベル 4)|'*シンボル*': 例外の指定が前の宣言と一致しません|
|C4987 (レベル 4)|非標準の拡張機能が使用されています: 'throw (...)' です。|
|C4988 (レベル 4)|'*シンボル*': 変数には、外側のクラス/関数スコープが宣言されています|
|C5022|'*型*': 指定された複数の移動コンス トラクター|
|C5023|'*型*': 指定された複数の移動代入演算子|
|C5024 (レベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5025 (レベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5026 (レベル 1 およびレベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5027 (レベル 1 およびレベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5029 (レベル 4)|使用される標準の拡張機能: C++ のアラインメント属性は、変数、データ メンバーおよびタグの種類のみに適用|
|C5031 (レベル 4)|#pragma warning (pop): ポップの警告状態の別のファイルにプッシュされた可能性が高い不一致|
|C5032 (レベル 4)|いない対応する #pragma warning (pop) と #pragma warning (push) が検出されました|
|C5035|機能の使用 '*機能*' 関数*関数*ゲスト コードとしてコンパイルされます|
|C5036 (レベル 1)|/hybrid:x86arm64 でコンパイルすると、varargs 関数へのポインター変換 '*type1*'to'*type2*'|

しない限り、これらの警告は無効、[寛容/-](../build/reference/permissive-standards-conformance.md)コンパイラ オプションを設定します。

|||
|-|-|
|[C4471 (レベル 4)](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md)|対象範囲外の列挙の事前宣言には基になる型が必要です (int が想定されます)。|
|[C4608 警告 (レベル 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|'共用体\_メンバー' は既に初期化子リスト 'union_member' 内の他の共用体メンバーにより初期化されました|


これらの警告は、Visual Studio 2015 の前に、コンパイラのバージョンでは既定でオフしました。

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (レベル 2)|'conversion': 'type1' から 'type2' へ切り詰めます。|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (レベル 1)|'変数' : ポインターを '型' から '型' へ切り詰めます。|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (レベル 1)|'操作' :  'type1' からより大きいサイズの 'type2' へ変換します。|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (レベル 1)|'operator': ゼロ拡張 'type1' から 'type2' より大きいサイズの|

これらの警告は、Visual Studio 2012 より前に、コンパイラのバージョンでは既定でオフしました。

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (レベル 4)|型指定子がありません - int と仮定しました。 メモ: C は、現在 int を既定値としてサポートしていません|

## <a name="see-also"></a>関連項目

[warning](../preprocessor/warning.md)