---
title: "コンパイラの警告 (レベル 1) C4028 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1db6458377104463d7f350e7ed5cdaa4bc25739a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4028"></a>コンパイラの警告 (レベル 1) C4028
仮パラメーター宣言とは異なる ' 数値'  
  
 正式なパラメーターの型は、宣言に対応するパラメーターとは一致しません。 元の宣言で型が使用されます。  
  
 この警告は C ソース コードに対してのみです。  
  
## <a name="example"></a>例  
 次の例では、C4028 を生成します。  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```
