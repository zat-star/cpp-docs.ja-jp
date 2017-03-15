---
title: "リンケージのない名前 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "列挙子 [C++], リンケージ"
  - "関数パラメーター [C++]"
  - "関数 [C++], パラメーター"
  - "名前 [C++], リンケージなし"
  - "typedef 名, リンケージ"
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# リンケージのない名前
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リンケージを持たない名前は次のとおりです。  
  
-   関数パラメーター。  
  
-   `extern` または **static** として宣言されていないブロック スコープの名前。  
  
-   列挙子。  
  
-   `typedef` ステートメントで宣言されている名前。  例外は、名前のないクラス型に名前を付けるために `typedef` ステートメントが使用されている場合です。  クラスに外部リンケージがある場合、名前に外部リンケージがある場合があります。  次の例は、`typedef` 名に外部リンケージがある状況を示しています。  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     `typedef` 名の `POINT` は、無名構造体のクラス名になります。  その後、外部リンケージで関数を宣言するために使用されます。  
  
 `typedef` 名にリンケージがないため、それらの定義は変換単位の間で異なる場合があります。  コンパイルは個別に実行されるため、コンパイラがこれらの相違点を検出する方法はありません。  その結果、この種類のエラーは、リンク時まで検出されません。  次のケースがあるとします。  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 前のコードは、リンク時に「未解決の外部」エラーを生成します。  
  
## 使用例  
 C\+\+ 関数は、ファイル スコープまたはクラス スコープでのみ定義できます。  次の例では、関数を定義する方法と、間違った関数定義を示します。  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## 参照  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)