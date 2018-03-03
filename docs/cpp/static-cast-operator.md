---
title: "static_cast 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- static_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3913937d9099304c478404c4c55a09fa54392785
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="staticcast-operator"></a>static_cast 演算子
変換、*式*の型に*タイプ id*は式内に存在する型にのみ基づいてです。  
  
## <a name="syntax"></a>構文  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>コメント  
 標準 C++ では、変換の安全性を確認する実行時の型チェックはありません。 C++/CX では、コンパイル時チェックと実行時チェックが実行されます。 詳細については、次を参照してください。[キャスト](casting.md)です。  
  
 `static_cast` 演算子は、基底クラスへのポインターを派生クラスへのポインターに変換するなどの操作に使用できます。 このような変換は、必ずしも安全であるとは限りません。  
  
 一般に、列挙から int、または int から float のような数値データ型の変換には、`static_cast` を使用することで、データ型を特定して変換を行うことができます。 `static_cast` が実行時の型チェックを実行する一方で `dynamic_cast` は実行しないため、`static_cast` 変換は `dynamic_cast` 変換ほど安全ではありません。 あいまいなポインターへの `dynamic_cast` は失敗しますが、`static_cast` は何も問題ないように戻ります。これは危険です。 `dynamic_cast` 変換がより安全ですが、`dynamic_cast` は、ポインターまたは参照にのみ機能し、ランタイム型チェックはオーバーヘッドです。 詳細については、次を参照してください。 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)です。  
  
 次の例では、`D* pd2 = static_cast<D*>(pb);` は `D` にないフィールドとメソッドがあるため、行 `B` は安全ではありません。 ただし、`B* pb2 = static_cast<B*>(pd);` には `D` のすべてが常に含まれているため、行 `B` は安全な変換です。  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 対照的に[dynamic_cast](../cpp/dynamic-cast-operator.md)、実行時チェックが行われません、`static_cast`への変換`pb`です。 `pb` によってポイントされるオブジェクトは、型 `D` のオブジェクトではない場合があります。その場合は、`*pd2` を使用すると、深刻な結果が発生する可能性があります。 たとえば、`D` クラスではなく、`B` クラスのメンバーである関数を呼び出すと、アクセス違反が発生する可能性があります。  
  
 `dynamic_cast` と `static_cast` 演算子は、クラス階層構造のあらゆる場所にポインターを移動します。 ただし、`static_cast` はキャスト ステートメントで提供される情報に排他的に依存するため、安全でない場合があります。 例:  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 `pb` が `D` 型のオブジェクトを実際に指し示している場合、`pd1` および `pd2` は同じ値になります。 また、`pb == 0` の場合、同じ値も取得します。  
  
 `pb` が `B` 型のオブジェクトを指し示し、完全な `D` クラスを指し示していない場合、`dynamic_cast` には、0 を返す十分な認識があります。 ただし、`static_cast` は、`pb` が `D` 型のオブジェクトを指し示すというプログラマのアサーションに依存し、単純にその想定される `D` オブジェクトへのポインターを返します。  
  
 その結果、`static_cast` は暗黙的な型変換の逆の操作を行うことができますが、その場合の結果は未定義になります。 `static_cast` 変換の結果が安全かどうかの検証は、プログラマが行うことです。  
  
 この動作は、クラス型以外の型にも適用されます。 たとえば、int から `static_cast` に変換するために `char` を使用できます。 ただし、結果の `char` には、`int` 値全体を格納できる十分なビットがない場合があります。 もう一度に任されていることを確認するプログラマの結果、`static_cast`変換が安全です。  
  
 `static_cast` 演算子は、標準変換やユーザー定義変換など、暗黙の変換を実行するために使用することもできます。 例:  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 `static_cast` 演算子では、整数値を明示的に列挙型に変換できます。 整数型の値が列挙値の範囲内にない場合、結果の列挙値は未定義になります。  
  
 `static_cast` 演算子は、null ポインター値を変換先の型の null ポインター値に変換します。  
  
 式は、`static_cast` 演算子で void 型に明示的に変換できます。 変換先の void 型は、オプションで、`const`、`volatile`、または `__unaligned` 属性を含むことができます。  
  
 `static_cast` 演算子は、`const`、`volatile`、または `__unaligned` 属性をキャストできません。 参照してください[const_cast 演算子](../cpp/const-cast-operator.md)これらの属性を削除する方法についてです。  
  
 再配置を行うガベージ コレクターの先頭で unchecked キャストを実行する危険性があるため、`static_cast` は、正しく機能することがわかっている場合にパフォーマンスが重要なコードでのみ使用する必要があります。 使用する場合は`static_cast`リリース モードでは、置換後[safe_cast](../windows/safe-cast-cpp-component-extensions.md)にデバッグ ビルドで成功を確認してください。  
  
## <a name="see-also"></a>参照  
 [キャスト演算子](../cpp/casting-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)