---
title: "コンパイラ エラー C2012 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2012
dev_langs:
- C++
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5de5edabdd860f89099d8f2b9aa0632e98740403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2012"></a>コンパイラ エラー C2012
'<' の後にファイル名がありません。  
  
 `#include` ディレクティブに必要なファイル名がありません。  
  
 次の例では C2012 エラーが生成されます。  
  
```  
// C2012.cpp  
#include <   // C2012 include the filename to resolve  
```  
  
 考えられる解決方法:  
  
```  
// C2012b.cpp  
// compile with: /c  
#include <stdio.h>  
```