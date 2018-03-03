---
title: "コンパイラ エラー C2055 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04ba07229b1beeb0fdf4362d2b382121ab7606b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2055"></a>コンパイラ エラー C2055
型リストではなく、仮パラメーター リストが必要です。  
  
 関数の定義には、仮パラメーター リストの代わりにパラメーターの型リストが含まれています。 ANSI C には、void または、省略記号でない限り、名前を指定する仮パラメーターが必要です (`...`)。  
  
 次の例では、C2055 が生成されます。  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```