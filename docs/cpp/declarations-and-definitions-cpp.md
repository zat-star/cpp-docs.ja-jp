---
title: 宣言と定義 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f8a0922d66a9421bcc7c6c07b9396b277499d0d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="declarations-and-definitions-c"></a>宣言と定義 (C++)
宣言は、プログラムでは、名前、変数、名前空間、関数およびクラスの名前などを紹介します。 また、宣言では、型情報だけでなく、宣言されるオブジェクトの他の特性も指定します。 名前は使用する前に宣言する必要があります。C++ では、名前が宣言される位置でコンパイラから可視になるかどうかが決まります。 関数またはコンパイル ユニットです。 後で宣言されているクラスを参照することはできません。使用することができます*宣言を転送*この制限を回避するためです。  
  
 定義では、名前が記述されるコードまたはデータを指定します。 宣言されているものに対して記憶域スペースを割り当てるために、コンパイラは定義を必要とします。  
  
## <a name="declarations"></a>宣言  
 宣言は、プログラムに 1 つ以上の名前を導入します。 宣言は、プログラムに複数回記述できます。 そのため、クラス型、構造体型、列挙型、およびその他のユーザー定義型を、コンパイル単位ごとに宣言できます。 この複数回の宣言に対する制約として、すべての宣言は同じである必要があります。 宣言は、その宣言が以下に当てはまる場合を除いて、定義にもなります。  
  
1.  宣言が関数プロトタイプ (関数本体のない関数宣言) である。  
  
2.  宣言が `extern` 指定子を含んでいるが、初期化子 (オブジェクトや変数) や関数本体 (関数) を含んでいない。 これは、現在の翻訳単位内に定義が存在するとは限らないことを示しており、宣言された名前は外部リンケージを持ちます。  
  
3.  クラス宣言内の静的データ メンバーの宣言である。  
  
     静的クラスのデータ メンバーは、クラスのすべてのオブジェクトで共有される個別の変数であるため、クラス宣言の外側で定義し、初期化する必要があります (クラスおよびクラス メンバーの詳細については、次を参照してください[クラス](../cpp/classes-and-structs-cpp.md)。)。  
  
4.  後ろに定義が続かない、`class T;` などのようなクラス名の宣言である。  
  
5.  宣言が `typedef` ステートメントである。  
  
 定義でもある宣言の例を次に示します。  
  
```  
// Declare and define int variables i and j.  
int i;  
int j = 10;  
  
// Declare enumeration suits.  
enum suits { Spades = 1, Clubs, Hearts, Diamonds };  
  
// Declare class CheckBox.  
class CheckBox : public Control  
{  
public:  
            Boolean IsChecked();  
    virtual int     ChangeState() = 0;  
};  
```  
  
 定義でない宣言のいくつかを次に示します。  
  
```  
  
extern int i;  
char *strchr( const char *Str, const char Target );  
```  
  
 名前は宣言子の直後、ただし初期化子 (省略可能) よりも前の位置で宣言されるものと見なされます 詳細については、次を参照してください。[宣言の位置](../cpp/point-of-declaration-in-cpp.md)です。  
  
 宣言が発生する、*スコープ*です。 スコープは、宣言された名前の可視性と定義されたオブジェクトの継続時間 (存在する場合) を制御します。 スコープ規則が宣言と対話する方法の詳細については、次を参照してください。[スコープ](../cpp/scope-visual-cpp.md)です。  
  
 オブジェクトの宣言も定義が含まれている場合を除き、`extern`ストレージ クラス指定子の記載[ストレージ クラス](storage-classes-cpp.md)です。 関数宣言は、プロトタイプでない限り定義でもあります。 プロトタイプは定義する関数本体がない関数ヘッダーです。 オブジェクトの定義により、そのオブジェクトのストレージの割り当てと適切な初期化が行われます。  
  
## <a name="definitions"></a>定義  
 定義とは、オブジェクトまたは変数、関数、クラス、または列挙子の一意な仕様です。 定義は一意である必要があるため、1 つのプログラムに含められるの特定プログラム要素の定義は、1 つだけです。 宣言と定義は、多対一の対応関係を持つことができます。 プログラム要素を定義しないで宣言できるケースとして、次の 2 つがあります。  
  
1.  関数が宣言されても、関数呼び出しや関数のアドレスを受け取る式で参照されない場合。  
  
2.  クラスが、そのクラスの定義を知っている必要のない方法でのみ使用される場合。 ただし、そのクラスは、宣言されている必要があります。 このような場合のコードを次に示します。  
  
    ```  
    // definitions.cpp  
    class WindowCounter;   // Forward declaration; no definition  
  
    class Window  
    {  
       // Definition of WindowCounter not required  
       static WindowCounter windowCounter;  
    };  
  
    int main()  
    {  
    }  
    ```  
  
## <a name="see-also"></a>関連項目  
 [基本的な概念](../cpp/basic-concepts-cpp.md)   
 [宣言の位置](../cpp/point-of-declaration-in-cpp.md)