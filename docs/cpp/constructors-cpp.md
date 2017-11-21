---
title: "コンス トラクター (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 77007b3d3805bb2fa159680c88d8e41825336da2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="constructors-c"></a>コンストラクター (C++)
コンストラクターは、そのクラスのインスタンスを初期化する一種のメンバー関数です。 コンストラクターにはクラスと同じ名前があり、戻り値はありません。 コンストラクターは任意の数のパラメーターを持つことができ、クラスは任意の数のオーバーロードされたコンストラクターを持つことができます。 コンストラクターには、"public"、"protected"、"private" の中から任意のアクセシビリティを設定できます。 コンストラクターを定義していない場合、パラメーターを受け取らない既定のコンストラクターがコンパイラによって生成されます。既定のコンストラクターを削除済みとして宣言することで、この動作をオーバーライドできます。  
  
## <a name="in-this-topic"></a>このトピックの内容  
  
-   [コンストラクションの順序](#order_of_construction)  
  
-   [メンバー リスト](#member_lists)  
  
-   [明示的なコンス トラクター](#explicit_constructors)  
  
-   [既定のコンス トラクター](#default_constructors)  
  
-   [コピーし、移動コンス トラクター](#copy_and_move_constructors)  
  
-   [明示的に既定化および削除のコンス トラクター](#explicitly_defaulted_and_deleted_constructors)  
  
-   [派生クラスのコンス トラクター](#constructors_in_derived_classes)  
  
-   [コンス トラクターの仮想関数](#virtual_functions_in_constructors)  
  
-   [コンス トラクターと複合クラス](#constructors_in_composite_classes)  
  
-   [デリゲート コンス トラクター](#delegating_constructors)  
  
-   [コンス トラクター (c++ 11) の継承](#inheriting_constructors)  
  
-   [コンストラクターの宣言に関する規則](#rules_for_declaring_constructors)  
  
-   [コンス トラクターの明示的な呼び出し](#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a>コンストラクションの順序  
 コンストラクターによる処理は次の順序で実行されます。  
  
1.  基底クラスとメンバーのコンストラクターを宣言の順序で呼び出します。  
  
2.  クラスが仮想基底クラスから派生されている場合は、オブジェクトの仮想基底ポインターを初期化します。  
  
3.  クラスが仮想関数を含むか継承する場合は、オブジェクトの仮想関数ポインターを初期化します。 仮想関数ポインターは、クラスの仮想関数テーブルをポイントし、コードへの仮想関数呼び出しの正しいバインドを可能にします。  
  
4.  その関数本体のコードをすべて実行します。  
  
 次の例に、基底クラスとメンバーのコンストラクターが派生クラスのコンストラクターで呼び出される順序を示します。 まず、基底コンストラクターが呼び出され、基底クラスのメンバーがクラス宣言内の出現順に初期化されて、その後に派生コンストラクターが呼び出されます。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 出力を次に示します。  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 コンストラクターが例外をスローした場合、破棄の順序はコンストラクションの順序と逆になります。  
  
1.  コンストラクター関数本体のコードがアンワインドされます。  
  
2.  基底クラスとメンバーのオブジェクトが宣言とは逆の順序で破棄されます。  
  
3.  コンストラクターがデリゲート コンストラクターでない場合は、完全に構築されたすべての基底クラスのオブジェクトとメンバーが破棄されます。 ただし、オブジェクト自体が完全に構築されていないため、デストラクターは実行されません。  
  
##  <a name="member_lists"></a>メンバー リスト  
 コンストラクター引数のクラス メンバーを、メンバー初期化子リストを使用して初期化します。 このメソッドを使用して*直接の初期化*、これは、コンス トラクターの本文内で代入演算子を使用するよりも効率的です。  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 ボックス オブジェクトを作成します。  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a>明示的なコンス トラクター  
 クラスが 1 つのパラメーターを持つコンストラクターを含む場合、または 1 つを除くすべてのパラメーターに既定値がある場合は、パラメーター型をクラス型へ暗黙的に変換できます。 `Box` クラスに次のようなコンストラクターがある場合を例に説明します。  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 次のように、ボックスを初期化することができます。  
  
```  
Box b = 42;  
```  
  
 または、int をボックスを受け取る関数に渡します。  
  
```  
class ShippingOrder  
{  
public:  
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}  
  
private:  
    Box m_box;  
    double m_postage;  
}  
//elsewhere...  
    ShippingOrder so(42, 10.8);  
  
```  
  
 このような変換が便利な場合もありますが、微妙でありながら重大なコードのエラーにつながることが多くあります。 一般的な規則としては、このような暗黙の型変換を防ぐために、コンストラクター (とユーザー定義演算子) で `explicit` キーワードを使用する必要があります。  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 コンストラクターが明示的な場合、次の行ではコンパイラ エラーが発生します: `ShippingOrder so(42, 10.8);`。  詳細については、次を参照してください。[ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)です。  
  
##  <a name="default_constructors"></a>既定のコンス トラクター  
 *既定のコンス トラクター* ; のパラメーターは必要ありません若干異なる規則に従います。  
  
 既定のコンス トラクターは、1 つの*特殊なメンバー関数*以外の場合は、クラスでコンス トラクターが宣言されていない場合、コンパイラは、既定のコンス トラクターを提供します。  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 既定のコンストラクターを呼び出し、丸かっこを使用しようとすると、次の警告が出力されます。  
  
```cpp  
class myclass{};  
int main(){  
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)  
}  
```  
  
 これは最も厄介な解析の例です。 例の式は、関数の宣言としても、既定のコンストラクターの呼び出しとしても解釈できるため、さらに、C++ パーサーが宣言を最優先に処理するため、この式は関数宣言として扱われます。 詳細については、次を参照してください。[最も厄介な解析](http://en.wikipedia.org/wiki/Most_vexing_parse)です。  
  
 既定以外のコンストラクターが宣言されている場合は、コンパイル時に既定のコンストラクターは生成されません。  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
int main(){  
  
    Box box1(1, 2, 3);  
    Box box2{ 2, 3, 4 };  
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 クラスに既定のコンストラクターがない場合、そのクラスのオブジェクトの配列は、角かっこ構文を使用して構築することはできません。 たとえば、前に示したコード ブロックでは、Boxes の配列は次のように宣言することはできません。  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 ただし、Boxes の配列を初期化する一連の初期化リストを使用することはできます。  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a>コピーし、移動コンス トラクター  
 A*コピー コンス トラクター*の同じオブジェクトへの参照は、「」と、そのコピーは、入力として取得する特殊なメンバー関数です。 詳細については、次を参照してください。[コピー コンス トラクターとコピー代入演算子 (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)です。 A*移動コンス トラクター*はでも、元のデータをコピーすることがなく既存のオブジェクトのデータの所有権を新しい変数に移動する特殊なメンバー関数。 詳細については、次を参照してください。[移動コンス トラクターと移動代入演算子 (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)です。  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a>明示的に既定化および削除のコンス トラクター  
 明示的に*既定*コピー コンス トラクター、既定のコンス トラクター、移動コンス トラクター、コピー代入演算子、代入演算子、およびデストラクターを移動します。 明示的に*削除*すべての特殊なメンバー関数。 詳細については、次を参照してください。[明示的に既定化および削除された関数](../cpp/explicitly-defaulted-and-deleted-functions.md)です。  
  
##  <a name="constructors_in_derived_classes"></a>派生クラスのコンス トラクター  
 派生クラスのコンストラクターは常に、基底クラスのコンストラクターを呼び出します。それにより、完全に構築された基底クラスに依存して、追加の処理を実行できるようになります。 基底クラスのコンストラクターは派生の順序で呼び出されます。たとえば、ClassA が ClassB から派生され、ClassB が ClassC から派生されている場合、まず ClassC のコンストラクター、次に ClassB のコンストラクター、最後に ClassA のコンストラクターが呼び出されます。  
  
 基底クラスに既定のコンストラクターがない場合は、派生クラスのコンストラクターで基底クラスのコンストラクターのパラメーターを指定する必要があります。  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height){  
       m_width = width;  
       m_length = length;  
       m_height = height;  
    }  
  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){  
        m_label = label;  
    }  
private:  
    string m_label;  
};  
  
int main(){  
  
    const string aLabel = "aLabel";  
    StorageBox sb(1, 2, 3, aLabel);  
}   
```  
  
### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>多重継承を使用するクラスのコンストラクター  
 クラスが複数の基底クラスから派生されている場合、基底クラスのコンストラクターは、派生クラスの宣言で示されている順序で呼び出されます。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 予想される出力を次に示します。  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a>コンス トラクターの仮想関数  
 コンストラクターの仮想関数の呼び出しは慎重に行うことをお勧めします。 基底クラスのコンストラクターは常に派生クラスのコンストラクターの前に呼び出されるため、基底コンストラクターで呼び出される関数は基底クラスのバージョンであり、派生クラスのバージョンではありません。 次の例では、`DerivedClass` を構築すると、`BaseClass` の `print_it()` 実装が行われてから、`DerivedClass` コンストラクターにより `DerivedClass` の `print_it()` 実装が行われます。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass{  
public:  
    BaseClass(){  
        print_it();  
    }  
    virtual void print_it() {  
        cout << "BaseClass print_it" << endl;  
    }  
};  
  
class DerivedClass : public BaseClass {  
public:  
    DerivedClass() {  
        print_it();  
    }  
    virtual void print_it(){  
        cout << "Derived Class print_it" << endl;  
    }  
};  
  
int main() {  
  
    DerivedClass dc;  
}  
```  
  
 出力を次に示します。  
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a>コンス トラクターと複合クラス  
 クラス型のメンバーを含むクラスと呼ばれる*複合クラス*です。 複合クラスのクラス型のメンバーが作成されると、そのコンストラクターはクラス自体のコンストラクターの前に呼び出されます。 含まれるクラスに既定のコンストラクターがないときは、複合クラスのコンストラクターで初期化リストを使用する必要があります。 前に示した `StorageBox` の例で、`m_label` メンバー変数の型を新しい `Label` クラスに変更した場合、両方の基底クラスのコンストラクターを呼び出し、`m_label` のコンストラクターで `StorageBox` 変数を初期化する必要があります。  
  
```cpp  
class Label {  
public:  
    Label(const string& name, const string& address) { m_name = name; m_address = address; }  
    string m_name;  
    string m_address;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, Label label)   
        : Box(width, length, height), m_label(label){}  
private:  
    Label m_label;  
};  
  
int main(){  
// passing a named Label  
    Label label1{ "some_name", "some_address" };  
    StorageBox sb1(1, 2, 3, label1);  
  
    // passing a temporary label  
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });  
  
    // passing a temporary label as an initializer list  
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});  
}  
```  
  
##  <a name="delegating_constructors"></a>デリゲート コンス トラクター  
 A*デリゲート コンス トラクター*をいくつかの初期化の処理を行うには、同じクラスには異なるコンス トラクターを呼び出します。 次の例では、派生クラスに 3 つのコンストラクターがあります。2 番目のコンストラクターは最初のコンストラクターに委任し、3 番目のコンストラクターは 2 番目のコンストラクターに委任します。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 出力を次に示します。  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 コンストラクターによって作成されたオブジェクトは、コンストラクターが終了するとすぐに完全に初期化されます。 `DerivedContainer(int int1)` は成功しますが、`DerivedContainer(int int1, int int2)` は失敗してデストラクターが呼び出されます。  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 Output:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 詳細については、次を参照してください。[均一な初期化とデリゲート コンス トラクター](../cpp/uniform-initialization-and-delegating-constructors.md)です。  
  
##  <a name="inheriting_constructors"></a>コンス トラクター (c++ 11) の継承  
 派生クラスは、次の例に示すように using 宣言を使用することにより、コンストラクターを直接基底クラスから継承できます。  
  
```  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:      
    Base() { cout << "Base()" << endl; }  
    Base(const Base& other) { cout << "Base(Base&)" << endl; }  
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }  
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }  
  
private:  
    int num;  
    char letter;  
};  
  
class Derived : Base  
{  
public:  
    // Inherit all constructors from Base  
    using Base::Base;  
  
private:  
    // Can't initialize newMember from Base constructors.  
    int newMember{ 0 };  
};  
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 using 宣言を使用すると、派生クラス内のコンストラクターとシグネチャが同じであるものを除き、基底クラスのすべてのコンストラクターがスコープ内に取りこまれます。 一般に、派生クラスが新しいデータ メンバーまたはコンストラクターを宣言しない場合は、コンストラクターの継承を使用することをお勧めします。  
  
 型が基底クラスを指定している場合、クラス テンプレートは型の引数からすべてのコンストラクターを継承できます。  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 派生クラスは、複数の基底クラスに同じシグネチャを持つコンストラクターがある場合、複数の基底クラスからは継承できません。  
  
##  <a name="rules_for_declaring_constructors"></a>コンス トラクターの宣言に関する規則  
 コンストラクターはそのクラスと同じ名前になります。 コンストラクターは、オーバーロードされた関数の規則に従っていくつでも宣言できます。  
  
 `argument-declaration-list` は空の場合もあります。  
  
 C++ では、次の表に示す 2 種類の特殊なコンストラクター、既定のコンストラクターとコピー コンストラクターが定義されています。  
  
### <a name="default-and-copy-constructors"></a>既定のコンストラクターとコピー コンストラクター  
  
|コンストラクションの種類|引数|目的|  
|--------------------------|---------------|-------------|  
|既定のコンストラクター|引数なしで呼び出すことができます。|クラス型の既定のオブジェクトを構築します。|  
|コピー コンストラクター|同じクラス型への参照の単一の引数を受け取ることができます。|クラス型のオブジェクトをコピーします。|  
  
 既定のコンストラクターは、引数なしで呼び出すことができます。 ただし、すべての引数に既定値がある場合は、引数リストを含む既定のコンストラクターを宣言できます。 同様に、コピー コンストラクターは、同じクラス型への参照の引数を 1 つ受け入れる必要があります。 以降のすべての引数に既定値がある場合、その他の引数を指定できます。  
  
 コンストラクターを指定しないと、コンパイラは既定のコンストラクターを生成しようとします。 コピー コンストラクターを指定しない場合、コンパイラが生成を試みます。 コンパイラによって生成されたこのようなコンストラクターは、パブリック メンバー関数と見なされます。 最初の引数が参照ではなくオブジェクトであるコピー コンストラクターを指定すると、エラーが発生します。  
  
 コンパイラによって生成された既定のコンストラクターは、オブジェクトを設定 (前に説明したように、vftable および vbtable を初期化) し、基底クラスとメンバーの既定のコンストラクターを呼び出しますが、それ以外のアクションは実行しません。 基底クラスとメンバーのコンストラクターは、存在していて、アクセスでき、あいまいでない場合にのみ呼び出されます。  
  
 コンパイラによって生成されたコピー コンストラクターは、新しいオブジェクトを設定し、コピーするオブジェクトのコンテンツのメンバーごとのコピーを実行します。 基底クラスまたはメンバーのコンストラクターが存在する場合は、それらが呼び出されます。存在しない場合は、ビット単位のコピーが実行されます。  
  
 場合はすべて基底クラスとメンバー クラス クラスの`type`を受け入れるコピー コンス トラクターがある、 **const**コンパイラによって生成されたコピー コンス トラクターの引数が型の 1 つの引数を受け取ります**const** `type`**&**. それ以外の場合、コンパイラによって生成されたコピー コンス トラクターが型の単一の引数を受け入れる`type`  **&**です。  
  
 初期化するために、コンス トラクターを使用することができます、 **const**または`volatile`としては、オブジェクトがそれ自体のコンス トラクターを宣言することはできません**const**または`volatile`です。 コンス トラクターにのみ有効なストレージ クラスが**インライン**; 他のストレージ クラス修飾子の使用を含む、`__declspec`キーワード、コンス トラクターを持つ、コンパイラ エラーが発生します。  
  
 Stdcall 呼び出し規約は静的メンバー関数で使用され、グローバル関数で宣言、 **_ _stdcall**キーワード、およびを可変個引数リストを使用しないでください。 使用すると、 **_ _stdcall**コンス トラクターなどの非静的メンバー関数ではキーワード、コンパイラは、thiscall 呼び出し規約が使用されます"。  
  
 基底クラスのコンストラクターは、派生クラスによって継承されません。 派生クラス型のオブジェクトが作成されるときは、最初に基底クラスのコンポーネントの構築が行われ、その後、派生クラスのコンポーネントに移ります。 完全なオブジェクトの部分が初期化されると、コンパイラは各基底クラスのコンス トラクターを使用 (仮想派生の場合は除きます。  
  
##  <a name="explicitly_invoking_constructors"></a>コンス トラクターの明示的な呼び出し  
 コンストラクターは、指定した型のオブジェクトを作成するために、プログラムで明示的に呼び出すことができます。 たとえば、行の終わりを記述する 2 つの `Point` オブジェクトを作成するには、次のコードを作成します。  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 `Point` 型の 2 つのオブジェクトが作成され、`DrawLine` 関数に渡され、式 (関数呼び出し) の最後に破棄されます。  
  
 コンストラクターが明示的に呼び出される別のコンテキストは初期化です。  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 `Point` 型のオブジェクトが、`int` 型の 2 つの引数を受け取るコンストラクターを使用して作成および初期化されます。  
  
 前の 2 つの例のように、コンストラクターを明示的に呼び出すことによって作成されたオブジェクトには名前がなく、オブジェクトを作成する式には有効期間があります。 さらに詳しく説明しています[一時オブジェクト](../cpp/temporary-objects.md)です。  
  
 オブジェクトがユーザー コードの最初の行の実行前に完全に設定されているので (仮想テーブルが初期化されているなど)、通常、内部メンバー関数をコンストラクター内部から呼び出すのは安全です。 ただし、構築または破棄中に抽象基底クラスの仮想メンバー関数をメンバー関数で呼び出すのは、安全ではない可能性があります。  
  
 コンストラクターは仮想関数を呼び出すことができます。 仮想関数を呼び出す場合、呼び出される関数は、コンストラクターの独自のクラス (またはその基底クラスから継承されたクラス) に対して定義された関数です。 次の例は、仮想関数がコンストラクター内から呼び出されるときに何か起きるかを示します。  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 前のプログラムを実行すると、`Derived d` 宣言によって次の一連のイベントが発生します。  
  
1.  `Derived` (`Derived::Derived`) クラスのコンストラクターが呼び出されます。  
  
2.  `Derived` クラスのコンストラクターの本体を入力する前に、`Base` (`Base::Base`) クラスのコンストラクターが呼び出されます。  
  
 `Base::Base` は仮想関数 `f` を呼び出します。 `Derived::f` オブジェクトは `d` 型なので、通常は `Derived` が呼び出されます。 `Base::Base` 関数はコンストラクターなので、オブジェクトはまだ `Derived` 型ではなく、`Base::f` が呼び出されます。  
  
