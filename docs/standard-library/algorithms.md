---
title: "アルゴリズム |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 5b5ffafb841fcb883dc66880933e8d123256e575
ms.lasthandoff: 02/24/2017

---
# <a name="algorithms"></a>アルゴリズム
アルゴリズムは、C++ 標準ライブラリの基本的な部分です。 アルゴリズムは、コンテナー自体と共に機能するのではありません。反復子と共に機能します。 そのため、C++ 標準ライブラリ コンテナーのすべてではありませんが、そのほとんどで同じアルゴリズムを使用できます。 このセクションでは、C++ 標準ライブラリ アルゴリズムの規則と用語について説明します。  
  
## <a name="remarks"></a>コメント  
 アルゴリズム テンプレート関数の説明では、いくつかの簡略な語句を使用しています。  
  
-   "範囲 [*A*, *B*) 内" は、*A* から始まり *B* の直前までの&0; 個以上の離散値のシーケンスを意味します。範囲は、*B* が *A* から到達可能な場合にのみ有効です。*A* をオブジェクト *N* に格納 (*N* = *A*) し、オブジェクトを&0; 回以上インクリメント (++*N*) して、有限数のインクリメント (N == B*) の後で *B* と等しいかどうかを比較できます。*  
  
-   "各 *N* (範囲 [*A*, *B*) 内)" は、*N* が値 *A* で始まり、値 *B* と等しくなるまで&0; 回以上インクリメントされるという意味です。*N* == *B* の場合は、範囲外です。  
  
-   "*X* のような範囲 [*A*, *B* の最小値 *N*)" という語句は、条件 *X* が満たされるまで、範囲 [*A*, *B*) 内の各 *N* に対して、条件 *X* が判断されるという意味です。  
  
-   "*X* のような範囲 [*A*, *B* 内の最大値 *N*)" という語句は、範囲 [*A*, *B*) 内の各 *N* に対して、*X* が判断されるという意味です。 関数は、条件 *X* が満たされるたびに `K` に *N* のコピーを格納します。 このように格納されると、関数は *B* に等しい *N* の最終的な値を `K` の値に置き換えます。 ただし、双方向アクセス反復子またはランダム アクセス反復子の場合は、*N* が範囲内の最大値から始まり、条件 *X* が満たされるまでその範囲でデクリメントされることを意味する場合もあります。  
  
-   *X* - *Y* のような式 (ここで *X* と *Y* はランダム アクセス反復子以外の反復子にすることができます) は、数学的な意味で使用されます。 関数は、このような値を決定する必要がある場合に、演算子 **-** を評価するとは限りません。 *X* + *N* および *X* - *N* (ここで、*N*は整数型) などの式にも同じことが当てはまります。  
  
 いくつかのアルゴリズムでは、`bool` の結果が得られるように `operator==` を使用するようなペアの比較を実行する述語を使用します。 述語関数 `operator==`、または、それに変わる関数では、どちらのオペランドも変更されません。 評価されるたびに、同じ `bool` の結果となります。また、いずれかのオペランドのコピーがオペランドに代入される場合、同じ結果となります。  
  
 いくつかのアルゴリズムでは、厳密弱順序をシーケンスの要素のペアに強制する述語を使用します。 述語 `pr`(*X*, *Y*) の意味は、次のとおりです。  
  
-   厳密とは、`pr`(*X*, *X*) が false であることを意味します。  
  
-   弱とは、!`pr`(*X*, *Y*) && !`pr`(*Y*, *X*) の場合、*X* と *Y* は同等の順序であることを意味します (*X* == *Y* を定義する必要はありません)。  
  
-   順序は、`pr`(*X*, *Y*) && `pr`(*Y*, Z) が `pr`(*X*, Z) を暗黙的に意味することを示します。  
  
 これらのアルゴリズムの一部は、暗黙的に述語 *X* \< *Y* を使用します。通常、厳密弱順序要件に適合するその他の述語は *X* > *Y*、**less**(*X*, *Y*)、および `greater`(*X*, *Y*) です。 ただし、*X* \<= *Y* や *X* >= *Y* などの述語は、この要件を満たしません。  
  
 範囲 [0, `Last` - `First`) 内の各 *N* および範囲 (N, `Last` - `First`) の各 *M* に対し、述語 !(\*(`First` + *M*) < \*(*First* + *N*)) が true の場合、範囲 [`First`, `Last`) 内で反復子によって指定された要素のシーケンスは、演算子 **<** で順序付けられたシーケンスです。 (要素が昇順で並べ替えられていることに注意してください)。述語関数 **operator<**、または、それに代わる関数では、どちらのオペランドも変更されません。 評価されるたびに、同じ `bool` の結果となります。また、いずれかのオペランドのコピーがオペランドに代入される場合、同じ結果となります。 さらに、比較するオペランドに対して厳密弱順序を適用する必要があります。  
  
 範囲 [1, `Last` - `First`) の各 *N* に対し、述語 !(\*`First` < \*(`First` + *N*)) が true の場合、範囲 [`First`, `Last`) 内の反復子で指定された要素のシーケンスは、**operator<** によって順序付けられたヒープです。 (最初の要素が最大です)。その内部構造は、テンプレート関数 [make_heap](http://msdn.microsoft.com/Library/b09f795c-f368-4aa8-b57e-61ee6100ddc2)、[pop_heap]--brokenlink--(../Topic/not%20found:c10b0c65-410c-4c83-abf8-8b7f61bba8d0.md#pop_heap)、および [push_heap] - brokenlink--(../Topic/not%20found:c10b0c65-410c-4c83-abf8-8b7f61bba8d0.md#push_heap) にのみ別名で知られています。 順序付けられたシーケンスと同様、述語関数 **operator<**、または、それに変わる関数では、そのどちらのオペランドも変更できません。さらに、比較するオペランドに対して厳密弱順序を強制します。 評価されるたびに、同じ `bool` の結果となります。また、いずれかのオペランドのコピーがオペランドに代入される場合、同じ結果となります。  
  
 C++ 標準ライブラリ アルゴリズムは、[\<algorithm>](../standard-library/algorithm.md) および [\<numeric>](../standard-library/numeric.md) ヘッダー ファイルにあります。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


