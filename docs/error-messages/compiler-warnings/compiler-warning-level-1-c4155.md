---
title: "コンパイラの警告 (レベル 1) C4155 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4155
dev_langs: C++
helpviewer_keywords: C4155
ms.assetid: ba233353-09e3-4195-8127-13a27ddd8d70
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34f0654042e063f757f9ae70f2b94caee455dae5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4155"></a>コンパイラの警告 (レベル 1) C4155
'delete' の配列でない形式を使った配列の削除は、定義されていません。  
  
 **delete** の配列形式は、配列を削除するために使用する必要があります。 この警告は、ANSI 互換 (/Za) の環境でのみ発生します。  
  
## <a name="example"></a>例  
 次の例では C4155 が生成されます。  
  
```  
// C4155.cpp  
// compile with: /Za /W1  
#include <stdio.h>  
  
int main(void)  
{  
    int (*array)[ 10 ] = new int[ 5 ] [ 10 ];  
    array[0][0] = 8;  
  
    printf_s("%d\n", array[0][0]);  
  
   delete array;   // C4155  
    // try the following line instead  
    // delete [] array;   // C4155  
}  
```