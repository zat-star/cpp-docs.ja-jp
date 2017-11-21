---
title: "スコープ (Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dcf85a2feff9aa16434f626804edefa4dbe4610e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="scope-visual-c"></a>スコープ (Visual C++)
C++ の名前は、プログラムの特定の領域でのみ使用できます。 この領域は名前の "スコープ" と呼ばれます。 スコープは、静的なオブジェクトを表さない名前の "有効期間" を決定します。 スコープも、クラス コンストラクターおよびデストラクターが呼び出されたとき、およびスコープに対してローカルな変数が初期化されたときに名前の可視性を決定します。 (詳細については、次を参照してください[コンス トラクター](../cpp/constructors-cpp.md)と[デストラクター](../cpp/destructors-cpp.md)。)。スコープは 5 種類あります。  
  
-   **ローカル スコープ**ブロック内で宣言された名前がそのブロックと、これによって、および宣言の位置の後にのみを囲むブロック内でのみアクセスできます。 関数の最も外側のブロックのスコープでは、関数への仮引数の名前は、関数本体の外側のブロック内で宣言された場合と同様に、ローカル スコープを持ちます。 次のコードがあるとします。  
  
    ```  
    {  
        int i;  
    }  
    ```  
  
     `i` の宣言は中かっこで囲まれたブロックにあるため、コードが最後の中かっこの前にアクセスしないため、`i` にはローカル スコープがあり、アクセス可能ではありません。  
  
-   **関数スコープ**ラベルは関数スコープを持つ唯一の名前。 これらは関数内のどの位置でも使用できますが、その関数の外部からはアクセスできません。 関数の仮引数 (関数定義で指定された引数) は、関数本体の最も外側のブロックのスコープ内にあると見なされます。  
  
-   **ファイル スコープ**すべてのブロックまたはクラスの外側で宣言された任意の名前はファイル スコープを持ちます。 宣言の後、翻訳単位内の任意の場所でアクセスできます。 静的オブジェクトを宣言しないファイル スコープを持つ名前は、グローバル名とも呼ばれます。  
  
     C++ では、ファイル スコープは、名前空間スコープとも呼ばれます。  
  
-   **クラス スコープ**クラス メンバーの名前はクラス スコープを設定します。 クラス メンバー関数は、メンバー選択演算子を使用してのみアクセスできます (**です。** または **->** ) またはメンバーへのポインター演算子 (**.\***または **-> \*** ) オブジェクトまたはそのクラスのオブジェクトへのポインターに対する非静的クラス メンバーのデータと見なされますそのクラスのオブジェクトに対してローカルです。 クラス宣言の例を次に示します。  
  
    ```  
    class Point  
    {  
        int x;  
        int y;  
    };  
    ```  
  
     クラス メンバー `x` および `y` は、`Point` クラスのスコープ内にあると見なされます。  
  
-   **プロトタイプ スコープ**関数プロトタイプで宣言された名前が、プロトタイプの末尾までのみ表示されます。 次のプロトタイプは、3 つの名前 (`strDestination`、`numberOfElements`、`strSource`) を宣言します。これらの名前は、プロトタイプの最後にスコープの外に出ます。  
  
    ```  
    errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
    ```  
  
## <a name="hiding-names"></a>名前の隠ぺい  
 囲まれたブロック内で名前を宣言すると、その名前が非表示になります。 次の図では、内側のブロックで `i` が再宣言されています。そのため、外側のブロック スコープでは `i` に関連付けられた変数が隠し変数になります。  
  
 ![ブロック &#45; スコープの名前の隠ぺい](../cpp/media/vc38sf1.png "vc38SF1")  
ブロック スコープおよび名前の非表示  
  
 このプログラムの出力を次の図に示します。  
  
```  
i = 0  
i = 7  
j = 9  
i = 0  
```  
  
> [!NOTE]
>  `szWhat` 引数は、この関数のスコープ内にあると見なされます。 したがって、この関数の外側のブロックで宣言されたものとして処理されます。  
  
## <a name="hiding-class-names"></a>クラス名の非表示  
 関数、オブジェクト、変数、または列挙子を同じスコープ内で宣言することで、クラス名を非表示にできます。 ただし、クラス名アクセスできますキーワードで始まるとき**クラス**です。  
  
```  
// hiding_class_names.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
// Declare class Account at file scope.  
class Account  
{  
public:  
    Account( double InitialBalance )  
        { balance = InitialBalance; }  
    double GetBalance()  
        { return balance; }  
private:  
    double balance;  
};  
  
double Account = 15.37;            // Hides class name Account  
  
int main()  
{  
    class Account Checking( Account ); // Qualifies Account as   
                                       //  class name  
  
    cout << "Opening account with balance of: "  
         << Checking.GetBalance() << "\n";  
}  
//Output: Opening account with balance of: 15.37  
```  
  
> [!NOTE]
>  クラス名 (`Account`) を呼び出すときは、ファイル スコープ変数 Account と区別するため、class キーワードを使用する必要があります。 スコープ解決演算子 (::) の左側がクラス名の場合は、この規則が適用されません。 スコープ解決演算子の左側の名前は、常にクラス名と見なされます。  
  
 次の例は、型のオブジェクトへのポインターを宣言する方法を示します`Account`を使用して、**クラス**キーワード。  
  
```  
class Account *Checking = new class Account( Account );  
```  
  
 `Account` (かっこ内) 上記のステートメントで初期化子ではファイル スコープ以外の型である**二重**です。  
  
> [!NOTE]
>  この例のように、識別子名を再使用するのは適切なプログラミング方法ではありません。  
  
 ポインターの詳細については、次を参照してください。[派生型](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c)です。 クラスのオブジェクトの宣言と初期化については、次を参照してください。[クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)です。 使用方法について、**新しい**と**削除**フリー ストア演算子を参照してください[新しい演算子と delete 演算子](new-and-delete-operators.md)です。  
  
## <a name="hiding-names-with-file-scope"></a>ファイル スコープによる名前の非表示  
 ブロック スコープで同じ名前で明示的に宣言して、ファイル スコープを持つ名前を非表示にすることができます。 ただし、スコープ解決演算子 (`::`) を使用して、ファイル スコープ名にアクセスできます。  
  
```  
// file_scopes.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int i = 7;   // i has file scope, outside all blocks  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   int i = 5;   // i has block scope, hides i at file scope  
   cout << "Block-scoped i has the value: " << i << "\n";  
   cout << "File-scoped i has the value: " << ::i << "\n";  
}  
```  
  
```Output  
Block-scoped i has the value: 5  
File-scoped i has the value: 7  
```  
  
## <a name="see-also"></a>関連項目  
 [基本的な概念](../cpp/basic-concepts-cpp.md)