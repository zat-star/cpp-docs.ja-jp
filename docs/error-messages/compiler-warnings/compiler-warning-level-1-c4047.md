---
title: "コンパイラの警告 (レベル 1) C4047 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4047
dev_langs: C++
helpviewer_keywords: C4047
ms.assetid: b75ad6fb-5c93-4434-a85f-c4083051a5de
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d42913533129fad2cbdc803e6f3d81bdea3ebd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4047"></a>コンパイラの警告 (レベル 1) C4047
'operator' : 間接参照のレベルが 'identifier1' と 'identifier2' で異なっています。  
  
 ポインターを別のポインターが指す変数 (2 レベルの間接参照) というように、変数 (1 つのレベルの間接参照) をポイントできます。  
  
## <a name="example"></a>例  
 次の例では、C4047 が生成されます。  
  
```  
// C4047.c  
// compile with: /W1  
  
int main() {  
   char **p = 0;   // two levels of indirection  
   char *q = 0;   // one level of indirection  
  
   char *p2 = 0;   // one level of indirection  
   char *q2 = 0;   // one level of indirection  
  
   p = q;   // C4047  
   p2 = q2;  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C4047 が生成されます。  
  
```  
// C4047b.c  
// compile with: /W1  
#include <stdio.h>  
  
int main() {  
   int i;  
   FILE *myFile = NULL;  
   errno_t  err = 0;  
   char file_name[256];  
   char *cs = 0;  
  
   err = fopen_s(&myFile, "C4047.txt", "r");  
   if ((err != 0) || (myFile)) {  
      printf_s("fopen_s failed!\n");  
      exit(-1);  
    }  
   i = fgets(file_name, 256, myFile);   // C4047  
   cs = fgets(file_name, 256, myFile);   // OK  
}  
```