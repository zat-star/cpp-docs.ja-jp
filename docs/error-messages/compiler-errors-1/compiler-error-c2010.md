---
title: "コンパイラ エラー C2010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2010
dev_langs:
- C++
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e7cbee2b1864789bd0ff5b0faccd843cb89e6c66
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2010"></a>コンパイラ エラー C2010
'character': マクロ仮引数リスト内に予期しません。  
  
 マクロ定義の仮パラメーター リストの中で、文字が正しくない方法で使用されています。 エラーを解決するのには文字を削除します。  
  
 次の例では、C2010 が生成されます。  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```
