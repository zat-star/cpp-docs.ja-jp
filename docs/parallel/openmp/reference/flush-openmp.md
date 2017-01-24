---
title: "flush (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Flush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flush OpenMP directive"
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# flush (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

すべてのスレッドにすべての共有オブジェクトのメモリ内の同じビューを持つことを指定します。  
  
## 構文  
  
```  
#pragma omp flush [(var)]  
```  
  
## 解説  
 指定項目  
  
 `var` \(省略可能\)  
 オブジェクトを表す変数のリスト \(コンマ区切り\) を同期する場合。  `var` が指定されていない場合メモリはすべてフラッシュされます。  
  
## 解説  
 **フラッシュ**  のディレクティブはOpenMP 句をサポートしていません。  
  
 詳細については、「[2.6.5 flush Directive](../Topic/2.6.5%20flush%20Directive.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
  **スレッド 0: データを読み込みます。**  
**スレッド 1: プロセス データ**  
**データ \= 2**    
## 参照  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)