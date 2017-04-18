---
title: "コンパイラ エラー C2283 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2283
dev_langs:
- C++
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
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
ms.openlocfilehash: 987c6c4602c3f8c9252b1c2c7ce54aea611bf218
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2283"></a>コンパイラ エラー C2283
'identifier' : 名前指定されていない struct が、純粋関数または抽象オーバーライド関数として指定されています  
  
 名前が指定されていないクラスまたは構造体のメンバー関数が、純粋指定子で宣言されていますが、これは許可されません。  
  
 次の例では C2283 が生成されます。  
  
```  
// C2283.cpp  
// compile with: /c  
struct {  
   virtual void func() = 0;   // C2283  
};  
struct T {  
   virtual void func() = 0;   // OK  
};  
```
