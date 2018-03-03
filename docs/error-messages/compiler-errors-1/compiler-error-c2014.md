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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5f718aee1cb7ede548719a8275ea6788b70d1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2014"></a>コンパイラ エラー C2014
最初の空白としてプリプロセッサ コマンドを起動する必要があります。  
  
 `#`プリプロセッサ ディレクティブの記号が空白ではない行の最初の文字にする必要があります。  
  
 次の例では、C2014 が生成されます。  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 考えられる解決方法:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```