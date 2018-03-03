---
title: "コンパイラ エラー C2006 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4db382ab78cbd230813fada89f9c04244035932f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2006"></a>コンパイラ エラー C2006
'directive' 'token' が見つかりません、ファイル名を想定します。  
  
 などのディレクティブ[#include](../../preprocessor/hash-include-directive-c-cpp.md)または[#import](../../preprocessor/hash-import-directive-cpp.md)ファイル名を必要とします。 エラーを解決するには、確認*トークン*は有効なファイル名。 また、ファイル名を二重引用符や山かっこで配置します。  
  
 次の例では、C2006 が生成されます。  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 考えられる解決方法:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```