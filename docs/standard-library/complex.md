---
title: '&lt;complex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <complex>
- std.<complex>
- std::<complex>
dev_langs:
- C++
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
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
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: c1753b0f4f017c6d02fc41c427285e6adae6521b
ms.lasthandoff: 02/24/2017

---
# <a name="ltcomplexgt"></a>&lt;complex&gt;
コンテナーのテンプレート クラス complex とそのサポート用テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <complex>  
  
```  
  
## <a name="remarks"></a>コメント  
 複素数は、順序付けされた実数のペアです。 純粋に幾何学的な見地からすれば、複素平面は実数からなる&2; 次元平面です。 複素平面には代数構造が加えられているため、実数平面とは異なる特殊な性質を持ちます。 この代数構造には次の&2; つの基本的な演算が含まれます。  
  
-   (*a, b*) + (*c, d*) = (*a + c, b + d)* の形で定義される加算  
  
-   (*a, b*) \* (*c, d*) = (*ac - bd, ad + bc*) の形で定義される乗算  
  
 複素数の加算や乗算を伴う複素数の集合は、標準の代数学的な意味での体 (field) です。  
  
-   実数の体 (field) における実数の加算や乗算と全く同様、加算や乗算の演算には交換法則や結合法則が成り立ち、加法に対する乗法の分配法則も成り立ちます。  
  
-   複素数 (*0, 0*) が加法の単位元であり、(*1, 0*) が乗法の単位元です。  
  
-   複素数 (*a, b*) の加法逆元は (*- a, b*) で、(*0, 0*) 以外のすべての複素数の乗法逆元は次のとおりに定義されます。  
  
     (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>)  
  
 複素数 *z = (a, b)* を *z = a + bi* 形式 (*i*<sup>2</sup> *=*-1) で表す場合、実数集合の代数演算規則が複素数集合とその要素にも当てはまります。 例:  
  
 (1 + 2*i*) \* (2 + 3*i*)    = 1\*(2 + 3*i*) + 2*i*\*(2 + 3*i*) = (2 + 3*i*) + (4*i* + 6*i*<sup>2</sup>)  
  
 = (2 –6) + (3 + 4)*i* = -4 + 7*i*  
  
 複素数系は体 (field) ですが、順序体 (ordered field) ではありません。 複素数には、実数とその部分集合の場合に存在するような順序がありません。このため、順序体である実数の場合のような不等式は成り立ちません。  
  
 複素数 *z* を表す形式としては、次の&3; つが一般的です。  
  
-   デカルト形式: *z = a + bi*  
  
-   極形式: *z = r* (cos *+ i*sin)  
  
-   指数関数型: *z = r \** exp()  
  
 これらの標準的な複素数の表現で使用される用語は、次のように呼ばれます。  
  
-   デカルト形式の実数要素、または実数部 *a*。  
  
-   デカルト形式の虚数要素、または虚数部 *b*。  
  
-   複素数の係数、もしくは絶対値 P。  
  
-   偏角または位相角。  
  
 特に指定しない場合、複数の値を返すことができる関数は、–π より大きく +π 以下であるような引数の主値を返し、一価にしておく必要があります。 角度はすべてラジアンで指定する必要があります。1 周は 2 π ラジアン (360°) です。  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[abs](../standard-library/complex-functions.md#abs)|複素数の係数を計算します。|  
|[arg](../standard-library/complex-functions.md#arg)|複素数から偏角を抽出します。|  
|[conj](../standard-library/complex-functions.md#conj)|複素数の複素共役を返します。|  
|[cos](../standard-library/complex-functions.md#cos)|複素数のコサインを返します。|  
|[cosh](../standard-library/complex-functions.md#cosh)|複素数のハイパーボリック コサインを返します。|  
|[exp](../standard-library/complex-functions.md#exp)|複素数の指数関数を返します。|  
|[imag](../standard-library/complex-functions.md#imag)|複素数の虚数部を抽出します。|  
|[log](../standard-library/complex-functions.md#log)|複素数の自然対数を返します。|  
|[log10](../standard-library/complex-functions.md#log10)|複素数の底 10 の対数を返します。|  
|[norm](../standard-library/complex-functions.md#norm)|複素数のノルムを抽出します。|  
|[polar](../standard-library/complex-functions.md#polar)|デカルト形式で、指定した係数と偏角に対応する複素数を返します。|  
|[pow](../standard-library/complex-functions.md#pow)|複素数の底を、別の複素数で累乗することによって得られる複素数を評価します。|  
|[real](../standard-library/complex-functions.md#real)|複素数の実数部を抽出します。|  
|[sin](../standard-library/complex-functions.md#sin)|複素数のサインを返します。|  
|[sinh](../standard-library/complex-functions.md#sinh)|複素数のハイパーボリック サインを返します。|  
|[sqrt](../standard-library/complex-functions.md#sqrt)|複素数の平方根を返します。|  
|[tan](../standard-library/complex-functions.md#tan)|複素数のタンジェントを返します。|  
|[tanh](../standard-library/complex-functions.md#tanh)|複素数のハイパーボリック タンジェントを返します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator!=](../standard-library/complex-operators.md#operator_neq)|2 つの複素数の間の非同等性をテストします。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator*](../standard-library/complex-operators.md#operator_star)|2 つの複素数を乗算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator+](../standard-library/complex-operators.md#operator_add)|2 つの複素数を加算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator-](../standard-library/complex-operators.md#operator-)|2 つの複素数を減算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator/](../standard-library/complex-operators.md#operator_)|2 つの複素数を除算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator<\<](../standard-library/complex-operators.md#operator_lt__lt_)|出力ストリームに複素数を挿入するテンプレート関数。|  
|[operator==](../standard-library/complex-operators.md#operator_eq_eq)|2 つの複素数の間の同等性をテストします。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|  
|[operator>>](../standard-library/complex-operators.md#operator_gt__gt_)|入力ストリームから複素数を抽出するテンプレート関数。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[complex\<double>](../standard-library/complex-double.md)|明示的に特殊化されたこのテンプレート クラスは、順序付けされたオブジェクトのペア (いずれも **double**** 型) を格納するオブジェクトを記述します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。|  
|[complex\<float>](../standard-library/complex-float.md)|明示的に特殊化されたこのテンプレート クラスは、順序付けされたオブジェクトのペア (いずれも **float**** 型) を格納するオブジェクトを記述します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。|  
|[complex\<long double>](../standard-library/complex-long-double.md)|明示的に特殊化されたこのテンプレート クラスは、順序付けされたオブジェクトのペア (いずれも `long double`** 型) を格納するオブジェクトを記述します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。|  
|[complex](../standard-library/complex-class.md)|このテンプレート クラスは、複素数の算術演算に使用する複素数系を表すオブジェクトを記述します。|  
  
### <a name="literals"></a>リテラル  
 \<complex> ヘッダーでは次の[ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)が定義されており、実数部が&0; および虚数部が入力パラメーターの値である複素数を作成します。  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|`complex<long double>{0.0L, static_cast<long double>(d)}` を返します。|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|`complex<double>{0.0, static_cast<double>(d)}` を返します。|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|`complex<float>{0.0f, static_cast<float>(d)}` を返します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




