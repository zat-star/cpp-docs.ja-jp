---
title: "コンパイラ エラー C2659 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2659
dev_langs:
- C++
helpviewer_keywords:
- C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c69af55d7a5fd61508505bd96091ffcbed41c5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2659"></a>コンパイラ エラー C2659
'演算子' : 関数がオペランドの左辺にあります  
  
 関数が、指定された演算子の左側にあります。 このエラーの最も一般的な原因は、開発者が変数のつもりで提供した演算子の左側にある ID を、コンパイラが関数として解析したことです。 について詳細については、Wikipedia の記事[一番面倒な解析](http://en.wikipedia.org/wiki/Most_vexing_parse)です。 この例は、混乱しやすい関数宣言と変数定義を示しています。  
  
```  
// C2659a.cpp  
// Compile using: cl /W4 /EHsc C2659a.cpp  
#include <string>  
using namespace std;  
  
int main()   
{  
   string string1(); // string1 is a function returning string  
   string string2{}; // string2 is a string initialized to empty   
  
   string1 = "String 1"; // C2659  
   string2 = "String 2";  
}  
```  
  
 この問題を解決するには、ID の宣言を変更して、その宣言が関数宣言として解析されないようにします。  
  
 C2659 エラーは、指定した演算子の左側にある関数の型を式で使用できない場合にも発生する可能性があります。 この例では、コードが関数ポインターを関数に割り当てるときに C2659 が生成されます。  
  
```  
// C2659b.cpp  
// Compile using: cl /W4 /EHsc C2659b.cpp  
int func0(void) { return 42; }  
int (*func1)(void);  
  
int main()  
{  
   func1 = func0;  
   func0 = func1; // C2659  
}  
```