---
title: "コンパイラの警告 (レベル 1) C4677 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4677
dev_langs: C++
helpviewer_keywords: C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a597fa2373de1a2650a86c0b8d4f51bad35d9818
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4677"></a>コンパイラの警告 (レベル 1) C4677
'function': 公開されたメンバーのシグネチャには、アセンブリ プライベート型 'private_type' が含まれています。  
  
 アセンブリの外側のパブリック アクセシビリティを持つ型では、アセンブリの外側のプライベート アクセス権を持つ型を使用します。 パブリック アセンブリの型を参照するコンポーネントは、型のメンバーまたはアセンブリ プライベート型を参照するメンバーを使用できません。  
  
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