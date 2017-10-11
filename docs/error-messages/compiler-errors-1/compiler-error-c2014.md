---
title: "コンパイラ エラー C2014 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a4c6a3cc07b28e5636e61769b6dce0760938c591
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2014"></a>コンパイラ エラー C2014
最初の空白としてプリプロセッサ コマンドを起動する必要があります。  
  
 `#`プリプロセッサ ディレクティブの記号が空白ではない行の最初の文字にする必要があります。  
  
 次の例では、C2014 が生成されます。  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 考えられる解決策:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```
