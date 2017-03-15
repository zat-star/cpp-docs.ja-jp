---
title: "3.3.1 omp_get_wtime Function | Microsoft Docs"
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
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.1 omp_get_wtime Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一部の 「以前の」がタイムアウトため `omp_get_wtime` 関数の戻り値の秒経過したウォール クロック時間を表す倍精度浮動小数点値。  実際の 「までの時間は」任意ですがアプリケーション プログラムの実行中に変更されないことが保証されます。  形式は次のとおりです。  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 次の例に示すように経過時間を測定するために関数が使用されることが予期されます :  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 意図されているかによって帰着時刻 「」スレッド タイムアウトします。アプリケーションで使用するすべてのスレッドでグローバルに一致する必要がないことができます。