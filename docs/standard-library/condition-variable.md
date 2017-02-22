---
title: "&lt;condition_variable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<condition_variable>"
dev_langs: 
  - "C++"
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;condition_variable&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

true にするための基準を待機するオブジェクトを作成するために使用されるクラス [condition\_variable](../standard-library/condition-variable-class.md) と [condition\_variable\_any](../standard-library/condition-variable-any-class.md) を定義します。  
  
 このヘッダーでは同時実行ランタイム \(ConcRT\) が使用されます。これにより、このヘッダーを他の ConcRT メカニズムと共に使用できます。  ConcRT の詳細については、「[同時実行ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。  
  
## 構文  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  **\/clr** や **\/clr:pure** を使用してコンパイルされたコードでは、このヘッダーはブロックされます。  
  
### 解説  
 条件の変数の待機は、`mutex`を使用しなければならないコード。  呼び出し元のスレッドは、条件の変数を待機している関数を呼び出す前に `mutex` をロックする必要があります。  `mutex` 時は、呼び出された関数の戻り値がロックされます。  `mutex` はスレッドが true になるように条件を待機している間、ロックされません。  予測できない結果になるように、条件の変数の待機が `mutex` の同じオブジェクトを使用する必要があります。各スレッド。  
  
 型 `condition_variable_any` オブジェクトは、任意の型のミューテックスで使用できます。  使用されるミューテックスの種類は `try_lock` のメソッドを用意する必要はありません。  型 `condition_variable` オブジェクトは型の `unique_lock<mutex>`ミューテックスでのみ使用できます。  この型のオブジェクトは型 `condition_variable_any<unique_lock<mutex>>`オブジェクトより高速になる場合があります。  
  
 イベントを待機するには、まずミューテックスをロックし、条件の変数の `wait` のメソッドのうち 1 つを呼び出します。  別のスレッドの `wait` までの呼び出しのブロックは、条件の変数に通知します。  
  
 *Paddle のアラームは*、条件の変数を待機しているスレッドが適切な通知なしにブロックされなくなると発生します。  コードが待機関数から戻ると条件の待機条件が True になる明示的に条件をチェックする必要があります。このような Paddle のアラームを識別するには、コード。  これは通常、ループを使用して;されます ためのループの実行に `wait(unique_lock<mutex>& lock, Predicate pred)` を使用できます。  
  
```cpp  
while (condition is false)  
    wait for condition variable;  
```  
  
 `condition_variable_any` と `condition_variable` はそれぞれを持つ条件を待機する 3 種類のメソッドを使用します。  
  
-   Infinite の`wait` の を待ちます。  
  
-   指定 `time`までの`wait_until` の を待ちます。  
  
-   指定 `time interval`の`wait_for` の を待ちます。  
  
 これらのメソッドには、それぞれの 2 種類のバージョンがあります。  第 1 の方法では、待ち、疑って目覚めるできます。  そのほかの述語を定義する追加テンプレート引数を受け取ります。  メソッドは、述語が `true`になるまで制御を戻しません。  
  
 各クラスには、状態 `true`です。条件の変数を通知するために使用される 2 種類のメソッドがあります。  
  
-   `notify_one` は、条件の変数を待機しているスレッドの 1 を目覚めます。  
  
-   `notify_all` は、条件の変数を待機しているスレッドをすべて目覚めます。  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [condition\_variable クラス](../standard-library/condition-variable-class.md)   
 [condition\_variable\_any クラス](../standard-library/condition-variable-any-class.md)   
 [cv\_status 列挙型](../Topic/cv_status%20Enumeration.md)