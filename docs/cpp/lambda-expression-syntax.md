---
title: "ラムダ式の構文 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "VCF1 Lambda_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ラムダ式 [C++], 構文"
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ラムダ式の構文
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事では、ラムダ式の構文と構造体要素を説明します。  ラムダ式の説明については、「[ラムダ式](../cpp/lambda-expressions-in-cpp.md)」を参照してください。  
  
## 関数オブジェクトとラムダ  
 コードを記述する場合、特に [STL アルゴリズム](../cpp/algorithms-modern-cpp.md)を使用するときに、関数ポインターおよび関数オブジェクトを使用して問題を解決し、計算を実行することがよくあります。  関数ポインターと関数オブジェクトには、それぞれに利点と欠点があります。たとえば、関数ポインターは、最小限の構文オーバーヘッドで済みますが、スコープ内の状態を保持しません。関数オブジェクトは、状態を保持できますが、クラス定義の構文オーバーヘッドが必要となります。  
  
 ラムダは、関数ポインターと関数オブジェクトの両方の利点を持ち、それらの欠点を回避できます。  ラムダは、関数オブジェクトのように柔軟性があり状態を保持できますが、関数オブジェクトとは異なり、その簡潔な構文には明示的なクラス定義は必要ありません。  ラムダを使用すると、同等の関数オブジェクトのコードよりも使いやすくエラーが発生しにくいコードを作成できます。  
  
 次の例では、ラムダの使用と関数オブジェクトの使用を比較しています。  最初の例では、ラムダを使用して `vector` オブジェクト内の各要素が偶数か奇数であるかをコンソールに出力します。  2 番目の例では、関数オブジェクトを使用して同じことを行っています。  
  
## 例 1: ラムダの使用  
 この例では、ラムダを `for_each` 関数に渡します。  ラムダは、`vector` オブジェクト内の各要素が偶数か奇数かを示す結果を出力します。  
  
### コード  
  
```cpp  
// even_lambda.cpp  
// compile with: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
   // Create a vector object that contains 10 elements.  
   vector<int> v;  
   for (int i = 1; i < 10; ++i) {  
      v.push_back(i);  
   }  
  
   // Count the number of even numbers in the vector by   
   // using the for_each function and a lambda.  
   int evenCount = 0;  
   for_each(v.begin(), v.end(), [&evenCount] (int n) {  
      cout << n;  
      if (n % 2 == 0) {  
         cout << " is even " << endl;  
         ++evenCount;  
      } else {  
         cout << " is odd " << endl;  
      }  
   });  
  
   // Print the count of even numbers to the console.  
   cout << "There are " << evenCount   
        << " even numbers in the vector." << endl;  
}  
```  
  
### 出力  
  **1 is odd**  
**2 is even**  
**3 is odd**  
**4 is even**  
**5 is odd**  
**6 is even**  
**7 is odd**  
**8 is even**  
**9 is odd**  
**There are 4 even numbers in the vector.**   
### コメント  
 この例では、`for_each` 関数への 3 番目の引数がラムダです。  `[&evenCount]` の部分は、式の capture 句を指定します。`(int n)` はパラメーター リストを指定します。残りの部分は、式の本体を指定します。  
  
## 例 2: 関数オブジェクトの使用  
 ラムダは、前の例よりも拡張するのがはるかに複雑になる場合があります。  次の例では、ラムダの代わりに、`for_each` 関数と関数オブジェクトを使用して、例 1. と同じ結果を生成します。  どちらの例でも `vector` オブジェクトに含まれる偶数の数を格納します。  操作の状態を保持するために、`FunctorClass` クラスはメンバー変数の参照として `m_evenCount` 変数を格納します。  操作を実行するには、`FunctorClass` が関数呼び出し演算子 `operator()` を実装します。  Visual C\+\+ コンパイラは、サイズとパフォーマンスにおいて例 1. のラムダ コードと同等のコードを生成します。  ここで紹介したような基本的な問題の場合は、おそらく、より単純なラムダのデザインの方が関数オブジェクトよりも適切です。  ただし、後で大幅な機能拡張が必要となる可能性がある場合は、コードの保守が容易になるように、関数オブジェクトのデザインを使用します。  
  
 `operator()` の詳細については、「[関数呼び出し](../Topic/Function%20Call%20\(C++\).md)」を参照してください。  `for_each` 関数の詳細については、「[for\_each](../Topic/for_each.md)」を参照してください。  
  
### コード  
  
```cpp  
// even_functor.cpp  
// compile with: /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class FunctorClass  
{  
public:  
    // The required constructor for this example.  
    explicit FunctorClass(int& evenCount)  
        : m_evenCount(evenCount) { }  
  
    // The function-call operator prints whether the number is  
    // even or odd. If the number is even, this method updates  
    // the counter.  
    void operator()(int n) const {  
        cout << n;  
  
        if (n % 2 == 0) {  
            cout << " is even " << endl;  
            ++m_evenCount;  
        } else {  
            cout << " is odd " << endl;  
        }  
    }  
  
private:  
    // Default assignment operator to silence warning C4512.  
    FunctorClass& operator=(const FunctorClass&);  
  
    int& m_evenCount; // the number of even variables in the vector.  
};  
  
int main()  
{  
    // Create a vector object that contains 10 elements.  
    vector<int> v;  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
  
    // Count the number of even numbers in the vector by   
    // using the for_each function and a function object.  
    int evenCount = 0;  
    for_each(v.begin(), v.end(), FunctorClass(evenCount));  
  
    // Print the count of even numbers to the console.  
    cout << "There are " << evenCount  
        << " even numbers in the vector." << endl;  
}  
  
```  
  
## 出力  
  **1 is odd**  
**2 is even**  
**3 is odd**  
**4 is even**  
**5 is odd**  
**6 is even**  
**7 is odd**  
**8 is even**  
**9 is odd**  
**There are 4 even numbers in the vector.**   
## 参照  
 [ラムダ式](../cpp/lambda-expressions-in-cpp.md)   
 [ラムダ式の例](../cpp/examples-of-lambda-expressions.md)   
 [生成](../Topic/generate.md)   
 [generate\_n](../Topic/generate_n.md)   
 [for\_each](../Topic/for_each.md)   
 [例外の仕様 \(スロー\)](../cpp/exception-specifications-throw-cpp.md)   
 [コンパイラの警告 \(レベル 1\) C4297](../Topic/Compiler%20Warning%20\(level%201\)%20C4297.md)   
 [Microsoft 固有の修飾子](../Topic/Microsoft-Specific%20Modifiers.md)