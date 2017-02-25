---
title: "omp_get_wtime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_wtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_wtime OpenMP function"
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# omp_get_wtime
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

時刻の秒の部分が経過する位置を返します。  
  
## 構文  
  
```  
double omp_get_wtime( );  
```  
  
## 戻り値  
 時刻の秒の部分が経過することも一貫性を返します。  
  
## 解説  
 この時点では以降の比較を使用するプログラムの実行中に一貫性です。  
  
 詳細については、「[3.3.1 omp\_get\_wtime Function](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
  **開始 \= 594255.3671159324**   
**末尾 \= 594256.3664474116**   
**diff \= 0.9993314791936427**  
**wtick \= 2.793651148400146e\-007**  
**1\/wtick \= 3579545**   
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)