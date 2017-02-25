---
title: "&lt;iterator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<iterator>"
  - "std.<iterator>"
  - "<iterator>"
  - "iterator/std::<iterator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator ヘッダー"
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;iterator&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反復子のプリミティブ、定義済みの反復子とストリーム反復子、およびサポート テンプレートをいくつか定義します。  定義済み反復子には、挿入アダプターとリバース アダプターが含まれます。  挿入反復子アダプターのクラスには、フロント、バック、汎用の 3 つがあります。  これには、コンテナーのメンバー関数の反復子が提供する上書きセマンティクスではなく、挿入セマンティクスが用意されています。  
  
## 構文  
  
```  
  
#include <iterator>  
  
```  
  
## 解説  
 反復子はポインターを一般化したもので、C\+\+ プログラムが一貫した方法でさまざまなデータ構造を操作できるように要件が抽象化されています。  反復子は、コンテナーとジェネリックなアルゴリズムの仲介として機能します。  特定のデータ型を操作するのではなく、反復子の型で指定されている範囲を操作するようにアルゴリズムが定義されます。  そして、反復子の要件を満たすすべてのデータ構造をアルゴリズムで操作できます。  反復子には 5 つの種類またはカテゴリがあり、それぞれが独自の一連の要件と、結果として生じる機能を持ちます。  
  
-   出力: 前方移動。値を格納できますが、取得できません。ostream および inserter によって指定されます。  
  
-   入力: 前方移動。値を取得できますが、格納できません。istream によって指定されます。  
  
-   前方: 前方移動。値を格納および取得できます。  
  
-   双方向: 前方\/後方移動。値を格納および取得できます。list、set、multiset、map、および multimap によって指定されます。  
  
-   ランダム アクセス: 任意の順序でアクセスされる要素。値を格納および取得できます。vector、deque、string、および array によって指定されます。  
  
 より多くの要件を持ち、より強力に要素にアクセスできる反復子が、要件の少ない反復子の代わりに使用される場合があります。  たとえば、前方反復子が呼び出された場合は、ランダム アクセス反復子が代わりに使用される可能性があります。  
  
 Visual Studio では、C\+\+ 標準ライブラリの反復子に、チェックを行う反復子とチェックを行わない反復子のさまざまなデバッグ モードの状況をサポートする拡張機能が追加されました。  詳細については、「[安全なライブラリ: C\+\+ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)」を参照してください。  
  
### 関数  
  
|||  
|-|-|  
|[advance](../Topic/advance.md)|指定された位置の番号によって反復子をインクリメントします。|  
|[back\_inserter](../Topic/back_inserter.md)|指定されたコンテナーの後ろに要素を挿入できる反復子を作成します。|  
|[begin](../Topic/begin.md)|指定されたコンテナーの最初の要素への反復子を取得します。|  
|[cbegin](../Topic/cbegin.md)|指定されたコンテナーの最初の要素への定数反復子を取得します。|  
|[cend](../Topic/cend.md)|指定されたコンテナーの最後の要素の後ろにある要素への定数反復子を取得します。|  
|[distance](../Topic/distance.md)|2 つの反復子によってアドレス指定された位置の間のインクリメント数を決定します。|  
|[End](../Topic/end.md)|指定されたコンテナーの最後の要素の後ろにある要素への反復子を取得します。|  
|[front\_inserter](../Topic/front_inserter.md)|指定されたコンテナーの前に要素を挿入できる反復子を作成します。|  
|[の挿入演算子です。](../Topic/inserter.md)|指定された挿入ポイントにあるコンテナーに新しい要素を追加する反復子アダプター。|  
|[make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)|他のアルゴリズムで使用できる [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) を作成します。 **Note:**  この関数は、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。|  
|[make\_move\_iterator](../Topic/make_move_iterator.md)|提供された反復子を含む移動反復子を、格納された基本反復子としてを返します。|  
|[make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)|他のアルゴリズムで使用できる [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md) を作成します。 **Note:**  この関数は、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。|  
|[next](../Topic/next.md)|指定された回数を繰り返し、新しい反復子の位置を返します。|  
|[prev](../Topic/prev.md)|指定された回数を逆方向に繰り返し、新しい反復子の位置を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しくないかどうかを調べます。|  
|[operator\=\=](../Topic/operator==%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しいかどうかを調べます。|  
|[operator\<](../Topic/operator%3C%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより小さいかどうかを調べます。|  
|[operator\<\=](../Topic/operator%3C=%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以下かどうかを調べます。|  
|[operator\>](../Topic/operator%3E%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより大きいかどうかを調べます。|  
|[operator\>\=](../Topic/operator%3E=%20\(%3Citerator%3E\).md)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以上かどうかを調べます。|  
|[operator\+](../Topic/operator+%20\(%3Citerator%3E\).md)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。|  
|[operator\-](../Topic/operator-%20\(%3Citerator%3E\).md)|ある反復子を別の反復子から減算し、その差異を返します。|  
  
### クラス  
  
|||  
|-|-|  
|[back\_insert\_iterator](../standard-library/back-insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。  このクラスは型 **Container** のコンテナーに要素を挿入します。これには、コンテナーと呼ばれる、格納された保護 **pointer** オブジェクトを介してアクセスします。|  
|[bidirectional\_iterator\_tag](../Topic/bidirectional_iterator_tag%20Struct.md)|双方向反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。|  
|[checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)|チェックを行うランダム アクセス反復子を使用して配列にアクセスするクラス。 **Note:**  このクラスは、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。|  
|[forward\_iterator\_tag](../standard-library/forward-iterator-tag-struct.md)|前方反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。|  
|[front\_insert\_iterator](../standard-library/front-insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。  このクラスは型 **Container** のコンテナーに要素を挿入します。これには、コンテナーと呼ばれる、格納された保護 **pointer** オブジェクトを介してアクセスします。|  
|[input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)|入力反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。|  
|[insert\_iterator](../standard-library/insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。  このクラスは型 **Container** のコンテナーに要素を挿入します。これには、コンテナーと呼ばれる、格納された保護 **pointer** オブジェクトを介してアクセスします。  また、**iter** という **Container::iterator** クラスの保護された **iterator** オブジェクトも格納します。|  
|[istream\_iterator](../standard-library/istream-iterator-class.md)|このテンプレート クラスは、入力反復子オブジェクトを表します。  このクラスは、入力ストリームから **Ty** クラスのオブジェクトを抽出します。これには、`basic_istream`\<**Elem**, **Tr**\> への型 pointer の、格納されたオブジェクトを介してアクセスします。|  
|[istreambuf\_iterator](../standard-library/istreambuf-iterator-class.md)|このテンプレート クラスは、入力反復子オブジェクトを表します。  このクラスは、出力ストリーム バッファーに **Elem** クラスの要素を挿入します。これには、`basic_streambuf`\<**Elem**, **Tr**\> への型 **pointer** の、格納されたオブジェクトを介してアクセスします。|  
|[iterator](../Topic/iterator%20Struct.md)|このテンプレート クラスは、すべての反復子の基本型として使用されます。|  
|[iterator\_traits](../standard-library/iterator-traits-struct.md)|同じ方法で参照できるように、別の反復子の型に関連付けられているクリティカルな型を指定するテンプレート ヘルパー クラス。|  
|[move\_iterator](../standard-library/move-iterator-class.md)|`move_iterator` オブジェクトには、型 `RandomIterator` のランダム アクセス反復子が格納されています。  これは、逆参照された場合を除いて、ランダム アクセス反復子と同じように動作します。  `operator*` の結果は `value_type&&:` に暗黙的にキャストされ、`rvalue reference` が作成されます。|  
|[ostream\_iterator](../standard-library/ostream-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。  このクラスは、出力ストリームに **Type** クラスのオブジェクトを挿入します。これには、`basic_ostream`\<**Elem**, **Tr**\> への型 **pointer** の、格納されたオブジェクトを介してアクセスします。|  
|[ostreambuf\_iterator Class](../standard-library/ostreambuf-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。  このクラスは、出力ストリーム バッファーに **Elem** クラスの要素を挿入します。これには、`basic_streambuf`\<**Elem**, **Tr**\> への型 pointer の、格納されたオブジェクトを介してアクセスします。|  
|[output\_iterator\_tag](../standard-library/output-iterator-tag-struct.md)|出力反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。|  
|[random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md)|ランダム アクセス反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。|  
|[reverse\_iterator](../standard-library/reverse-iterator-class.md)|このテンプレート クラスは、逆方向でのみランダム アクセス反復子のように動作するオブジェクトを表します。|  
|[unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)|チェックを行わないランダム アクセス反復子を使用して配列にアクセスするクラス。 **Note:**  このクラスは、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)