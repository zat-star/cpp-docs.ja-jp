---
title: "complex&lt;double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.complex<double>"
  - "complex<double>"
  - "std::complex<double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "複雑な < double > 関数"
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# complex&lt;double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

順序付けされたオブジェクトのペア \(いずれも **double**型\) を格納するオブジェクトについて説明します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。  
  
## 構文  
  
```  
template<>  
   class complex<double> {  
public:  
   constexpr complex(  
      double _RealVal = 0,   
      double _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr explicit complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### パラメーター  
 `_RealVal`  
 構築される複素数の実数部の **double** 型の値。  
  
 `_ImagVal`  
 構築される複素数の虚数部の **double** 型の値。  
  
 `_ComplexNum`  
 **float** 型または `long double` 型で、その実数部と虚数部の値が、構築される **double** 型の複素数の初期化に使用される複素数。  
  
## 戻り値  
 **double** 型の複素数。  
  
## 解説  
 テンプレート クラス complex の **double** 型の complex クラスに対する明示的な特殊化と、テンプレート クラスによって定義されるコンストラクター内でのみ使用するテンプレート クラスとは異なります。**float** から **double** への変換は暗黙的に行えますが、`long double` から **double** への変換は **explicit** でなければなりません。**explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。  
  
 このテンプレート クラスの詳細については `complex`, を参照してください [complex クラス](../standard-library/complex-class.md)します。 テンプレート クラス `complex` のメンバー一覧については、以下を参照してください。  
  
## 使用例  
  
```  
// complex_comp_dbl.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type double gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 4.0 , 5.0 );  
   complex <double> c2double ( c2float );  
   cout << "Implicit conversion from type float to type double,"  
        << "\n gives c2double = " << c2double << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 4.0 , 5.0 );  
   complex <double> c3double ( c3longdouble );  
   cout << "Explicit conversion from type float to type double,"  
        << "\n gives c3longdouble = " << c3longdouble << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3longdouble );  
   double argc3 = arg ( c3longdouble );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
 **初期実際 & 仮想的な部分を指定すると、として型二重により c1 \= により c2double double 型への float 型 \(4,5\) 暗黙的に変換により c3longdouble double 型への float 型に明示的に変換 \(4,5\) \= \= \(4, 5\) c3 の剰余が c3 を使用してから回復しました: abs \(c3\) \= 6.40312 c3 の引数が c3 を使用してから回復しました: arg \(c3\) 51.3402 度で 0.896055 ラジアン \= です。**   
## 必要条件  
 **ヘッダー**: \<complex\>  
  
 **名前空間:** std  
  
## 参照  
 [complex クラス](../standard-library/complex-class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)