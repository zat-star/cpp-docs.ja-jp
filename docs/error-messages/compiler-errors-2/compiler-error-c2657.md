---
title: "コンパイラ エラー C2657 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2657
dev_langs:
- C++
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
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
ms.openlocfilehash: 8a9140955ff0bd35b13ee212fa890afcfc59678c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2657"></a>コンパイラ エラー C2657
' クラス:: *' のステートメントの先頭にある (を忘れましたかの種類を指定するか)。  
  
 メンバーへのポインターの識別子を持つ行を開始しました。  
  
 このエラーは、メンバーへのポインターの宣言で型指定子がありませんによって発生ことができます。  
  
 次の例では、c2657 エラーが生成されます。  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```
