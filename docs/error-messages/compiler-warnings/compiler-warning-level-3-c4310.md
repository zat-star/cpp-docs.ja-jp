---
title: "コンパイラの警告 (レベル 3) C4310 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4310
dev_langs: C++
helpviewer_keywords: C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e831459aaf2161d83a62cd1241673780293c02d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4310"></a>コンパイラの警告 (レベル 3) C4310
キャストには、定数値が切り捨てられました。  
  
 定数値は、小さい型にキャストされます。 コンパイラでは、データが切り捨てられます、キャストを実行します。 次の例では、C4310 が生成されます。  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```