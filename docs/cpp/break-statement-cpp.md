---
title: "break ステートメント (C++) | Microsoft Docs"
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
  - "break_cpp"
  - "break"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "break キーワード [C++]"
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# break ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`break` ステートメントは、それを囲む最も近いループまたは条件付きステートメントの実行を終了させます。  このステートメントの終了の後ろにステートメントがある場合は、そこに制御が移動します。  
  
## 構文  
  
```  
break;  
```  
  
## 解説  
 `break` ステートメントは、条件付き [switch](../cpp/switch-statement-cpp.md) ステートメントと、[do](../cpp/do-while-statement-cpp.md)、[for](../cpp/for-statement-cpp.md)、および [while](../cpp/while-statement-cpp.md) ループ ステートメントと共に使用されます。  
  
 `switch` ステートメントでは、`break` ステートメントがあると、その `switch` ステートメントの外側にある次のステートメントが実行されます。  `break` ステートメントがない場合は、一致する `case` ラベルから `switch` ステートメントの最後までのすべてのステートメントが、`default` 句も含めて実行されます。  
  
 ループでは、`break` ステートメントは、そのすぐ外側の `do`、`for`、または `while` ステートメントの実行を終了します。  終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。  
  
 入れ子になったステートメント内では、`break` ステートメントは、それを直接囲む `do`、`for`、`switch`、または `while` ステートメントだけを終了させます。  `return` ステートメントまたは `goto` ステートメントを使用して、より深い入れ子構造から制御を移すことができます。  
  
## 使用例  
 次のコードでは、`for` ループ内で `break` ステートメントを使用する方法を示しています。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
  **各 case で:**   
**1**  
**2**  
**3** 次のコードでは、`while` ループ内と `do` ループ内で `break` ステートメントを使用する方法を示しています。  
  
```cpp  
  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
  **各 case で:**   
**0**  
**1**  
**2**  
**3** 次のコードでは、switch ステートメント内で `break` を使用する方法を示しています。  各 case を個別に処理する場合は、それぞれの case で `break` を使用する必要があります。`break` を使用しない場合、コードの実行は次の case にフォール スルーします。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## 参照  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [continue ステートメント](../cpp/continue-statement-cpp.md)