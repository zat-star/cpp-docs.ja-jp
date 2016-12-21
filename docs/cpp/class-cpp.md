---
title: "class (C++) | Microsoft Docs"
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
  - "class_cpp"
  - "class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class キーワード [C++]"
  - "クラスの型, class ステートメント"
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# class (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`class` キーワードは、クラス型を宣言したり、クラス型のオブジェクトを定義したりします。  
  
## 構文  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### パラメーター  
 `template-spec`  
 テンプレートの指定 \(省略可能\)。  詳細については、「[テンプレートの仕様](../Topic/Template%20Specifications.md)」を参照してください。  
  
 `class`  
 `class` キーワード。  
  
 `ms-decl-spec`  
 ストレージ クラスの指定 \(省略可能\)。  詳細については、[\_\_declspec](../cpp/declspec.md) キーワードを参照してください。  
  
 `tag`  
 クラスに渡す型名。  タグは、クラスのスコープ内で予約語になります。  タグは省略できます。  省略した場合、匿名クラスが定義されます。  詳細については、「[匿名クラス型](../cpp/anonymous-class-types.md)」を参照してください。  
  
 `base-list`  
 このクラスがメンバーを継承するクラスまたは構造体のリスト \(省略可能\)。  詳細については、「[基本クラス](../cpp/base-classes.md)」を参照してください。  各基底クラスまたは構造体の名前の前には、アクセス指定子 \([public](../cpp/public-cpp.md)、[private](../Topic/private%20\(C++\).md)、[protected](../Topic/protected%20\(C++\).md)\) および [virtual](../cpp/virtual-cpp.md) キーワードを付けることができます。  詳細については、「[クラス メンバーへのアクセスの制御](../misc/controlling-access-to-class-members.md)」のメンバー アクセスの表を参照してください。  
  
 `member-list`  
 クラス メンバーのリスト。  詳細については、「[クラス メンバーの概要](../Topic/Class%20Member%20Overview.md)」を参照してください。  
  
 `declarators`  
 クラス型の 1 つ以上のインスタンスの名前を指定する宣言子リスト。  宣言子には、クラスのすべてのデータ メンバーが `public` である場合、初期化子リストが含まれる場合があります。  これは、クラスよりも、データ メンバーが既定で `public` である構造体で、より一般的です。  詳細については、「[宣言の概要](../cpp/overview-of-declarators.md)」を参照してください。  
  
## 解説  
 一般的なクラスの詳細については、次のトピックのいずれかを参照してください。  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [\_\_multiple\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_single\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_virtual\_inheritance](../cpp/inheritance-keywords.md)  
  
 マネージ クラスと構造体の詳細については、「[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
  
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
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [クラスと構造体](../Topic/Classes%20and%20Structs%20\(C++\).md)