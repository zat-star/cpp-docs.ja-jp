---
title: "sizeof 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
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
ms.openlocfilehash: 67b699a93880a89e634ac024699ac79a9ea8d3ba
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="sizeof-operator"></a>sizeof 演算子
型 `char` のサイズに対するオペランドのサイズが出力されます。  
  
> [!NOTE]
>  については、`sizeof ...`演算子を参照してください[楕円および可変値引数テンプレート](../cpp/ellipses-and-variadic-templates.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>コメント  
 `sizeof` 演算子の結果は、インクルード ファイル STDDEF.H で定義されている整数型、`size_t` です。 この演算子を使うと、コンピューターに依存するデータ サイズをプログラムで指定せずに済みます。  
  
 `sizeof` のオペランドには、次のいずれかを指定できます。  
  
-   型の名前。 `sizeof` を型名を指定して使用するには、名前をかっこで囲む必要があります。  
  
-   任意の式を指定します。 式で使用する場合、`sizeof` はかっこ付きでもかっこなしでも指定できます。 式は評価されません。  
  
 `sizeof` 演算子を `char` 型のオブジェクトに適用すると、1 になります。 `sizeof` 演算子を配列に適用すると、配列識別子によって表されるポインターのサイズではなく、その配列の合計バイト数になります。 配列識別子によって表されるポインターのサイズを取得するには、`sizeof` を使用する関数にそれをパラメーターとして渡します。 例:  
  
## <a name="example"></a>例  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 `sizeof` 演算子を `class`、`struct`、または `union` 型に適用すると、結果はその型のオブジェクトのバイト数に、ワード境界にメンバーをアラインするために追加されたパディングを加えたものになります。 結果は、個々のメンバーのストレージ要件を追加することで計算されたサイズには必ずしも対応しません。 [/Zp](../build/reference/zp-struct-member-alignment.md)コンパイラ オプションおよび[パック](../preprocessor/pack.md)プラグマは、メンバーのアラインメント境界に影響します。  
  
 `sizeof` 演算子は、空のクラスの場合でも 0 を生成しません。  
  
 `sizeof` 演算子は、次のオペランドには使用できません。  
  
-   関数  (ただし、関数へのポインターに `sizeof` を適用することはできます)。  
  
-   ビット フィールド。  
  
-   定義されていないクラス。  
  
-   型 `void`。  
  
-   動的に割り当てられる配列。  
  
-   外部配列。  
  
-   不完全な型。  
  
-   かっこで囲まれた不完全な型の名前。  
  
 `sizeof` 演算子を参照に適用すると、結果は `sizeof` をオブジェクト自体に適用した場合と同じです。  
  
 可変長配列が構造の最後の要素である場合、`sizeof` 演算子は配列のない構造体のサイズを返します。  
  
 `sizeof` 演算子は、通常、次の形式の式を使用して配列の要素の数を計算するために使用されます。  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)
