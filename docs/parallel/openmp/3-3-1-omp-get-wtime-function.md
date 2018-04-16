---
title: "3.3.1 omp_get_wtime 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f89a71d1b91a27dfdd0abf13be4a5f0e30b3fd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime 関数
`omp_get_wtime` 「過去の時間」からの秒数で関数が経過ウォール クロック時間に等しいにある倍精度浮動小数点値を返します。  実際「の時間、過去に」は任意、されるわけでは、アプリケーション プログラムの実行中に変更しないようにします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 次の例で示すように、経過時間を測定する関数が使用されることが予想されます。  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 返される時間は、「スレッドごとの時間」を使用するアプリケーションに参加しているすべてのスレッドでグローバルに一貫している必要がないものでは、します。