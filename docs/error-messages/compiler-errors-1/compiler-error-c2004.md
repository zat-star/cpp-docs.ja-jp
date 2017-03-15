---
title: "コンパイラ エラー C2004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 71754f86c18bbff5a10c58b6eb9effae27505974
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2004"></a>コンパイラ エラー C2004
'defined (id)' の形式にしてください。  
  
 プリプロセッサのキーワードに続く識別子は、かっこで囲む必要があります。  
  
 このエラーは、Visual Studio .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。プリプロセッサ ディレクティブにかっこがありません。 プリプロセッサ ディレクティブに閉じかっこがない場合は、コンパイラによってエラーが生成されます。  
  
## <a name="example"></a>例  
 次の例では C2004 が生成されます。  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>例  
 考えられる解決策:  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```
