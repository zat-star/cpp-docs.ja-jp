---
title: "3.1.6 omp_in_parallel 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2e5d05af81eb112894ca27a7599c271138893ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 関数
**Omp_in_parallel**関数は、並列で実行される並列領域の動的な範囲内で呼び出された場合に 0 以外の値を返します。 それ以外の場合は 0 を返します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 この関数は、シリアル化される入れ子になった領域を含む、並列で実行される領域内から呼び出された場合は 0 以外の値を返します。