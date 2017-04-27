---
title: "コンパイラの警告 C4000 C4199 を通じて |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4000
- C4002
- C4006
- C4008
- C4019
- C4023
- C4025
- C4026
- C4027
- C4030
- C4033
- C4035
- C4036
- C4038
- C4041
- C4045
- C4051
- C4052
- C4053
- C4057
- C4060
- C4063
- C4064
- C4065
- C4066
- C4068
- C4069
- C4075
- C4076
- C4077
- C4080
- C4081
- C4085
- C4086
- C4087
- C4097
- C4102
- C4109
- C4112
- C4115
- C4117
- C4119
- C4120
- C4122
- C4123
- C4125
- C4130
- C4131
- C4132
- C4137
- C4138
- C4141
- C4143
- C4145
- C4152
- C4153
- C4155
- C4158
- C4160
- C4161
- C4163
- C4164
- C4165
- C4166
- C4167
- C4168
- C4174
- C4175
- C4176
- C4177
- C4178
- C4179
- C4180
- C4181
- C4182
- C4185
- C4186
- C4187
- C4188
- C4189
- C4191
- C4193
- C4194
- C4195
- C4196
- C4199
dev_langs:
- C++
ms.assetid: 426f495a-43af-4906-ad2b-6e5822c09965
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 9e7f0c939f5260991d18b69fc8965e1073bff406
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-warnings-c4000-through-c4199"></a>コンパイラの警告 C4000 C4199 経由
ドキュメントのこの部分の記事には、Visual C コンパイラの警告のサブセットについてを説明します。 ここで、情報にアクセスすることができますか、**出力**ウィンドウ Visual Studio で、警告番号を選択して F1 キーを押します。  
  
> [!NOTE]
>  すべて[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]エラーまたは警告は、MSDN に記載されています。 多くの場合は、診断メッセージは、すべての使用可能な情報を提供します。 エラー メッセージに追加の情報が必要と思われる場合は、どうぞお知らせください。 このページでフィードバック フォームを使用してまたはに Visual Studio のメニュー バーを選択する**ヘルプ**、**バグの報告を**、提案やバグ レポートを送信することができますか[Microsoft Connect](http://connect.microsoft.com/VisualStudio)です。  
  
 MSDN のパブリック フォーラムに関するエラーと警告の追加サポートが必要があります。 [Visual C の言語](http://go.microsoft.com/fwlink/?LinkId=158195)に関する質問や議論は、フォーラム、[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]言語の構文とコンパイラです。 [Visual C++ 全般](http://go.microsoft.com/fwlink/?LinkId=158194)に関する質問については、フォーラム[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]するその他のフォーラムでは説明しません。 エラーと警告に関するヘルプもあります[スタック オーバーフロー](http://stackoverflow.com/)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|警告|メッセージ|  
|-------------|-------------|  
|コンパイラの警告 C4000|原因不明の警告<br /><br /> Visual C のサポート情報コマンドを選択してください。<br /><br /> [ヘルプ] メニューのまたは詳細については、テクニカル サポート ヘルプ ファイルを開く|  
|[コンパイラの警告 (レベル 4) C4001](../../error-messages/compiler-warnings/compiler-warning-level-4-c4001.md)|標準外の言語拡張 (単一行コメント) が行われています。|  
|コンパイラの警告 (レベル 1) C4002|マクロ 'identifier' に指定された実引数の数が多すぎます|  
|[コンパイラの警告 (レベル 1) C4003](../../error-messages/compiler-warnings/compiler-warning-level-1-c4003.md)|マクロ 'identifier' に指定された実引数の数が少なすぎます|  
|[コンパイラの警告 (レベル 1) C4005](../../error-messages/compiler-warnings/compiler-warning-level-1-c4005.md)|'identifier': 再定義はマクロ|  
|コンパイラの警告 (レベル 1) C4006|#undef 識別子|  
|[コンパイラの警告 (レベル 2) C4007](../../error-messages/compiler-warnings/compiler-warning-level-2-c4007.md)|'function': '属性' する必要があります|  
|コンパイラの警告 (レベル 3) C4008|'function': '属性' 属性は無視されました|  
|[コンパイラの警告 (レベル 1) C4010](../../error-messages/compiler-warnings/compiler-warning-level-1-c4010.md)|単一行コメント (//) に、行連結文字があります。|  
|[コンパイラの警告 (レベル 3) C4013](../../error-messages/compiler-warnings/compiler-warning-level-3-c4013.md)|' function' が定義されていません。extern int を返すと仮定した場合|  
|[コンパイラの警告 (レベル 1) C4015](../../error-messages/compiler-warnings/compiler-warning-level-1-c4015.md)|'識別子': ビット フィールドの型は整数でなければなりません|  
|[コンパイラの警告 (レベル 3) C4018](../../error-messages/compiler-warnings/compiler-warning-level-3-c4018.md)|'expression': signed と unsigned の数値が一致しません|  
|コンパイラの警告 (レベル 4) C4019|グローバル スコープで空行があります。|  
|[コンパイラの警告 (レベル 1) C4020](../../error-messages/compiler-warnings/compiler-warning-level-1-c4020.md)|'function': 実引数が多すぎます|  
|[コンパイラの警告 (レベル 1) C4022](../../error-messages/compiler-warnings/compiler-warning-level-1-c4022.md)|'function': ポインター実際のパラメーター 'parameter number' が一致しません|  
|コンパイラの警告 (レベル 1) C4023|'function': _based ポインターがプロトタイプ宣言されていない関数に渡されました: パラメーター 'parameter_number'|  
|[コンパイラの警告 (レベル 1) C4024](../../error-messages/compiler-warnings/compiler-warning-level-1-c4024.md)|'function': 仮引数と実際のパラメーター 'parameter_number' の種類|  
|コンパイラの警告 (レベル 1) C4025|'function': _based ポインターが可変個の引数を伴う関数に渡されました: パラメーター 'parameter_number'|  
|コンパイラの警告 (レベル 1) C4026|関数はパラメーター リストを使って宣言されています。|  
|コンパイラの警告 (レベル 1) C4027|関数はパラメーター リストなしで宣言されています。|  
|[コンパイラの警告 (レベル 1) C4028](../../error-messages/compiler-warnings/compiler-warning-level-1-c4028.md)8|仮パラメーター宣言から別の ' parameter_number'|  
|[コンパイラの警告 (レベル 1) C4029](../../error-messages/compiler-warnings/compiler-warning-level-1-c4029.md)|宣言されたパラメーター リストが定義と一致しません。|  
|コンパイラの警告 (レベル 1) C4030|関数の 2 回目の宣言で引数の数が減少しています。|  
|[コンパイラの警告 (レベル 1) C4031](../../error-messages/compiler-warnings/compiler-warning-level-1-c4031.md)|関数の 2 回目の宣言で引数の数が増加しています。|  
|[コンパイラの警告 (レベル 4) C4032](../../error-messages/compiler-warnings/compiler-warning-level-4-c4032.md)|仮パラメーター 'parameter_number' が昇格するときに別の種類|  
|コンパイラの警告 (レベル 1) C4033|'function': 値を返さなければいけません|  
|[コンパイラの警告 (レベル 1) C4034](../../error-messages/compiler-warnings/compiler-warning-level-1-c4034.md)|sizeof 演算子がサイズが 0 となったオペランドに適用されました。|  
|コンパイラの警告 (レベル 3) C4035|'function': 戻り値はありません|  
|コンパイラの警告 (レベル 1) C4036|実パラメーターとして渡される 'type' に型指定がありません|  
|コンパイラの警告 (レベル 1) C4038|'modifier': 無効なクラス修飾子|  
|コンパイラの警告 (レベル 1) C4041|コンパイラの制限: ブラウザーの出力を中止します。|  
|[コンパイラの警告 (レベル 1) C4042](../../error-messages/compiler-warnings/compiler-warning-level-1-c4042.md)|'identifier': 無効なストレージ クラスがあります。|  
|コンパイラの警告 (レベル 1) C4045|'array': 配列の境界オーバーフロー|  
|[コンパイラの警告 (レベル 1) C4047](../../error-messages/compiler-warnings/compiler-warning-level-1-c4047.md)|'operator': 'identifier1' と 'identifier2' で間接参照のレベル|  
|[コンパイラの警告 (レベル 1) C4048](../../error-messages/compiler-warnings/compiler-warning-level-1-c4048.md)|別の配列の添字: 'identifier1' と 'identifier2'|  
|[コンパイラの警告 (レベル 1) C4049](../../error-messages/compiler-warnings/compiler-warning-level-1-c4049.md)|コンパイラの制限: 行番号の出力を中止します。|  
|コンパイラの警告 (レベル 1) C4051|型変換が行われました。データが失われている可能性があります。|  
|コンパイラの警告 (レベル 4) C4052|関数に対する宣言の 1 つに可変個の引数が含まれていません。|  
|コンパイラの警告 (レベル 4) C4053|'?:' 演算に void 型の式がオペランドとして使われています。|  
|[コンパイラの警告 (レベル 2) C4056](../../error-messages/compiler-warnings/compiler-warning-level-2-c4056.md)|浮動小数点数の定数演算でオーバーフローしました。|  
|コンパイラの警告 (レベル 4) C4057|'operator': 'identifier1' と間接で若干異なる基本型を 'identifier2'|  
|コンパイラの警告 C4060|switch ステートメントに 'case' または 'default' ラベルがありません。|  
|[コンパイラの警告 (レベル 4) C4061](../../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md)|列挙型 'enumeration' のスイッチで 'identifier' が case ラベルによって明示的にハンドルされません。|  
|[コンパイラの警告 (レベル 4) C4062](../../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md)|列挙型 'enumeration' を切り替えた列挙子 'identifier' はハンドルされません|  
|コンパイラの警告 C4063|'identifier' の場合は、列挙型 'enumeration' のスイッチの有効な値ではありません。|  
|コンパイラの警告 C4064|不完全な列挙型 'enumeration' のスイッチ|  
|コンパイラの警告 C4065|switch 文に 'default' はありますが 'case' ラベルがありません。|  
|コンパイラの警告 (レベル 3) C4066|ワイド文字定数の文字列は無視されます。|  
|[コンパイラの警告 (レベル 1) C4067](../../error-messages/compiler-warnings/compiler-warning-level-1-c4067.md)|プリプロセッサ ディレクティブの後に余分な文字がありました - 改行が必要です|  
|コンパイラの警告 (レベル 1) C4068|不明なプラグマがありました。|  
|コンパイラの警告 C4069|long double は double と同じ精度です。|  
|[コンパイラの警告 (レベル 3) C4073](../../error-messages/compiler-warnings/compiler-warning-level-3-c4073.md)|初期化子がライブラリ初期化領域にあります。|  
|[コンパイラの警告 (レベル 1) C4074](../../error-messages/compiler-warnings/compiler-warning-level-1-c4074.md)|初期化子がコンパイラの予約初期化領域にあります。|  
|コンパイラの警告 (レベル 1) C4075|初期化子が不明な初期化領域にあります。|  
|コンパイラの警告 (レベル 1) C4076|'type_modifier': 型 'typename' では使用できません|  
|コンパイラの警告 (レベル 1) C4077|check_stack プラグマに不明なオプションが与えられました。|  
|[コンパイラの警告 (レベル 1) C4079](../../error-messages/compiler-warnings/compiler-warning-level-1-c4079.md)|不要なトークン 'token' が見つかりました|  
|コンパイラの警告 (レベル 1) C4080|セグメント名の識別子が必要です。'symbol' が見つかりました。|  
|コンパイラの警告 (レベル 1) C4081|'token1' が必要でしたが、'token2' が見つかりました|  
|[コンパイラの警告 (レベル 1) C4083](../../error-messages/compiler-warnings/compiler-warning-level-1-c4083.md)|' トークン ';識別子 'identifier' が見つかりました|  
|コンパイラの警告 (レベル 1) C4085|プラグマに、'on' か 'off' のパラメーターが必要です。|  
|コンパイラの警告 (レベル 1) C4086|プラグマに '1'、'2'、'4'、'8'、'16' のいずれかのパラメーターが必要です。|  
|コンパイラの警告 (レベル 1) C4087|'function': 'void' パラメーター リストで宣言されています|  
|[コンパイラの警告 (レベル 1) C4088](../../error-messages/compiler-warnings/compiler-warning-level-1-c4088.md)|'function': 実パラメーター 'parameter_number'、'parameter_number' の仮パラメーターのポインターが一致しません|  
|[コンパイラの警告 (レベル 1) C4089](../../error-messages/compiler-warnings/compiler-warning-level-1-c4089.md)|'function': 実パラメーター 'parameter_number'、'parameter_number' の仮パラメーターの種類|  
|[コンパイラの警告 (レベル 1) C4090](../../error-messages/compiler-warnings/compiler-warning-level-1-c4090.md)|'operation': 異なる 'modifier' 修飾子|  
|[コンパイラの警告 (レベル 1) C4091](../../error-messages/compiler-warnings/compiler-warning-level-1-c4091.md)|キーワード ': 'type' の左側で変数が宣言されていない場合は無視されます|  
|[コンパイラの警告 (レベル 4) C4092](../../error-messages/compiler-warnings/compiler-warning-level-4-c4092.md)|sizeof 演算子が 'unsigned long' の値を返しました。|  
|[コンパイラの警告 (レベル 2) C4094](../../error-messages/compiler-warnings/compiler-warning-level-2-c4094.md)|タグ付けされていない ' token' シンボルが宣言されていません。|  
|[コンパイラの警告 (レベル 1) C4096](../../error-messages/compiler-warnings/compiler-warning-level-1-c4096.md)|'identifier': インターフェイスは、COM インターフェイスです。IDL には出力されません。|  
|コンパイラの警告 (レベル 1) C4097|プラグマ パラメーターに 'restore' または 'off' が必要です。|  
|[コンパイラの警告 (レベル 1) C4098](../../error-messages/compiler-warnings/compiler-warning-level-1-c4098.md)|'function': 'void' 関数の値を返す|  
|[コンパイラの警告 (レベル 2) C4099](../../error-messages/compiler-warnings/compiler-warning-level-2-c4099.md)|'identifier': 'object_type1' 使われて 'object_type2' を使用して 1 つ目の種類名|  
|[コンパイラの警告 (レベル 4) C4100](../../error-messages/compiler-warnings/compiler-warning-level-4-c4100.md)|'identifier': 未参照仮パラメーター|  
|[コンパイラの警告 (レベル 3) C4101](../../error-messages/compiler-warnings/compiler-warning-level-3-c4101.md)|'identifier': 参照されていないローカル変数|  
|コンパイラの警告 (レベル 3) C4102|'label': 参照されていないラベル|  
|[コンパイラの警告 (レベル 1) C4103](../../error-messages/compiler-warnings/compiler-warning-level-1-c4103.md)|'filename': #pragma pack(pop) がないため配置ヘッダーを含めた後に変更された可能性があります|  
|コンパイラの警告 (レベル 1) C4109|予期しない識別子 'identifier' が含まれていました|  
|コンパイラの警告 (レベル 1) C4112|#行 1 と 'line_count' までの整数が必要です。|  
|[コンパイラの警告 (レベル 1) C4113](../../error-messages/compiler-warnings/compiler-warning-level-1-c4113.md)|'identifier1' と 'identifier2' のパラメーター リスト|  
|[コンパイラの警告 (レベル 1) C4114](../../error-messages/compiler-warnings/compiler-warning-level-1-c4114.md)|同じ型の修飾子が 2 度以上使われています。|  
|コンパイラの警告 (レベル 1 およびレベル 4) C4115|'type': 名前付きの型をかっこで|  
|[コンパイラの警告 (レベル 1) C4116](../../error-messages/compiler-warnings/compiler-warning-level-1-c4116.md)|無名の型が式のかっこの中で定義されました。|  
|コンパイラの警告 (レベル 1) C4117|マクロ名 'name' に予約されていますが、"command"は無視されます。|  
|コンパイラの警告 (レベル 1) C4119|異なったシンボリックベース 'base1' と 'base2' が指定されています。|  
|コンパイラの警告 (レベル 1) C4120|_based ポインターとベース以外のポインターが式に含まれています。|  
|[コンパイラの警告 (レベル 4) C4121](../../error-messages/compiler-warnings/compiler-warning-level-4-c4121.md)|'symbol': メンバーのアラインメントはパッキングに影響|  
|コンパイラの警告 (レベル 1) C4122|'function': alloc_text プラグマ C リンケージを持つ関数|  
|コンパイラの警告 (レベル 1) C4123|式に _based ポインター間の変換が含まれていますが、2 つのポインターのベース式が異なります。|  
|[コンパイラの警告 (レベル 1) C4124](../../error-messages/compiler-warnings/compiler-warning-level-1-c4124.md)|キーワード __fastcall が使われましたが スタックチェッキングがあるため低速コードになります。|  
|コンパイラの警告 (レベル 4) C4125|8 進数のエスケープ シーケンスが、10 進数のところで中断されました。|  
|[コンパイラの警告 (レベル 4) C4127](../../error-messages/compiler-warnings/compiler-warning-level-4-c4127.md)|条件式が定数です。|  
|[コンパイラの警告 (レベル 1) C4129](../../error-messages/compiler-warnings/compiler-warning-level-1-c4129.md)|'character': 認識できない文字エスケープ シーケンス|  
|コンパイラの警告 (レベル 4) C4130|'operator': 文字列定数のアドレスで論理演算|  
|コンパイラの警告 (レベル 4) C4131|'function': 旧スタイルの宣言の使用|  
|コンパイラの警告 (レベル 4) C4132|'object': const オブジェクトを初期化する必要があります|  
|[コンパイラの警告 (レベル 3) C4133](../../error-messages/compiler-warnings/compiler-warning-level-3-c4133.md)|'expression': 'type1' から 'type2' に互換性のない型|  
|コンパイラの警告 C4137|'function': 浮動小数点関数の戻り値はありません|  
|コンパイラの警告 (レベル 1) C4138|始まりのデリミターがない閉じのコメントデリミター (*/) が見つかりました。|  
|コンパイラの警告 (レベル 1) C4141|'modifier': 複数回使用|  
|[コンパイラの警告 (レベル 1) C4142](../../error-messages/compiler-warnings/compiler-warning-level-1-c4142.md)|型が再定義されていますが、それはコード生成上何の効果もありません。|  
|コンパイラの警告 (レベル 1) C4143|'same_seg' プラグマはサポートされていません ; 代わりに __based を使用してください。|  
|[コンパイラの警告 (レベル 1) C4144](../../error-messages/compiler-warnings/compiler-warning-level-1-c4144.md)|'expression': switch 式としてのリレーショナル表現|  
|コンパイラの警告 (レベル 1) C4145|'expression1': switch 式として関係式'expression2' と見なされます|  
|[コンパイラの警告 (レベル 2) C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|符号付きの値を代入する変数は、符号付き型にキャストしなければなりません。|  
|[コンパイラの警告 (レベル 2) C4150](../../error-messages/compiler-warnings/compiler-warning-level-2-c4150.md)|不完全な型 'type' へのポインターの削除ないデストラクターが呼び出されます|  
|コンパイラの警告 (レベル 4) C4152|関数へのポインターがデータへのポインターに変換されました。|  
|コンパイラの警告 (レベル 1) C4153|関数へのポインターがデータへのポインターに変換されました。|  
|[コンパイラの警告 (レベル 1) C4154](../../error-messages/compiler-warnings/compiler-warning-level-1-c4154.md)|配列の delete が定義されていません。配列は、ポインターに変換されます。|  
|コンパイラの警告 (レベル 1) C4155|'delete' の配列でない形式を使った配列の削除は、定義されていません。|  
|[コンパイラの警告 (レベル 2) C4156](../../error-messages/compiler-warnings/compiler-warning-level-2-c4156.md)|'delete' の配列でない形式を使った配列の削除は、定義されていません。|  
|[コンパイラの警告 (レベル 1) C4157](../../error-messages/compiler-warnings/compiler-warning-level-1-c4157.md)|プラグマは無視されます。|  
|コンパイラの警告 (レベル 1) C4158|#pragma pointers_to_members (full_generality, 'inheritance_type') と仮定した場合|  
|[コンパイラの警告 (レベル 3) C4159](../../error-messages/compiler-warnings/compiler-warning-level-3-c4159.md)|#プラグマ ' pragma'(pop,...): 以前にプッシュされた識別子 'identifier' がポップされます。|  
|コンパイラの警告 (レベル 1) C4160|#プラグマ ' pragma'(pop,...): 以前にプッシュされた識別子 'identifier' が見つかりませんでした|  
|コンパイラの警告 (レベル 3) C4161|#プラグマ ' pragma'(pop...): ポップがプッシュ|  
|[コンパイラの警告 (レベル 1) C4162](../../error-messages/compiler-warnings/compiler-warning-level-1-c4162.md)|'identifier': 見つかった C リンケージを持つ関数|  
|コンパイラの警告 (レベル 1) C4163|'identifier': 組み込み関数として使用できません。|  
|コンパイラの警告 (レベル 1) C4164|'function': 組み込み関数が宣言されていません|  
|コンパイラの警告 (レベル 1) C4165|'HRESULT' は 'bool' に変換されようとしています。続行しますか?|  
|コンパイラの警告 (レベル 1) C4166|コンストラクターとデストラクターの呼び出し規約が無効です。|  
|コンパイラの警告 (レベル 1) C4167|'function': 組み込み関数としてのみ使用できます|  
|コンパイラの警告 (レベル 1) C4168|コンパイラの制限: デバッガー タイプではありません、プログラム データベース 'database' を削除および再構築|  
|[コンパイラの警告 (レベル 1) C4172](../../error-messages/compiler-warnings/compiler-warning-level-1-c4172.md)|ローカル変数またはテンポラリのアドレスを返します。|  
|コンパイラの警告 (レベル 1) C4174|'name': #pragma コンポーネントとして使用できません。|  
|コンパイラの警告 (レベル 1) C4175|#プラグマ component(browser, on): ブラウザー情報は、コマンドラインで最初に指定する必要があります|  
|コンパイラの警告 (レベル 1) C4176|'subcomponent': #pragma コンポーネント ブラウザーの不明なサブコンポーネント|  
|コンパイラの警告 (レベル 1) C4177|#プラグマ 'pragma' はグローバル スコープまたは名前空間スコープでのみ使用する必要があります。|  
|コンパイラの警告 (レベル 1) C4178|case 定数 'constant' が switch 式の型としては大きすぎます|  
|コンパイラの警告 (レベル 4) C4179|'//*': として解析 '/' および '/\*': 標準との混同 '//' のコメント|  
|コンパイラの警告 (レベル 1) C4180|関数型へ適用された修飾子は無効なため、無視されます。|  
|コンパイラの警告 C4181|参照型に適用された修飾子は無視されました。|  
|コンパイラの警告 (レベル 1) C4182|#入れ子のレベルは 'nest_count' deep です。無限再帰の可能性|  
|[コンパイラの警告 (レベル 1) C4183](../../error-messages/compiler-warnings/compiler-warning-level-1-c4183.md)|'identifier': 戻り値の型がありません'int' を返すメンバー関数と見なされます|  
|コンパイラの警告 (レベル 1) C4185|不明な #import の属性 'attribute' を無視します|  
|コンパイラの警告 (レベル 1) C4186|#インポート属性 'attribute' が 'argument_count' 引数が必要です。無視されます。|  
|コンパイラの警告 (レベル 1) C4187|#インポート属性 'attribute1' と 'attribute2' は互換性がありません。両方とも無視されます。|  
|コンパイラの警告 (レベル 1) C4188|定数式が整数ではありません。|  
|コンパイラの警告 (レベル 4) C4189|'identifier': ローカル変数が初期化されて、参照されていません|  
|[コンパイラの警告 (レベル 1) C4190](../../error-messages/compiler-warnings/compiler-warning-level-1-c4190.md)|'identifier1' を指定すると、C リンケージを持つ UDT 'identifier2' C と互換性がないを返す|  
|コンパイラの警告 (レベル 3) C4191|' operator/operation ': 'type_of_expression' から 'type_required' \nCalling への安全でない変換結果のポインターを使用して関数が原因、プログラムが失敗するには|  
|[コンパイラの警告 (レベル 3) C4192](../../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)|タイプ ライブラリ 'library' のインポート中に 'identifier' を自動的に除外|  
|コンパイラの警告 (レベル 3) C4193|#プラグマ warning (pop): いない一致する '#pragma warning (push)'|  
|コンパイラの警告 (レベル 1) C4194|#プラグマ start_map_region は入れ子にすることはできません。無視されます。|  
|コンパイラの警告 (レベル 1) C4195|#プラグマ stop_map_region が一致する #pragma start_map_region; なしで使用無視されます。|  
|コンパイラの警告 (レベル 1) C4196|'%$L' または '%$L' が期待されています。'%$L' が見つかりました|  
|[コンパイラの警告 (レベル 3) C4197](../../error-messages/compiler-warnings/compiler-warning-level-3-c4197.md)|'type': キャストのトップレベルの volatile は無視されます|  
|コンパイラの警告 (レベル 1、レベル 2、レベル 3、およびレベル 4) C4199|%s|
