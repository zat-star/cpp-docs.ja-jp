---
title: "omp_set_nested | Microsoft Docs"
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
  - "omp_set_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nested OpenMP function"
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子になった並列化を有効にします。  
  
## 構文  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## 解説  
 指定項目  
  
 `val`  
 以外の場合の入れ子になった並列化。  インデックスが無効の入れ子になった並列化。  
  
## 解説  
 OMP の入れ子になった並列化は `omp_set_nested`または [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) の環境変数を設定して行うことができます。  
  
 `omp_set_nested` の設定は `OMP_NESTED` 環境変数の設定をオーバーライドします。  
  
 有効にすると環境変数は並列領域を入れ子にするときにスレッドの数値を指数関数的に増加するため別の方法で操作上のプログラムを中断できます。  再帰が 6 OMP スレッドの数によってがタイムアウトたとえば関数は 4 にスレッド数がプロセッサ数を超えている場合に必要です。4,096 を設定します \(6\) スレッドのべき乗を 4 回は通常アプリケーションのパフォーマンス低下します。  ただし1 種類の例外はI\/O 主体のアプリケーションです。  
  
 `omp_set_nested` の現在の設定を表示するに [omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md) を使用します。  
  
 詳細については、「[3.1.9 omp\_set\_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
  **1**  
**1**   
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)