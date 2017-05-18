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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0641a441d68dc411c344861af984dd6be3cff9f3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2765"></a>コンパイラ エラー C2765
'function': 関数テンプレートの明示的な特殊化は、既定の引数を持つことはできません  
  
 既定の引数は、関数テンプレートの明示的な特殊化では許可されません。 詳細については、次を参照してください。[関数テンプレートの明示的な特殊化](../../cpp/explicit-specialization-of-function-templates.md)します。  
  
 次の例では、c2765 エラーが生成されます。  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```
