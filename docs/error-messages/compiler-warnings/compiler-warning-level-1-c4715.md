---
title: "コンパイラの警告 (レベル 1) C4715 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4715
dev_langs: C++
helpviewer_keywords: C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b060585cd3ba6b51c9c91d42e5f3fecaf74ae1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4715"></a>コンパイラの警告 (レベル 1) C4715
'function': 値を返さないコントロール パスのすべて  
  
 指定された関数は、値を返すない可能性があることができます。  
  
## <a name="example"></a>例  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 この警告を回避するのには、すべてのパスは、関数に戻り値を割り当てるようにコードを変更します。  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 コードが、次の例のようにを返すことはありません関数への呼び出しを含めることがあります。  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 このコードは、コンパイラはわからないためをも、警告を生成`fatal`を返しません。 このコードがエラー メッセージを生成するようにするのには、宣言`fatal`を使用して[__declspec(noreturn)](../../cpp/noreturn.md)です。