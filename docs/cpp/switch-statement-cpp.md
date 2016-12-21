---
title: "switch ステートメント (C++) | Microsoft Docs"
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
  - "default"
  - "default_cpp"
  - "switch"
  - "switch_cpp"
  - "case"
  - "case_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case キーワード [C++], switch ステートメント内"
  - "default キーワード [C++]"
  - "switch キーワード [C++]"
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# switch ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

整数式の値に応じてコードの複数のセクション間を切り替えます。  
  
## 構文  
  
```  
  
      switch ( expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## 解説  
 *expression* は整数型であるか、整数型へのあいまいでない変換が行われるクラス型であることが必要です。  整数の上位変換は「[整数の上位変換](../misc/integral-promotions.md)」で説明されているように実行されます。  
  
 `switch` ステートメントの本体は一連の **case** ラベルと省略可能な **default** ラベルで構成されます。  **case** ステートメントの 2 つの定数式は同じ値に評価できません。  **default** ラベルは一度だけ記述できます。  ラベル付きステートメントは構文上の要件ではありませんが、ラベル付きステートメントがないと、`switch` ステートメントを使用する意味がありません。   default ステートメントを最後に記述する必要はありません。switch ステートメントの本体内の任意の場所で使用できます。  case ラベルまたは default ラベルは、switch ステートメント内でのみ使用できます。  
  
 各 **case** ラベル内の *constant\-expression* は、*expression* 型に変換され、*expression* と等しいかどうかが比較されます。  **case** *constant\-expression* が *expression* の値と一致するステートメントに制御が移ります。  結果の動作を次の表に示します。  
  
### switch ステートメントの動作  
  
|条件|動作|  
|--------|--------|  
|変換後の値は、上位変換された制御式の値と一致します。|制御は、そのラベルの次のステートメントに移ります。|  
|定数のいずれも **case** ラベル内の定数と一致しません。**default** ラベルが存在します。|制御は **default** ラベルに移動します。|  
|定数のいずれも **case** ラベル内の定数と一致しません。**default** ラベルが存在しません。|制御は `switch` ステートメントの後のステートメントに移動します。|  
  
 一致する式が見つかった場合、後続の **case** ラベルまたは **defalt** ラベルで制御が妨げられることはありません。  [break](../cpp/break-statement-cpp.md) ステートメントは、実行を停止し、`switch` ステートメントの後のステートメントに制御を移すために使用されます。  **break** ステートメントがない場合は、一致する **case** ラベルから `switch` ステートメントの最後までのすべてのステートメントは、**default** ステートメントも含めて実行されます。  次に例を示します。  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 上の例では、`capa` は `c` が大文字 `A` の場合、インクリメントします。  `capa++` の後の `break` ステートメントによって `switch` ステートメントの本体の実行が終了し、制御が `while` ループに移ります。  `break` ステートメントがない場合は、`lettera` と `nota` もインクリメントされます。  同様の目的で、`case 'a'` の `break` ステートメントを使用しています。  `c` が小文字の `a` の場合、`lettera` はインクリメントされて、`break` ステートメントで `switch` ステートメントの本体が終了します。  `c` が `a` または `A` でない場合、`default` ステートメントが実行されます。  
  
 `switch` ステートメントの内部ブロックには、到達できた \(すべての可能な実行パスで回避されなかった\) 場合に実行される初期化の定義を含めることができます。  これらの宣言を使用して導入された名前にはローカル スコープがあります。  次に例を示します。  
  
```  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 `switch` ステートメントは入れ子にすることもできます。  このような場合、**case** か **default** のラベルは、そのすぐ外側の `switch` ステートメントと関連付けられます。  
  
## Microsoft 固有の仕様 →  
 Microsoft C では、`switch` ステートメントの case 値の数を制限していません。  この数は、使用できるメモリによってのみ制限されます。  ANSI C では、1 つの `switch` ステートメント内に 257 個までの case ラベルを使用できます。  
  
 Microsoft C の既定では、Microsoft 拡張機能が有効になっています。  これらの拡張機能を無効にするには、[\/Za](../build/reference/za-ze-disable-language-extensions.md) コンパイラ オプションを使用します。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) Using Labels in the case Statement](http://msdn.microsoft.com/ja-jp/a6ff057d-1aee-42ed-a28d-ee6a565b3197)