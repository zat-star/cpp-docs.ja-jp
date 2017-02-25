---
title: "valarray クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "valarray"
  - "std.valarray"
  - "std::valarray"
  - "valarray/std::valarray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray クラス"
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# valarray クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、型の要素のシーケンスを制御するオブジェクトを表します **型** を配列として格納され、高速の数学的演算を実行するために設計されていますおよび計算のパフォーマンスの最適化されます。  
  
## <a name="remarks"></a>コメント  
 このクラスは、順序付けられた値のセットからなる数学的な概念の表現で、要素はゼロから順に番号が付けられます。 など、コンテナー、シーケンス処理をファースト クラスの機能のいくつかサポートしているために、近くのコンテナーとして、クラスが説明されている [ベクトル](../standard-library/vector-class.md), をサポートします。 次の 2 つの重要な点で、テンプレート クラス vector とは異なります。  
  
-   対応する要素の間で多数の算術演算を定義 **valarray \< 種類>** 同じの型と長さ、オブジェクトなど *xarr* = cos ( *yarr*) + sin ( *zarr*)。  
  
-   さまざまな添字の興味深い方法を定義、 **valarray \< 種類>** のオーバー ロードによって、オブジェクト [演算子 & #91、#93;](#valarray__operator_at)します。  
  
 クラスのオブジェクト **型**:  
  
-   従来の動作で、パブリックな既定のコンストラクター、デストラクター、コピー コンストラクター、および代入演算子が用意されています。  
  
-   従来の動作で、必要に応じて浮動小数点型に対して定義される算術演算子と数学関数を定義します。  
  
 特に、コピーによる構築と、代入に先行する既定の構築の間に、微妙な違いはありません。 クラスのオブジェクトに対する操作のいずれも **型** 例外をスローする可能性があります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[valarray](#valarray__valarray)|構築、 `valarray` 要素の特定の値または別のコピーとして、特定のサイズまたは `valarray` または別のサブセット `valarray`します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[value_type](#valarray__value_type)|`valarray` 内に格納された要素の型を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[適用](#valarray__apply)|`valarray` 内の各要素に対して指定された関数を適用します。|  
|[cshift](#valarray__cshift)|指定された位置数で、`valarray` 内のすべての要素を周期的にシフトします。|  
|[解放](#valarray__free)|`valarray` によって使用されるメモリを解放します。|  
|[max](#valarray__max)|`valarray` 内の最大要素を検索します。|  
|[最小値](#valarray__min)|`valarray` 内の最小要素を検索します。|  
|[サイズを変更します。](#valarray__resize)|必要に応じて要素を追加または削除して、`valarray` 内の要素数を指定された数に変更します。|  
|[shift キー](#valarray__shift)|`valarray` 内のすべての要素を指定された位置数だけシフトします。|  
|[サイズ](#valarray__size)|`valarray` 内の要素数を検索します。|  
|[合計](#valarray__sum)|`valarray` 内にある長さが 0 以外の要素すべての合計を求めます。|  
|[スワップ](#valarray__swap)||  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子。](#valarray__operator_not)|`valarray` 内の各要素の論理 `NOT` 値を取得する、単項演算子。|  
|[operator % =](#valarray__operator_mod_eq)|指定された `valarray` または要素型の値で配列の要素を要素ごとに除算した剰余を取得します。|  
|[演算子 & =](#valarray__operator_amp__eq)|配列内の要素のビットごとの `AND` を、指定された `valarray` 内の対応する要素か要素型の値と共に取得します。|  
|[演算子 >> =](#valarray__operator_gt__gt__eq)|`valarray` オペランドの各要素のビットを、指定された位置数だけ右にシフトさせるか、2 番目の `valarray` で指定された要素ごとの量だけ右にシフトさせます。|  
|[演算子 << =](#valarray__operator_lt__lt__eq)|`valarray` オペランドの各要素のビットを、指定された位置数だけ左にシフトさせるか、2 番目の `valarray` で指定された要素ごとの量だけ左にシフトさせます。|  
|[演算子 * =](#valarray__operator_star_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` に対して乗算します。|  
|[operator +](#valarray__operator_add)|`valarray` 内の各要素に正符号を適用する単項演算子。|  
|[operator + =](#valarray__operator_add_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` に対して加算します。|  
|[演算子の](#valarray__operator-)|`valarray` 内の各要素に負符号を適用する単項演算子。|  
|[-= 演算子](#valarray__operator-_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` から減算します。|  
|[演算子/=](#valarray__operator__eq)|オペランド `valarray` を、指定された `valarray` の要素か要素型の値で要素ごとに除算します。|  
|[演算子 =](#valarray__operator_eq)|値が直接指定されているか、または他の `valarray` か `slice_array`、`gslice_array`、`mask_array`、や `indirect_array` の一部として値が指定されている `valarray` に要素を代入します。|  
|[演算子 & #91、#93 です。](#valarray__operator_at)|指定されたインデックスまたは指定されたサブセットにある、要素またはその値への参照を返します。|  
|[演算子 ^ =](#valarray__operator_xor_eq)|Element-wise 排他的論理 or 演算子を取得 ( `XOR`) の指定した valarray または要素の型の値を持つ配列です。|  
|[演算子 &#124; =](#valarray__operator_or_eq)|配列内の要素のビットごとの `OR` を、指定された `valarray` 内の対応する要素か要素型の値と共に取得します。|  
|[演算子 ~](#valarray__operator_dtor)|`valarray` 内の各要素のビットごとの `NOT` 値を取得する単項演算子。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< valarray>  
  
 **名前空間:** std  
  
##  <a name="a-namevalarrayapplya-valarrayapply"></a><a name="valarray__apply"></a>  valarray::apply  
 Valarray の各要素に指定された関数を適用します。  
  
```  
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *_Func(Type)*  
 オペランド valarray の各要素に適用する関数オブジェクト。  
  
 *_Func(const Type&)*  
 オペランド valarray の各要素に適用される const の関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 要素を持って valarray `_Func` オペランド valarray の要素に element-wise 適用します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、クラスのオブジェクトを返します。 [valarray](../standard-library/valarray-class.md)**\< 種類>**, 、長さの [サイズ](#valarray__size), 、要素の各 `I` は **func**(( **\*これ**) [ `I`])。  
  
### <a name="example"></a>例  
  
```  
// valarray_apply.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
using namespace std;  
  
int __cdecl MyApplyFunc( int n )  
{  
   return n*2;  
}  
  
int main( int argc, char* argv[] )  
{  
   valarray<int> vaR(10), vaApplied(10);  
   int i;  
  
   for ( i = 0; i < 10; i += 3 )  
      vaR[i] = i;  
  
   for ( i = 1; i < 10; i += 3 )  
      vaR[i] = 0;  
  
   for ( i = 2; i < 10; i += 3 )  
      vaR[i] = -i;  
  
   cout << "The initial Right valarray is: (";  
   for   ( i=0; i < 10; ++i )  
      cout << " " << vaR[i];  
   cout << " )" << endl;  
  
   vaApplied = vaR.apply( MyApplyFunc );  
  
   cout << "The element-by-element result of "  
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";  
   for ( i = 0; i < 10; ++i )  
      cout << " " << vaApplied[i];  
   cout << " )" << endl;  
}  
\* Output:   
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )  
The element-by-element result of applying MyApplyFunc to vaR is the  
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )  
*\  
```  
  
##  <a name="a-namevalarraycshifta-valarraycshift"></a><a name="valarray__cshift"></a>  valarray::cshift  
 指定した桁数で valarray 内のすべての要素を周期的戻しています。  
  
```  
valarray<Type> cshift(int count) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` count`  
 要素を前方にシフトする対象の場所の数。  
  
### <a name="return-value"></a>戻り値  
 移動された要素に指定したすべての新しい valarray ` count` 周期オペランド valarray 内の位置を基準に左 valarray の前部に位置します。  
  
### <a name="remarks"></a>コメント  
 値が正 ` count` 周期左の要素のシフト ` count` を配置します。  
  
 負の値の ` count` 周期右の要素のシフト ` count` を配置します。  
  
### <a name="example"></a>例  
  
```  
// valarray_cshift.cpp  
// compile with: /EHsc  
  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
  
    valarray<int> va1(10), va2(10);  
    for (i = 0; i < 10; i+=1)  
        va1[i] = i;  
    for (i = 0; i < 10; i+=1)  
        va2[i] = 10 - i;  
  
    cout << "The operand valarray va1 is: (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va1[i];  
    cout << ")" << endl;  
  
    // A positive parameter shifts elements right  
    va1 = va1.cshift(4);  
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va1[i];  
    cout << ")" << endl;  
  
    cout << "The operand valarray va2 is: (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va2[i];  
    cout << ")" << endl;  
  
    // A negative parameter shifts elements left  
    va2 = va2.cshift(-4);  
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va2[i];  
    cout << ")" << endl;  
}  
\* Output:   
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)  
The cyclically shifted valarray va1 is:  
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)  
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)  
The cyclically shifted valarray va2 is:  
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)  
*\  
```  
  
##  <a name="a-namevalarrayfreea-valarrayfree"></a><a name="valarray__free"></a>  valarray::free  
 Valarray によって使用されるメモリを解放します。  
  
```  
void free();
```  
  
### <a name="remarks"></a>コメント  
 この非標準の関数は、空の valarray を割り当てることと同じです。 例:  
  
```  
valarray<T> v;  
v = valarray<T>();

// equivalent to v.free()  
```  
  
##  <a name="a-namevalarraymaxa-valarraymax"></a><a name="valarray__max"></a>  valarray::max  
 Valarray 内で最も大きな要素を検索します。  
  
```  
Type max() const;
```  
  
### <a name="return-value"></a>戻り値  
 オペランド valarray の要素の最大値。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用して値を比較する **演算子 \<** または **演算子 >** クラスの要素のペア間 **型**, 、どのような操作には、要素の指定必要があります **型**します。  
  
### <a name="example"></a>例  
  
```  
// valarray_max.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i, MaxValue;  
  
   valarray<int> vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  2*i - 1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  10 - i;  
  
   cout << "The operand valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   MaxValue = vaR.max (  );  
   cout << "The largest element in the valarray is: "  
        << MaxValue  << "." << endl;  
}  
\* Output:   
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).  
The largest element in the valarray is: 13.  
*\  
```  
  
##  <a name="a-namevalarraymina-valarraymin"></a><a name="valarray__min"></a>  valarray::min  
 Valarray 内の最小の要素を検索します。  
  
```  
Type min() const;
```  
  
### <a name="return-value"></a>戻り値  
 オペランド valarray の要素の最小値。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用して値を比較する **演算子 \<** または **演算子 >** クラスの要素のペア間 **型**, 、どのような操作には、要素の指定必要があります **型**します。  
  
### <a name="example"></a>例  
  
```  
// valarray_min.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i, MinValue;  
  
   valarray<int> vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  2*i;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  5 - i;  
  
   cout << "The operand valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   MinValue = vaR.min ( );  
   cout << "The smallest element in the valarray is: "  
        << MinValue  << "." << endl;  
}  
\* Output:   
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).  
The smallest element in the valarray is: -9.  
*\  
```  
  
##  <a name="a-namevalarrayoperatornota-valarrayoperator"></a><a name="valarray__operator_not"></a>  valarray::operator!  
 単項演算子、論理を取得する **いない** valarray 内の各要素の値。  
  
```  
valarray<bool> operator!() const;
```  
  
### <a name="return-value"></a>戻り値  
 オペランド valarray の要素の値の否定であるブール値の valarray。  
  
### <a name="remarks"></a>コメント  
 論理演算 **いない** 、ものをすべてゼロに変換されたゼロ以外の値をすべての既定でし、ゼロに変換して、要素の符号を反転します。 ブール値の返された valarray では、オペランド valarray と同じサイズです。  
  
 ビットごと **いない**[valarray::operator ~](#valarray__operator_dtor) のバイナリ表現内のビットごとのレベルに符号を反転する `char` と `int` valarray の要素。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_lognot.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<bool> vaNOT ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT = !vaL;  
   cout << "The element-by-element result of "  
        << "the logical NOT operator! is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The element-by-element result of the logical NOT operator! is the  
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatormodeqa-valarrayoperator"></a><a name="valarray__operator_mod_eq"></a>  valarray::operator % =  
 指定した valarray または要素の型の値のいずれかに element-wise、配列の要素を除算した剰余を取得します。  
  
```  
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray またはと同じではオペランド valarray element-wise、分割するオペランド valarray の要素型の値。  
  
### <a name="return-value"></a>戻り値  
 要素は、除算の剰余、element-wise オペランド valarray の valarray で ` right.`  
  
### <a name="example"></a>例  
  
```  
// valarray_class_op_rem.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 6 ), vaR ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  53;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -67;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  3*i+1;  
  
   cout << "The initial valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL %= vaR;  
   cout << "The remainders from the element-by-element "  
        << "division is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 53 -67 53 -67 53 -67 ).  
The initial  right valarray is: ( 1 4 7 10 13 16 ).  
The remainders from the element-by-element division is the  
 valarray: ( 0 -3 4 -7 1 -3 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorampeqa-valarrayoperatoramp"></a><a name="valarray__operator_amp__eq"></a>  valarray::operator&amp;=  
 ビットごとの取得 **AND** 指定 valarray 内の対応要素または要素の型の値を配列の要素のです。  
  
```  
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray または結合するのには、オペランド valarray の場合と同じ、element-wise 論理によって、要素型の値 **AND** オペランド valarray とします。  
  
### <a name="return-value"></a>戻り値  
 要素は、element-wise valarray 論理 **AND** によってオペランド valarray の ` right.`  
  
### <a name="remarks"></a>コメント  
 ビットごとの演算は、ビットを操作する場合にのみ使用できます `char` と `int` データ型とバリアントされません **float**, 、**二重**, 、**longdouble**, 、`void`, 、`bool`, 、またはその他より複雑なデータ型。  
  
 ビットごとの AND が論理として同じ真理値表 **AND** がビットごとのレベルでのデータ型に適用されます。 ビットを指定した *b*1 と *b*2、 *b*1 **AND** *b*2 は **true** 両方のビットが true である場合 **false** 少なくとも 1 つの条件が false の場合。  
  
### <a name="example"></a>例  
  
```  
// valarray_class_op_bitand.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL &= vaR;  
   cout << "The element-by-element result of "  
        << "the logical AND operator&= is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the logical AND operator&= is the  
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorgtgteqa-valarrayoperatorgtgt"></a><a name="valarray__operator_gt__gt__eq"></a>  valarray::operator&gt;&gt;=  
 Valarray オペランドを 2 つ目の valarray で指定された element-wise 量または位置の指定した数の各要素に対してビットを右にシフトします。  
  
```  
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 右シフトまたは valarray の要素を持つことを示して element-wise 右シフトの量を示す値。  
  
### <a name="return-value"></a>戻り値  
 されている要素を持つ valarray は右シフトで指定した量 ` right`します。  
  
### <a name="remarks"></a>コメント  
 符号付き数値がある、アット マークは保持されます。  
  
### <a name="example"></a>例  
  
```  
// valarray_class_op_rs.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  64;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -64;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial operand valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL >>= vaR;  
   cout << "The element-by-element result of "  
        << "the right shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the right shift is the  
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorltlteqa-valarrayoperatorltlt"></a><a name="valarray__operator_lt__lt__eq"></a>  valarray::operator&lt;&lt;=  
 Valarray オペランドを 2 つ目の valarray で指定された element-wise 量または位置の指定した数の各要素に対してビットを左にシフトします。  
  
```  
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 左シフトまたは valarray の要素が左シフトの element-wise 量を指定の量を示す値。  
  
### <a name="return-value"></a>戻り値  
 要素がシフトされた valarray で指定した量のまま ` right`します。  
  
### <a name="remarks"></a>コメント  
 符号付き数値がある、アット マークは保持されます。  
  
### <a name="example"></a>例  
  
```  
// valarray_class_op_ls.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial operand valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL <<= vaR;  
   cout << "The element-by-element result of "  
        << "the left shift\n on the operand array is the valarray:\n ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the left shift  
 on the operand array is the valarray:  
 ( 1 -2 4 -8 16 -32 64 -128 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorstareqa-valarrayoperator"></a><a name="valarray__operator_star_eq"></a>  valarray::operator * =  
 オペランド valarray を指定した valarray の要素または要素の型の値を element-wise を乗算します。  
  
```  
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 オペランド valarray element-wise、乗算には、オペランド valarray の要素型の値または valarray します。  
  
### <a name="return-value"></a>戻り値  
 含まれる要素がオペランド valarray のごとの積 valarray と ` right.`  
  
### <a name="example"></a>例  
  
```  
// valarray_op_emult.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL *= vaR;  
   cout << "The element-by-element result of "  
        << "the multiplication is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the multiplication is the  
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoradda-valarrayoperator"></a><a name="valarray__operator_add"></a>  valarray::operator +  
 Valarray 内の各要素に、プラス記号を適用する単項演算子です。  
  
```  
valarray<Type> operator+() const;
```  
  
### <a name="return-value"></a>戻り値  
 さらに、オペランドの配列の方を要素の valarray。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_eplus.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<int> vaPLUS ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaPLUS = +vaL;  
   cout << "The element-by-element result of "  
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaPLUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoraddeqa-valarrayoperator"></a><a name="valarray__operator_add_eq"></a>  valarray::operator + = 演算子  
 オペランド valarray を指定した valarray の要素または要素の型の値を element-wise を追加します。  
  
```  
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray またはと同じですに追加する、element-wise、オペランド valarray オペランド valarray の要素型の値。  
  
### <a name="return-value"></a>戻り値  
 含まれる要素がオペランド valarray の element-wise 合計 valarray と ` right.`  
  
### <a name="example"></a>例  
  
```  
// valarray_op_eadd.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL += vaR;  
   cout << "The element-by-element result of "  
        << "the sum is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the sum is the  
 valarray: ( 2 0 4 2 6 4 8 6 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-a-valarrayoperator-"></a><a name="valarray__operator-"></a>  valarray::operator-  
 Valarray 内の各要素にマイナス記号を適用する単項演算子です。  
  
```  
valarray<Type> operator-() const;
```  
  
### <a name="return-value"></a>戻り値  
 マイナス オペランド配列の方を要素の valarray。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_eminus.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<int> vaMINUS ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaMINUS = -vaL;  
   cout << "The element-by-element result of "  
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaMINUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-eqa-valarrayoperator-"></a><a name="valarray__operator-_eq"></a>  valarray::operator-=  
 オペランド valarray から、指定した valarray の要素または要素の型の値を element-wise を減算します。  
  
```  
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray または減算する、element-wise、オペランド valarray からオペランド valarray の要素型の値。  
  
### <a name="return-value"></a>戻り値  
 含まれる要素がオペランド valarray の element-wise 差 valarray と ` right.`  
  
### <a name="example"></a>例  
  
```  
// valarray_op_esub.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  10;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL -= vaR;  
   cout << "The element-by-element result of "  
        << "the difference is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the difference is the  
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator__eq"></a>  valarray::operator/=  
 オペランド valarray を element-wise 指定 valarray の要素または要素の型の値で除算します。  
  
```  
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray またはと同じですを分割する、element-wise、オペランド valarray オペランド valarray の要素型の値。  
  
### <a name="return-value"></a>戻り値  
 含まれる要素がオペランド valarray element-wise の商 valarray がで割った値 ` right.`  
  
### <a name="example"></a>例  
  
```  
// valarray_op_ediv.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<double> vaL ( 6 ), vaR ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  100;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -100;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  2*i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL /= vaR;  
   cout << "The element-by-element result of "  
        << "the quotient is the\n valarray: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 100 -100 100 -100 100 -100 ).  
The initial Right valarray is: ( 0 2 4 6 8 10 ).  
The element-by-element result of the quotient is the  
 valarray: ( 1.#INF -50 25 -16.6667 12.5 -10 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator_eq"></a>  valarray::operator =  
 直接または slice_array、gslice_array、mask_array、または indirect_array によっていくつか他の valarray の一部として指定の値を持つ valarray の要素に割り当てます。  
  
```  
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 オペランド valarray にコピーされる valarray。  
  
 ` val`  
 オペランド valarray の要素に割り当てられる値です。  
  
 `_Slicearray`  
 オペランド valarray にコピーされる slice_array。  
  
 `_Gslicearray`  
 オペランド valarray にコピーされる gslice_array。  
  
 `_Maskarray`  
 オペランド valarray にコピーされる mask_array。  
  
 `_Indarray`  
 オペランド valarray にコピーされる indirect_array。  
  
### <a name="return-value"></a>戻り値  
 1 つ目のメンバー演算子によって制御されるシーケンスのコピーの被制御シーケンスを置換する ` right`です。  
  
 2 番目のメンバー演算子は、1 つは、ですと同じ、 [右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。  
  
 被制御シーケンスの各要素のコピーに置き換えて、3 番目のメンバー演算子 ` val`します。  
  
 残りのメンバー演算子でのみ生成される、引数が選択した被制御シーケンスの要素を交換する [演算子 & #91、#93;](#valarray__operator_at)します。  
  
 交換が制御されるシーケンス内のメンバーの値は、初期被制御シーケンス内のメンバーに依存する場合、結果は未定義です。  
  
### <a name="remarks"></a>コメント  
 被制御シーケンスの長さが変更された場合、結果は一般に定義されています。 この実装では、ただし、効果は単なる任意のポインターまたは被制御シーケンス内の要素への参照を無効にするためです。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_assign.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va [ i ] = i;  
   for ( i = 0 ; i < 10 ; i+=1 )  
      vaR [ i ] = 10 -  i;  
  
   cout << "The operand valarray va is:";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << " " << va [ i ];  
   cout << endl;  
  
   cout << "The operand valarray vaR is:";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << " " << vaR [ i ];  
   cout << endl;  
  
   // Assigning vaR to va with the first member functon  
   va = vaR;  
   cout << "The reassigned valarray va is:";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << " " << va [ i ];  
   cout << endl;  
  
   // Assigning elements of value 10 to va  
   // with the second member functon  
   va = 10;  
   cout << "The reassigned valarray va is:";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << " " << va [ i ];  
   cout << endl;  
}  
\* Output:   
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9  
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10  
*\  
```  
  
##  <a name="a-namevalarrayoperatorata-valarrayoperator"></a><a name="valarray__operator_at"></a>  valarray::operator  
 指定されたインデックスまたは指定されたサブセットにある、要素またはその値への参照を返します。  
  
```  
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;

 
valarray<Type> operator[](slice _Slice) const;

 
valarray<Type> operator[](const gslice& _Gslicearray) const;

 
valarray<Type> operator[](const valarray<bool>& _Boolarray) const;

 
valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Off`  
 値を代入する要素のインデックス。  
  
 `_Slicearray`  
 選択/新しい valarray に返される対象のサブセットを指定する valarray の slice_array。  
  
 `_Gslicearray`  
 選択/新しい valarray に返される対象のサブセットを指定する valarray の gslice_array。  
  
 *_Boolarray*  
 選択/新しい valarray に返される対象のサブセットを指定する valarray の bool_array です。  
  
 `_Indarray`  
 選択/新しい valarray に返される対象のサブセットを指定する valarray の indirect_array。  
  
### <a name="return-value"></a>戻り値  
 要素または指定したインデックスまたは指定したサブセットでは、その値への参照。  
  
### <a name="remarks"></a>コメント  
 メンバー演算子がオーバー ロードによって制御されるものの中から要素の順序を選択するためにいくつかの方法を提供するように *\****この**します。 5 つのメンバー演算子の最初のグループのさまざまなオーバー ロードと連携して動作 [演算子 =](#valarray__operator_eq) (およびその他の割り当ての演算子) (スライス) 被制御シーケンスの選択的な交換を許可するようにします。 選択した要素が存在する必要があります。  
  
 _SECURE_SCL 1 でコンパイル、valarray の境界の外側の要素にアクセスしようとすると、ランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して [slice::slice](../Topic/slice%20Class.md#slice__slice) と [gslice::gslice](../Topic/gslice%20Class.md#gslice__gslice) 宣言、および演算子を使用する方法の例についてです。  
  
##  <a name="a-namevalarrayoperatorxoreqa-valarrayoperator"></a><a name="valarray__operator_xor_eq"></a>  valarray::operator ^ =  
 Element-wise 排他的論理 or 演算子を取得 ( **XOR**) の指定した valarray または要素の型の値を持つ配列です。  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray または結合するのには、オペランド valarray の場合と同じ、element-wise が専用の論理によって、要素型の値 **XOR** オペランド valarray とします。  
  
### <a name="return-value"></a>戻り値  
 含まれる要素が element-wise、排他的論理 valarray **XOR** オペランド valarray のおよび ` right.`  
  
### <a name="remarks"></a>コメント  
 専用の論理またはとも呼ば **XOR**, 、次の意味を持ちます: 要素が与え *e*1 と *e*2、 *e*1 **XOR** *e*2 は **true** 要素を 1 つが true である場合 **false** 両方の要素が false の場合、または両方の要素に該当する場合。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_exor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL ^= vaR;  
   cout << "The element-by-element result of "  
        << "the bitwise XOR operator^= is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise XOR operator^= is the  
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatororeqa-valarrayoperator124"></a><a name="valarray__operator_or_eq"></a>  valarray::operator &#124; =  
 ビットごとの取得 `OR` の指定した valarray 内の対応要素または要素の型の値を配列の要素。  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 Valarray または結合するのには、オペランド valarray の場合と同じ、element-wise 演算によって、要素型の値 `OR` オペランド valarray とします。  
  
### <a name="return-value"></a>戻り値  
 要素はビットごとの element-wise valarray `OR` によってオペランド valarray の ` right.`  
  
### <a name="remarks"></a>コメント  
 ビットごとの演算は、ビットを操作する場合にのみ使用できます `char` と `int` データ型とバリアントされません **float**, 、**二重**, 、**longdouble**, 、`void`, 、`bool`, 、またはその他より複雑なデータ型。  
  
 ビットごと `OR` が論理として同じ真理値表 `OR` がビットごとのレベルでのデータ型に適用されます。 ビットを指定した *b*1 と *b*2、 *b*1 `OR` *b*2 は **true** ビットの両方が true である場合 **false** 両方のビットが false の場合。  
  
### <a name="example"></a>例  
  
```  
// valarray_class_op_bitor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial operand valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL |= vaR;  
   cout << "The element-by-element result of "  
        << "the logical OR\n operator|= is the valarray:\n ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  
 ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is:  
 ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the logical OR  
 operator|= is the valarray:  
 ( 1 0 1 3 3 4 7 6 7 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatordtora-valarrayoperator"></a><a name="valarray__operator_dtor"></a>  valarray::operator ~  
 単項演算子、ビット単位を取得する **いない** valarray 内の各要素の値。  
  
```  
valarray<Type> operator~() const;
```  
  
### <a name="return-value"></a>戻り値  
 ビットごとのブール値の valarray **いない** オペランド valarray の要素の値。  
  
### <a name="remarks"></a>コメント  
 ビットごとの演算は、ビットを操作する場合にのみ使用できます `char` と `int` データ型とバリアントされません **float**, 、**二重**, 、**longdouble**, 、`void`, 、`bool` またはその他より複雑なデータ型。  
  
 ビットごと **いない** 論理として同じ真理値表は **いない** がビットごとのレベルでのデータ型に適用されます。 ビットを指定 *b*, 、~ *b* が true 場合 *b* が false の場合は false *b* は true です。 論理 **いない**[演算子です。](#valarray__operator_not) カウントとしてゼロ以外のすべての値、要素レベルで適用される **true**, 、され、結果はブール値の valarray。 ビットごと **NOToperator ~**, 、0 または 1 のビットごとの演算の結果に応じて、以外の値の valarray でこれに対し、発生することができます。  
  
### <a name="example"></a>例  
  
```  
// valarray_op_bitnot.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<unsigned short int> vaL1 ( 10 );  
   valarray<unsigned short int> vaNOT1 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL1 [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL1 [ i ] =  5*i;  
  
   cout << "The initial valarray <unsigned short int> is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL1 [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT1 = ~vaL1;  
   cout << "The element-by-element result of "  
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT1 [ i ] << " ";  
   cout << ")." << endl << endl;  
  
   valarray<int> vaL2 ( 10 );  
   valarray<int> vaNOT2 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL2 [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL2 [ i ] =  -2 * i;  
  
   cout << "The initial valarray <int> is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL2 [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT2 = ~vaL2;  
   cout << "The element-by-element result of "  
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // The negative numbers are represented using  
   // the two's complement approach, so adding one  
   // to the flipped bits returns the negative elements  
   vaNOT2 = vaNOT2 + 1;  
   cout << "The element-by-element result of "  
        << "adding one\n is the negative of the "  
        << "original elements the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).  
  
The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).  
The element-by-element result of adding one  
 is the negative of the original elements the  
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).  
*\  
```  
  
##  <a name="a-namevalarrayresizea-valarrayresize"></a><a name="valarray__resize"></a>  valarray::resize  
 valarray 内の要素の数を指定された数に変更します。  
  
```  
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,   
    const Type val);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Newsize`  
 サイズ変更後の valarray 内の要素の数。  
  
 ` val`  
 サイズ変更後の valarray の要素に与えられる値。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、既定のコンストラクターを使用して要素を初期化します。  
  
 制御されるシーケンス内の要素へのすべてのポインターまたは参照は無効になります。  
  
### <a name="example"></a>例  
  valarray::resize メンバー関数の使用例を次に示します。  
  
```  
// valarray_resize.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
    size_t size1, sizeNew;  
  
    valarray<int> va1(10);  
    for (i = 0; i < 10; i+=1)  
        va1[i] = i;  
  
    cout << "The valarray contains ( ";  
        for (i = 0; i < 10; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
  
    size1 = va1.size();  
    cout << "The number of elements in the valarray is: "  
         << size1  << "." <<endl << endl;  
  
    va1.resize(15, 10);  
  
    cout << "The valarray contains ( ";  
        for (i = 0; i < 15; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
    sizeNew = va1.size();  
    cout << "The number of elements in the resized valarray is: "  
         << sizeNew  << "." <<endl << endl;  
}  
\* Output:   
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray is: 10.  
  
The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).  
The number of elements in the resized valarray is: 15.  
*\  
```  
  
##  <a name="a-namevalarrayshifta-valarrayshift"></a><a name="valarray__shift"></a>  valarray::shift  
 Valarray 内のすべての要素は、指定した桁数でに戻しています。  
  
```  
valarray<Type> shift(int count) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` count`  
 要素を前方にシフトする対象の場所の数。  
  
### <a name="return-value"></a>戻り値  
 移動された要素に指定したすべての新しい valarray ` count` オペランド valarray 内の位置を基準に左 valarray の先頭近くに位置します。  
  
### <a name="remarks"></a>コメント  
 値が正 ` count` 要素を左にシフト ` count` ゼロで埋めるには、配置します。  
  
 負の値の ` count` 、要素を右にシフト ` count` ゼロで埋めるには、配置します。  
  
### <a name="example"></a>例  
  
```  
// valarray_shift.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va1 ( 10 ), va2 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va1 [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va2 [ i ] = 10 -  i;  
  
   cout << "The operand valarray va1(10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va1 [ i ] << " ";  
   cout << ")." << endl;  
  
   // A positive parameter shifts elements left  
   va1 = va1.shift ( 4 );  
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va1 [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The operand valarray va2(10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // A negative parameter shifts elements right  
   va2 = va2.shift ( - 4 );  
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).  
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).  
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).  
*\  
```  
  
##  <a name="a-namevalarraysizea-valarraysize"></a><a name="valarray__size"></a>  valarray::size  
 valarray 内の要素の数を調べます。  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>戻り値  
 オペランド valarray 内の要素の数。  
  
### <a name="example"></a>例  
  valarray::size メンバー関数の使用例を次に示します。  
  
```  
// valarray_size.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
    size_t size1, size2;  
  
    valarray<int> va1(10), va2(12);  
    for (i = 0; i < 10; i += 1)  
        va1[i] =  i;  
    for (i = 0; i < 10; i += 1)  
        va2[i] =  i;  
  
    cout << "The operand valarray va1(10) is: ( ";  
        for (i = 0; i < 10; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
  
    size1 = va1.size();  
    cout << "The number of elements in the valarray va1 is: va1.size = "  
         << size1  << "." <<endl << endl;  
  
    cout << "The operand valarray va2(12) is: ( ";  
        for (i = 0; i < 10; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
  
    size2 = va2.size();  
    cout << "The number of elements in the valarray va2 is: va2.size = "  
         << size2  << "." << endl << endl;  
  
    // Initializing two more elements to va2  
    va2[10] = 10;  
    va2[11] = 11;  
    cout << "After initializing two more elements,\n "  
         << "the operand valarray va2(12) is now: ( ";  
        for (i = 0; i < 12; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
    cout << "The number of elements in the valarray va2 is still: "  
         << size2  << "." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va1 is: va1.size = 10.  
  
The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va2 is: va2.size = 12.  
  
After initializing two more elements,  
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).  
The number of elements in the valarray va2 is still: 12.  
*\  
```  
  
##  <a name="a-namevalarraysuma-valarraysum"></a><a name="valarray__sum"></a>  valarray::sum  
 0 以外の長さの valarray 内のすべての要素の合計を決定します。  
  
```  
Type sum() const;
```  
  
### <a name="return-value"></a>戻り値  
 オペランド valarray の要素の合計です。  
  
### <a name="remarks"></a>コメント  
 メンバー関数が、適用することで、合計に値を追加、長さが 1 より大きい場合は、 `operator+=` クラスの要素のペア間 **型**, 、演算子をその結果、必要があるを指定する型の要素に対して **型**します。  
  
### <a name="example"></a>例  
  
```  
// valarray_sum.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   int sumva = 0;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i+=1 )  
      va [ i ] =  i;  
  
   cout << "The operand valarray va (10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   sumva = va.sum ( );  
   cout << "The sum of elements in the valarray is: "  
        << sumva  << "." <<endl;  
}  
\* Output:   
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The sum of elements in the valarray is: 45.  
*\  
```  
  
##  <a name="a-namevalarrayswapa-valarrayswap"></a><a name="valarray__swap"></a>  valarray::swap  
 2 つの `valarray` の要素を交換します。  
  
```  
void swap(valarray& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|` right`|交換する要素を提供する `valarray`。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`*this` と ` right` の間で被制御シーケンスを交換します。 この処理は一定時間に実行されます。例外がスローされることはなく、参照や、ポインター、2 つの被制御シーケンス内の要素を指定する反復子が無効にされることもありません。  
  
##  <a name="a-namevalarrayvalarraya-valarrayvalarray"></a><a name="valarray__valarray"></a>  valarray::valarray  
 特定のサイズの valarray や特定の値の要素を持つ valarray を構築します。また、他の valarray のコピーやサブセットとして valarray を構築します。  
  
```  
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,   
    size_t Count);

valarray(
    const Type* Ptr,   
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```  
  
### <a name="parameters"></a>パラメーター  
 `Count`  
 valarray 内の要素の数。  
  
 `Val`  
 valarray 内の要素の初期化に使用する値。  
  
 `Ptr`  
 valarray 内の要素の初期化に使用する値へのポインター。  
  
 `Right`  
 新しい valarray を初期化するための既存の valarray。  
  
 `SliceArray`  
 構築する valarray の要素の初期化に使用される要素の値を持つ slice_array。  
  
 `GsliceArray`  
 構築する valarray の要素の初期化に使用される要素の値を持つ gslice_array。  
  
 `MaskArray`  
 構築する valarray の要素の初期化に使用される要素の値を持つ mask_array。  
  
 `IndArray`  
 構築する valarray の要素の初期化に使用される要素の値を持つ indirect_array。  
  
 `IList`  
 コピーする要素を含む initializer_list。  
  
### <a name="remarks"></a>コメント  
 最初の (既定の) コンストラクターは、オブジェクトを空の配列に初期化します。 次の 3 つの各コンストラクターは、オブジェクトを `Count` 要素の配列に初期化します。  
  
-   明示的な `valarray(size_t Count)` の場合、各要素は既定のコンストラクターで初期化されます。  
  
-   `valarray(const Type& Val, Count)` の場合、各要素は `Val` で初期化されます。  
  
-    `valarray(const Type* Ptr, Count)`, 、位置にある要素 `I` で初期化される `Ptr`[ `I`] です。  
  
 残りの各コンス トラクターが valarray のオブジェクトを初期化 \< 種類> 引数で指定されたサブセットによって決定されるオブジェクト。  
  
 最後のコンス トラクターは次にすると同じ最後がの [右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。  
  
### <a name="example"></a>例  
  
```  
// valarray_ctor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
  
    // The second member function  
    valarray<int> va(10);  
    for (auto i : va){  
        va[i] = 2 * (i + 1);  
    }  
  
    cout << "The operand valarray va is:\n(";  
    for (auto i : va) {  
        cout << " " << va[i];  
    }  
    cout << " )" << endl;  
  
    slice Slice(2, 4, 3);  
  
    // The fifth member function  
    valarray<int> vaSlice = va[Slice];  
  
    cout << "The new valarray initialized from the slice is vaSlice ="  
        << "\nva[slice( 2, 4, 3)] = (";  
    for (int i = 0; i < 3; i++) {  
        cout << " " << vaSlice[i];  
    }  
    cout << " )" << endl;  
  
    valarray<int> va2{{ 1, 2, 3, 4 }};  
    for (auto& v : va2){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4  
```  
  
##  <a name="a-namevalarrayvaluetypea-valarrayvaluetype"></a><a name="valarray__value_type"></a>  valarray::value_type  
 Valarray 内の要素の型を表す型。  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **型**します。  
  
### <a name="example"></a>例  
  
```  
// valarray_value_type.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // value_type declaration and initialization:  
   valarray<int>::value_type Right = 10;  
  
   cout << "The decalared value_type Right is: "   
           << Right << endl;  
   va *= Right;  
   cout << "The resulting valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The decalared value_type Right is: 10  
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).  
*\  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

