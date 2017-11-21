---
title: "コンパイラの警告 (レベル 1) C4551 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4551
dev_langs: C++
helpviewer_keywords: C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fd90560d72bbc475525a81b630823c51215d8f01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4551"></a>コンパイラの警告 (レベル 1) C4551
関数呼び出しに引数リストがありません。  
  
 関数呼び出しは、関数にパラメーターがない場合でも、関数名の後に始めと終わりかっこを含める必要があります。  
  
 次の例では、C4551 が生成されます。  
  
```  
// C4551.cpp  
// compile with: /W1  
void function1() {  
}  
  
int main() {  
   function1;   // C4551  
   function1();   // OK  
}  
```