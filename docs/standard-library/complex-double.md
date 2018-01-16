---
title: complex&lt;double&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: complex/std::complex<double>
dev_langs: C++
helpviewer_keywords: complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b279b78c309dd9fff87954d9b50b255b7f0d9f25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;
順序付けされたオブジェクトのペア (いずれも **double***,* 型) を格納するオブジェクトについて説明します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as template class complex
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `RealVal`  
 構築される複素数の実数部の **double** 型の値。  
  
 `ImagVal`  
 構築される複素数の虚数部の **double** 型の値。  
  
 `complexNum`  
 **float** 型または `long double` 型で、その実数部と虚数部の値が、構築される **double** 型の複素数の初期化に使用される複素数。  
  
## <a name="return-value"></a>戻り値  
 **double** 型の複素数。  
  
## <a name="remarks"></a>コメント  
 テンプレート クラス complex の **double** 型の complex クラスに対する明示的な特殊化と、テンプレート クラスによって定義されるコンストラクター内でのみ使用するテンプレート クラスとは異なります。 **float** から **double** への変換は暗黙的に行えますが、`long double` から **double** への変換は**明示的**でなければなりません。 **explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。  
  
 テンプレート クラス `complex` の詳細については、「[complex クラス](../standard-library/complex-class.md)」を参照してください。 テンプレート クラス `complex` のメンバー一覧については、以下を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
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
\* Output:   
Specifying initial real & imaginary parts,  
 as type double gives c1 = (4,5)  
Implicit conversion from type float to type double,  
 gives c2double = (4,5)  
Explicit conversion from type float to type double,  
 gives c3longdouble = (4,5)  
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312  
Argument of c3 is recovered from c3 using:  
 arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.  
*\  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: \<complex>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [complex クラス](../standard-library/complex-class.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



