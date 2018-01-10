---
title: "typeid 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b27f3bcb7358b3ea05907df1a4372c107538dfb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="typeid-operator"></a>typeid 演算子
## <a name="syntax"></a>構文  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## <a name="remarks"></a>コメント  
 `typeid` 演算子は、オブジェクトの型を実行時に決定できるようにします。  
  
 結果`typeid`は、 **const type_info &**です。 値がへの参照を**type_info**いずれかを表すオブジェクト、*タイプ id*またはの種類、*式*の形式に応じて、`typeid`を使用. 参照してください[type_info クラス](../cpp/type-info-class.md)詳細についてはします。  
  
 `typeid`演算子はマネージ型 (抽象宣言子またはのインスタンス) では機能しませんを参照してください[typeid](../windows/typeid-cpp-component-extensions.md)取得について、<xref:System.Type>指定の型。  
  
 `typeid` 演算子は、オブジェクトの実際の型を指定された静的な情報によって判断できない場合に、ポリモーフィックなクラス型の左辺値への適用時にランタイム チェックを実行します。 そのようなケースを次に示します。  
  
-   クラスへの参照  
  
-   * で逆参照されるポインター  
  
-   添字付きのポインター ([ ]) (一般に、ポリモーフィックな型へのポインターで添字を使用すると、安全ではないことに注意してください)。  
  
 場合、*式*まだその基底クラスから派生した型のオブジェクトが実際には、基本クラス型を指す、 **type_info**派生クラスは、結果を参照します。 *式*ポリモーフィック型 (仮想関数を持つクラス) をポイントする必要があります。 それ以外の場合、結果は、 **type_info**で参照される静的クラスの*式*です。 さらに、ポインターが指し示すオブジェクトが使用されるように、ポインターを逆参照する必要があります。 ポインターを逆参照なしになります、 **type_info**どのような it ではないが指すポインターです。 例:  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 場合、*式*、ポインターを逆参照でポインターの値が 0、 **typeid**スロー、 [bad_typeid 例外](../cpp/bad-typeid-exception.md)です。 ポインターが有効なオブジェクトを指していない場合は、`__non_rtti_object`例外をスローすると、エラーをトリガーした RTTI を分析しようを示す (アクセス違反など)、オブジェクトが何らかの理由で無効 (無効なポインターまたはコードされなかったでコンパイルされた[/GR](../build/reference/gr-enable-run-time-type-information.md))。  
  
 場合、*式*はポインターでも、オブジェクトの基底クラスへの参照を結果は、 **type_info**参照の静的な型を表す、*式*. *静的な型*式の型を参照式のコンパイル時に認識されています。 実行セマンティクスは、式の静的な型を評価するときは無視されます。 さらに、式の静的な型を判断するときに、参照は可能な限り無視されます。  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid**できますもテンプレートで使用するテンプレート パラメーターの種類を判断します。  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム型情報](../cpp/run-time-type-information.md)   
 [キーワード](../cpp/keywords-cpp.md)