---
title: "コンパイラの警告 (レベル 3) C4738 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4738
dev_langs: C++
helpviewer_keywords: C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30f56b7963d8c6e98d4564ec90adee6bd3d29f9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4738"></a>コンパイラの警告 (レベル 3) C4738
メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります  
  
 C4738 は、キャスト、代入式の結果に渡された引数、またはその他の操作の丸めが必要になることや、操作がレジスタ不足しています (に書き込むときに) メモリを使用するために必要なことを警告します。 その場合、パフォーマンスが低下します。  
  
 この警告を解決し、丸め処理を避けるため、コンパイル時に[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)使用または`double`の代わりに`float`です。  
  
 この警告を解決し、レジスタの不足を回避する、計算の順序を変更しの使用を変更インライン展開  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4738 が生成されます。  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```