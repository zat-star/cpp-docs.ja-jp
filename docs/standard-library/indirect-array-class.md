---
title: "indirect_array クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::indirect_array
- indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
caps.latest.revision: 20
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 7a5b105b9c812d81dfbbe5905bb593bba1b98ef8
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="indirectarray-class"></a>indirect_array クラス
親 valarray のインデックスのサブセットを指定することにより定義されるサブセット配列間の演算を実行して valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
  
  
## <a name="remarks"></a>コメント  
 このクラスは、クラス **valarray<size_t>** のオブジェクト **xa** と共に、クラス [valarray](../standard-library/valarray-class.md)**\<Type>** のオブジェクト **va** への参照を格納するオブジェクトを表します。これらは **valarray\<Type>** オブジェクトから選択する要素のシーケンスを説明します。  
  
 **indirect_array\<Type>** オブジェクトの構築は、**va[xa]** という形式の式を記述するだけです。 クラス indirect_array のメンバー関数は **valarray\<Type>** に対して定義された対応する関数のシグネチャのように動作しますが、選択された要素のシーケンスだけが影響を受けるという点が異なります。  
  
 シーケンスは **xa.**[size](../standard-library/valarray-class.md#size) 要素で構成されます。ここで、要素 `I` は **va** 内のインデックス **xa**[ `I`] になります。  
  
## <a name="example"></a>例:  
  
```  
// indirect_array.cpp  
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
  
   // Select 2nd, 4th & 6th elements  
   // and assign a value of 10 to them  
   valarray<size_t> indx ( 3 );  
   indx [0] = 2;  
   indx [1] = 4;  
   indx [2] = 6;  
   va[indx] = 10;  
  
   cout << "The modified operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>出力  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<valarray>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


