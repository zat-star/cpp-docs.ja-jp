---
title: "C++ では宣言の位置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 64c1fa1d6d8feb4b869957101bb4b37f125d0f8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="point-of-declaration-in-c"></a>C++ での宣言の位置
名前は宣言子の直後、ただし初期化子 (省略可能) よりも前の位置で宣言されるものと見なされます (宣言子の詳細については、次を参照してください[宣言と定義](declarations-and-definitions-cpp.md)。)。  
  
 次の例について考えます。  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 宣言の位置があった場合*後*、初期化には、次に、ローカル`dVar`7.0 では、グローバル変数の値に初期化が`dVar`です。 しかし、実際にはそうでないため、`dVar` は未定義の値に初期化されます。  
  
## <a name="see-also"></a>参照  
 [スコープ](../cpp/scope-visual-cpp.md)