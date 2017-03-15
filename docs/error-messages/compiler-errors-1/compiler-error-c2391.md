---
title: "コンパイラ エラー C2391 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2391
dev_langs:
- C++
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: 8
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
ms.openlocfilehash: e1f75e50ee409eb0ebd02107f07e38cb245406d4
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2391"></a>コンパイラ エラー C2391
'identifier': 'friend' は型定義の中に使用できません  
  
 `friend`宣言には、完全なクラス宣言が含まれています。 A`friend`宣言を指定できますが、メンバー関数、または、詳細な型指定子を完全なクラス宣言ではありません。  
  
 次の例では C2326 が生成されます。  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```
