---
title: "構造体 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- struct
- struct_cpp
dev_langs:
- C++
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
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
ms.openlocfilehash: 4918adb779a620afd4a0c1e4ef64ef9892de1ba8
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="struct-c"></a>struct (C++ )
`struct` キーワードは構造体型や構造体型の変数の定義に使用します。  
  
## <a name="syntax"></a>構文  
  
```  
[template-spec] struct[ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `template-spec`  
 テンプレートの指定 (省略可能)。 詳細についてを参照してください[テンプレートの仕様](templates-cpp.md)です。  
  
 `struct`  
 `struct` キーワード。  
  
 `ms-decl-spec`  
 ストレージ クラスの指定 (省略可能)。 詳細についてを参照してください、 [_ _declspec](../cpp/declspec.md)キーワード。  
  
 `tag`  
 構造体に渡す型名。 タグは構造体のスコープ内で予約語になります。 タグは省略できます。 省略した場合、匿名構造体が定義されます。 詳細については、次を参照してください。[匿名クラス型](../cpp/anonymous-class-types.md)です。  
  
 `base-list`  
 この構造体がメンバーを継承するクラスまたは構造体のリスト (省略可能)。 参照してください[基底クラス](../cpp/base-classes.md)詳細についてはします。 各基底クラスまたは構造体名の前に、アクセス指定子 ([パブリック](../cpp/public-cpp.md)、[プライベート](../cpp/private-cpp.md)、[保護](../cpp/protected-cpp.md)) および[仮想](../cpp/virtual-cpp.md)キーワードです。 メンバー アクセス テーブルを参照してください[クラス メンバーへのアクセスの制御](member-access-control-cpp.md)詳細についてはします。  
  
 `member-list`  
 構造体のメンバーのリスト。 参照してください[クラス メンバーの概要](../cpp/class-member-overview.md)詳細についてはします。 ここで唯一の違いは、`struct` が `class` の代わりに使用されることです。  
  
 `declarators`  
 クラスの名前を指定する宣言子リスト。 宣言子リストは構造体型の 1 つ以上のインスタンスを宣言します。 宣言子には、クラスのすべてのデータ メンバーが `public` である場合、初期化子リストが含まれる場合があります。 初期子のリストは構造体では一般的です。構造体のデータ メンバーは既定で `public` であるためです。  参照してください[概要の宣言子](../cpp/overview-of-declarators.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 構造体型はユーザー定義の複合データ型です。 この型は異なる型のフィールドやメンバーで構成されます。  
  
 C++ では、構造体はクラスと同じですが、そのメンバーが既定で `public` である点は異なります。  
  
 詳細については、マネージ クラスと構造体は、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
## <a name="using-a-structure"></a>構造体の使用  
 C では、構造体を宣言するには、`struct` キーワードの明示的な使用が必要です。 C++ では、型の定義後に `struct` キーワードを使用する必要はありません。  
  
 右中かっことセミコロンの間に 1 つ以上のコンマ区切りの変数名を挿入することで構造体型を定義している場合は、変数を宣言してもかまいません。  
  
 構造体の変数は初期化できます。 各変数の初期化は中かっこで囲む必要があります。  
  
 関連情報については、次を参照してください。[クラス](../cpp/class-cpp.md)、[共用体](../cpp/unions.md)、および[enum](../cpp/enumerations-cpp.md)です。  
  
## <a name="example"></a>例  
  
```  
#include <iostream>  
using namespace std;  
  
struct PERSON {   // Declare PERSON struct type  
    int age;   // Declare member types  
    long ss;  
    float weight;  
    char name[25];  
} family_member;   // Define object of type PERSON  
  
struct CELL {   // Declare CELL bit field  
    unsigned short character  : 8;  // 00000000 ????????  
    unsigned short foreground : 3;  // 00000??? 00000000  
    unsigned short intensity  : 1;  // 0000?000 00000000  
    unsigned short background : 3;  // 0???0000 00000000  
    unsigned short blink      : 1;  // ?0000000 00000000  
} screen[25][80];       // Array of bit fields   
  
int main() {  
    struct PERSON sister;   // C style structure declaration  
    PERSON brother;   // C++ style structure declaration  
    sister.age = 13;   // assign values to members  
    brother.age = 7;  
    cout << "sister.age = " << sister.age << '\n';  
    cout << "brother.age = " << brother.age << '\n';  
  
    CELL my_cell;  
    my_cell.character = 1;  
    cout << "my_cell.character = " << my_cell.character;  
}  
// Output:  
// sister.age = 13  
// brother.age = 7  
// my_cell.character = 1  
```  
  

