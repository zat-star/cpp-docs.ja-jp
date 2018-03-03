---
title: "コンパイラの警告 (レベル 1) C4744 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6fa95f8477f889aa8664d2b6d99c753cb9848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4744"></a>コンパイラの警告 (レベル 1) C4744
'var' が 'file1' および 'file2' で別の種類: 'type1' および 'type2'  
  
 参照または 2 つのファイルで定義された外部変数にそれらのファイルのさまざまな種類です。  を解決するには、同じ種類の定義を作成するか、ファイルの 1 つの変数名を変更します。  
  
 /Gl ファイルはコンパイル時にだけ C4744 が生成されます。  詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。  
  
> [!NOTE]
>  C++ では、変数名は、型情報で装飾されているために、C4744 は通常 C (C++ ではなく) ファイルで発生します。  (以下) のサンプルでは、C++ としてコンパイルが、リンカー エラー lnk2019 エラーが表示されます。  
  
## <a name="example"></a>例  
 このサンプルには、最初の定義が含まれています。  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>例  
 次の例では、C4744 を生成します。  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```