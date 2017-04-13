---
title: "コンパイラ エラー C3485 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 40c35bdb5be6fad108e612208b53773ceb4105e9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3485"></a>コンパイラ エラー C3485
ラムダ定義に cv 修飾子は使用できません  
  
 ラムダ式の定義の一部として `const` 修飾子または `volatile` 修飾子を使用することはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式の定義から `const` 修飾子または `volatile` 修飾子を削除します。  
  
## <a name="example"></a>例  
 次の例では、ラムダ式の定義の一部として `const` 修飾子を使用しているため、C3485 が生成されます。  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
