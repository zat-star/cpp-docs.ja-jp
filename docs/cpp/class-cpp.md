---
title: "クラス (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: class_cpp
dev_langs: CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed344d5c15e709b09b760dee74a986dde6383d22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="class-c"></a>class (C++)
`class` キーワードは、クラス型を宣言したり、クラス型のオブジェクトを定義したりします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `template-spec`  
 テンプレートの指定 (省略可能)。 詳細についてを参照してください[テンプレート](templates-cpp.md)です。  
  
 `class`  
 `class` キーワード。  
  
 `ms-decl-spec`  
 ストレージ クラスの指定 (省略可能)。 詳細についてを参照してください、 [_ _declspec](../cpp/declspec.md)キーワード。  
  
 `tag`  
 クラスに渡す型名。 タグは、クラスのスコープ内で予約語になります。 タグは省略できます。 省略した場合、匿名クラスが定義されます。 詳細については、次を参照してください。[匿名クラス型](../cpp/anonymous-class-types.md)です。  
  
 `base-list`  
 このクラスがメンバーを継承するクラスまたは構造体のリスト (省略可能)。 参照してください[基底クラス](../cpp/base-classes.md)詳細についてはします。 各基底クラスまたは構造体名の前に、アクセス指定子 ([パブリック](../cpp/public-cpp.md)、[プライベート](../cpp/private-cpp.md)、[保護](../cpp/protected-cpp.md)) および[仮想](../cpp/virtual-cpp.md)キーワードです。 メンバー アクセス テーブルを参照してください[クラス メンバーへのアクセスの制御](member-access-control-cpp.md)詳細についてはします。  
  
 `member-list`  
 クラス メンバーのリスト。 参照してください[クラス メンバーの概要](../cpp/class-member-overview.md)詳細についてはします。  
  
 `declarators`  
 クラス型の 1 つ以上のインスタンスの名前を指定する宣言子リスト。 宣言子には、クラスのすべてのデータ メンバーが `public` である場合、初期化子リストが含まれる場合があります。 これは、クラスよりも、データ メンバーが既定で `public` である構造体で、より一般的です。 参照してください[概要の宣言子](../cpp/overview-of-declarators.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 一般的なクラスの詳細については、次のトピックのいずれかを参照してください。  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [_ _multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [_ _single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [_ _virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 詳細については、マネージ クラスと構造体は、次を参照してください[クラスと構造体。](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>例  
  
```  
// class.cpp  
// compile with: /EHsc  
// Example of the class keyword  
// Exhibits polymorphism/virtual functions.  
  
#include <iostream>  
#include <string>  
#define TRUE = 1  
using namespace std;  
  
class dog  
{  
public:  
   dog()  
   {  
      _legs = 4;  
      _bark = true;  
   }  
  
   void setDogSize(string dogSize)  
   {  
      _dogSize = dogSize;  
   }  
   virtual void setEars(string type)      // virtual function  
   {  
      _earType = type;  
   }  
  
private:  
   string _dogSize, _earType;  
   int _legs;  
   bool _bark;  
  
};  
  
class breed : public dog  
{  
public:  
   breed( string color, string size)  
   {  
      _color = color;  
      setDogSize(size);  
   }  
  
   string getColor()  
   {  
      return _color;  
   }  
  
   // virtual function redefined  
   void setEars(string length, string type)  
   {  
      _earLength = length;  
      _earType = type;  
   }  
  
protected:  
   string _color, _earLength, _earType;  
};  
  
int main()  
{  
   dog mongrel;  
   breed labrador("yellow", "large");  
   mongrel.setEars("pointy");  
   labrador.setEars("long", "floppy");  
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;  
}  
```  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)