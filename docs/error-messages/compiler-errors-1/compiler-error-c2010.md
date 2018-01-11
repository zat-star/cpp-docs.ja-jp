---
title: "コンパイラ エラー C2010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2010
dev_langs: C++
helpviewer_keywords: C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f06e02e3e566c8b01edd24d159b42c452113775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2010"></a>コンパイラ エラー C2010
'character': マクロの仮パラメーター リストに予期しません。  
  
 マクロ定義の仮パラメーター リストの中で、文字が正しくない方法で使用されています。 エラーを解決するのには、文字を削除します。  
  
 次の例では、C2010 が生成されます。  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```