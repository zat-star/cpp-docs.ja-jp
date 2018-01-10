---
title: "列挙型 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: enum_cpp
dev_langs: C++
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96b1b29baaa779fda1e1f076daf3d8bd9335403b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="enumerations-c"></a>列挙型 [C++]
列挙体は、列挙子と呼ばれる一連の名前付き整数定数で構成されるユーザー定義型です。  
  
> [!NOTE]
>  ここでは、ISO 標準 C++ 言語の `enum` 型とスコープを持つ (または厳密に型指定された) `enum class` 型について説明します。列挙型クラスは C++11 で導入されました。 については、`public enum class`または`private enum class`型 C + +/CLI および C++ + CX を参照してください[列挙型クラス](../windows/enum-class-cpp-component-extensions.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
// unscoped enum:  
enum [identifier] [: type]  
{enum-list};   
  
// scoped enum:  
enum [class|struct]   
[identifier] [: type]   
{enum-list};  
```  
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```  
  
## <a name="parameters"></a>パラメーター  
 `identifier`  
 列挙体に渡す型名。  
  
 `type`  
 列挙子の基になる型であり、すべての列挙子は同じ型を基にしています。 任意の整数型を指定できます。  
  
 `enum-list`  
 列挙体に含まれる列挙子のコンマ区切りのリスト。 スコープ内のすべての列挙子または変数名は一意である必要があります。 ただし、値は複製できます。 スコープを持たない列挙型では、スコープは親のスコープです。スコープを持つ列挙型では、スコープは `enum-list` 自体のスコープです。  スコープ列挙で一覧空でもかまいません有効で、新しい整数型を定義します。
  
 `class`  
 宣言内でこのキーワードを使用することにより、列挙型がスコープを持ち、`identifier` が提供される必要があることを指定します。 `struct` の代わりに、このコンテキストで意味的に同等な `class` キーワードを使用することもできます。  
  
## <a name="enumerator-scope"></a>列挙子のスコープ  
 列挙型を使用すると、名前付き定数として表される値の範囲 (列挙子) を記述できます。 元の C と C++ の列挙型では、修飾なしの列挙子は列挙型が宣言されているスコープ内で可視です。 スコープを持つ列挙型では、列挙子の名前は列挙型の名前で修飾する必要があります。 次の例に、2 種類の列挙型のこの基本的な相違点を示します。  
  
```cpp  
namespace CardGame_Scoped  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type  
        { /*...*/}  
    }  
}  
  
namespace CardGame_NonScoped  
{  
    enum Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Clubs) // Enumerator is visible without qualification  
        { /*...*/  
        }  
    }  
}  
```  
  
 列挙型の各値の名前には、列挙型の値の順序に対応する場所の整数値が割り当てられます。 既定では、最初の値には 0、その次の値には 1 などのように割り当てられますが、次に示すように、列挙体の値を明示的に設定することもできます。  
  
```cpp  
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };  
  
```  
  
 `Diamonds` 列挙子に値 `1` を割り当てます。 明示的な値を指定しない場合、後続の列挙子は前の列挙子の値に 1 を加えた数値が指定されます。 前の例では、`Hearts` の値が 2、`Clubs` の値が 3 などのようになります。  
  
 すべての列挙子は定数として扱われ、`enum` が定義されているスコープ内で (スコープを持たない列挙型の場合)、または列挙型自体のスコープ内で (スコープを持つ列挙型の場合)、列挙子の名前は一意である必要があります。 列挙子の名前に対応する値は一意である必要はありません。 たとえば、スコープを持たない列挙型 `Suit` が次のように宣言されているとします。  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 この場合、`Diamonds`、`Hearts`、`Clubs`、`Spades` の値はそれぞれ 5、6、4、5 になります。 5 つが複数回使用されています。これは意図した値と異なる可能性がありますが、それ自体は問題ありません。 これらの規則はスコープを持つ列挙型でも同じです。  
  
 ## <a name="casting-rules"></a>キャストの規則  
  
 スコープを持たない列挙型の定数が暗黙的に `int` に変換されることはありますが、`int` が列挙型の値に暗黙的に変換されることはありません。 次の例では、`hand` に `Suit` 型でない値を代入しようとするとどうなるかを示します。  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 スコープを持つまたは持たない列挙子に `int` を変換するには、キャストが必要です。 ただし、スコープを持たない列挙子はキャストなしで整数値に上位変換できます。  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 このような暗黙の型変換を使用すると、意図しない副作用につながることがあります。 スコープを持たない列挙型に関連するプログラミング エラーをなくすために役立つように、スコープを持つ列挙型の値は厳密に型指定します。 次の例に示すように、スコープを持つ列挙子は列挙型の名前 (識別子) で修飾する必要があり、暗黙的に変換されることはありません。  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 `hand = account_num;` 行では、前に示したように、スコープを持たない列挙型に関連するエラーが発生することに注意してください。 これは、明示的にキャストすることでエラーを回避できます。 ただし、スコープを持つ列挙型を使用しても、次のステートメント、`account_num = Suit::Hearts;` での変換の試みは、明示的なキャストなしではエラーが発生します。 

## <a name="enums-with-no-enumerators"></a>いない列挙子の列挙型
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): (定期的またはスコープを持つ) 列挙型を定義すると、明示的な基になる型となしの列挙子と、導入するには有効で、新しい整数を入力します。その他の種類へ暗黙的な変換がありません。 この型を使用して、その組み込みの基になる型ではなく、不注意による暗黙の変換による微妙なエラーが発生する可能性を排除できます。  


```cpp
enum class byte : unsigned char { };
```

新しいタイプは、基になる型の正確なコピーし、ために、同じの呼び出し規約で、パフォーマンスが低下せず ABIs 全体で使用できることを意味します。 キャストは必要ありませんダイレクト リストの初期化を使用して、型の変数が初期化される場合です。 次の例では、さまざまなコンテキストでない列挙子の列挙型を初期化する方法を示します。

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X 
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 }; 

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
``` 
  
## <a name="see-also"></a>参照  
 [C 列挙体の宣言](../c-language/c-enumeration-declarations.md)   
 [キーワード](../cpp/keywords-cpp.md)