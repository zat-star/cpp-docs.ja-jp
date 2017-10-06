---
title: "const_cast 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8f72367cb4970b2ce0121efc43b79691155808df
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="constcast-operator"></a>const_cast 演算子
削除、 **const**、 `volatile`、および**_ _unaligned**クラスからの属性です。  
  
## <a name="syntax"></a>構文  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>コメント  
 どのオブジェクト型へのポインターまたはデータ メンバーへのポインターを除いて同一である型に明示的に変換できる、 **const**、 `volatile`、および**_ _unaligned**修飾子です。 ポインターと参照の場合、結果は元のオブジェクトを参照します。 データ メンバーへのポインターの場合、結果は元の (キャストされていない) ポインターが指していたデータ メンバーと同じメンバーを参照します。 参照されるオブジェクトの型によっては、結果のポインター、参照、またはデータ メンバーへのポインターを通じた書き込み操作で未定義の動作が発生する可能性があります。  
  
 `const_cast` 演算子を使用して定数変数の一定した状態を直接オーバーライドすることはできません。  
  
 `const_cast` 演算子は、null ポインター値を変換先の型の null ポインター値に変換します。  
  
## <a name="example"></a>例  
  
```  
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 `const_cast` を含む行で、`this` ポインターのデータ型は `const CCTest *` です。 `const_cast` 演算子は、`this` ポインターのデータ型を `CCTest *` に 変更して、`number` メンバーを修正できるようにしています。 キャストは、そのキャストが発生したステートメントの残り時間の間だけ持続します。  
  
## <a name="see-also"></a>関連項目  
 [キャスト演算子](../cpp/casting-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)
