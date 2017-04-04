---
title: complex&lt;float&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::complex<float>
- std.complex<float>
- complex<float>
dev_langs:
- C++
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
caps.latest.revision: 23
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
ms.openlocfilehash: b3c76d33bcdf1e5882bd09b49c73dcef4d0474b3
ms.lasthandoff: 02/24/2017

---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;
順序付けされたオブジェクトのペア (いずれも **float*** *型) を格納するオブジェクトについて説明します。最初のオブジェクトが複素数の実数部、2 番目のオブジェクトが虚数部を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `_RealVal`  
 構築される複素数の実数部の **float** 型の値。  
  
 `_ImagVal`  
 構築される複素数の虚数部の **float** 型の値。  
  
 `complexNum`  
 **double** 型または `long double` 型で、その実数部と虚数部の値が、構築される **float** 型の複素数の初期化に使用される複素数。  
  
## <a name="return-value"></a>戻り値  
 **float** 型の複素数。  
  
## <a name="remarks"></a>コメント  
 テンプレート クラス complex の **float** 型の complex クラスに対する明示的な特殊化と、テンプレート クラスによって定義されるコンストラクター内でのみ使用するテンプレート クラスとは異なります。 **float** から **double** への変換は暗黙的に行えますが、安全性の低い **float** から `long double` への変換は **explicit** でなければなりません。 **explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。  
  
 テンプレート クラス `complex` の詳細については、「[complex クラス](../standard-library/complex-class.md)」を参照してください。 テンプレート クラス `complex` のメンバー一覧については、以下を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// complex_comp_flt.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <float> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type double  
   complex <double> c2double ( 1.0 , 3.0 );  
   complex <float> c2float ( c2double );  
   cout << "Implicit conversion from type double to type float,"  
        << "\n gives c2float = " << c2float << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 3.0 , 4.0 );  
   complex <float> c3float ( c3longdouble );  
   cout << "Explicit conversion from type long double to type float,"  
        << "\n gives c3float = " << c3float << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3float);  
   double argc3 = arg ( c3float);  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
\* Output:   
Specifying initial real & imaginary parts,  
 as type float gives c1 = (4,5)  
Implicit conversion from type double to type float,  
 gives c2float = (1,3)  
Explicit conversion from type long double to type float,  
 gives c3float = (3,4)  
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5  
Argument of c3 is recovered from c3 using:  
 arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.  
*\  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: \<complex>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [complex クラス](../standard-library/complex-class.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




