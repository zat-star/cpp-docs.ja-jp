---
title: "unary_negate クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unary_negate"
  - "std::unary_negate"
  - "std.unary_negate"
  - "xfunctional/std::unary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_negate クラス"
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unary_negate クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した単項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。  
  
## 構文  
  
```  
  
   template<class Predicate>  
class unary_negate  
   : public unary_function<  
      typename Predicate::argument_type,  
      bool>   
{  
public:  
explicit unary_negate(  
   const Predicate& _Func  
);  
bool operator()(  
   const typename Predicate::argument_type& _Left ) const;  
};  
```  
  
#### パラメーター  
 `_Func`  
 単項否定する関数。  
  
 `_Left`  
 単項否定する関数のオペランド。  
  
## 戻り値  
 単項関数の否定。  
  
## 解説  
 このテンプレート クラスは単項関数オブジェクトの\_Func*のコピーを保存します。*これは \#\#\#\!の\_Func *\(\_Left\) を*返すようにメンバー関数 `operator()` を定義します。  
  
 `unary_negate` のコンストラクターは、あまり直接使用されません。  ヘルパー関数 [not1](../Topic/not1%20Function.md) は **unary\_negator** アダプターの述語を宣言して使用する単純な方法を提供します。  
  
## 使用例  
  
```  
// functional_unary_negate.cpp  
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
    for (i = 0; i <= 7; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    vector<int>::iterator::difference_type result1;  
    // Count the elements greater than 10  
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    vector<int>::iterator::difference_type result2;  
    // Use the negator to count the elements less than or equal to 10  
    result2 = count_if(v1.begin(), v1.end(),  
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));  
  
    // The following helper function not1 also works for the above line  
    // not1(bind2nd(greater<int>(), 10)));  
  
    cout << "The number of elements in v1 not greater than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **ベクター v1 \= \(0 5 10 15 20 25 30 35\)**   
**大きな v1 の要素の数は、10 次の操作: 5。**  
**小さい v1 の要素の数は、10 次の操作: 3。**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)