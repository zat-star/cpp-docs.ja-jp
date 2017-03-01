---
title: "コンパイラの警告 (レベル 3) C4738 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4c05725e155f4b3f5de4a17f66ae15d3b2885a1e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4738"></a>コンパイラの警告 (レベル 3) C4738
メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります  
  
 C4738 では、キャスト、代入の結果に渡された引数、またはその他の操作の丸めが必要になること、または、操作はレジスタが不足しており、メモリ (書き込み) を使用するために必要な警告が表示されます。 これは、結果、パフォーマンス失われることができます。  
  
 この警告を解決し、丸め処理を避けるため、使用してコンパイル[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)不正使用を`double`の代わりに s `float`s です。  
  
 この警告を解決し、レジスタの不足を回避、計算の順序を変更しの使用を変更インライン展開  
  
 既定では、この警告はオフに設定されています。 詳細については、次を参照してください。[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)します。  
  
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
