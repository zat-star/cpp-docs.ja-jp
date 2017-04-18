---
title: "コンパイラ エラー C3298 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3298
dev_langs:
- C++
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: 3
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
ms.openlocfilehash: f425cec7ff93bbf98f63b0ebd8e197d7b9b153c2
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3298"></a>コンパイラ エラー C3298
'constraint_1': 'constraint_2' を制約として使用できません。'constraint_2' は ref 制約を含んでおり、'constraint_1' は値の制約を含んでいるためです  
  
 制約に相互に排他的な特性を指定することはできません。 たとえば、ジェネリック型パラメーターを、値型と参照型の両方に制限することはできません。  
  
 詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C3298 が生成されます。  
  
```  
// C3298.cpp  
// compile with: /clr /c   
generic<class T, class U>  
where T : ref class  
where U : T, value class   // C3298  
public ref struct R {};  
```
