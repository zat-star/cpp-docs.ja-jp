---
title: "コンパイラ エラー C2001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aedba438451089aa2d71e06da7ce189ab97d4190
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2001"></a>コンパイラ エラー C2001
定数の改行  
  
 文字列定数は、以下を実行する場合を除き、行目では継続できません。  
  
-   円記号で最初の行を終了します。  
  
-   二重引用符で最初の行の文字列を閉じて、もう 1 つの二重引用符で次の行に文字列を開きます。  
  
 \N で最初の行を終了することは、十分ではありません。  
  
## <a name="example"></a>例  
 次の例では、C2001 が生成されます。  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## <a name="example"></a>例  
 文字列定数には、行連結文字の後に次の行の先頭にスペースが含まれています。 上記の例は、のいずれもは、文字列定数に改行文字を埋め込みません。 次に示すように、改行文字を埋め込むことができます。  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```
