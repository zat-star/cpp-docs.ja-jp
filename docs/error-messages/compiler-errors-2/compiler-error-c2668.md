---
title: "コンパイラ エラー C2668 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: efb9abfa44a9c90d44a87046a6320a5e4ace8f57
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2668"></a>コンパイラ エラー C2668
'function': オーバー ロードされた関数のあいまいな呼び出し  
  
 指定されたオーバー ロードされた関数の呼び出しを解決できませんでした。 1 つ以上の実際のパラメーターを明示的にキャストすることがあります。  
  
 テンプレートを使用して、このエラーを取得することもできます。 同じクラスには、通常のメンバー関数と同じシグネチャを持つ template 宣言されたメンバー関数がある場合、テンプレート化された&1; つを最初に記述する必要があります。 これは、Visual C の現在の実装の制限です。  
  
 関数テンプレートの部分的な順序付けの詳細については、サポート技術情報資料 Q240869 を参照してください。  
  
 サポートする COM オブジェクトを含む ATL プロジェクトを作成するかどうかは`ISupportErrorInfo`、サポート技術情報記事 Q243298 を参照してください。  
  
## <a name="example"></a>例  
 次の例では C2668 が生成されます。  
  
```  
// C2668.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
  
void func( X, X ){}  
void func( A, B ){}  
D d;  
int main() {  
   func( d, d );   // C2668 D has an A, B, and X   
   func( (X)d, (X)d );   // OK, uses func( X, X )  
}  
```  
  
## <a name="example"></a>例  
 このエラーを解決するのには別の方法として、[宣言を使用して](../../cpp/using-declaration.md):  
  
```  
// C2668b.cpp  
// compile with: /EHsc /c  
// C2668 expected  
#include <iostream>  
class TypeA {  
public:  
   TypeA(int value) {}  
};  
  
class TypeB {  
   TypeB(int intValue);  
   TypeB(double dbValue);  
};  
  
class TestCase {  
public:  
   void AssertEqual(long expected, long actual, std::string  
                    conditionExpression = "");  
};  
  
class AppTestCase : public TestCase {  
public:  
   // Uncomment the following line to resolve.  
   // using TestCase::AssertEqual;  
   void AssertEqual(const TypeA expected, const TypeA actual,  
                    std::string conditionExpression = "");  
   void AssertEqual(const TypeB expected, const TypeB actual,  
                    std::string conditionExpression = "");  
};  
  
class MyTestCase : public AppTestCase {  
   void TestSomething() {  
      int actual = 0;  
      AssertEqual(0, actual, "Value");  
   }  
};  
```  
  
## <a name="example"></a>例  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラへの準拠作業の結果として生成することもできます。: 定数 0 のキャストにあいまいな変換です。  
  
 Long 型と void * int の両方への変換が必要なために、0 の定数を使用してキャストの変換はあいまいです。 このエラーを解決するには、変換を実行 (このコードと Visual Studio .NET 2003 および Visual Studio .NET のバージョンの Visual C で有効である場合は) 必要がないようにするは使用されているが、関数のパラメーターの正確な型に 0 をキャストします。  
  
```  
// C2668c.cpp  
#include "stdio.h"  
void f(long) {  
   printf_s("in f(long)\n");  
}  
void f(void*) {  
   printf_s("in f(void*)\n");  
}  
int main() {  
   f((int)0);   // C2668  
  
   // OK  
   f((long)0);  
   f((void*)0);  
}  
```  
  
## <a name="example"></a>例  
 このエラーは、CRT は浮動小数点演算とすべての数値演算関数の&2; つのフォームを持つために発生することができます。  
  
```  
// C2668d.cpp  
#include <math.h>  
int main() {  
   int i = 0;  
   float f;  
   f = cos(i);   // C2668  
   f = cos((float)i);   // OK  
}  
```  
  
## <a name="example"></a>例  
 (Int、int) pow は CRT の math.h から削除されたために、このエラーが発生することができます。  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```
