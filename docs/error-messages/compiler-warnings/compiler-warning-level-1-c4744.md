---
title: "コンパイラの警告 (レベル 1) C4744 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4744"
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' は 'file1' and 'file2' 内で異なる型を含んでいます: 'type1' および 'type2'  
  
 2 つのファイルで参照または定義された外部変数の型が、それぞれのファイルで異なっています。解決するには、型定義を同じにするか、一方のファイルで変数名を変更します。  
  
 C4744 は、ファイルが \/GL を指定してコンパイルされている場合のみ出力されます。詳細については、「[\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。  
  
> [!NOTE]
>  C\+\+ では変数名が型情報で装飾されているので、C4744 は、通常 \(C\+\+ ではなく\) C ファイルで発生します。次の例を C\+\+ でコンパイルすると、リンカー エラー LNK2019 が発生します。  
  
## 使用例  
 次の例には、1 つ目の定義が含まれています。  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## 使用例  
 次の例では C4744 エラーが生成されます。  
  
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