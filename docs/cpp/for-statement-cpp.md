---
title: "for ステートメント (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for キーワード [C++]"
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

条件が偽 \(false\) になるまでステートメントを繰り返し実行します。  範囲ベースの for ステートメントの詳細については、「[範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)」を参照してください。  
  
## 構文  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## 解説  
 指定された回数だけ実行する必要のあるループの構築に `for` ステートメントを使用します。  
  
 次の表に示すように、`for` ステートメントは 3 つのオプション部分から構成されます。  
  
### for ループ要素  
  
|構文の名前|実行タイミング|説明|  
|-----------|-------------|--------|  
|`init-expression`|**for** ステートメントの他の要素の前。`init-expression` は一度だけ実行されます。  その後、制御は `cond-expression` に渡されます。|ループ インデックスを初期化するためによく使用されます。  式または宣言を含めることができます。|  
|`cond-expression`|最初のイテレーションを含む `statement` の各イテレーションの実行前。  `statement` は、`cond-expression` が true \(0 以外\) に評価された場合にのみ実行されます。|整数型に評価される式、または整数型へのあいまいでない変換が行われるクラス型。  通常、for ループの終了条件をテストするために使用します。|  
|`loop-expression`|`statement` の各イテレーションの終了時。  `loop-expression` の実行後に `cond-expression` が実行されます。|通常、ループ インデックスのインクリメントに使用します。|  
  
 次の例では、`for` ステートメントを使用するさまざまな方法を示しています。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` と `loop-expression` には、コンマで区切った複数のステートメントを含めることができます。  たとえば、次のようにします。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression` はインクリメントまたはデクリメントするか、他の方法で変更することができます。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 `for` ループは、`statement` 内の [break](../cpp/break-statement-cpp.md)、[return](../Topic/return%20Statement%20\(C++\).md)、または [goto](../cpp/goto-statement-cpp.md) \(**for** ループの外側のラベルが付いたステートメントに対する\) が実行されると終了します。  `for` ループ内の [continue](../cpp/continue-statement-cpp.md) ステートメントは、現在のイテレーションのみを終了します。  
  
 `cond-expression` が省略されている場合は true と見なされ、**for** ループは `statement` 内の `break`、`return`、または `goto` なしでは終了しません。  
  
 通常、`for` ステートメントの 3 種類のフィールドは初期化、終了のテスト、およびインクリメントのためによく使用されますが、これらの使用に限定されません。  たとえば、次のコードは、数値 0 ～ 4 を出力します。  この場合、`statement` は null ステートメントです。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## for ループおよび C\+\+ 標準  
 C\+\+ 標準では `for` ループの終了後に `for` ループ内で宣言された変数がスコープ外に出ることを通知します。  次のように記述します。  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 既定では、[\/Ze](../build/reference/za-ze-disable-language-extensions.md) の下に、`for` ループの外側のスコープが終了するまで、`for` ループで宣言された変数がスコープ内に残ります。  
  
 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) は、\/Za を指定せずに for ループで宣言された変数の標準動作を有効にします。  
  
 また、次のように、\/Ze の下で変数を再宣言するために `for` ループのスコープの相違点を使用することも可能です。  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 これにより、`for` ループで宣言された変数の標準動作がより正確に模倣されます。その場合、ループの終了後にスコープ外に出るために `for` ループで宣言された変数が必要です。  変数が `for` ループで宣言される場合、既に同じ名前のローカル変数がある場合でも、コンパイラは `for` ループの外側のスコープでローカル変数に内部的に引き上げます。  
  
## 参照  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [while ステートメント \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while ステートメント \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)