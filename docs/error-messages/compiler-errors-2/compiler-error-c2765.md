---
title: "コンパイラ エラー C2765 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2765
dev_langs:
- C++
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec01af8ee743ff9eeccce11ed42c047149457ce6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2765"></a>コンパイラ エラー C2765
'function': 関数テンプレートの明示的な特殊化は、既定引数を持つことはできません  
  
 既定の引数は関数テンプレートの明示的な特殊化では許可されません。 詳細については、次を参照してください。[関数テンプレートの明示的な特殊化](../../cpp/explicit-specialization-of-function-templates.md)です。  
  
 次の例では、C2765 が生成されます。  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```