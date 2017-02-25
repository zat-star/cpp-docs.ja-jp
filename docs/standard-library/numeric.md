---
title: "&lt; 数値 &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<numeric>"
  - "std.<numeric>"
  - "<numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< 数値 > ヘッダー"
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt; 数値 &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数値処理のアルゴリズムを実行するコンテナーのテンプレート関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <numeric>  
```  
  
## <a name="remarks"></a>解説  
 このアルゴリズムは標準テンプレート ライブラリ (STL) のアルゴリズムと似ていますが、C++ 標準ライブラリに含まれています。 いずれにしても、STL と互換性があり、STL アルゴリズムと同様に、さまざまなデータ構造体を操作することもできます。 STL コンテナー クラスが含まれます — たとえば、 [ベクトル](../standard-library/vector-class.md) と [リスト](../standard-library/list-class.md), とプログラム定義のデータの構造体と、特定のアルゴリズムの要件を満たす要素の配列。 アルゴリズムは、反復子によって間接的にコンテナー要素にアクセスし、走査することによって、このレベルの一般性を実現します。 アルゴリズムは、通常、開始位置または終了位置によって指定される反復子範囲を処理します。 参照される範囲は、範囲内のすべてのポインターが逆参照可能であるという意味において有効であり、かつ各範囲のシーケンス内で先頭位置からのインクリメントにより最後の位置に到達可能である必要があります。  
  
 アルゴリズムでは、各 STL コンテナーの操作およびメンバー関数でサポートされている操作を拡張し、異なる型のコンテナー オブジェクトを同時に操作できるようにします。  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[蓄積](../Topic/%3Cnumeric%3E%20functions.md#accumulate)|連続する部分和を計算することで、初期値を含め、指定された範囲のすべての要素の合計を計算します。または、合計演算の代わりに、指定された二項演算を使用して取得された連続する部分的な結果を計算します。|  
|[adjacent_difference](../Topic/%3Cnumeric%3E%20functions.md#adjacent_difference)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[inner_product](../Topic/%3Cnumeric%3E%20functions.md#inner_product)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[iota](../Topic/%3Cnumeric%3E%20functions.md#iota)|開始値を格納し、最初の要素から始めて、一連の値のインクリメント (`value++`) を `[first, last)` の間隔で各要素に入力します。|  
|[partial_sum](../Topic/%3Cnumeric%3E%20functions.md#partial_sum)|一連の最初の要素から入力範囲内の合計値の計算、 *は*番目の要素は各合計の結果を格納し、 *は*番目の要素をターゲット範囲のまたは合計演算は別に置換する、汎用化されたプロシージャの結果には、二項演算が指定されている計算します。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

