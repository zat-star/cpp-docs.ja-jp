---
title: "コンパイラ エラー C2106 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2106
dev_langs: C++
helpviewer_keywords: C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b4c09d450bdb010b8436c841cd57b7c2978567c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2106"></a>コンパイラ エラー C2106
'operator': 左のオペランドが左辺値にする必要があります  
  
 演算子の左側のオペランドとして左辺値が必要です。  
  
 次の例では、C2106 が生成されます。  
  
```  
// C2106.cpp  
int main() {  
   int a;  
   1 = a;   // C2106  
   a = 1;   // OK  
}  
```