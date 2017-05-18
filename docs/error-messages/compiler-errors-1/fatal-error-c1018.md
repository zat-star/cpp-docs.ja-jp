---
title: "致命的なエラー C1018 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1018
dev_langs:
- C++
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: dc31094266e886d8bee27e2e70c9a89a7fd55731
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1018"></a>致命的なエラー C1018
予期しない #elif です。  
  
 `#elif` ディレクティブが、 `#if`、 `#ifdef`、または `#ifndef` コンストラクトの外側に置かれています。 `#elif` は、これらのコンストラクトのいずれかの内側だけで使用してください。  
  
 次の例では C1018 が生成されます。  
  
```  
// C1018.cpp  
#elif      // C1018  
#endif  
  
int main() {}  
```  
  
 考えられる解決策:  
  
```  
// C1018b.cpp  
#if 1  
#elif  
#endif  
  
int main() {}  
```
