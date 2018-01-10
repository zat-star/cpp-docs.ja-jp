---
title: "mask_array クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: valarray/std::mask_array
dev_langs: C++
helpviewer_keywords: mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7aafc5a418fbbe4d12a759237657e1909541a7eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="maskarray-class"></a>mask_array クラス
サブセット配列間の演算を提供することにより、ブール式で指定された親 valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
  
  
## <a name="remarks"></a>コメント  
 このクラスは、クラス [valarray](../standard-library/valarray-class.md)**\<Type>** のオブジェクト **va** と共に、クラス [valarray\<bool>](../standard-library/valarray-bool-class.md) のオブジェクト **ba** への参照を格納するオブジェクトを表します。これらは **valarray\<Type>** オブジェクトから選択する要素のシーケンスを説明します。  
  
 **mask_array\<Type>** オブジェクトの構築は、[va&#91;ba&#93;](../standard-library/valarray-class.md#op_at) という形式の式を記述するだけです。 クラス mask_array のメンバー関数は **valarray\<Type>** に対して定義された対応する関数のシグネチャのように動作しますが、選択された要素のシーケンスだけが影響を受けるという点が異なります。  
  
 シーケンスは最大で **ba.size** 個の要素で構成されます。 要素 *J* は **ba**[ *J*] が true である場合にのみ含まれます。 このため、 **ba**内の true の要素の数だけシーケンス内に要素があります。 `I` が **ba**内の最下位の true 要素である場合、 **va**[ `I`] は選択されているシーケンス内で要素 0 です。  
  
## <a name="example"></a>例:  
  
```  
// mask_array.cpp  
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
  
   // Use masked subsets to assign a value of 10  
   // to all elements grrater than 3 in value  
   va [va > 3 ] = 10;  
   cout << "The modified operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>出力  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<valarray>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

