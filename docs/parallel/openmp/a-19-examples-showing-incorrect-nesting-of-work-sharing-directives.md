---
title: "A.19   Examples Showing Incorrect Nesting of Work-sharing Directives | Microsoft Docs"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.19   Examples Showing Incorrect Nesting of Work-sharing Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このセクションの例ではディレクティブの入れ子の規則について説明します。  ディレクティブの入れ子の詳細についてはページの 33 [セクション 2.9](../../parallel/openmp/2-9-directive-nesting.md) を参照してください。  
  
 次の例では `for` の内側と外側のディレクティブが入れ子になっていて`parallel` のディレクティブにバインドするため非準拠です :  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 前の例の次に動的に入れ子形式は非準拠です :  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 次の例では `for` と `single` のディレクティブが入れ子になっている同じ並列領域にバインドするため非準拠です :  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 次の例では `for` 内の `barrier` のディレクティブがデッドロックが発生する可能性があるため非準拠です :  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 次の例では `barrier` が 1 台のスレッドは一度にクリティカル セクションに入ることができるとは限らないためデッドロックが発生するため非準拠です :  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 次の例ではが 1 `barrier` 一つのスレッドだけ `single` のセクションを実行することによりデッドロックが発生するため非準拠です :  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```