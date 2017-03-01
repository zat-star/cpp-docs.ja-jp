---
title: "コンパイラの警告 (レベル 4) C4706 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: 6
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
ms.openlocfilehash: d4f4edcbf4a4cb147c2acb8e6cb530a4a0f9a9a9
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4706"></a>コンパイラの警告 (レベル 4) C4706
条件式の比較値は、代入の結果になっています。  
  
 条件式でのテストの値は、代入式の結果をしました。  
  
 割り当てには、テスト式を含む別の式で規則上問題なく使用できる値 (割り当ての左側にある値) があります。  
  
 次の例では、C4706 が生成されます。  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 テスト条件を囲むかっこは&2; 倍にする場合でも、警告が発生します。  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 リレーションシップをテストし、使用して、割り当てしないようにする場合、`==`演算子。 たとえば、次のようにするかどうか、b が等しいとします。  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 値の代入式の結果、テストを作成する場合をテストに割り当てが&0; 以外、または null でないことを確認します。 たとえば、次のコードでは、この警告が発生されます。  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```
