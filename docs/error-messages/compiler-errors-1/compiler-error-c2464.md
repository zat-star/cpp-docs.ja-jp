---
title: "コンパイラ エラー C2464 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7e2600608ae490363d9042ad72ad91bf7cfe32d2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2464"></a>コンパイラ エラー C2464
'identifier': 参照の割り当てに 'new' を使用することはできません  
  
 参照識別子がで割り当てられた、`new`演算子。 参照ではないメモリ オブジェクトのため`new`にポインターを返すことはできません。 参照を宣言するのにには、標準の変数宣言の構文を使用します。  
  
 次の例では、C2464 が生成されます。  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```
