---
title: "STL/CLR コンテナー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コンテナー, STL/CLR"
  - "STL/CLR, コンテナー"
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# STL/CLR コンテナー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\/CLR ライブラリと標準 C\+\+ ライブラリであるが、.NET Framework のマネージ環境内で実行する同じコンテナーがあります。  既に標準テンプレート ライブラリ \(STL\) を使い慣れている場合、STL\/CLR は既に開発したスキルを引き続き使用するのに最適です。共通言語ランタイム \(CLR\) を使用するようにコードをアップグレードします。  
  
 このドキュメントはコンテナー要素の要件など、STL\/CLR のコンテナーの概要を、コンテナーに挿入できる所有権はコンテナー要素と表示要素の種類を示します。  必要に応じて、ネイティブ標準テンプレート ライブラリと STL\/CLR の違いを説明します。  
  
## コンテナー要素の要件  
 STL コンテナーに挿入されるすべての要素が特定のガイドラインに従う必要があります。  詳細については、「[STL\/CLR コンテナー要素の要件](../Topic/Requirements%20for%20STL-CLR%20Container%20Elements.md)」を参照してください。  
  
## 有効なコンテナー要素  
 STL\/CLR コンテナーは要素の 2 種類の 1 を保持できます:  
  
-   参照型のハンドル。  
  
-   参照型  
  
-   ボックス化解除された値型。  
  
 STL\/CLR のコンテナーにボックス化された値型を挿入できません。  
  
### 参照型のハンドル  
 STL\/CLR のコンテナーに参照型にハンドルを挿入できます。  CLR を対象とする C\+\+ のハンドルは、ネイティブ C\+\+ ポインターに似ています。  詳細については、「[オブジェクト演算子 \(^\) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)」を参照してください。  
  
#### 例  
 次の例に [cliext::set](../dotnet/set-stl-clr.md)に Employee オブジェクトへのハンドルを挿入する方法を示しています。  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee^ empl1419 = gcnew Employee();  
    empl1419->Name = L"Darin Lockert";  
    empl1419->EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee^>^ emplSet = gcnew set<Employee^>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### 参照型  
 \(参照型へのハンドル\) ではなく STL\/CLR のコンテナーに参照型を挿入することもできます。  次の主な違いは、参照型のコンテナーが削除された場合、デストラクターはすべてのコンテナー要素の内部に対して呼び出されます。  参照型のハンドルのコンテナーで、これらの要素のデストラクターは呼び出されません。  
  
#### 例  
 次の例に `cliext::set`に Employee オブジェクトを挿入する方法を示しています。  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### ボックス化解除された値型  
 また、STL\/CLR のコンテナーにボックス化解除された値型を挿入できます。  ボックス化解除された値型を参照型に *囲まれなかった* 値型です。  
  
 要素が値型では、値型の 1、`int`など\) にすることも、`value class`などのユーザー定義の値型でもかまいません。  詳細については、「[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
#### 例  
 次の例は、Employee クラスに値型を表示することによって、最初の例を修正します。  この型の値は、最初の例と同様に、`cliext::set` に挿入されます。  
  
```  
// cliext_container_valid_valuetype.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
value class Employee  
{  
public:  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl.EmployeeNumber, empl.Name);  
    }  
  
    return 0;  
}  
```  
  
 コンテナーに値型にハンドルを挿入しようとすると [コンパイラ エラー C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) が生成されます。  
  
### パフォーマンスとメモリ影響  
 かどうかを決定するときにコンテナー要素として参照型または値型へのハンドルを使用するいくつかの要因を考慮する必要があります。  値型を使用する場合、その要素のコピーがコンテナーに要素に挿入されるたびに作成されることに注意してください。  小さなオブジェクトの場合、これは問題にはなりません。挿入されたオブジェクトが大きい場合、パフォーマンスが低下する可能性があります。  各コンテナーが要素の独自のコピーを持つため、値型を使用すると、複数のコンテナーに 1 個の要素を同時に格納することは不可能です。  
  
 参照型にハンドルを使用する場合、パフォーマンスはコンテナーに挿入されると要素のコピーを作成する必要がないため、増える可能性があります。  また、値型とは異なり、同じ要素は、コンテナーに含めることができます。  ただし、ハンドルを使用する場合、ハンドルが有効であること、および確認する注意を払う必要があります。プログラムの他の場所で削除されなかったことを参照するオブジェクトにする必要があります。  
  
## コンテナーを持つ所有権問題  
 値セマンティクスの STL\/CLR 作業のコンテナー。  コンテナーに要素を挿入するたびに、その要素のコピーが挿入されます。  参照と同様のセマンティクスを取得する場合は、オブジェクト自体ではなくオブジェクトへのハンドルを挿入できます。  
  
 Clear を呼び出すか、またはハンドル オブジェクトのコンテナーのメソッドを消去するときに、ハンドルが参照するオブジェクトがメモリから解放されません。  オブジェクトを明示的に削除するか、これらのオブジェクトがマネージ ヒープ内に存在するため、オブジェクトは使用しなくなったと判断した場合、ガベージ コレクターがメモリを解放するようにします。  
  
## 参照  
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)