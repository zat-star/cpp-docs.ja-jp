---
title: "コンパイラ エラー C3182 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 3dfd76788c55e74625172dedf2ceb5b8bdfaa061
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3182"></a>コンパイラ エラー C3182
'class': メンバーを使用して宣言またはアクセスの宣言は、マネージ コードまたは WinRTtype 内で無効  
  
 A[を使用して](../../cpp/using-declaration.md)宣言がマネージ クラスのすべてのフォーム内で有効ではありません。  
  
 次の例では C3182 が生成され、その修正方法が示されています。  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  

