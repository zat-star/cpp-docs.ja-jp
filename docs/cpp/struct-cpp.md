---
title: "struct (C++ ) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "struct"
  - "struct_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "静的コンストラクター"
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# struct (C++ )
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`struct` キーワードは構造体型や構造体型の変数の定義に使用します。  
  
## 構文  
  
```  
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### パラメーター  
 `template-spec`  
 テンプレートの指定 \(省略可能\)。  詳細については、「[テンプレートの仕様](../Topic/Template%20Specifications.md)」を参照してください。  
  
 `struct`  
 `struct` キーワード。  
  
 `ms-decl-spec`  
 ストレージ クラスの指定 \(省略可能\)。  詳細については、「[\_\_declspec](../cpp/declspec.md) キーワード」を参照してください。  
  
 `tag`  
 構造体に渡す型名。  タグは構造体のスコープ内で予約語になります。  タグは省略できます。  省略した場合、匿名構造体が定義されます。  詳細については、「[匿名クラス型](../cpp/anonymous-class-types.md)」を参照してください。  
  
 `base-list`  
 この構造体がメンバーを継承するクラスまたは構造体のリスト \(省略可能\)。  詳細については、「[基本クラス](../cpp/base-classes.md)」を参照してください。  各基底クラスまたは構造体の名前の前には、アクセス指定子 \([public](../cpp/public-cpp.md)、[private](../Topic/private%20\(C++\).md)、[protected](../Topic/protected%20\(C++\).md)\) および [virtual](../cpp/virtual-cpp.md) キーワードを付けることができます。  詳細については、「[クラス メンバーへのアクセスの制御](../misc/controlling-access-to-class-members.md)」のメンバー アクセス テーブルを参照してください。  
  
 `member-list`  
 構造体のメンバーのリスト。  詳細については、「[クラス メンバーの概要](../Topic/Class%20Member%20Overview.md)」を参照してください。  ここで唯一の違いは、`struct` が `class` の代わりに使用されることです。  
  
 `declarators`  
 クラスの名前を指定する宣言子リスト。  宣言子リストは構造体型の 1 つ以上のインスタンスを宣言します。  宣言子には、クラスのすべてのデータ メンバーが `public` である場合、初期化子リストを含めてもかまいません。  初期子のリストは構造体では一般的です。構造体のデータ メンバーは既定で `public` であるためです。詳細については、「[宣言の概要](../cpp/overview-of-declarators.md)」を参照してください。  
  
## 解説  
 構造体型はユーザー定義の複合データ型です。  この型は異なる型のフィールドやメンバーで構成されます。  
  
 C\+\+ では、構造体はクラスと同じですが、そのメンバーが既定で `public` である点は異なります。  
  
 マネージ クラスと構造体の詳細については、「[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
## 構造体の使用  
 C では、構造体を宣言するには、`struct` キーワードの明示的な使用が必要です。  C\+\+ では、型の定義後に `struct` キーワードを使用する必要はありません。  
  
 右中かっことセミコロンの間に 1 つ以上のコンマ区切りの変数名を挿入することで構造体型を定義している場合は、変数を宣言してもかまいません。  
  
 構造体の変数は初期化できます。  各変数の初期化は中かっこで囲む必要があります。  
  
 関連情報については、「[クラス](../cpp/class-cpp.md)」、「[共用体](../cpp/unions.md)」、「[列挙型](../cpp/enumerations-cpp.md)」を参照してください。  
  
## 使用例  
  
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
  
## 参照  
 [\(NOTINBUILD\) Defining Class Types](http://msdn.microsoft.com/ja-jp/e8c65425-0f3a-4dca-afc2-418c3b1e57da)