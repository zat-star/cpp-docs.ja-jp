---
title: "コンパイラ エラー C2015 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2015
dev_langs: C++
helpviewer_keywords: C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a04a5c113ca39dac137f2f225a8dcad9318a29bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2015"></a>コンパイラ エラー C2015
定数の文字が多すぎます  
  
 文字定数には、3 つ以上の文字が含まれています。 制限されて標準の文字定数の 1 つの文字長の文字定数の 2 つの文字です。  
  
 \T などのエスケープ シーケンスは、1 つの文字に変換されます。  
  
## <a name="example"></a>例  
 次の例では、C2015 が生成されます。  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## <a name="example"></a>例  
 C2015 は、Microsoft 拡張機能、文字定数の整数に変換を使用する場合にも発生することができます。  次の例では、C2015 が生成されます。  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```