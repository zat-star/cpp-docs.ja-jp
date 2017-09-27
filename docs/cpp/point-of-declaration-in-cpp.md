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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 77f66182052cc2a031b7f1f8db8018f49b36801d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
## <a name="see-also"></a>関連項目  
 [スコープ](../cpp/scope-visual-cpp.md)
