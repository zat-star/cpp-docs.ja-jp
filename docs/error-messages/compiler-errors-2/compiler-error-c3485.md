---
title: "コンパイラ エラー C3485 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cd49b93beb54776bf17a9ee2bc5c9816f0964451
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

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
