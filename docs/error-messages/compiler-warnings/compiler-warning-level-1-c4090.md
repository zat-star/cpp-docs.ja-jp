---
title: "コンパイラの警告 (レベル 1) C4090 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4090
dev_langs: C++
helpviewer_keywords: C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b508e27d72454568e26d2f1d173b05c8a65c250
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4090"></a>コンパイラの警告 (レベル 1) C4090
'operation': 異なる 'modifier' 修飾子  
  
 操作で使用される変数は、コンパイラによって検出せず変更中であるため、指定された修飾子を伴って定義されます。 式は、変更せずにコンパイルされます。  
  
 ポインターの場合に、この警告が発生することが、 **const**または`volatile`項目が指すとして宣言されていないポインターに割り当てられている**const**または`volatile`です。  
  
 この警告は、C プログラムに対して実行されます。 C++ プログラムでは、コンパイラ エラーが発生: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md)です。  
  
 次の例では、C4090 が生成されます。  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```