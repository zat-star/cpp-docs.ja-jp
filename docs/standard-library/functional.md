---
title: "&lt; 機能 &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<functional>"
  - "functional/std::<functional>"
  - "std.<functional>"
  - "std::<functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファンクター"
  - "functional ヘッダー"
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; 機能 &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

作成に役立つ標準ライブラリ関数を定義 *関数オブジェクト*— ファンクターとも呼ばれる — とそれらのバインダー。 関数オブジェクトは、`operator()` を定義するオブジェクトの種類です。 関数オブジェクトは関数ポインターとしても使用できますが、一般的に、関数オブジェクトは、関数呼び出しの実行中にアクセスできる追加情報を格納するために使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
#include <functional>  
```  
  
## <a name="remarks"></a>解説  
 アルゴリズムでは、単項および二項という 2 種類の関数オブジェクトが使用されます。 単項関数オブジェクトは 1 つの引数を必要とし、二項関数オブジェクトは 2 つの引数を必要とします。 関数オブジェクトと関数ポインターは述語としてアルゴリズムに渡すことができますが、関数オブジェクトは適応性があり、STL のスコープ、柔軟性、効率が向上します。 たとえば、値をアルゴリズムに渡す前に、その値を関数にバインドする必要がある場合は、関数ポインターを使用できないことがあります。 関数アダプターを利用すると、関数ポインターが、値にバインドできる適応性のある関数オブジェクトに変換されます。 ヘッダー \< 機能> を適応性のある関数オブジェクトとして呼び出せる関数メンバーができるメンバー関数アダプターも含まれます。 関数が引数と戻り値の型を指定する入れ子になった型宣言を持っている場合、それらの関数は適応性があります。 C++ 標準では、すべての標準オブジェクト クラスで、unary_function 基底クラスや binary_function 基底クラスから継承することによって、この適応性を実装する必要があります。 関数オブジェクトとそのアダプターを使用すると、STL で既存のアプリケーションをアップグレードでき、STL と C++ プログラミング環境との統合に役立てることができます。  
  
  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 内の関数オブジェクトの実装 \< 機能> を含む *透過的な演算子のファンクター*, 、関数オブジェクトは、標準の特殊化し、テンプレート パラメーターを受け取らないあり関数の引数の完全転送と結果の完全取得を実行します。 この機能は、C++14 ドラフト標準の仕様の一部です。 これらのテンプレートの特殊化では、算術演算子のファンクター、比較演算子のファンクター、論理演算子のファンクター、ビットごとの演算子のファンクターを呼び出すときに、引数の型を指定する必要はありません。 ユーザー独自の型または異なる種類の型の組み合わせに対して算術演算子、比較演算子、論理演算子、ビットごとの演算子をオーバーロードしてから、透過的な演算子のファンクターを関数の引数として使用できます。 たとえば場合、型 *MyType* を実装する `operator<`, 、呼び出すことができます `sort(my_collection.begin(), my_collection.end(), less<>())` 型を明示的に指定する代わりに `sort(my_collection.begin(), my_collection.end(), less<MyType>())`します。  
  
## <a name="c11c14-implementation"></a>C++11/C++14 実装  
 C++11/C++14 の Visual C++ 実装では、次の機能が追加されます。  
  
-   A *呼び出しシグネチャ* に続くかっこで囲まれたコンマ区切りリスト 0 個以上の引数型の戻り値の型の名前を指定します。  
  
-   A *呼び出し可能型* 関数、メンバー関数へのポインター、メンバー データへのポインター、またはオブジェクトを持つは関数呼び出し演算子の左側にすぐに表示できるクラス型へのポインターです。  
  
-   A *呼び出し可能オブジェクト* 呼び出し可能型のオブジェクトです。  
  
-   A *呼び出しラッパーの型* は、呼び出し可能オブジェクトを保持し、そのオブジェクトに転送される呼び出し操作をサポートする型です。  
  
-   A *呼び出しラッパー* 呼び出しラッパー型のオブジェクトです。  
  
-   A *ターゲット オブジェクト* 呼び出しラッパー オブジェクトによって保持される呼び出し可能オブジェクトです。  
  
 擬似関数 `INVOKE(f, t1, t2, ..., tN)` は、次のいずれかを意味します。  
  
- `(t1.*f)(t2, ..., tN)`。`f` がクラス `T` のメンバー関数へのポインターであり、`t1` が型 `T` のオブジェクト、型 `T` のオブジェクトへの参照、`T` から派生した型のオブジェクトへの参照のいずれかである場合。  
  
- `((*t1).*f)(t2, ..., tN)`。`f` がクラス `T` のメンバー関数へのポインターであり、`t1` が上で説明した以外の型のオブジェクトである場合。  
  
- `t1.*f`。N == 1 で、`f` がクラス `T` のメンバー データへのポインターであり、`t1` が型 `T` のオブジェクト、型 `T` のオブジェクトへの参照、`T` から派生した型のオブジェクトへの参照のいずれかである場合。  
  
- `(*t1).*f`。N == 1 で、`f` がクラス `T` のメンバー データへのポインターであり、`t1` が上で説明した以外の型のオブジェクトである場合。  
  
- `f(t1, t2, ..., tN)`。上記のいずれのケースにも該当しない場合。  
  
 擬似関数 `INVOKE(f, t1, t2, ..., tN, R)` は、暗黙的に `INVOKE(f, t1, t2, ..., tN)` に変換される `R` を意味します。  
  
 呼び出しラッパーがある場合、 *弱い結果型*, 、そのメンバー型の型 `result_type` 型に基づく `T` 次のように、ラッパーのターゲット オブジェクトの。  
  
-   `T` が関数へのポインターである場合、`result_type` は 戻り値の型 `T` のシノニムになります。  
  
-   `T` がメンバー関数へのポインターである場合、`result_type` は 戻り値の型 `T` のシノニムになります。  
  
-   `T` がメンバー型 `result_type` を持つクラス型である場合、`result_type` は `T::result_type` のシノニムになります。  
  
-   それ以外の場合は、メンバー `result_type` は存在しません。  
  
 すべての呼び出しラッパーには、移動コンストラクターとコピー コンストラクターが含まれています。 A *単純な呼び出しラッパー* を持つ、代入演算子がコピー コンス トラクター、移動コンス トラクターと代入演算子が例外をスローしない呼び出しラッパーです。 A *転送呼び出しラッパー* 、任意の引数リストを使用して呼び出すことができる呼び出しラッパーであり、ラップされた呼び出し可能オブジェクトを参照として引数を提供します。 すべての右辺値引数は右辺値参照として渡され、左辺値引数は左辺値参照として渡されます。  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[bad_function_call](../standard-library/bad-function-call-class.md)|示すためにスローされる例外への呼び出しを表すクラス `operator()` 上、 [関数](../standard-library/function-class.md) オブジェクトが空であるために、オブジェクトが失敗しました。|  
|[binary_negate](../Topic/binary_negate%20Class.md)|指定した二項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。|  
|[binder1st](../standard-library/binder1st-class.md)|指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。|  
|[binder2nd](../standard-library/binder2nd-class.md)|指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。|  
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|参照引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。|  
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|ポインター引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。|  
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|参照引数による初期化を行うときに、1 つの引数を使用する const メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。|  
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|ポインター引数による初期化を行うときに、1 つの引数を使用する const メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。|  
|[関数](../standard-library/function-class.md)|呼び出し可能オブジェクトをラップするクラス。|  
|[ハッシュ](../standard-library/hash-class.md)|値のハッシュ コードを計算するクラス。|  
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|`bind` を呼び出すことによって特定の型が生成されるかどうかをテストするクラス。|  
|[is_placeholder](../Topic/is_placeholder%20Class.md)|特定の型がプレースホルダーであるかどうかをテストするクラス。|  
|[mem_fun_ref_t](../Topic/mem_fun_ref_t%20Class.md)|使用するアダプター クラス、 **non_const** 参照引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。|  
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|使用するアダプター クラス、 **non_const** ポインター引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。|  
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|使用するアダプター クラス、 **non_const** メンバー関数を 1 つの引数の参照引数による初期化を行うときは、二項関数オブジェクトとして呼び出せるようにします。|  
|[mem_fun1_t](../Topic/mem_fun1_t%20Class.md)|使用するアダプター クラス、 **non_const** をポインター引数による初期化を行うときは、二項関数オブジェクトとして呼び出せるようにする単一の引数を取るメンバー関数。|  
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|二項関数ポインターを適応性のある二項関数に変換します。|  
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|単項関数ポインターを適応性のある単項関数に変換します。|  
|[reference_wrapper](../Topic/reference_wrapper%20Class.md)|参照をラップするクラス。|  
|[result_of](../standard-library/result-of-class2.md)|ラップされた呼び出し可能オブジェクトの戻り値の型を保持する構造体。|  
|[unary_negate](../standard-library/unary-negate-class.md)|指定した単項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[バインド](../Topic/%3Cfunctional%3E%20functions.md#bind_function)|呼び出し可能オブジェクトに引数をバインドします。|  
|[bind1st](../Topic/%3Cfunctional%3E%20functions.md#bind1st_function)|指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。|  
|[bind2nd](../Topic/%3Cfunctional%3E%20functions.md#bind2nd_function)|指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。|  
|[bit_and](../Topic/%3Cfunctional%3E%20functions.md#bit_and_function)|2 つのパラメーターのビットごとの論理 AND (二項演算子 &) を返します。|  
|[bit_not](../Topic/%3Cfunctional%3E%20functions.md#bit_not_function)|パラメーターのビットごとの論理補数 (演算子 ~) を返します。|  
|[bit_or](../Topic/%3Cfunctional%3E%20functions.md#bit_or_function)|ビットごとの論理和を返します (演算子 &#124;) の 2 つのパラメーターです。|  
|[bit_xor](../Topic/%3Cfunctional%3E%20functions.md#bit_xor_function)|2 つのパラメーターのビットごとの論理 XOR (演算子 ^) を返します。|  
|[cref](../Topic/%3Cfunctional%3E%20functions.md#cref_function)|引数から const の `reference_wrapper` を構築します。|  
|[mem_fn](../Topic/%3Cfunctional%3E%20functions.md#mem_fn_function)|単純な呼び出しラッパーを生成します。|  
|[mem_fun](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_function)|ポインター引数による初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。|  
|[mem_fun_ref](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_ref_function)|参照引数による初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。|  
|[not1](../Topic/%3Cfunctional%3E%20functions.md#not1_function)|単項述語の補数を返します。|  
|[not2](../Topic/%3Cfunctional%3E%20functions.md#not2_function)|二項述語の補数を返します。|  
|[ptr_fun](../Topic/%3Cfunctional%3E%20functions.md#ptr_fun_function)|単項関数ポインターと二項関数ポインターをそれぞれ適応性のある単項関数および二項関数に変換するために使用されるヘルパー テンプレート関数。|  
|[ref](../Topic/%3Cfunctional%3E%20functions.md#ref_function)|引数から `reference_wrapper` を構築します。|  
|[スワップ](../Topic/%3Cfunctional%3E%20functions.md#swap_function)|2 つの `function` オブジェクトを交換します。|  
  
### <a name="structs"></a>構造体  
  
|||  
|-|-|  
|[binary_function](../Topic/binary_function%20Struct.md)|二項関数オブジェクトを提供する派生クラスによって継承される可能性がある型を定義する空の基底クラス。|  
|[除算](../standard-library/divides-struct.md)|クラスには、指定した値型の要素に対して算術演算 (除算) を実行する定義済みの関数オブジェクトが用意されています。|  
|[equal_to](../standard-library/equal-to-struct.md)|指定した型の値がその型の他の値と等しいかどうかをテストする二項述語。|  
|[大きい値](../standard-library/greater-struct.md)|指定した型の値がその型の他の値よりも大きいかどうかをテストする二項述語。|  
|[greater_equal](../standard-library/greater-equal-struct.md)|指定した型の値がその型の他の値以上であるかどうかをテストする二項述語。|  
|[以下](../standard-library/less-struct.md)|指定した型の値がその型の他の値よりも小さいかどうかをテストする二項述語。|  
|[less_equal](../standard-library/less-equal-struct.md)|指定した型の値がその型の他の値以下であるかどうかをテストする二項述語。|  
|[logical_and](../Topic/logical_and%20Struct.md)|クラスには、指定した値型の要素に対して論理積演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|  
|[logical_not](../Topic/logical_not%20Struct.md)|クラスには、指定した値型の要素に対して論理否定演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|  
|[logical_or](../standard-library/logical-or-struct.md)|クラスには、指定した値型の要素に対して論理和演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|  
|[マイナス](../standard-library/minus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (減算) を実行する定義済みの関数オブジェクトが用意されています。|  
|[剰余](../standard-library/modulus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (剰余) を実行する定義済みの関数オブジェクトが用意されています。|  
|[乗算](../standard-library/multiplies-struct.md)|クラスには、指定した値型の要素に対して算術演算 (乗算) を実行する定義済みの関数オブジェクトが用意されています。|  
|[負数化します。](../standard-library/negate-struct.md)|クラスには、要素の値の負数を返す定義済みの関数オブジェクトが用意されています。|  
|[not_equal_to](../standard-library/not-equal-to-struct.md)|指定した型の値がその型の他の値と等しくないかどうかをテストする二項述語。|  
|[プラス](../standard-library/plus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (加算) を実行する定義済みの関数オブジェクトが用意されています。|  
|[unary_function](../Topic/unary_function%20Struct.md)|単項関数オブジェクトを提供する派生クラスによって継承される可能性がある型を定義する空の基底クラス。|  
  
### <a name="objects"></a>オブジェクト  
  
|||  
|-|-|  
|[_1.._M](../standard-library/1-object.md)|置き換え可能な引数のプレースホルダーです。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 = =](../Topic/%3Cfunctional%3E%20operators.md#operator_eq_eq)|呼び出し可能オブジェクトの等価比較を否定します。|  
|[operator! =](../Topic/%3Cfunctional%3E%20operators.md#operator_neq)|呼び出し可能オブジェクトの非等価比較を否定します。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

