---
title: "メンバー アクセス コントロール (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセス制御 [C++]"
  - "メンバー アクセス [C++]"
  - "メンバー アクセス コントロール [C++]"
ms.assetid: 2d596bca-56ad-4277-94e1-ce3db45fa14a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メンバー アクセス コントロール (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アクセス制御を使用すると、クラスの [public](../cpp/public-cpp.md) インターフェイスを、 [private](../Topic/private%20\(C++\).md) 実装の詳細や、派生クラスでのみ使用する [protected](../Topic/protected%20\(C++\).md) メンバーから分離できます。  アクセス指定子は、その後で宣言されたすべてのメンバーに対して当てはまり、これは、次のアクセス指定子が検出されるまで続きます。  
  
```  
class Point  
{  
public:                   
    Point( int, int ) // Declare public constructor.;  
    Point();// Declare public default constructor.  
    int &x( int ); // Declare public accessor.  
    int &y( int ); // Declare public accessor.  
  
private:                 // Declare private state variables.  
    int _x;  
    int _y;  
  
protected:      // Declare protected function for derived classes only.  
    Point ToWindowCoords();  
};  
  
```  
  
 既定のアクセスは、クラスでは `private`、構造体または共用体では `public` です。  クラスのアクセス指定子は、任意の順序で何回でも使用できます。  クラス型のオブジェクトに対するストレージの割り当ては実装に依存しますが、メンバーはアクセス指定子の間で順次上位メモリ アドレスが割り当てられることが保証されます。  
  
### メンバー アクセス コントロール  
  
|アクセスの種類|説明|  
|-------------|--------|  
|[private](../Topic/private%20\(C++\).md)|`private` として宣言されたクラス メンバーは、そのクラスのメンバー関数とフレンド \(クラスまたは関数\) のみが使用できます。|  
|[protected](../Topic/protected%20\(C++\).md)|`protected` として宣言されたクラス メンバーは、そのクラスのメンバー関数とフレンド \(クラスまたは関数\) が使用できます。  また、そのクラスから派生したクラスも "protected" メンバーを使用できます。|  
|[public](../cpp/public-cpp.md)|**public** として宣言されたクラス メンバーは、どの関数からでも使用できます。|  
  
 アクセス制御により、不適切な方法でオブジェクトを使用するのを防ぐことができます。  明示的な型変換 \(キャスト\) を実行すると、この保護機能が働かなくなります。  
  
> [!NOTE]
>  アクセス制御は、すべての名前 \(メンバー関数、メンバー データ、入れ子のクラス、列挙子\) に同等に適用できます。  
  
## 派生クラスのアクセス コントロール  
 派生クラスでアクセスできる基底クラスのメンバーは、次の 2 つの要因によって制御されます。派生クラスの継承メンバーに対するアクセスも、この同じ要因によって制御されます。  
  
-   派生クラスが **class\-head** で *public* アクセス指定子を使用して基底クラスを宣言するかどうか \(*class\-head* は、「[Defining Class Types \(クラス型の定義\)](http://msdn.microsoft.com/ja-jp/e8c65425-0f3a-4dca-afc2-418c3b1e57da)」の文法のセクションで説明されています\)。  
  
-   基底クラスでメンバーへのアクセスがどのように指定されているか。  
  
 次の表は、これらの要因間の相互作用と、基底クラスのメンバーへのアクセスがどのように決定されるかを示しています。  
  
### 基底クラスのメンバー アクセス  
  
|private|protected|パブリック|  
|-------------|---------------|-----------|  
|派生のアクセスに関係なく常にアクセスできない|プライベート派生を使用する場合は派生クラス内でプライベート|プライベート派生を使用する場合は派生クラス内でプライベート|  
||プロテクト派生を使用する場合は派生クラス内でプロテクト|プロテクト派生を使用する場合は派生クラス内でプロテクト|  
||パブリック派生を使用する場合は派生クラス内でプロテクト|パブリック派生を使用する場合は派生クラス内でパブリック|  
  
 次に例を示します。  
  
```  
// access_specifiers_for_base_classes.cpp  
class BaseClass  
{  
public:  
    int PublicFunc();    // Declare a public member.  
protected:  
    int ProtectedFunc(); // Declare a protected member.  
private:  
    int PrivateFunc();   // Declare a private member.  
};  
  
// Declare two classes derived from BaseClass.  
class DerivedClass1 : public BaseClass  
{  
};  
  
class DerivedClass2 : private BaseClass  
{  
};  
  
int main()  
{  
}  
```  
  
 `DerivedClass1` では、メンバー関数 `PublicFunc` はパブリック メンバーであり、`ProtectedFunc` がパブリック基底クラスであるため、`BaseClass` はプロテクト メンバーになります。  `PrivateFunc` は `BaseClass` に対してプライベートであるため、派生クラスからはアクセスできません。  
  
 `DerivedClass2` では、`PublicFunc` がプライベート基底クラスであるため、`ProtectedFunc` 関数と `BaseClass` 関数は、プライベート メンバーと見なされます。  ここでも、`PrivateFunc` は `BaseClass` に対してプライベートであるため、派生クラスからはアクセスできません。  
  
 基底クラスにアクセス指定子を使用しなくても、派生クラスを宣言できます。  このような場合、派生クラスの宣言に **class** キーワードが使用されていれば、派生はプライベートと見なされます。  派生クラスの宣言で `struct` キーワードが使用されている場合、派生はパブリックと見なされます。  コード例を次に示します。  
  
```  
class Derived : Base  
...  
```  
  
 上の式は、下の式と同等です。  
  
```  
class Derived : private Base  
...  
```  
  
 同様に、  
  
```  
struct Derived : Base  
...  
```  
  
 上の式は、下の式と同等です。  
  
```  
struct Derived : public Base  
...  
```  
  
 関数や派生クラスは、基底クラスで `friend` 宣言を使用して宣言されていない限り、プライベート アクセスを持つように宣言されたメンバーにアクセスできないことに注意してください。  
  
 **union** 型は基底クラスを持つことはできません。  
  
> [!NOTE]
>  プライベート基底クラスを指定する場合は、派生クラスのユーザーにメンバー アクセスがわかるように、`private` キーワードを明示的に使用することをお勧めします。  
  
## アクセス制御と静的メンバー  
 基底クラスを `private` として指定した場合、非静的メンバーにのみ影響します。  パブリックな静的メンバーは、派生クラス内でもアクセスできます。  ただし、ポインター、参照、またはオブジェクトを使用して基底クラスのメンバーにアクセスするには、アクセス制御が再び適用される時点で変換が必要になる場合があります。  次に例を示します。  
  
```  
// access_control.cpp  
class Base  
{  
public:  
    int Print();             // Nonstatic member.  
    static int CountOf();    // Static member.  
};  
  
// Derived1 declares Base as a private base class.  
class Derived1 : private Base  
{  
};  
// Derived2 declares Derived1 as a public base class.  
class Derived2 : public Derived1  
{  
    int ShowCount();    // Nonstatic member.  
};  
// Define ShowCount function for Derived2.  
int Derived2::ShowCount()  
{  
   // Call static member function CountOf explicitly.  
    int cCount = Base::CountOf();     // OK.  
  
   // Call static member function CountOf using pointer.  
    cCount = this->CountOf();  // C2247. Conversion of  
                               //  Derived2 * to Base * not  
                               //  permitted.  
    return cCount;  
}  
```  
  
 このコードでは、アクセス制御により、`Derived2` へのポインターから `Base` へのポインターへの変換が禁止されます。  **this** ポインターは暗黙的に型 `Derived2 *` です。  `CountOf` 関数を選択するには、**これ**を `Base *` 型に変換する必要があります。  `Base` は `Derived2` に対するプライベート間接基底クラスであるため、このような変換は許可されません。  プライベート基底クラス型への変換は、直接の派生クラスへのポインターにのみ使用できます。  したがって、型 `Derived1 *` のポインターは型 `Base *` に変換できます。  
  
 ポインター、参照、またはオブジェクトを使用して選択することなく `CountOf` 関数を明示的に呼び出すことは、変換を意味しないことに注意してください。  したがって、呼び出しは許可されます。  
  
 派生クラス `T` のメンバーとフレンドは `T` へのポインターを、`T` のプライベート直接基底クラスへのポインターに変換できます。  
  
## 仮想関数へのアクセス  
 [仮想](../cpp/virtual-cpp.md)関数に適用されるアクセス制御は、関数呼び出しを行う型によって決まります。  関数の宣言のオーバーライドは、特定の型のアクセス制御には影響しません。  例:  
  
```  
// access_to_virtual_functions.cpp  
class VFuncBase  
{  
public:  
    virtual int GetState() { return _state; }  
protected:  
    int _state;  
};  
  
class VFuncDerived : public VFuncBase  
{  
private:  
    int GetState() { return _state; }  
};  
  
int main()  
{  
   VFuncDerived vfd;             // Object of derived type.  
   VFuncBase *pvfb = &vfd;       // Pointer to base type.  
   VFuncDerived *pvfd = &vfd;    // Pointer to derived type.  
   int State;  
  
   State = pvfb->GetState();     // GetState is public.  
   State = pvfd->GetState();     // C2248 error expected; GetState is private;  
}  
```  
  
 前の例では、型 `GetState` へのポインターを使用する仮想関数 `VFuncBase` の呼び出しは、`VFuncDerived::GetState` を呼び出します。`GetState` は public として扱われます。  ただし、`GetState` が `VFuncDerived` クラスで private として宣言されているため、`GetState` 型へのポインターを使用して `VFuncDerived` を呼び出すとアクセス制御違反になります。  
  
> [!CAUTION]
>  仮想関数 `GetState` は、基底クラス `VFuncBase` へのポインターを使用して呼び出すことができます。  これは、呼び出された関数がその関数の基底クラス版であることを意味しません。  
  
## 多重継承でのアクセス制御  
 仮想基底クラスを含む多重継承のグリッドでは、任意の名前に複数のパスを通じてアクセスできます。  パスが異なると適用できるアクセス制御も異なるため、コンパイラは最大のアクセスを許可するパスを選択します。  次の図を参照してください。  
  
 ![継承グラフのパスに沿ったアクセス](../cpp/media/vc38v91.png "vc38V91")  
継承グラフのパスに沿ったアクセス  
  
 図では、クラス `VBase` で宣言される名前は、必ずクラス `RightPath` 経由でアクセスされます。  `RightPath` が `VBase` をプライベート基底クラスとして宣言するのに対し、`LeftPath` は `VBase` をパブリック基底クラスとして宣言するため、右のパスの方がアクセスが簡単です。  
  
## 参照  
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)