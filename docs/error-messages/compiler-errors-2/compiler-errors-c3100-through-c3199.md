---
title: "コンパイラ エラー C3100 C3199 を通じて |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
helpviewer_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
dev_langs:
- C++
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc05c482c112753ffeb52d49b1badcfcab549cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-errors-c3100-through-c3199"></a>コンパイラ エラー C3100 C3199 経由

ドキュメントのこのセクションの記事では、コンパイラによって生成されるエラー メッセージのサブセットについて説明します。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>エラー メッセージ

|Error|メッセージ|
|-----------|-------------|
|[コンパイラ エラー C3100](compiler-error-c3100.md)|'*識別子*': 不明な属性の修飾子|
|[コンパイラ エラー C3101](compiler-error-c3101.md)|名前付き属性引数に無効な式 '*識別子*'|
|コンパイラ エラー C3102|互換性のために残されています。|
|[コンパイラ エラー C3103](compiler-error-c3103.md)|'*識別子*': 名前付き引数を繰り返す|
|[コンパイラ エラー C3104](compiler-error-c3104.md)|無効な属性引数|
|コンパイラ エラー C3105|'*シンボル*': 属性として使用することはできません|
|[コンパイラ エラー C3106](compiler-error-c3106.md)|'*属性*': 名前なし引数が名前付き引数に付ける必要があります|
|コンパイラ エラー C3107|'*属性*': ネイティブ属性のメンバー関数を定義することはできません|
|コンパイラ エラー C3108|初期化子リストが式ではないために、型を推測できません。|
|コンパイラ エラー C3109|'*識別子*': インターフェイス メソッドは、'_ _stdcall' または '_ _cdecl' 呼び出し規約を使用する必要があります|
|[コンパイラ エラー C3110](compiler-error-c3110.md)|'*関数*': COM インターフェイスのメソッドをオーバー ロードすることはできません|
|コンパイラ エラー C3111|初期化子リストは、テンプレート パラメーターの既定の引数として使用できません。|
|コンパイラ エラー C3112|'*インターフェイス*': インターフェイスはグローバルでのみ宣言可能または名前空間スコープ|
|[コンパイラ エラー C3113](compiler-error-c3113.md)|'インターフェイス/enum' がテンプレートまたはジェネリックにすることはできません。|
|[コンパイラ エラー C3114](compiler-error-c3114.md)|'*識別子*': 名前付き属性引数を有効ではありません|
|[コンパイラ エラー C3115](compiler-error-c3115.md)|'*属性*': この属性は許可されません'*構築*'|
|[コンパイラ エラー C3116](compiler-error-c3116.md)|'*指定子*': インターフェイス メソッドに対する無効なストレージ クラス|
|[コンパイラ エラー C3117](compiler-error-c3117.md)|'*インターフェイス*': インターフェイスは、1 つの基本クラスを持つことができますのみ|
|[コンパイラ エラー C3118](compiler-error-c3118.md)|'*インターフェイス*': インターフェイスは仮想継承をサポートしていません|
|コンパイラ エラー C3119|alignas(void) は許可されていません|
|[コンパイラ エラー C3120](compiler-error-c3120.md)|'*識別子*': インターフェイス メソッドは、可変個引数リストを取得できません。|
|[コンパイラ エラー C3121](compiler-error-c3121.md)|クラスの GUID を変更することはできません*クラス*'|
|コンパイラ エラー C3122|'*インターフェイス*': WinRT ジェネリック インターフェイスは GUID を持つことはできません|
|コンパイラ エラー C3123|WinRT ジェネリック インターフェイスは、制約を持つことはできません。|
|コンパイラ エラー C3124|'signed char' は有効な WinRT データ型ではありません。 代わりに、'unsigned char'、'wchar_t' または 'signed short' を使用します。|
|コンパイラ エラー C3125|'*型*': 型直接的または間接的に派生できません 'platform::exception' から|
|[コンパイラ エラー C3126](compiler-error-c3126.md)|共用体を定義できません '*共用体*'内でマネージまたは WinRT 型'*型*'。|
|コンパイラ エラー C3127|'*型*':'*特徴*' 特徴は WinRT ref クラスでのみ使用できます|
|コンパイラ エラー C3128|'*型*'によって導入された vtable がありませんでした'*型*'|
|コンパイラ エラー C3129|'*型*': _ _default_vptr_for_base は、ローカルに定義されたポリモーフィックな型およびベースでのみ使用できます|
|[コンパイラ エラー C3130](compiler-error-c3130.md)|内部コンパイラ エラー: が pdb ファイルに挿入されたコード ブロックを書き込みに失敗しました|
|[コンパイラ エラー C3131](compiler-error-c3131.md)|プロジェクトは、'name' プロパティに 'module' 属性を持つ必要があります。|
|[コンパイラ エラー C3132](compiler-error-c3132.md)|'*パラメーター*': パラメーター配列は、'1 次元のマネージまたは WinRT 配列' 型の仮引数にのみ適用できます|
|[コンパイラ エラー C3133](compiler-error-c3133.md)|C++ varargs に属性を適用することはできません。|
|[コンパイラ エラー C3134](compiler-error-c3134.md)|'*値*': 属性引数の値'*引数*'有効な型を持たない'*型*'|
|[コンパイラ エラー C3135](compiler-error-c3135.md)|'*識別子*': プロパティは 'const' を持つことはできませんまたは 'volatile' 型|
|[コンパイラ エラー C3136](compiler-error-c3136.md)|'*インターフェイス*': COM インターフェイスは、別の COM インターフェイスからのみ継承できます'*インターフェイス*' COM インターフェイスではありません|
|[コンパイラ エラー C3137](compiler-error-c3137.md)|'*識別子*': プロパティは初期化できません|
|[コンパイラ エラー C3138](compiler-error-c3138.md)|'*識別子*': は'*属性*' インターフェイスは IDispatch、または IDispatch から継承したインターフェイスから継承する必要があります|
|[コンパイラ エラー C3139](compiler-error-c3139.md)|'*型*': メンバーなしに UDT をエクスポートすることはできません|
|[コンパイラ エラー C3140](compiler-error-c3140.md)|同じコンパイル単位内の複数の 'module' 属性を持つことはできません。|
|[コンパイラ エラー C3141](compiler-error-c3141.md)|'*インターフェイス*': インターフェイスはパブリック継承のみをサポート|
|[コンパイラ エラー C3142](compiler-error-c3142.md)|'*プロパティ*': プロパティのアドレスを取得できません|
|コンパイラ エラー C3143|'*引数*': 属性引数は、複数の値を持つことはできません|
|コンパイラ エラー C3144|'*属性*': 属性には、明示的な引数が必要です'*引数*' は名前がありません。|
|[コンパイラ エラー C3145](compiler-error-c3145.md)|'*識別子*': グローバルまたは静的変数には、マネージまたは WinRT 型はありません'*型*'。|
|コンパイラ エラー C3146|互換性のために残されています。|
|コンパイラ エラー C3147|互換性のために残されています。|
|コンパイラ エラー C3148|互換性のために残されています。|
|[コンパイラ エラー C3149](compiler-error-c3149.md)|'*型*': 最上位せずに、この型をここでは使用できません'*トークン*'|
|[コンパイラ エラー C3150](compiler-error-c3150.md)|'*構築*':'*属性*' クラス、構造体、インターフェイス、配列またはポインターにのみ適用できます|
|コンパイラ エラー C3151|互換性のために残されています。|
|[コンパイラ エラー C3152](compiler-error-c3152.md)|'*関数*':'*キーワード*' クラス、構造体、または仮想メンバー関数にのみ適用できます|
|[コンパイラ エラー C3153](compiler-error-c3153.md)|'*インターフェイス*': インターフェイスのインスタンスを作成することはできません|
|[コンパイラ エラー C3154](compiler-error-c3154.md)|予想 ',' は、省略記号の前にします。 非コンマ区切りの省略記号パラメーター配列関数でサポートされていません。|
|[コンパイラ エラー C3155](compiler-error-c3155.md)|属性はプロパティ インデクサーでは使用できません。|
|[コンパイラ エラー C3156](compiler-error-c3156.md)|'*クラス*': マネージまたは WinRT 型のローカル定義を持つことはできません|
|[コンパイラ エラー C3157](compiler-error-c3157.md)|ParamArray 属性は、最後のパラメーターにのみ適用できます。|
|コンパイラ エラー C3158|'*関数*':'*キーワード*' 仮想メンバー関数にのみ適用できます|
|[コンパイラ エラー C3159](compiler-error-c3159.md)|'*識別子*': 値型へのポインターの配列を宣言することはできません|
|[コンパイラ エラー C3160](compiler-error-c3160.md)|'*型*': マネージまたは WinRT クラスのデータ メンバーは、この型を持つことはできません|
|[コンパイラ エラー C3161](compiler-error-c3161.md)|'*インターフェイス*': 入れ子のクラス、構造体、またはインターフェイスをインターフェイスではありません有効なクラスまたは構造体でインターフェイスを入れ子になったことはできません。|
|[コンパイラ エラー C3162](compiler-error-c3162.md)|'*型*': デストラクターを含む参照型は、静的データ メンバーの型として使用できません'*メンバー*'|
|[コンパイラ エラー C3163](compiler-error-c3163.md)|'*クラス*': 属性を前の宣言と整合性がありません|
|コンパイラ エラー C3164|互換性のために残されています。|
|コンパイラ エラー C3165|'*値*': 整数または浮動小数点値に変換できません|
|[コンパイラ エラー C3166](compiler-error-c3166.md)|互換性のために残されています。 '*型*': マネージまたは WinRT クラスのデータ メンバーが型を持つことはできません'*pointer_type*に内部*managed_pointer_type*'|
|[コンパイラ エラー C3167](compiler-error-c3167.md)|.NET Framework を初期化できません: インストールされていることを確認|
|[コンパイラ エラー C3168](compiler-error-c3168.md)|'*型*': 基になる列挙型の型が正しくありません。|
|コンパイラ エラー C3169|'*型*': から 'auto' の型を推測できません'*型*'|
|[コンパイラ エラー C3170](compiler-error-c3170.md)|プロジェクトで別のモジュール識別子を持つことはできません。|
|[コンパイラ エラー C3171](compiler-error-c3171.md)|'*モジュール*': プロジェクトで異なるモジュールの属性を指定することはできません|
|[コンパイラ エラー C3172](compiler-error-c3172.md)|'*識別子*': プロジェクトで異なる idl_module の属性を指定することはできません|
|[コンパイラ エラー C3173](compiler-error-c3173.md)|idl マージでバージョンが一致しません|
|[コンパイラ エラー C3174](compiler-error-c3174.md)|モジュール属性が指定されませんでした。|
|[コンパイラ エラー C3175](compiler-error-c3175.md)|'*関数*': アンマネージ関数からマネージ型のメソッドを呼び出すことはできません'*関数*'|
|[コンパイラ エラー C3176](compiler-error-c3176.md)|'*型*': ローカルの値の型を宣言することはできません|
|コンパイラ エラー C3177|含む型への変換関数を持つことはできません '*型*'|
|コンパイラ エラー C3178|'*型*': 既定の引数を持つ関数で ParamArray は使用できません|
|[コンパイラ エラー C3179](compiler-error-c3179.md)|名前のないマネージまたは WinRT 型は許可されていません|
|[コンパイラ エラー C3180](compiler-error-c3180.md)|'*型*': 名前のメタデータの限度を超えています'*数*' 文字。|
|[コンパイラ エラー C3181](compiler-error-c3181.md)|'*型*': 無効な演算子のオペランド*演算子*|
|[コンパイラ エラー C3182](compiler-error-c3182.md)|'*型*': マネージまたは WinRT 型の中でメンバーを使用して宣言または access 宣言はできません|
|[コンパイラ エラー C3183](compiler-error-c3183.md)|名前のないクラス、構造体または共用体マネージまたは WinRT 型の内部では定義できません '*クラス*'|
|コンパイラ エラー C3184|互換性のために残されています。|
|[コンパイラ エラー C3185](compiler-error-c3185.md)|'typeid': マネージまたは WinRT 型で使用される '*型*' を使用して '*演算子*' 代わりに|
|コンパイラ エラー C3186|互換性のために残されています。|
|[コンパイラ エラー C3187](compiler-error-c3187.md)|'*識別子*': はのみ、関数の本体で使用できます|
|コンパイラ エラー C3188|互換性のために残されています。|
|[コンパイラ エラー C3189](compiler-error-c3189.md)|' typeid <*宣言子*>': この構文は、不要になったサポート、use::typeid 代わりに|
|[コンパイラ エラー C3190](compiler-error-c3190.md)|'*宣言子*'の指定されたテンプレート引数はすべてのメンバー関数の明示的なインスタンス化'*型*'|
|コンパイラ エラー C3191|互換性のために残されています。|
|[コンパイラ エラー C3192](compiler-error-c3192.md)|構文エラー: '^' プレフィックス演算子ではありません ('sizeof...'' *' ですか?)|
|コンパイラ エラー C3193|'*構築*': 必要があります '/clr' または '/ZW' コマンド ライン オプション|
|[コンパイラ エラー C3194](compiler-error-c3194.md)|'*型*': 値型は、代入演算子を持つことはできません|
|[コンパイラ エラー C3195](compiler-error-c3195.md)|'*キーワード*': 予約されており、ref クラスまたは値型のメンバーとして使用することはできません。 'Operator' キーワードを使用して CLR または WinRT 演算子を定義する必要があります。|
|[コンパイラ エラー C3196](compiler-error-c3196.md)|'*識別子*': 複数回使用|
|[コンパイラ エラー C3197](compiler-error-c3197.md)|'*キーワード*': 定義でのみ使用できます|
|[コンパイラ エラー C3198](compiler-error-c3198.md)|無効な浮動小数点プラグマの使用: fenv_access プラグマは precise モードでのみ動作|
|[コンパイラ エラー C3199](compiler-error-c3199.md)|無効な浮動小数点プラグマの使用: 例外は precise でないモードでサポートされていません|
