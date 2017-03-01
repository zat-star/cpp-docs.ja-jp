---
title: "コンパイラ エラー C3354 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3354
dev_langs:
- C++
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 10
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: bebeb383e77e4da16a24867731535d9fa36d6c5e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3354"></a>コンパイラ エラー C3354
'function': デリゲートを作成するための関数に、戻り値の型 'type' を指定することはできません。  
  
 次の種類は、の戻り値の型としては無効な`delegate`:  
  
-   関数へのポインター  
  
-   メンバーへのポインター  
  
-   メンバー関数へのポインター  
  
-   関数への参照  
  
-   メンバー関数への参照  
  
 次の例では C3354 が生成されます。  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  

