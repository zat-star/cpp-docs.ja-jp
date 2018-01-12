---
title: "コンパイラ エラー C2004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2004
dev_langs: C++
helpviewer_keywords: C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 754f0099ac0b69eebbc98a34f7f6206591c75925
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 考えられる解決方法:  
  
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