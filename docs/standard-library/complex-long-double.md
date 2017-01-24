---
title: "complex&lt;long double&gt; | Microsoft Docs"
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
  - "std::complex<long double>"
  - "complex<long double>"
  - "std.complex<long double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex<long double> 関数"
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# complex&lt;long double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

順序付けされたオブジェクトのペア \(いずれも `long double` 型\) を格納するオブジェクトについて説明します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。  
  
## 構文  
  
```  
template<>  
   class complex<long double> {  
public:  
   constexpr complex(  
      long double _RealVal = 0,   
      long double _ImagVal = 0  
   );  
complex(  
      constexpr complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### パラメーター  
 `_RealVal`  
 構築される複素数の実数部の **long double** 型の値。  
  
 `_ImagVal`  
 構築される複素数の虚数部の `long double` 型の値。  
  
 `_ComplexNum`  
 **double** 型または **float** 型で、その実数部と虚数部の値が、構築される `long double` 型の複素数の初期化に使用される複素数。  
  
## 戻り値  
 `long double` 型の複素数。  
  
## 解説  
 テンプレート クラス complex の `long double` 型の complex クラスに対する明示的な特殊化と、テンプレート クラスによって定義されるコンストラクター内でのみ使用するテンプレート クラスとは異なります。  `long double` から **float** への変換は暗黙的に行えますが、**double** から `long double` への変換は **explicit** でなければなりません。  **explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。  
  
 テンプレート クラス `complex` の詳細については、「[complex クラス](../standard-library/complex-class.md)」を参照してください。  テンプレート クラス `complex` のメンバー一覧については、以下を参照してください。  
  
## 使用例  
  
```  
// complex_comp_ld.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <long double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 1.0 , 3.0 );  
   complex <long double> c2longdouble ( c2float );  
   cout << "Implicit conversion from type float to type long double,"  
        << "\n gives c2longdouble = " << c2longdouble << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type double  
   complex <double> c3double ( 3.0 , 4.0 );  
   complex <long double> c3longdouble ( c3double );  
   cout << "Implicit conversion from type long double to type float,"  
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
  
  **実数部と虚数部の初期値を**  
 **float 型として指定すると、c1 \= \(4,5\)**  
**float 型から long double 型に暗黙的に変換すると、**  
 **c2longdouble \= \(1,3\)**  
**long double 型から float 型に暗黙的に変換すると、**  
 **c3longdouble \= \(3,4\)**  
**abs \( c3 \) \= 5 を使用すると、c3 の剰余が c3 から復元される**  
**次の式を使用すると、c3 の引数が c3 から復元される**  
 **arg \( c3 \) \= 0.927295 radians \(53.1301 度に相当\)**   
## 必要条件  
 **ヘッダー:** \<complex\>  
  
 **名前空間:** std  
  
## 参照  
 [complex クラス](../standard-library/complex-class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)