---
title: "コンパイラの警告 (レベル 1) C4288 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a10a7573df5986ed20475b34208a1e0f301d9bb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4288"></a>コンパイラの警告 (レベル 1) C4288
使用される標準の拡張機能: 'var': for ループで宣言したループ コントロール変数が for ループのスコープです外部で使用。外側のスコープ内の宣言と競合します。  
  
 コンパイルするときに[/Ze](../../build/reference/za-ze-disable-language-extensions.md)と**/Zc:forscope-**で宣言された変数、**の**ループが後に使用された、[の](../../cpp/for-statement-cpp.md)-ループにスコープします。 C++ 言語に対する Microsoft 拡張機能により、この変数のスコープ内に存続して、C4288 は、変数の最初の宣言を使用しないことを通知します。  
  
 参照してください[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)については、Microsoft の拡張機能を指定する方法について**の**/ze オプションでループします。  
  
 次の例では、C4288 が生成されます。  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```