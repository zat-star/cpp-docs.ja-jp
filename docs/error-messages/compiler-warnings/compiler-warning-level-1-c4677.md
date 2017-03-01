---
title: "コンパイラの警告 (レベル 1) C4677 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: 12
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
ms.openlocfilehash: 477b5def0b956dc06aa107003f93adea6ca1437c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4677"></a>コンパイラの警告 (レベル 1) C4677
'function': 公開されたメンバーのシグネチャには、アセンブリのプライベート型 'private_type' が含まれています。  
  
 アセンブリの外部のパブリック アクセシビリティを持つ型では、アセンブリの外部のプライベート アクセス権を持つ型を使用します。 パブリック アセンブリの型を参照するコンポーネントは、型のメンバーまたはアセンブリのプライベート型を参照するメンバーを使用できません。  
  
## <a name="example"></a>例  
 次の例では、C4677 を生成します。  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```
