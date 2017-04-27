---
title: "コンパイラの警告 C4800 C4999 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
- C4872
- C4880
- C4881
- C4882
- C4900
- C4910
- C4912
- C4913
- C4916
- C4918
- C4920
- C4921
- C4925
- C4926
- C4932
- C4934
- C4935
- C4936
- C4937
- C4938
- C4939
- C4944
- C4947
- C4950
- C4951
- C4952
- C4953
- C4954
- C4955
- C4956
- C4957
- C4958
- C4959
- C4960
- C4961
- C4962
- C4963
- C4966
- C4970
- C4971
- C4972
- C4973
- C4974
- C4981
- C4985
- C4987
- C4988
- C4989
- C4990
- C4991
- C4992
- C4997
- C4998
- C4999
- C4808
- C4809
dev_langs:
- C++
ms.assetid: c3182430-8b3b-4ab2-a532-5cd436707dc8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: ac03a99c1a9413b697b6e40101bf1c3e2be9a3a6
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-warnings-c4800-through-c4999"></a>コンパイラの警告 C4800 C4999
ドキュメントのこの部分の記事には、Visual C コンパイラの警告のサブセットについてを説明します。 ここでの情報にアクセスするまたは、Visual Studio の [出力] ウィンドウで、エラー番号を選択し、F1 キーを押します。  
  
> [!NOTE]
>  すべて[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]エラーまたは警告は、MSDN に記載されています。 多くの場合は、診断メッセージは、すべての使用可能な情報を提供します。 エラー メッセージに追加の情報が必要と思われる場合は、どうぞお知らせください。 このページでフィードバック フォームを使用してまたはに Visual Studio のメニュー バーを選択する**ヘルプ**、**バグの報告を**、提案やバグ レポートを送信することができますか[Microsoft Connect](http://connect.microsoft.com/VisualStudio)です。  
  
MSDN のパブリック フォーラムに関するエラーと警告の追加サポートが必要があります。 [Visual C の言語](http://go.microsoft.com/fwlink/?LinkId=158195)に関する質問や議論は、フォーラム、[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]言語の構文とコンパイラです。 [Visual C++ 全般](http://go.microsoft.com/fwlink/?LinkId=158194)に関する質問については、フォーラム[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]するその他のフォーラムでは説明しません。 エラーと警告に関するヘルプもあります[スタック オーバーフロー](http://stackoverflow.com/)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|警告|メッセージ|  
|-------------|-------------|  
|[コンパイラの警告 (レベル 3) C4800](../../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md)|'type': 値を強制的にブール値 'true' または 'false' (パフォーマンスの警告)|  
|[コンパイラの警告 (レベル 1) C4803](../../error-messages/compiler-warnings/compiler-warning-level-1-c4803.md)|'method': raise メソッドが、イベントと異なるストレージ クラス 'event'|  
|[コンパイラの警告 (レベル 1) C4804](../../error-messages/compiler-warnings/compiler-warning-level-1-c4804.md)|'operation': 型 'bool' の操作で安全でないを使用します。|  
|[コンパイラの警告 (レベル 1) C4805](../../error-messages/compiler-warnings/compiler-warning-level-1-c4805.md)|'operation': 型と型 'type' の混用は安全でない 'type' の操作で|  
|コンパイラの警告 (レベル 1) C4806|'operation': 安全でない演算: 型 'type' 型 'type' に上位変換の値が与えられた定数を等しくないです。|  
|コンパイラの警告 (レベル 1) C4807|'operation': 型 'type' と 'type' 型の符号付きビット フィールドの安全でないミックス|  
|コンパイラの警告 (レベル 1) C4808|'value' の場合は、'bool' 型の switch の有効な値ではありません。|  
|コンパイラの警告 (レベル 1) C4809|switch 文に冗長な 'default' ラベルが存在します。可能な 'case' 条件はすべて記述されています|  
|コンパイラの警告 (レベル 1) C4810|pragma の値 pack(show) == n|  
|コンパイラの警告 (レベル 1) C4811|プラグマ conform(forScope, show) の値 == value|  
|コンパイラの警告 (レベル 1) C4812|旧形式の宣言スタイル: 'new_syntax' を使用してください|  
|コンパイラの警告 (レベル 1) C4813|'function': ローカル クラスの friend 関数必要がありますが宣言されていません|  
|コンパイラの警告 (レベル 4) C4816|'param': パラメーター (オブジェクトが参照渡しで) 場合は切り捨てられますが、サイズが 0 の配列には|  
|コンパイラの警告 (レベル 1) C4817|'member': 正しく使用 '.'; このメンバーにアクセスするには'->' にコンパイラが置き換えられます|  
|[コンパイラの警告 (レベル 1) C4819](../../error-messages/compiler-warnings/compiler-warning-level-1-c4819.md)|ファイルは、現在のコード ページ (数) で表示できない文字を含んでいます。 データの損失を防ぐために Unicode 形式でファイルを保存します。|  
|[コンパイラの警告 (レベル 4) C4820](../../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md)|'バイト' : 'バイト' バイトのパディングを 'コンスラクト' 'member_name' の後に追加しました。|  
|[コンパイラの警告 (レベル 1) C4821](../../error-messages/compiler-warnings/compiler-warning-level-1-c4821.md)|Unicode エンコードの種類を指定できません。シグネチャ (BOM) つきファイルを保存してください。|  
|コンパイラの警告 (レベル 1) C4822|'member function': ローカル クラス メンバー関数は本体がありません|  
|[コンパイラの警告 (レベル 3) C4823](../../error-messages/compiler-warnings/compiler-warning-level-3-c4823.md)|'function': を使用して固定ポインターが、アンワインド セマンティクスが有効ではありません。 /EHa を使用してください。|  
|コンパイラの警告 (レベル 4) C4825||  
|コンパイラの警告 (レベル 3) C4827|パラメーターが指定されていない 'ToString' パブリック メソッドは、virtual および override に設定する必要があります|  
|[コンパイラの警告 (レベル 1) C4829](../../error-messages/compiler-warnings/compiler-warning-level-1-c4829.md)|関数 main への正しくないパラメーターである可能性があります。 検討 ' int main (platform::array\<platform::string ^ > ^ argv)'|  
|[コンパイラの警告 (レベル 1) C4835](../../error-messages/compiler-warnings/compiler-warning-level-1-c4835.md)|'variable': マネージ コードがホスト アセンブリで最初に実行されるまで、エクスポートされたデータの初期化子は実行されません|  
|[コンパイラの警告 (レベル 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md)|'type_1' から 'type_2' への変換で縮小変換が必要です。|  
|[コンパイラの警告 C4867](../../error-messages/compiler-warnings/compiler-warning-c4867.md)|'function': 関数呼び出しの引数リストがありません。'call' を使用して、メンバーへのポインターを作成するには|  
|[コンパイラの警告 C4868](../../error-messages/compiler-warnings/compiler-warning-c4868.md)|'file(line_number)' コンパイラは、中かっこで囲んだ初期化リスト内で左から右へ評価順序を強制いない可能性があります。|  
|コンパイラの警告 (レベル 2) C4872|concurrency::parallel_for_each の呼び出し先をコンパイルするときに 0 による浮動小数点除算が検出されました (concurrency::parallel_for_each の位置: '%s')|  
|コンパイラの警告 (レベル 1) C4880|'const type_1' から 'type_2' にキャスト: ポインターまたは参照から constness でキャストして、可能性があります、amp 制限関数で未定義の動作|  
|コンパイラの警告 (レベル 4) C4881|コンス トラクターおよびデストラクターは呼び出されません tile_static 変数 'variable' の|  
|コンパイラの警告 (レベル 1) C4882|非 const 呼び出し演算子を使用した関数を concurrency::parallel_for_each に渡す処理は推奨されません|  
|コンパイラの警告 C4900|'Tool1' バージョン 'version1' と 'tool2' バージョン 'version2' の間が一致しません。|  
|[コンパイラの警告 (レベル 1) C4905](../../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md)|'LPSTR' にキャストされた幅の広いリテラル文字列|  
|[コンパイラの警告 (レベル 1) C4906](../../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md)|'LPWSTR' にキャストされたリテラル文字列|  
|コンパイラの警告 (レベル 1) C4910|'\<識別子 >: '関数' と 'extern' 明示的なインスタンス化に互換性がありません|  
|コンパイラの警告 (レベル 1) C4912|'attribute': 属性は入れ子の UDT 上での動作が定義されていません|  
|コンパイラの警告 (レベル 4) C4913|ユーザー定義のバイナリ演算子 ',' は存在しますが、すべてのオペランドに適用できるオーバーロードは見つかりませんでした。既定のビルドインバイナリ演算子 ',' を使用します。|  
|コンパイラの警告 (レベル 1) C4916|dispid を指定するためには、'%$S' はインターフェイスによって導入されなければなりません。|  
|[コンパイラの警告 (レベル 1) C4917](../../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md)|'declarator': GUID はクラス、インターフェイスまたは名前空間に関連付けできます。|  
|コンパイラの警告 (レベル 4) C4918|'character': プラグマ最適化リスト内に無効な文字|  
|コンパイラの警告 (レベル 1) C4920|enum enum メンバー member_1 = 既に enum enum で member_2 として認識 value_1 value_2 を =|  
|コンパイラの警告 (レベル 3) C4921|'%s': 属性の値 '%s' を複製指定しないでください。|  
|コンパイラの警告 (レベル 1) C4925|'method': dispinterface メソッドはスクリプトから呼び出すことはできません|  
|コンパイラの警告 (レベル 1) C4926|'identifier': シンボルは既に定義されています。属性は無視されます。|  
|[コンパイラの警告 (レベル 1) C4927](../../error-messages/compiler-warnings/compiler-warning-level-1-c4927.md)|変換が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。|  
|[コンパイラの警告 (レベル 1) C4928](../../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md)|コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。|  
|[コンパイラの警告 (レベル 1) C4929](../../error-messages/compiler-warnings/compiler-warning-level-1-c4929.md)|'file': タイプ ライブラリには、共用体が含まれています。'embedded_idl' 修飾子は無視されます。|  
|[コンパイラの警告 (レベル 1) C4930](../../error-messages/compiler-warnings/compiler-warning-level-1-c4930.md)|'プロトタイプ': プロトタイプ関数が呼び出されません (でした変数の定義が対象としていますか?)|  
|[コンパイラの警告 (レベル 4) C4931](../../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md)|number ビット ポインター用にタイプ ライブラリがビルドされていることを想定します。|  
|コンパイラの警告 (レベル 4) C4932|__identifier(identifier) と\__identifier(identifier) を区別できません|  
|コンパイラの警告 (レベル 1) C4934|'__delegate(multicast)' は非推奨 '\__delegate' 代わりに|  
|コンパイラの警告 (レベル 1) C4935|アセンブリ アクセス指定子が 'access' から変更されました|  
|コンパイラの警告 (レベル 1) C4936|この __declspec は、/clr または /clr:pure でコンパイルされるときのみサポートされます|  
|コンパイラの警告 (レベル 4) C4937|'text1' と 'text2' を、'directive' への引数として区別できません|  
|コンパイラの警告 (レベル 4) C4938|'var': 浮動小数点の減少変数/fp で矛盾する結果が発生する可能性があります: 厳密なまたは #pragma fenv_access|  
|コンパイラの警告 C4939|#プラグマ vtordisp は廃止されており、Visual C の将来のリリースで削除される予定|  
|コンパイラの警告 (レベル 1) C4944|'symbol': 'assembly1' からシンボルをインポートできません: 'symbol' は既に現在のスコープに存在します|  
|[コンパイラの警告 (レベル 1) C4945](../../error-messages/compiler-warnings/compiler-warning-level-1-c4945.md)|'symbol': 'assembly1' からシンボルをインポートできません: 'symbol' は既に別のアセンブリ 'assembly2' からインポートされて、|  
|[コンパイラの警告 (レベル 1) C4946](../../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md)|reinterpret_cast が関連クラスの間で使用されました : 'class1' と 'class2'|  
|コンパイラの警告 (レベル 1) C4947|'type_or_member': 廃止としてマークされています。|  
|[コンパイラの警告 (レベル 2) C4948](../../error-messages/compiler-warnings/compiler-warning-level-2-c4948.md)|'accessor' の戻り値の型が、対応する setter の最後のパラメーターの型と一致しません|  
|[コンパイラの警告 (レベル 1 およびレベル 4) C4949](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4949.md)|マネージおよびアンマネージのプラグマはコンパイルしたときにのみ意味のある '/clr [: オプション]'|  
|コンパイラの警告 (レベル 1) C4950|'type_or_member': 廃止としてマークされています。|  
|コンパイラの警告 C4951|プロファイル データ が収集されてから、'function' が編集されました。関数のプロファイル データは使用されません。|  
|コンパイラの警告 C4952|'function': プログラム データベース 'pgd_fil' ではプロファイル データが見つかりませんでした|  
|コンパイラの警告 C4953|プロファイル データが収集されたプロファイル データは使用されませんからインライン 'function' が編集されました|  
|コンパイラの警告 C4954|'function': プロファイルされません (_ _int64 スイッチ式が含まれています)|  
|コンパイラの警告 C4955|'import2': インポートは無視されます。'import1' から既にインポートされて|  
|コンパイラの警告 (レベル 1) C4956|'type': この型は、検証できません|  
|コンパイラの警告 (レベル 1) C4957|'cast': 'へ 'からキャスト' からの明示的なキャストは検証可能ではありません|  
|コンパイラの警告 (レベル 1) C4958|'operation': ポインター演算は検証可能ではありません|  
|コンパイラの警告 (レベル 1) C4959|アンマネージ型 'type' は検証不可能なコードを生成するそのメンバーにアクセスするため、/clr:safe で定義できません。|  
|コンパイラの警告 C4960|'function' はプロファイルするには多き過ぎます|  
|コンパイラの警告 C4961|プロファイル データが '.pgd ファイル' にマージされませんでした。プロファイルのガイド付き最適化を無効にします|  
|コンパイラの警告 C4962|'function': プロファイル ガイド付き最適化の最適化によってプロファイル データに矛盾が生じたために使用できません|  
|コンパイラの警告 C4963|'%s': プロファイル データが見つかりません。別のコンパイラ オプションがインストルメント化されたビルドで使用されました|  
|[コンパイラの警告 (レベル 1) C4964](../../error-messages/compiler-warnings/compiler-warning-level-1-c4964.md)|最適化のオプションが指定されませんでした。プロファイル情報は収集されません|  
|[コンパイラの警告 (レベル 1) C4965](../../error-messages/compiler-warnings/compiler-warning-level-1-c4965.md)|整数 0 の暗黙的なボックスです。nullptr または明示的なキャストを使用してください|  
|コンパイラの警告 C4966|'%s' には、サポートされていないセグメント名を含む __code_seg 注釈があります。注釈は無視されます|  
|コンパイラの警告 C4970|delegate コンストラクター: '%$pS' がスタティックであるため、ターゲット オブジェクトは無視されます|  
|コンパイラの警告 (レベル 1) C4971|引数の順序:\<ターゲット オブジェクト >、\<ターゲット関数 > デリゲート コンス トラクターは推奨されず、使用して\<ターゲット関数 >、\<ターゲット オブジェクト ="">|  
|コンパイラの警告 (レベル 1) C4972|アンボックス操作の結果を左辺の値として扱う、または直接変更することは検証可能ではありません|  
|コンパイラの警告 C4973|'%$S': 非推奨として設定されています|  
|コンパイラの警告 C4974|'%$S': 非推奨として設定されています|  
|コンパイラの警告 C4981|Warbird: 関数 '%$pD' は例外のセマンティクスを含んでいるため、インライン関数ではなく、__forceinline として記述されています|  
|コンパイラの警告 (レベル 3) C4985|シンボル名 ': 前の宣言に属性が存在しません。|  
|[コンパイラの警告 C4986](../../error-messages/compiler-warnings/compiler-warning-c4986.md)|'%$pS': 例外指定が以前の宣言と一致しません|  
|コンパイラの警告 (レベル 4) C4987|非標準の拡張機能が使用されています: 'throw (...)' です。|  
|コンパイラの警告 (レベル 4) C4988|'%$S': 変数がクラス/関数スコープの外部で宣言されています|  
|コンパイラの警告 C4989|'%s': 型に競合する定義があります。|  
|コンパイラの警告 C4990|Warbird: %s|  
|コンパイラの警告 C4991|Warbird: インラインの保護レベルが親よりも高いため、関数 '%$pD' はインライン関数ではなく、__forceinline として記述されています|  
|コンパイラの警告 C4992|Warbird: 関数 '%$pD' は保護できないインライン アセンブリを含んでいるため、インライン関数ではなく、__forceinline として記述されています|  
|[コンパイラの警告 (レベル 3) C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|'function': 名前が #pragma 非推奨としてマークされました|  
|[コンパイラの警告 (レベル 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|'%$pS': %$*|  
|コンパイラの警告 (レベル 1) C4997|'class': コクラスは COM インターフェイスまたは擬似インターフェイスを実装しません|  
|コンパイラの警告 (レベル 1) C4998|予測は失敗しました: %s(%d)|  
|コンパイラの警告 C4999|原因不明の警告%$N Visual C++ のサポート情報 コマンドを選択してください%$N ヘルプ メニュー、またはサポート情報のヘルプ ファイルを参照してください|
