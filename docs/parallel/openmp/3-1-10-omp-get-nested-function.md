---
title: "3.1.10 omp_get_nested 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36b213ee45018e7cc0ccf3a1cb99dcbd640d4457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 関数
`omp_get_nested`関数 0 を返します入れ子になった並列処理が有効になっている場合は 0 以外の値が無効な場合です。 入れ子になった並列処理の詳細については、40 ページの 3.1.9 セクションを参照してください。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 実装が入れ子になった並列処理を実装していない場合、この関数は常に 0 を返します。