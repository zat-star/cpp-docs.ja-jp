---
title: "コンパイラ エラー C2429 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18fd64199ff043b660bb205199b982ee2843cdcd
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2429"></a>コンパイラ エラー C2429
'*言語機能*'コンパイラ フラグが必要'*コンパイラ オプション*'  
  
言語機能には、サポートについては、特定のコンパイラ オプションが必要です。  
  
エラー C2429: 言語機能 '入れ子になった名前空間の定義' コンパイラ フラグが必要 '/std:c:operator++ 最新 ' を定義しようとする場合に生成される、*複合名前空間*、1 つまたは複数のスコープの入れ子になった名前空間名を含む名前空間、Visual Studio 2015 Update 3 で起動します。 複合の名前空間の定義が、c++ 17 の前に C++ では許可されていません。 コンパイラは、複合名前空間の定義をサポートしているときに、 [/std:c + + 最新](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
