---
title: "A.20   Binding of barrier Directives | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.20   Binding of barrier Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`parallel` の最も近いのディレクティブにバインドする  **バリア**  のディレクティブのディレクティブの結合規則を呼び出します。  ディレクティブのバインディングの詳細についてはページの 32 [セクション 2.8](../../parallel/openmp/2-8-directive-binding.md) を参照してください。  
  
 次の例ではMain から *sub2* の呼び出しは  **バリア**  が *sub2* の並列領域に *sub3*\(に対応\) にバインドするためです。  Main から *sub1* の呼び出しは  **バリア**  はサブルーチン *sub2* の並列領域にバインドされるため準拠しています。  Main から *sub3* の呼び出しは  **バリア**  は並列領域にバインドせずに無視するための対応する。  または  **バリア**  は外側の並列領域のスレッドと *sub1* で作成されたすべてのスレッドのチームだけを同期しないことに注意してください。  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```