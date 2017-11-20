---
title: "コンパイラ エラー C2563 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2563
dev_langs: C++
helpviewer_keywords: C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8fe3ca54a90b91151288076fd657752e3195e318
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2563"></a>コンパイラ エラー C2563
正式なパラメーター リストが一致しません  
  
 関数 (または関数へのポインター) の仮パラメーター リストには、別の関数 (またはメンバー関数へのポインター) のものと一致しません。 その結果、または関数ポインターの代入を行うことはできません。  
  
 次の例では、C2563 が生成されます。  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```