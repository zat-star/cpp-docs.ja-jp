---
title: "コンパイラの警告 (レベル 1) C4326 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 7
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
ms.openlocfilehash: 08919a46a9f48ef42849351f19099c339b15ed90
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4326"></a>コンパイラの警告 (レベル 1) C4326
'function' の戻り値の型が 'type2' ではなく ' type1' にする必要があります。  
  
 関数が以外の型を返した***type1***します。 たとえばを使用して[/Za](../../build/reference/za-ze-disable-language-extensions.md)、main は返されませんでした、`int`です。  
  
 次の例では、C4326 が生成されます。  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```
