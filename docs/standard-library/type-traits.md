---
title: "&lt;type_traits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<type_traits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typetrait ヘッダー [TR1]"
  - "type_traits"
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# &lt;type_traits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

生成される場合も、型引数のプロパティに関する情報を提供するコンパイル時定数型の変換を提供するテンプレートを定義します。  
  
## 構文  
  
```  
#include <type_traits>  
```  
  
## 解説  
 クラスと内のテンプレート `<type_traits>` 型の推定、分類、および種類に関連するエラーが検出されると、汎用的なコードを最適化するため、コンパイル時に変換をサポートするために使用します。 これらのクラスやテンプレートには、単項の型の特徴型のプロパティを記述する型、および型のプロパティを変更する変換の特徴間のリレーションシップを表すバイナリ型の特徴にはが含まれます。  
  
 型の特徴をヘルパー クラスをサポートするために `integral_constant`, 、定義されています。 テンプレートの特殊化が `true_type` と `false_type` 型述語の基本クラスを形成します。 A *型述語* は、1 つまたは複数の型引数を受け取るテンプレートです。 型述語が *true を保持*する場合は、[true\_type](../Topic/true_type%20Typedef.md) からパブリックに \(直接または間接的に\) 派生されます。 型述語が *false を保持*する場合は、[false\_type](../Topic/false_type%20Typedef.md) からパブリックに \(直接または間接的に\) 派生されます。  
  
 A *型修飾子* または *変換の特徴である* 1 つまたは複数のテンプレート引数を受け取るテンプレートは、1 つのメンバー `type`, 、変更後の型のシノニムであります。  
  
### エイリアス テンプレート  
 型の特徴 \(traits\) の式を簡略化する [エイリアス テンプレート](../cpp/aliases-and-typedefs-cpp.md) の `typename some_trait<T>::type` が提供されます" `some_trait`"テンプレート クラスの名前です。 たとえば、 [add\_const](../Topic/add_const%20Class.md) エイリアス テンプレートがその型の `add_const_t`, として定義されている。  
  
```cpp  
template<class T>  
    using add_const_t = typename add_const<T>::type;  
```  
  
|||||  
|-|-|-|-|  
|add\_const\_t|aligned\_storage\_t|make\_signed\_t|remove\_pointer\_t|  
|add\_cv\_t|aligned\_union\_t|make\_unsigned\_t|remove\_reference\_t|  
|add\_lvalue\_reference\_t|common\_type\_t|remove\_all\_extents\_t|remove\_volatile\_t|  
|add\_pointer\_t|conditional\_t|remove\_const\_t|result\_of\_t|  
|add\_rvalue\_reference\_t|decay\_t|remove\_cv\_t|underlying\_type\_t|  
|add\_volatile\_t|enable\_if\_t|remove\_extent\_t||  
  
### クラス  
 ヘルパー クラスと typedef  
  
|||  
|-|-|  
|[integral\_constant](../standard-library/integral-constant-class-bool-constant-class.md)|型、および値から整数定数を作成します。|  
|[true\_type](../Topic/true_type%20Typedef.md)|true 値を持つ整数定数を保持します。|  
|[false\_type](../Topic/false_type%20Typedef.md)|false 値を持つ整数定数を保持します。|  
  
 主な種類のカテゴリ  
  
|||  
|-|-|  
|[is\_void](../standard-library/is-void-class.md)|型があるかどうかをテスト `void`します。|  
|[is\_null\_pointer](../standard-library/is-null-pointer-class.md)|型があるかどうかをテスト `std::nullptr_t`します。|  
|[is\_integral](../standard-library/is-integral-class.md)|型が整数型であるかどうかをテストします。|  
|[is\_floating\_point](../standard-library/is-floating-point-class.md)|型が浮動小数点型であるかどうかをテストします。|  
|[is\_array](../Topic/is_array%20Class.md)|型が配列型であるかどうかをテストします。|  
|[is\_pointer](../standard-library/is-pointer-class.md)|型がポインターであるかどうかをテストします。|  
|[is\_lvalue\_reference](../standard-library/is-lvalue-reference-class.md)|型が左辺値参照かどうかをテストします。|  
|[is\_rvalue\_reference](../Topic/is_rvalue_reference%20Class.md)|型が右辺値参照かどうかをテストします。|  
|[is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)|型がメンバー オブジェクトへのポインターであるかどうかをテストします。|  
|[is\_member\_function\_pointer](../Topic/is_member_function_pointer%20Class.md)|型がメンバー関数へのポインターであるかどうかをテストします。|  
|[is\_enum](../standard-library/is-enum-class.md)|型が列挙型であるかどうかをテストします。|  
|[is\_union](../standard-library/is-union-class.md)|型が共用体であるかどうかをテストします。|  
|[is\_class](../standard-library/is-class-class.md)|型がクラスであるかどうかをテストします。|  
|[is\_function](../standard-library/is-function-class.md)|型が関数型であるかどうかをテストします。|  
  
 複合型のカテゴリ  
  
|||  
|-|-|  
|[is\_reference](../Topic/is_reference%20Class.md)|型が参照であるかどうかをテストします。|  
|[is\_arithmetic](../Topic/is_arithmetic%20Class.md)|型が演算型であるかどうかをテストします。|  
|[is\_fundamental](../standard-library/is-fundamental-class.md)|型が `void` または演算型であるかどうかをテストします。|  
|[is\_object](../standard-library/is-object-class.md)|型がオブジェクト型であるかどうかをテストします。|  
|[is\_scalar](../standard-library/is-scalar-class.md)|型がスカラーであるかどうかをテストします。|  
|[is\_compound](../standard-library/is-compound-class.md)|型が非スカラーであるかどうかをテストします。|  
|[is\_member\_pointer](../standard-library/is-member-pointer-class.md)|型がメンバーへのポインターであるかどうかをテストします。|  
  
 型のプロパティ  
  
|||  
|-|-|  
|[is\_const](../Topic/is_const%20Class.md)|型があるかどうかをテスト `const`します。|  
|[is\_volatile](../standard-library/is-volatile-class.md)|型があるかどうかをテスト `volatile`します。|  
|[is\_trivial](../Topic/is_trivial%20Class.md)|型が単純かどうかをテストします。|  
|[is\_trivially\_copyable](../standard-library/is-trivially-copyable-class.md)|種類は普通にコピー可能かどうかをテストします。|  
|[is\_standard\_layout](../Topic/is_standard_layout%20Class.md)|型が標準レイアウト型であるかどうか。|  
|[is\_pod](../standard-library/is-pod-class.md)|型が POD であるかどうかをテストします。|  
|[is\_literal\_type](../standard-library/is-literal-type-class.md)|型かどうかをテストする `constexpr` 変数またはで使用される、 `constexpr` 関数です。|  
|[is\_empty](../standard-library/is-empty-class.md)|型が空のクラスであるかどうかをテストします。|  
|[is\_polymorphic](../Topic/is_polymorphic%20Class.md)|型がポリモーフィックなクラスであるかどうかをテストします。|  
|[is\_abstract](../Topic/is_abstract%20Class.md)|型が抽象クラスであるかどうかをテストします。|  
|[つまり is\_final](../standard-library/is-final-class.md)|種類がマークされたクラス型であるかどうかをテスト `final`します。|  
|[is\_signed](../Topic/is_signed%20Class.md)|型が符号付き整数であるかどうかをテストします。|  
|[is\_unsigned](../standard-library/is-unsigned-class.md)|型が符号なし整数であるかどうかをテストします。|  
|[is\_constructible](../standard-library/is-constructible-class.md)|型が指定した引数型を使用して構築可能な型であるかどうかをテストします。|  
|[is\_default\_constructible](../Topic/is_default_constructible%20Class.md)|型に既定のコンス トラクターがある存在するかどうかをテストします。|  
|[is\_copy\_constructible](../standard-library/is-copy-constructible-class.md)|種類は、コピー コンス トラクターを持つかどうかをテストします。|  
|[is\_move\_constructible](../standard-library/is-move-constructible-class.md)|型に移動コンス トラクターがある存在するかどうかをテストします。|  
|[is\_assignable](../standard-library/is-assignable-class.md)|最初の型に 2 つ目の型の値を割り当てることができるかどうかをテストします。|  
|[is\_copy\_assignable](../standard-library/is-copy-assignable-class.md)|型には、型の定数参照値を割り当てることができるかどうかをテストします。|  
|[is\_move\_assignable](../standard-library/is-move-assignable-class.md)|型の右辺値参照型を割り当てることができるかどうかをテストします。|  
|[is\_destructible](../standard-library/is-destructible-class.md)|型が破棄可能かどうかをテストします。|  
|[is\_trivially\_constructible](../standard-library/is-trivially-constructible-class.md)|型に、指定された型を使用して作成したときに、重要な操作で使用されていないかどうかをテストします。|  
|[is\_trivially\_default\_constructible](../standard-library/is-trivially-default-constructible-class.md)|型で使用されていない重要な操作既定の構築時にするかどうかをテストします。|  
|[is\_trivially\_copy\_constructible](../standard-library/is-trivially-copy-constructible-class.md)|型で使用されていない重要な操作のコピーの作成時にするかどうかをテストします。|  
|[is\_trivially\_move\_constructible](../standard-library/is-trivially-move-constructible-class.md)|型で使用されていない重要な操作の移動の構築時にするかどうかをテストします。|  
|[is\_trivially\_assignable](../Topic/is_trivially_assignable%20Class.md)|型に割り当てることが、割り当てに重要な操作で使用されていないかどうかをテストします。|  
|[is\_trivially\_copy\_assignable](../standard-library/is-trivially-copy-assignable-class.md)|重要な操作を使用していないかどうか、型は、割り当て可能なコピー割り当てをテストします。|  
|[is\_trivially\_move\_assignable](../standard-library/is-trivially-move-assignable-class.md)|重要な操作を使用していないかどうか、型は、割り当て可能な移動割り当てをテストします。|  
|[is\_trivially\_destructible](../standard-library/is-trivially-destructible-class.md)|種類は消滅させられると、デストラクターに重要な操作で使用されていないかどうかをテストします。|  
|[is\_nothrow\_constructible](../standard-library/is-nothrow-constructible-class.md)|型は、構築可能なと認識されて、指定された型を使用して作成したときにスローするかどうかをテストします。|  
|[is\_nothrow\_default\_constructible](../standard-library/is-nothrow-default-constructible-class.md)|テストは、構築可能な既定の型があるかどうかと既定構築されるときにスローしないように呼びます。|  
|[is\_nothrow\_copy\_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|型はコピーによって構築可能で、コピー コンス トラクターをスローしないように呼ばれるかどうかをテストします。|  
|[is\_nothrow\_move\_constructible](../standard-library/is-nothrow-move-constructible-class.md)|型で構築可能な移動、移動コンス トラクターをスローしないように呼ばれるかどうかをテストします。|  
|[is\_nothrow\_assignable](../standard-library/is-nothrow-assignable-class.md)|指定された型を使用して割り当てることができる型および割り当てをスローしないように呼ばれるかどうかをテストします。|  
|[is\_nothrow\_copy\_assignable](../Topic/is_nothrow_copy_assignable%20Class.md)|型が割り当て可能なコピーおよび割り当てをスローしないように呼ばれるかどうかをテストします。|  
|[is\_nothrow\_move\_assignable](../standard-library/is-nothrow-move-assignable-class.md)|型が割り当て可能な移動と割り当てをスローしないように呼ばれるかどうかをテストします。|  
|[is\_nothrow\_destructible](../standard-library/is-nothrow-destructible-class.md)|型は消滅させられると、デストラクターをスローしないように呼ばれるかどうかをテストします。|  
|[has\_virtual\_destructor](http://msdn.microsoft.com/ja-jp/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|型に仮想デストラクターが存在するかどうかをテストします。|  
  
 プロパティの種類のクエリ  
  
|||  
|-|-|  
|[alignment\_of](../standard-library/alignment-of-class.md)|型の配置を取得します。|  
|[rank](../Topic/rank%20Class.md)|配列の次元数を取得します。|  
|[extent](../standard-library/extent-class.md)|指定された配列の次元内の要素の数を取得します。|  
  
 型の関係  
  
|||  
|-|-|  
|[is\_same](../standard-library/is-same-class.md)|2 つの型が等しいかどうかをテストします。|  
|[is\_base\_of](../standard-library/is-base-of-class.md)|1 つの型が別のベースであるかどうかをテストします。|  
|[is\_convertible](../standard-library/is-convertible-class.md)|一方の型をもう一方の型に変換できるかどうかをテストします。|  
  
 Const 揮発性の変更  
  
|||  
|-|-|  
|[add\_const](../Topic/add_const%20Class.md)|生成、 `const` 型からの型。|  
|[add\_volatile](../standard-library/add-volatile-class.md)|生成、 `volatile` 型からの型。|  
|[add\_cv](../standard-library/add-cv-class.md)|生成、 `const``volatile` 型からの型。|  
|[remove\_const](../standard-library/remove-const-class.md)|型から非定数の型を生成します。|  
|[remove\_volatile](../Topic/remove_volatile%20Class.md)|型から非揮発性の型を生成します。|  
|[remove\_cv](../standard-library/remove-cv-class.md)|型から非定数の非 volatile 型を生成します。|  
  
 参照の変更  
  
|||  
|-|-|  
|[add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)|型から型への参照を生成します。|  
|[add\_rvalue\_reference](../standard-library/add-rvalue-reference-class.md)|型から型への参照を右辺値が生成されます。|  
|[remove\_reference](../standard-library/remove-reference-class.md)|型から非参照型型を生成します。|  
  
 符号の変更  
  
|||  
|-|-|  
|[make\_signed](../standard-library/make-signed-class.md)|入力するには、署名されている場合、型または最小符号付く型のサイズ以上生成します。|  
|[make\_unsigned](../standard-library/make-unsigned-class.md)|入力するには、符号なしの場合、型または最小符号なしの型のサイズ以上生成します。|  
  
 配列の変更  
  
|||  
|-|-|  
|[remove\_all\_extents](../standard-library/remove-all-extents-class.md)|配列型から非配列型を作成します。|  
|[remove\_extent](../standard-library/remove-extent-class.md)|配列型から要素の型を生成します。|  
  
 ポインターの変更  
  
|||  
|-|-|  
|[add\_pointer](../standard-library/add-pointer-class.md)|型から型へのポインターを生成します。|  
|[remove\_pointer](../Topic/remove_pointer%20Class.md)|入力するには、ポインターから型を生成します。|  
  
 その他の変換  
  
|||  
|-|-|  
|[aligned\_storage](../standard-library/aligned-storage-class.md)|整列された型の初期化されていないメモリを割り当てます。|  
|[aligned\_union](../Topic/aligned_union%20Class.md)|重要なコンストラクターまたはデストラクターを含む整列された共用体の初期化されていないメモリを割り当てます。|  
|[common\_type](../standard-library/common-type-class.md)|パラメーター パックのすべての型の共通の型を生成します。|  
|[conditional](../standard-library/conditional-class.md)|条件が true の場合と最初の指定した型それ以外の場合、2 番目の指定した型なります。|  
|[decay](../standard-library/decay-class.md)|値で渡される型を生成します。 非参照、非定数、非揮発の型、または型へのポインターを作成します。|  
|[enable\_if](../Topic/enable_if%20Class.md)|条件が true の場合と、指定された型それ以外の場合の型を持たないなります。|  
|[result\_of](../standard-library/result-of-class1.md)|指定した引数型を受け取る呼び出し可能型の戻り値の型を決定します。|  
|[underlying\_type](../standard-library/underlying-type-class.md)|列挙型の基になる整数型を生成します。|  
  
## 参照  
 [\<functional\>](../standard-library/functional.md)