---
title: "コンパイラの警告 C4956 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 782735be55c043482679740afa9571ba7b29dfc4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4956"></a>コンパイラの警告 C4956
'type' : この型は検証可能ではありません  
  
 この警告が生成されたときに[/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md)が指定されているコードにはで検証可能ではない型が含まれています。  
  
 詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
 この警告がエラーとして発行され、無効にする、[警告](../../preprocessor/warning.md)プラグマ、または[/wd](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。  
  
 次の例では C4956 が生成されます。  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```
