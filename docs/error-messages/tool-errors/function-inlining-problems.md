---
title: "関数インライン展開の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7f29cb8fb61dfc9f50cc5677e0d4f18f83627cdb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="function-inlining-problems"></a>関数インライン展開の問題
関数のインライン化を使用している場合は、次の操作を行う必要があります。  
  
-   含めるヘッダー ファイルで実装されたインライン関数があります。  
  
-   インライン展開ヘッダー ファイルで点灯します。  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 この場合、次のようになります。  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 使用している場合、`#pragma inline_depth`コンパイラ ディレクティブのことを確認する値が 2 以上設定されています。 オフになり、値が&0; のインライン展開されます。 またを使用していることを確認してください、 **/Ob1**または**/Ob2**コンパイラ オプション。  
  
 異なるモジュールでのインラインとインライン以外のコンパイル オプションが混在しても問題が発生場合があります。 関数のインライン化がオンで、C++ のライブラリが作成されたかどうか ([/Ob1](../../build/reference/ob-inline-function-expansion.md)または[/Ob2](../../build/reference/ob-inline-function-expansion.md)) が、対応するヘッダー ファイルが、機能の説明 (オプションではない) を無効になっていると、エラー LNK2001 が表示されます。 関数はヘッダー ファイルからはインライン関数では、コードにならないが、参照を解決するのにはアドレスがありませんが、ライブラリ ファイルに属していないためです。  
  
 同様に、関数のインライン化を使用するプロジェクトをまだ関数を定義 .cpp ファイルではなく、ヘッダー ファイルは lnk2019 します。 ヘッダー ファイルが含まれるすべての場所で、適切なと見なされますが、関数は、インライン関数では、.cpp ファイルは、コンパイラを通過するときそのため、リンカーでは、他のモジュールで使用する場合の未解決の外部参照として、関数が表示されます。  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 それから  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 それから  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リンカ ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
