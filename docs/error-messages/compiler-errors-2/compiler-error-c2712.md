---
title: "コンパイラ エラー C2712 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 89b7d0ad3c7e175db1525c2f3fb8407240ce943c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2712"></a>コンパイラ エラー C2712
オブジェクト アンワインディングが必要な関数内で __try を使用できません。  
  
 エラー C2712 は、使用する場合に発生する可能性が[/EHsc](../../build/reference/eh-exception-handling-model.md)、構造化例外処理もに関数がアンワインド (破棄) を必要とするオブジェクト。  
  
 考えられる解決策:  
  
-   SEH を必要とするコードを別の関数に移動します。  
  
-   デストラクターを含むローカル変数とパラメーターを使用しないように、SEH を使用する関数を記述し直します。 コンストラクターまたはデストラクターで SEH を使用しないようにします。  
  
-   /EHsc を使用せずにコンパイルします。  
  
 エラー C2712 を使用して宣言されているメソッドを呼び出す場合にも発生する、 [_ _event](../../cpp/event.md)キーワードです。 コンパイラが、基になるイベント オブジェクトの操作を防止し、SEH で生成されたコードを囲むコードを生成するため、イベントは、マルチ スレッド環境で使用される可能性があります、 [try-finally ステートメント](../../cpp/try-finally-statement.md)します。 その結果、イベント メソッドを呼び出し、型にデストラクターが含まれる引数を値渡しで渡すと、エラー C2712 が発生します。 このような場合の解決策の&1; つとして、引数を定数参照として渡します。  
  
## <a name="example"></a>例  
 C2712 は使用してコンパイルする場合にも発生する**/clr: 純粋な**内のポインター-関数の静的な配列を宣言し、`__try`ブロックします。 静的メンバーには、動的な初期化を使用するコンパイラが必要です。 **/clr: 純粋な**、C++ 例外処理が含まれています。 しかし、`__try` ブロックでは C++ の例外処理を実行できません。  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 次の例では、C2712 を生成し、その修正方法を示しています。  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```
