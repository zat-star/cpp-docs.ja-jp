---
title: "switch ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
dev_langs: C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e668756e8cabafbdef522d6754487efe452f96de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="switch-statement-c"></a>switch ステートメント (C++)
整数式の値に応じてコードの複数のセクション間を切り替えます。  
  
## <a name="syntax"></a>構文  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>コメント  
 *式*整数型またはクラス型が整数型への明確な変換の必要があります。 」の説明に従って、整数の上位変換が実行される[標準変換](standard-conversions.md)です。  
  
 `switch`ステートメント本体は、一連の**ケース**ラベルと省略可能な**既定**ラベル。 2 つ定数式の**ケース**ステートメントが同じ値に評価されることができません。 **既定**ラベルは 1 回だけ出現できます。 ラベル付きステートメントは構文上の要件ではありませんが、ラベル付きステートメントがないと、`switch` ステートメントを使用する意味がありません。   default ステートメントを最後に記述する必要はありません。switch ステートメントの本体内の任意の場所で使用できます。 case ラベルまたは default ラベルは、switch ステートメント内でのみ使用できます。  
  
 *定数式*各**ケース**ラベルの型に変換*式*と比較*式*の等しいかどうか。 コントロールがあるステートメントに移ります**ケース***定数式*の値と一致する*式*です。 結果の動作を次の表に示します。  
  
### <a name="switch-statement-behavior"></a>switch ステートメントの動作  
  
|条件|アクション|  
|---------------|------------|  
|変換後の値は、上位変換された制御式の値と一致します。|制御は、そのラベルの次のステートメントに移ります。|  
|定数の中に内の定数が一致するもの、**ケース**; ラベル、**既定**ラベルが存在します。|制御が移ります、**既定**ラベル。|  
|定数の中に内の定数が一致するもの、**ケース**ラベルです。**既定**ラベルが存在しません。|制御は `switch` ステートメントの後のステートメントに移動します。|  
  
 コントロールがそれ以降によって妨げられるいない一致する式が見つかった場合、**ケース**または**既定**ラベル。 [Break](../cpp/break-statement-cpp.md)ステートメントを使用して実行を停止し、後のステートメントに制御を移す、`switch`ステートメントです。 なし、 **break**ステートメントでは、すべてのステートメントから、一致する**ケース**の末尾にラベル、`switch`など、**既定**を実行します。 例:  
  
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
  
 上の例では、`capa` は `c` が大文字 `A` の場合、インクリメントします。 `break` の後の `capa++` ステートメントによって `switch` ステートメントの本体の実行が終了し、制御が `while` ループに移ります。 なし、`break`ステートメントでは、実行は「フォール スルーする」、[次へ] のラベル付きステートメントにできるように`lettera`と`nota`もインクリメントされます。 同様の目的で、`break` の `case 'a'` ステートメントを使用しています。 `c` が小文字の `a` の場合、`lettera` はインクリメントされて、`break` ステートメントで `switch` ステートメントの本体が終了します。 `c` が `a` または `A` でない場合、`default` ステートメントが実行されます。  

 **2017 およびそれ以降の visual Studio:** (で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md))、`[[fallthrough]]`属性は、c++ 17 規格で指定します。 使用できます、`switch`ステートメント (または、コードを読むすべてのユーザーを) コンパイラにヒントとしてそのフォール スルー動作が対象としています。 Visual C コンパイラ現在は警告 fallthrough が動作のため、この属性はコンパイラの動作の効果を持ちません。 ラベル付きステートメント内で空のステートメントに、属性が適用されることに注意してください。つまり、セミコロンは必要があります。

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): switch ステートメント可能性がありますを紹介し、その範囲は、switch ステートメントのブロックに制限されます、変数を初期化します。

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 `switch` ステートメントの内部ブロックには、到達できた (すべての可能な実行パスで回避されなかった) 場合に実行される初期化の定義を含めることができます。 これらの宣言を使用して導入された名前にはローカル スコープがあります。 例:  
  
```cpp  
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
  
 `switch` ステートメントは入れ子にすることもできます。 このような場合、**ケース**または**既定**ラベルが最も近いに関連付ける`switch`そのすぐ外側のステートメント。  

 
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Microsoft C では、`switch` ステートメントの case 値の数を制限していません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、1 つの `switch` ステートメント内に 257 個までの case ラベルを使用できます。  
  
 Microsoft C の既定では、Microsoft 拡張機能が有効になっています。 使用して、 [/Za](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションをこれらの拡張機能を無効にします。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 