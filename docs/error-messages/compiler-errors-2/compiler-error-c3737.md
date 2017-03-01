---
title: "コンパイラ エラー C3737 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3737
dev_langs:
- C++
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: 9
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
ms.openlocfilehash: fba4f70add3b92f2bbde8d5f1ad742a35f7d5bb6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3737"></a>コンパイラ エラー C3737
'delegate': デリゲートは、明示的な呼び出し規約をない可能性があります  
  
 指定することはできません、[呼び出し規約](../../cpp/calling-conventions.md)の`delegate`です。  
  
## <a name="example"></a>例  
次の例では、c3737 エラーが生成されます。  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  

