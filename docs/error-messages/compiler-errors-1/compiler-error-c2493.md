---
title: "コンパイラ エラー C2493 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2493
dev_langs: C++
helpviewer_keywords: C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5d44a9bff73eb32d0ff1f5dfd89f0238db29dc1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2493"></a>コンパイラ エラー C2493
_ _based の無効な形式  
  
 A`__based`式は、ポインターに基づく必要があります。  
  
 次の例では、C2493 が生成されます。  
  
```  
// C2493.cpp  
// compile with: /c  
char mybase;  
int __based(mybase) ptr;   // C2493  
  
// OK  
char * mybase;  
int __based(mybase) * ptr;  
```