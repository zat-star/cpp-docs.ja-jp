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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79c4aa00038f2d4d7e5cc3d1c86d2e28c6d44229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [キャスト演算子](../cpp/casting-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)