---
title: "コンパイラ エラー C3299 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3299
dev_langs:
- C++
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
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
ms.openlocfilehash: f18264be0d3fcc6ff0e5287b0a1592ddfca95fba
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3299"></a>コンパイラ エラー C3299
'member_function': 制約を指定できません。それらは基本メソッドから継承されています  
  
 汎用的なメンバー関数をオーバーライドする場合は、制約句を指定できません (制約を繰り返すことは、制約が継承されないことを意味します)。  
  
 オーバーライドするジェネリック関数の制約句が継承されます。  
  
 詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C3299 が生成されます。  
  
```  
// C3299.cpp  
// compile with: /clr /c  
public ref struct R {  
   generic<class T>   
   where T : R  
   virtual void f();  
};  
  
public ref struct S : R {  
   generic<class T>   
   where T : R   // C3299  
   virtual void f() override;  
};  
```
