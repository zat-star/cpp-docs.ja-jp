---
title: "reinterpret_cast 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: reinterpret_cast_cpp
dev_langs: C++
helpviewer_keywords: reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b3ad3912c9046e877da0913a34cb1b3253baa454
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast 演算子
ポインターが他のポインター型に変換されることを許可します。 また、整数型から任意のポインター型への変換およびその逆の変換を許可します。  
  
## <a name="syntax"></a>構文  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>コメント  
 `reinterpret_cast` 演算子の誤用により簡単に安全でない状態になります。 必要な変換が本質的に低レベルでない限り、他のキャスト演算子の 1 つを使用する必要があります。  
  
 `reinterpret_cast` 演算子は、本質的に安全でない `char*` から `int*` へ、`One_class*` から `Unrelated_class*` へなどの変換に使用できます。  
  
 `reinterpret_cast` の結果は、元の型にキャスト バックする場合以外は安全に使用することはできません。 その他の使用方法は、最高でも非ポータブルです。  
  
 `reinterpret_cast`キャストできません演算子、 **const**、 `volatile`、または**_ _unaligned**属性。 参照してください[const_cast 演算子](../cpp/const-cast-operator.md)これらの属性を削除する方法についてです。  
  
 `reinterpret_cast` 演算子は、null ポインター値を変換先の型の null ポインター値に変換します。  
  
 `reinterpret_cast` の実用的な使用方法の 1 つは、2 つの異なる値が同じインデックスで終わることがほとんどないようにインデックスに値を割り当てるハッシュ関数での使用です。  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 `reinterpret_cast` は、ポインターが整数型として処理されることを許可します。 結果は、一意のインデックス (高レベルの発生確率で一意) を生成するためにビット シフトされ、XOR されます。 インデックスは、関数の戻り値の型への標準 C 形式のキャストにより切り捨てられます。  
  
## <a name="see-also"></a>関連項目  
 [キャスト演算子](../cpp/casting-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)