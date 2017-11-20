---
title: "() はコードを生成せずに関数名を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 79f360bffa4938098b4b37dd2260596c70669d12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="using-function-name-without--produces-no-code"></a>"()" のない関数名とコードの生成
かっこを使用せず、プログラムで宣言された関数名を使用する場合、コンパイラがコードを生成しません。 これは、コンパイラは関数のアドレスを計算するために、関数がパラメーターを受け取るかどうかに関係なく発生します。ただし、関数呼び出し演算子 (「)」が存在しないため、呼び出しは行われません。 この結果は、次のようには。  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 Visual c で 4 の警告レベルを使用しても診断出力が生成されます。 警告メッセージは生成されません。コードは生成されません。  
  
 次のサンプル コードは、(警告) を使用してコンパイル、およびエラーを発生させずに正しくリンク コードに関連が生成されない`funcn( )`です。 これが正しく機能するには、関数呼び出し演算子 (「)」を追加します。  
  
```  
#include <stdio.h>  
void funcn();  
  
int main() {  
   funcn;      /* missing function call operator;   
                  call will fail.  Use funcn() */  
   }  
  
void funcn() {  
   printf("\nHello World\n");  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [コードの最適化](../../build/reference/optimizing-your-code.md)