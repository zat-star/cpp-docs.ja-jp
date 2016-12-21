---
title: "A.25   Examples of the copyprivate Data Attribute Clause | Microsoft Docs"
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
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.25   Examples of the copyprivate Data Attribute Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**例 1:** が `copyprivate` の句 \(ページの 32[セクション 2.7.2.8](../Topic/2.7.2.8%20copyprivate.md)\) 他のスレッドのプライベート変数のすべてのインスタンスにシングル スレッドによって直接取得した値をブロードキャストするために使用できます。  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 定期的な *init が*  並列領域から呼び出された場合動作はディレクティブがあるかどうかに影響されません。  *get\_values* ルーチンの呼び出しが 1 台のスレッドによって実行された後スレッドは *a**b**x* によって指定されるプライベート オブジェクトまでの構造から離れずしすべてのスレッドの *y は* 読み取られた値で定義されるようになっています。  
  
 前の例ではよる読み取り  **例 2:** は特定のスレッドによってはマスター スレッドを実行する必要があることを前提としています。  この場合`copyprivate` の句がブロードキャストを直接することはできません。一時共有オブジェクトへのアクセスを提供するために使用できます。  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **例 3:**並列領域内に必要なロック オブジェクトの数が簡単に入る前に決定できないことを前提としています。  `copyprivate` の句は並列領域内に割り当てられた共有ロック オブジェクトへのアクセスを提供するために使用できます。  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```