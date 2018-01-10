---
title: "binder2nd クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::binder2nd
dev_langs: C++
helpviewer_keywords: binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2f1a8dd24e20a10dffaab584ec88c43e1e87b43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="binder2nd-class"></a>binder2nd クラス
指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `Func`  
 単項関数オブジェクトに変換する二項関数オブジェクト。  
  
 `right`  
 二項関数オブジェクトの 2 つ目の引数がバインドされている値。  
  
 `left`  
 調整後の二項オブジェクトが 2 つ目の引数の固定値と比較する引数の値。  
  
## <a name="return-value"></a>戻り値  
 二項関数オブジェクトの 2 つ目の引数を値 `right.` にバインドした結果として生成される単項関数オブジェクト。  
  
## <a name="remarks"></a>コメント  
 テンプレート クラスは、二項関数オブジェクト _ *Func* のコピーを **op** に、`right` のコピーを **value** に格納します。 そのメンバー関数 `operator()` は **op**( `left`, **value**) を返すように定義されています。  
  
 `Func` が型 **Operation** のオブジェクトで、c が定数の場合、[bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` ) は `binder2nd` class constructor `binder2nd`\< **Operation**> ( `Func`, `c` ) と等しくなり、より便利です。  
  
## <a name="example"></a>例  
  
```cpp  
// functional_binder2nd.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder2nd<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare using binder1st fixing 1st argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder1st<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
/* Output:  
The vector v1 = ( 0 5 10 15 20 25 )  
The number of elements in v1 greater than 10 is: 3.  
The number of elements in v1 less than 10 is: 2.  
*/  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



