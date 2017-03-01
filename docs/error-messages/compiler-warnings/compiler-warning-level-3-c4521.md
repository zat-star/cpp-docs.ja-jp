---
title: "コンパイラの警告 (レベル 3) C4521 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4521
dev_langs:
- C++
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
caps.latest.revision: 10
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
ms.openlocfilehash: d05f0a0dc7b671a355d9789583603cbedb1e9ffc
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4521"></a>コンパイラの警告 (レベル 3) C4521
'class': 指定された複数のコピー コンス トラクター  
  
 クラスには、単一の型の複数のコピー コンス トラクターがあります。 この警告は、参照用です。コンス トラクターは、プログラムで呼び出し可能です。  
  
 使用して、[警告](../../preprocessor/warning.md)プラグマをこの警告を抑制します。  
  
## <a name="example"></a>例  
 次の例では、C4521 を生成します。  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```
