---
title: "checked_array_iterator クラス | Microsoft Docs"
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
  - "iterator/checked_array_iterator"
  - "checked_array_iterator"
  - "std::checked_array_iterator"
  - "std.checked_array_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked_array_iterator"
  - "checked_array_iterator クラス"
  - "checked_array_iterator, 構文"
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# checked_array_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`checked_array_iterator` クラスを使用すると、配列またはポインターをチェックを行う反復子に変換できます。  チェックを行わないポインター警告をグローバルに抑制する代わりに、チェック機能を提供し、これらの警告を管理するのに適した方法として、このクラスを生のポインターまたは配列のラッパーとして使用します \([make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md) 関数を使用\)。  必要に応じて、このクラスのチェックを行わないバージョンである [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md) を使用できます。  
  
> [!NOTE]
>  このクラスは、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。  このクラスを使用する必要がないコードを記述する方法を示す例については、次の 2 番目の例を参照してください。  
  
## 構文  
  
```  
template <class _Iterator>  
    class checked_array_iterator;  
```  
  
## 解説  
 このクラスは、[stdext](../Topic/stdext%20Namespace.md) 名前空間で定義されます。  
  
 チェックを行う反復子機能の詳細とコード例については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」をご覧ください。  
  
## 使用例  
 次の例は、チェックを行う配列反復子を定義および使用する方法を示しています。  
  
 コピー先がコピーされるすべての要素を保持するほど十分大きくない場合に、たとえば次のように行を変更した場合、  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
```  
  
 から  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));  
```  
  
 ランタイム エラーが発生します。  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
```  
  
  **\( 0 1 2 3 4 \)**  
**\( 0 1 2 3 4 \)**   
## 使用例  
 標準 C\+\+ ライブラリ アルゴリズムを使用する場合の `checked_array_iterator` クラスの必要性を回避するため、動的に割り当てられた配列の代わりに `vector` を使用することを検討してください。  この方法を次の例に示します。  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
### コンストラクター  
  
|||  
|-|-|  
|[checked\_array\_iterator](../Topic/checked_array_iterator::checked_array_iterator.md)|基になる反復子の既定の `checked_array_iterator` または `checked_array_iterator` を構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/checked_array_iterator::difference_type.md)|同じコンテナー内の要素を参照する 2 つの `checked_array_iterator` の違いを提供する型。|  
|[ポインター](../Topic/checked_array_iterator::pointer.md)|`checked_array_iterator` によってアドレス指定される要素へのポインターを提供する型。|  
|[参照](../Topic/checked_array_iterator::reference.md)|`checked_array_iterator` によってアドレス指定される要素への参照を提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[基本](../Topic/checked_array_iterator::base.md)|その `checked_array_iterator` から基になる反復子を復元します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/checked_array_iterator::operator==.md)|2 つの `checked_array_iterator` が等しいかどうかをテストします。|  
|[operator\!\=](../Topic/checked_array_iterator::operator!=.md)|2 つの `checked_array_iterator` が等しくないかどうかをテストします。|  
|[\< 演算子](../Topic/checked_array_iterator::operator%3C.md)|演算子の左側の `checked_array_iterator` オブジェクトが右側の `checked_array_iterator` オブジェクトより小さいかどうかをテストします。|  
|[\> 演算子](../Topic/checked_array_iterator::operator%3E.md)|演算子の左側の `checked_array_iterator` オブジェクトが右側の `checked_array_iterator` オブジェクトより大きいかどうかをテストします。|  
|[\<\= 演算子](../Topic/checked_array_iterator::operator%3C=.md)|演算子の左側の `checked_array_iterator` が右側の `checked_array_iterator` 以下かどうかをテストします。|  
|[\>\= 演算子](../Topic/checked_array_iterator::operator%3E=.md)|演算子の左側の `checked_array_iterator` が右側の `checked_array_iterator` 以上かどうかをテストします。|  
|[operator\*](../Topic/checked_array_iterator::operator*.md)|`checked_array_iterator` がアドレス指定する要素を返します。|  
|[operator\-\>](../Topic/checked_array_iterator::operator-%3E.md)|`checked_array_iterator` によってアドレス指定される要素へのポインターを返します。|  
|[operator\+\+](../Topic/checked_array_iterator::operator++.md)|`checked_array_iterator` を次の要素にインクリメントします。|  
|[operator\-\-](../Topic/checked_array_iterator::operator--.md)|`checked_array_iterator` を直前の要素にデクリメントします。|  
|[operator \+\=](../Topic/checked_array_iterator::operator+=.md)|指定したオフセットを `checked_array_iterator` に追加します。|  
|[operator\+](../Topic/checked_array_iterator::operator+.md)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `checked_array_iterator` アドレスを返します。|  
|[operator\-\=](../Topic/checked_array_iterator::operator-=.md)|指定したオフセットを `checked_array_iterator` からデクリメントします。|  
|[operator\-](../Topic/checked_array_iterator::operator-.md)|反復子からオフセットをデクリメントし、新しいオフセット位置に挿入された要素をアドレス指定する新しい `checked_array_iterator` アドレスを返します。|  
|[operator&#91;&#93;](../Topic/checked_array_iterator::operator.md)|`checked_array_iterator` によってアドレス指定される要素からの要素のオフセットへの参照を返します。|  
  
## 必要条件  
 **ヘッダー:**\<iterator\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)