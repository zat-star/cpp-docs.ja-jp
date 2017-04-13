---
title: "コンパイラ エラー C2157 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2157
dev_langs:
- C++
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 152b55fb228d73b03df615fd336e40e984521432
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2157"></a>コンパイラ エラー C2157
'function' : プラグマ リスト内で参照される前に宣言されていなければなりません  
  
 関数の一覧で参照される前に、関数名が宣言されていない、 [alloc_text](../../preprocessor/alloc-text.md)プラグマ。  
  
 次の例では C2157 が生成されます。  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```
