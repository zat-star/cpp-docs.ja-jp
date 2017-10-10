---
title: "コンパイラ エラー C2723 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3816640569a503c8a56c4cf37f1bf23360b30a12
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2723"></a>コンパイラ エラー C2723
'function' : 'specifier' 指定子が関数の定義で誤って指定されています  
  
 この指定子は、クラス宣言の外側にある関数定義では使用できません。 `virtual` 指定子は、クラス宣言内のメンバー関数宣言にしか指定できません。  
  
 次の例では、C2723 を生成し、その修正方法を示しています。  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```
